# LCD Technology and Interfacing: Educational Guide

## Overview

This document provides comprehensive educational material on how LCD character displays work, from the physical technology to the software interface. Students will understand LCD operation from first principles, including liquid crystal physics, controller operation, signaling protocols, ASCII encoding, and programming interfaces.

**Purpose**: Deep understanding of LCD technology and interfacing, from physics to software.

**Target Audience**: Years 2-4 (LCD integration), Years 5-6 (advanced programming)

---

## Table of Contents

1. [How LCD Displays Work](#how-lcd-displays-work)
2. [HD44780 Controller Internals](#hd44780-controller-internals)
3. [Signaling and Timing](#signaling-and-timing)
4. [ASCII Character Encoding](#ascii-character-encoding)
5. [Assembly Language Interface](#assembly-language-interface)
6. [Pascal Language Interface](#pascal-language-interface)
7. [Practical Examples](#practical-examples)

---

## How LCD Displays Work

### Liquid Crystal Physics

**What is a Liquid Crystal?**
- A state of matter between liquid and solid
- Molecules can flow like a liquid but maintain orientation like a solid
- Can be aligned by electric fields
- Changes optical properties when aligned

**LCD Operation Principle**:
1. **Polarized Light**: LCD uses polarized light filters
2. **Crystal Alignment**: Electric field rotates liquid crystal molecules
3. **Light Blocking**: Rotated crystals block or pass light
4. **Pixel Control**: Each character segment is a pixel controlled by voltage

**Character LCD Structure**:
```
┌─────────────────────────┐
│  Polarizer (Top)        │
│  ┌───────────────────┐  │
│  │  Liquid Crystal   │  │  ← Molecules rotate with voltage
│  │  Layer            │  │
│  └───────────────────┘  │
│  ┌───────────────────┐  │
│  │  Electrodes       │  │  ← Control voltage per segment
│  └───────────────────┘  │
│  ┌───────────────────┐  │
│  │  Backlight        │  │  ← Provides illumination
│  └───────────────────┘  │
│  Polarizer (Bottom)      │
└─────────────────────────┘
```

**Educational Insight**: Students see that each character segment is physically controlled by voltage, connecting software commands to physical light output.

### Character Generation

**How Characters Are Formed**:
- Each character position has a **5×8 pixel grid** (or 5×10 for some displays)
- Controller stores character patterns in **Character Generator ROM (CGROM)**
- ASCII code selects which pattern to display
- Pattern is rendered pixel-by-pixel in the character position

**Character Grid Example** (5×8 for 'A'):
```
Pixel Grid:
  ███
 █   █
 █   █
 █████
 █   █
 █   █
 █   █
```

**Memory Organization**:
- **Display Data RAM (DDRAM)**: Stores character codes for each position
- **Character Generator ROM (CGROM)**: Stores pixel patterns for ASCII characters
- **Character Generator RAM (CGRAM)**: Stores custom character patterns

**Educational Insight**: Students understand that characters are stored as codes (ASCII), which reference pixel patterns stored in ROM.

---

## HD44780 Controller Internals

### Controller Architecture

**HD44780 Block Diagram**:
```
┌─────────────────────────────────────┐
│         HD44780 Controller          │
│  ┌──────────┐  ┌─────────────────┐  │
│  │ Instruction│  │  Display       │  │
│  │  Decoder   │  │  Controller    │  │
│  └──────────┘  └─────────────────┘  │
│  ┌──────────┐  ┌─────────────────┐  │
│  │ DDRAM    │  │  CGROM          │  │
│  │ (80 bytes)│  │  (ASCII chars)  │  │
│  └──────────┘  └─────────────────┘  │
│  ┌──────────┐                       │
│  │ CGRAM    │                       │
│  │ (8 chars)│                       │
│  └──────────┘                       │
│  ┌─────────────────────────────────┐│
│  │  Timing & Control Logic          ││
│  └─────────────────────────────────┘│
└─────────────────────────────────────┘
```

### Memory Organization

**1. Display Data RAM (DDRAM)**
- **Size**: 80 bytes (stores character codes)
- **Purpose**: Holds ASCII codes for each display position
- **Addressing**: 
  - Line 1: Addresses 0x00-0x13 (20 characters)
  - Line 2: Addresses 0x40-0x53 (20 characters)
  - Line 3: Addresses 0x14-0x27 (20 characters)
  - Line 4: Addresses 0x54-0x67 (20 characters)

**2. Character Generator ROM (CGROM)**
- **Size**: 192 character patterns (ASCII 0x20-0x7F)
- **Purpose**: Stores pixel patterns for standard ASCII characters
- **Format**: 5×8 pixels = 8 bytes per character
- **Access**: Automatic when ASCII code written to DDRAM

**3. Character Generator RAM (CGRAM)**
- **Size**: 8 custom characters (64 bytes total)
- **Purpose**: User-defined character patterns
- **Addresses**: 0x00-0x07 (8 characters)
- **Use**: Create custom symbols, graphics, or non-ASCII characters

### Register Structure

**Instruction Register (IR)**:
- Stores command byte from CPU
- Decoded by instruction decoder
- Controls controller operation

**Data Register (DR)**:
- Temporary storage for data
- Used for DDRAM/CGRAM read/write operations

**Address Counter (AC)**:
- Points to current DDRAM or CGRAM address
- Auto-increments after write (if configured)
- Used for cursor positioning

**Status Register (BF)**:
- **Busy Flag (BF)**: Indicates controller is processing
- **Address Counter**: Current address value
- Read-only, checked before operations

---

## Signaling and Timing

### Parallel Interface Signals

**Data Bus (D0-D7)**:
- **8-bit parallel data bus**
- Carries commands or character data
- Bidirectional (read/write operations)
- Connected to CPU data bus via tri-state buffers

**Control Signals**:

**RS (Register Select)**:
- **RS = 0**: Instruction register (commands)
- **RS = 1**: Data register (character data)
- Determines what D0-D7 contains

**R/W (Read/Write)**:
- **R/W = 0**: Write operation (CPU → LCD)
- **R/W = 1**: Read operation (LCD → CPU)
- Often tied to ground (write-only mode)

**E (Enable)**:
- **Clock signal** for data transfer
- **High-to-low transition** latches data
- Must meet timing requirements

**Timing Diagram**:
```
RS:  ────┐     ────┐
         └─────┘     ────┘
         Command    Data

R/W: ──────────────── (tied low for write-only)

E:   ────┐     ────┐
         └─────┘     ────┘
         Pulse      Pulse

D0-D7: ────[Data]────[Data]────
         Setup    Hold
```

### Timing Requirements

**Enable Pulse Width**:
- **Minimum**: 450ns (high pulse)
- **Minimum**: 450ns (low pulse)
- **Total cycle**: ~1µs minimum

**Data Setup Time**:
- **Before E high**: 60ns minimum
- Data must be stable before enable pulse

**Data Hold Time**:
- **After E low**: 10ns minimum
- Data must remain stable after enable pulse

**Busy Flag Check**:
- **Before write**: Check BF (if reading status)
- **Alternative**: Wait fixed delay (simpler)
- **Typical delay**: 40µs for most operations

**Initialization Timing**:
- **Power-on delay**: 50ms minimum
- **Function set delay**: 4.1ms after power-on
- **Clear display delay**: 1.64ms
- **Other commands**: 40µs typical

### Signal Levels

**Voltage Levels**:
- **Logic High**: 2.2V minimum (5V system)
- **Logic Low**: 0.8V maximum
- **Power Supply**: 5V ±0.25V

**Current Requirements**:
- **Controller**: ~1mA typical
- **Backlight**: 20-200mA (varies by LCD)
- **Total**: ~50-250mA depending on backlight

---

## ASCII Character Encoding

### ASCII Fundamentals

**What is ASCII?**
- **American Standard Code for Information Interchange**
- **7-bit encoding**: 128 possible characters (0x00-0x7F)
- **Standard**: Maps numbers to characters
- **Universal**: Same code = same character everywhere

**ASCII Table Structure**:
```
Range        Type              Examples
─────────────────────────────────────────────
0x00-0x1F    Control Codes     NULL, LF, CR, ESC
0x20-0x7E    Printable ASCII    Space, A-Z, a-z, 0-9, symbols
0x7F         Control           DEL
```

### ASCII Character Categories

**1. Control Characters (0x00-0x1F)**:
- Non-printable control codes
- Examples: NULL (0x00), LF (0x0A), CR (0x0D)
- Used for communication, not display

**2. Printable Characters (0x20-0x7E)**:
- **Space**: 0x20
- **Numbers**: 0x30-0x39 ('0'-'9')
- **Uppercase**: 0x41-0x5A ('A'-'Z')
- **Lowercase**: 0x61-0x7A ('a'-'z')
- **Symbols**: Various (punctuation, operators)

**3. Extended ASCII (0x80-0xFF)**:
- Not standard ASCII (8-bit)
- Varies by system
- HD44780 supports some extended characters

### ASCII to LCD Mapping

**HD44780 ASCII Support**:
- **Standard ASCII**: 0x20-0x7F (96 characters)
- **Japanese characters**: Some models support katakana
- **Custom characters**: Use CGRAM for non-ASCII

**Character Code Examples**:
```
ASCII Code  Character  Binary      Hex
───────────────────────────────────────
0x20        Space      00100000    20
0x30        '0'        00110000    30
0x41        'A'        01000001    41
0x61        'a'        01100001    61
0x2B        '+'        00101011    2B
```

**Educational Insight**: Students see that characters are just numbers, and the LCD controller converts numbers to pixel patterns.

### Number to ASCII Conversion

**Decimal to ASCII**:
- **Digits 0-9**: Add 0x30 to digit value
- **Example**: 5 → 0x30 + 5 = 0x35 ('5')

**Hexadecimal to ASCII**:
- **Digits 0-9**: Add 0x30
- **Digits A-F**: Add 0x37 (or 0x41 for lowercase)
- **Example**: 0x0A → 'A' (0x41) or 'a' (0x61)

**Binary to ASCII**:
- Convert to decimal first
- Then convert decimal to ASCII
- Or convert to hex, then hex to ASCII

---

## Assembly Language Interface

### Memory-Mapped I/O

**Address Mapping** (Example for SAP-1):
```
Address      Register        RS    Function
─────────────────────────────────────────────
$0E          LCD Data        1     Write character
$0F          LCD Command     0     Send command
```

**Register Selection**:
- **Address decoder** sets RS based on address
- **RS = 0**: Command register (address $0F)
- **RS = 1**: Data register (address $0E)

### Basic Operations

**1. Write Command**:
```assembly
; Write command to LCD
; Input: A register contains command byte
LCD_CMD = $0F

write_lcd_cmd:
    STA LCD_CMD        ; Write command byte
    JSR delay_40us     ; Wait for command to complete
    RTS
```

**2. Write Character**:
```assembly
; Write character to LCD
; Input: A register contains ASCII character
LCD_DATA = $0E

write_lcd_char:
    STA LCD_DATA       ; Write character byte
    JSR delay_40us     ; Wait for character to display
    RTS
```

**3. Initialize LCD**:
```assembly
; Initialize LCD display
init_lcd:
    ; Wait for power-on
    JSR delay_50ms
    
    ; Function set: 8-bit, 2-line, 5×8 font
    LDA #$38
    STA LCD_CMD
    JSR delay_5ms
    
    ; Display control: display on, cursor off
    LDA #$0C
    STA LCD_CMD
    JSR delay_40us
    
    ; Clear display
    LDA #$01
    STA LCD_CMD
    JSR delay_2ms
    
    ; Entry mode: increment cursor, no shift
    LDA #$06
    STA LCD_CMD
    JSR delay_40us
    
    RTS
```

### Display Text

**Display String**:
```assembly
; Display null-terminated string
; Input: X register points to string
display_string:
    LDA string_data,X
    BEQ string_done        ; Null terminator?
    JSR write_lcd_char
    INX
    JMP display_string
string_done:
    RTS

string_data:
    .byte "HELLO", 0
```

**Display Number (Decimal)**:
```assembly
; Display 8-bit number as decimal
; Input: A register contains number (0-255)
display_decimal:
    LDX #0                 ; Digit counter
    LDY #100               ; Divisor
    
div_loop:
    CMP #100
    BCC less_than_100
    SBC #100
    INX
    JMP div_loop
    
less_than_100:
    PHA                    ; Save remainder
    TXA
    CLC
    ADC #$30               ; Convert to ASCII
    JSR write_lcd_char     ; Display hundreds
    
    PLA                    ; Restore remainder
    LDX #0
    LDY #10
    
div_tens:
    CMP #10
    BCC less_than_10
    SBC #10
    INX
    JMP div_tens
    
less_than_10:
    PHA                    ; Save remainder
    TXA
    CLC
    ADC #$30               ; Convert to ASCII
    JSR write_lcd_char     ; Display tens
    
    PLA                    ; Restore remainder (ones)
    CLC
    ADC #$30               ; Convert to ASCII
    JSR write_lcd_char     ; Display ones
    
    RTS
```

**Display Number (Hexadecimal)**:
```assembly
; Display 8-bit number as hexadecimal
; Input: A register contains number
display_hex:
    PHA                    ; Save original
    LSR A                  ; Get high nibble
    LSR A
    LSR A
    LSR A
    JSR hex_digit          ; Display high digit
    PLA                    ; Restore original
    AND #$0F               ; Get low nibble
    JSR hex_digit          ; Display low digit
    RTS

hex_digit:
    CMP #$0A
    BCC digit_0_9
    ; A-F
    CLC
    ADC #$37               ; 'A' = 0x41, so 0x0A + 0x37 = 0x41
    JMP write_digit
digit_0_9:
    CLC
    ADC #$30               ; '0' = 0x30
write_digit:
    JSR write_lcd_char
    RTS
```

### Cursor Control

**Set Cursor Position**:
```assembly
; Set cursor position
; Input: A = row (0-3), X = column (0-19)
set_cursor:
    PHA                    ; Save row
    ; Calculate DDRAM address
    ; Row 0: 0x00, Row 1: 0x40, Row 2: 0x14, Row 3: 0x54
    LDA row_addresses,Y
    CLC
    ADC X                  ; Add column
    ORA #$80               ; Set DDRAM address command
    STA LCD_CMD
    JSR delay_40us
    RTS

row_addresses:
    .byte $00, $40, $14, $54
```

**Clear Display**:
```assembly
clear_display:
    LDA #$01               ; Clear display command
    STA LCD_CMD
    JSR delay_2ms          ; Clear takes longer
    RTS
```

### Delay Routines

**Microsecond Delays**:
```assembly
; Delay 40 microseconds (approximate)
delay_40us:
    NOP                    ; 2 cycles
    NOP                    ; 2 cycles
    NOP                    ; 2 cycles
    NOP                    ; 2 cycles
    RTS                    ; 6 cycles
    ; Total: ~14 cycles at 1MHz = 14µs
    ; Adjust for actual CPU speed
```

**Millisecond Delays**:
```assembly
; Delay 2 milliseconds
delay_2ms:
    LDX #200               ; Loop counter
delay_loop:
    DEX
    BNE delay_loop
    RTS
```

---

## Pascal Language Interface

### Pascal Type Definitions

**LCD Interface Types**:
```pascal
type
  LCDCommand = byte;
  LCDChar = char;
  LCDRow = 0..3;
  LCDColumn = 0..19;
  
const
  LCD_CMD_ADDR = $0F;
  LCD_DATA_ADDR = $0E;
  
  { LCD Commands }
  LCD_CMD_CLEAR = $01;
  LCD_CMD_HOME = $02;
  LCD_CMD_DISPLAY_ON = $0C;
  LCD_CMD_DISPLAY_OFF = $08;
  LCD_CMD_CURSOR_ON = $0E;
  LCD_CMD_CURSOR_OFF = $0C;
```

### Basic Pascal Procedures

**Write Command**:
```pascal
procedure LCDWriteCommand(cmd: LCDCommand);
begin
  { Write command to LCD command register }
  mem[LCD_CMD_ADDR] := cmd;
  DelayMicroseconds(40);
end;
```

**Write Character**:
```pascal
procedure LCDWriteChar(ch: LCDChar);
begin
  { Write character to LCD data register }
  mem[LCD_DATA_ADDR] := ord(ch);
  DelayMicroseconds(40);
end;
```

**Initialize LCD**:
```pascal
procedure LCDInit;
begin
  { Wait for power-on }
  DelayMilliseconds(50);
  
  { Function set: 8-bit, 2-line, 5×8 font }
  LCDWriteCommand($38);
  DelayMilliseconds(5);
  
  { Display control: display on, cursor off }
  LCDWriteCommand($0C);
  
  { Clear display }
  LCDWriteCommand($01);
  DelayMilliseconds(2);
  
  { Entry mode: increment cursor, no shift }
  LCDWriteCommand($06);
end;
```

### Display Operations

**Display String**:
```pascal
procedure LCDWriteString(s: string);
var
  i: integer;
begin
  for i := 1 to length(s) do
    LCDWriteChar(s[i]);
end;
```

**Display Number (Decimal)**:
```pascal
procedure LCDWriteDecimal(n: integer);
var
  hundreds, tens, ones: integer;
begin
  { Extract hundreds }
  hundreds := n div 100;
  n := n mod 100;
  
  { Display hundreds (or space if zero) }
  if hundreds > 0 then
    LCDWriteChar(chr(ord('0') + hundreds))
  else
    LCDWriteChar(' ');
  
  { Extract tens }
  tens := n div 10;
  n := n mod 10;
  
  { Display tens }
  LCDWriteChar(chr(ord('0') + tens));
  
  { Display ones }
  ones := n;
  LCDWriteChar(chr(ord('0') + ones));
end;
```

**Display Number (Hexadecimal)**:
```pascal
procedure LCDWriteHex(n: byte);
var
  highNibble, lowNibble: byte;
begin
  { Extract high nibble }
  highNibble := n shr 4;
  
  { Display high digit }
  if highNibble < 10 then
    LCDWriteChar(chr(ord('0') + highNibble))
  else
    LCDWriteChar(chr(ord('A') + highNibble - 10));
  
  { Extract low nibble }
  lowNibble := n and $0F;
  
  { Display low digit }
  if lowNibble < 10 then
    LCDWriteChar(chr(ord('0') + lowNibble))
  else
    LCDWriteChar(chr(ord('A') + lowNibble - 10));
end;
```

### Cursor Control

**Set Cursor Position**:
```pascal
procedure LCDSetCursor(row: LCDRow; col: LCDColumn);
const
  RowAddresses: array[0..3] of byte = ($00, $40, $14, $54);
var
  address: byte;
begin
  { Calculate DDRAM address }
  address := RowAddresses[row] + col;
  
  { Set DDRAM address command }
  LCDWriteCommand($80 or address);
end;
```

**Clear Display**:
```pascal
procedure LCDClear;
begin
  LCDWriteCommand(LCD_CMD_CLEAR);
  DelayMilliseconds(2);
end;
```

### Complete Pascal Example

**LCD Display Program**:
```pascal
program LCDDemo;

{ LCD Interface }
const
  LCD_CMD_ADDR = $0F;
  LCD_DATA_ADDR = $0E;

procedure LCDWriteCommand(cmd: byte);
begin
  mem[LCD_CMD_ADDR] := cmd;
  DelayMicroseconds(40);
end;

procedure LCDWriteChar(ch: char);
begin
  mem[LCD_DATA_ADDR] := ord(ch);
  DelayMicroseconds(40);
end;

procedure LCDInit;
begin
  DelayMilliseconds(50);
  LCDWriteCommand($38);
  DelayMilliseconds(5);
  LCDWriteCommand($0C);
  LCDWriteCommand($01);
  DelayMilliseconds(2);
  LCDWriteCommand($06);
end;

procedure LCDWriteString(s: string);
var
  i: integer;
begin
  for i := 1 to length(s) do
    LCDWriteChar(s[i]);
end;

procedure LCDWriteDecimal(n: integer);
var
  hundreds, tens, ones: integer;
begin
  hundreds := n div 100;
  n := n mod 100;
  if hundreds > 0 then
    LCDWriteChar(chr(ord('0') + hundreds))
  else
    LCDWriteChar(' ');
  tens := n div 10;
  ones := n mod 10;
  LCDWriteChar(chr(ord('0') + tens));
  LCDWriteChar(chr(ord('0') + ones));
end;

{ Main Program }
var
  counter: integer;
begin
  { Initialize LCD }
  LCDInit;
  
  { Display welcome message }
  LCDWriteString('Hello World!');
  
  { Wait }
  DelayMilliseconds(1000);
  
  { Clear and display counter }
  for counter := 0 to 99 do
  begin
    LCDClear;
    LCDWriteString('Count: ');
    LCDWriteDecimal(counter);
    DelayMilliseconds(500);
  end;
end.
```

---

## Practical Examples

### Example 1: System Status Display

**Display CPU registers and memory**:
```assembly
; Display accumulator value
display_accumulator:
    PHA                    ; Save A
    LDA #'A'
    JSR write_lcd_char
    LDA #'='
    JSR write_lcd_char
    PLA                    ; Restore A
    JSR display_hex
    RTS
```

### Example 2: Menu System

**Simple menu navigation**:
```pascal
procedure DisplayMenu;
begin
  LCDClear;
  LCDSetCursor(0, 0);
  LCDWriteString('1. Run Program');
  LCDSetCursor(1, 0);
  LCDWriteString('2. View Memory');
  LCDSetCursor(2, 0);
  LCDWriteString('3. Settings');
end;
```

### Example 3: Debug Output

**Display debug information**:
```assembly
; Display debug message with value
; Input: X = string pointer, A = value
display_debug:
    JSR display_string     ; Display label
    LDA #':'
    JSR write_lcd_char
    LDA #' '
    JSR write_lcd_char
    PLA                    ; Get value
    JSR display_hex        ; Display value
    RTS
```

---

## Educational Exercises

### Exercise 1: Understanding ASCII

**Task**: Convert the following to ASCII codes:
- 'H' → ?
- '5' → ?
- 'A' + 32 → ? (hint: lowercase conversion)

**Answer**:
- 'H' = 0x48 (72 decimal)
- '5' = 0x35 (53 decimal)
- 'A' + 32 = 'a' = 0x61 (97 decimal)

### Exercise 2: Timing Analysis

**Task**: Calculate total time for LCD initialization sequence:
- Power-on delay: 50ms
- Function set: 5ms
- Display control: 40µs
- Clear display: 2ms
- Entry mode: 40µs

**Answer**: ~57ms total

### Exercise 3: Memory Mapping

**Task**: Design address decoder for LCD:
- LCD command at $0F
- LCD data at $0E
- Use 74HC138 decoder

**Solution**: 
- Address bits A0-A3 select register
- A4-A7 used for chip select
- RS = A0 (0 = command, 1 = data)

---

## Summary

**Key Concepts**:
1. **LCD Physics**: Liquid crystals rotate with voltage, controlling light
2. **Controller**: HD44780 manages character generation and display
3. **Signaling**: Parallel interface with timing requirements
4. **ASCII**: Character encoding maps numbers to characters
5. **Programming**: Assembly and Pascal interfaces for LCD control

**Educational Value**:
- Students understand display technology from physics to software
- See how software commands become physical light output
- Learn memory-mapped I/O and timing requirements
- Practice number-to-ASCII conversion
- Understand character encoding fundamentals

**Progression**:
- **Year 2-3**: Basic LCD integration and display
- **Year 4**: Advanced LCD programming before VGA
- **Year 5-6**: Pascal interface and system integration

---

**Document Created**: 2025-12-16  
**Purpose**: Comprehensive LCD technology education  
**Status**: Complete

