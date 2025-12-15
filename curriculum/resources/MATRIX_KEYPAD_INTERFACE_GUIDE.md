# Matrix Keypad Interface Guide

## Overview

This document provides guidance on implementing matrix keypad input for Year 4 systems (enhanced SAP-1 or 65C816). Matrix keypads provide numeric and limited text input capability, representing a progression from simple buttons to more sophisticated input devices.

**Purpose**: Enable text/numeric input for Year 4 systems, teaching matrix scanning, debouncing, and I/O port programming.

**Status**: **OPTIONAL** enhancement for Year 4 - valuable educational progression but not required.

**Target Systems**: Enhanced SAP-1 or 65C816 system with I/O port capability

---

## Quick Recommendation

**Best Option**: **4×4 Matrix Keypad** (16 keys: 0-9, A-F or 0-9, +, -, *, /)

- **Cost**: ~$3-5 (keypad module)
- **Wiring**: 8 wires (4 rows + 4 columns)
- **Interface**: Parallel I/O port
- **Educational Value**: High - teaches matrix scanning, debouncing, I/O programming
- **Feasibility**: High - simple hardware, straightforward software

**Alternative**: **4×3 Matrix Keypad** (12 keys: 0-9, *, #) - simpler, fewer keys

---

## Why Matrix Keypad?

### Educational Benefits

- **Progression from Buttons**: Next step after simple button interface
- **Matrix Scanning**: Learn keypad scanning technique
- **Debouncing**: Understand switch bounce and debouncing
- **I/O Programming**: Memory-mapped I/O for input
- **Text Input**: Can enter numbers and limited characters
- **Foundation**: Prepares for PS/2 keyboard in Year 6

### Alignment with Curriculum

- **Year 3**: Simple buttons (direct control)
- **Year 4**: Matrix keypad (optional enhancement)
- **Year 6**: PS/2 keyboard (full keyboard interface)

**Progression**: Buttons → Matrix Keypad → PS/2 Keyboard

---

## Matrix Keypad Fundamentals

### How Matrix Keypads Work

**Physical Structure**:
- Keys arranged in **rows and columns**
- Each key connects one row to one column when pressed
- **No key pressed**: Rows and columns are isolated
- **Key pressed**: Row and column are connected

**4×4 Keypad Layout**:
```
Column 1  Column 2  Column 3  Column 4
    ↓        ↓        ↓        ↓
Row 1 →  [ 1 ]    [ 2 ]    [ 3 ]    [ A ]
Row 2 →  [ 4 ]    [ 5 ]    [ 6 ]    [ B ]
Row 3 →  [ 7 ]    [ 8 ]    [ 9 ]    [ C ]
Row 4 →  [ * ]    [ 0 ]    [ # ]    [ D ]
```

**Electrical Structure**:
```
Row 1 ──┐
Row 2 ──┤
Row 3 ──┤──→ To I/O Port (Output)
Row 4 ──┘

Column 1 ──┐
Column 2 ──┤
Column 3 ──┤──→ To I/O Port (Input, with pull-ups)
Column 4 ──┘
```

### Matrix Scanning Principle

**How Scanning Works**:
1. **Set one row LOW** (others HIGH)
2. **Read columns** (check which column is LOW)
3. **If column is LOW**: Key at that row/column is pressed
4. **Repeat for each row**

**Example**:
- Set Row 1 LOW, others HIGH
- Read columns: Column 2 is LOW
- **Result**: Key at Row 1, Column 2 is pressed (key "2")

**Scanning Sequence**:
```
Step 1: Row 1 = LOW, Row 2-4 = HIGH
        → Check columns → Key "1", "2", "3", or "A" pressed?

Step 2: Row 2 = LOW, Row 1,3-4 = HIGH
        → Check columns → Key "4", "5", "6", or "B" pressed?

Step 3: Row 3 = LOW, Row 1-2,4 = HIGH
        → Check columns → Key "7", "8", "9", or "C" pressed?

Step 4: Row 4 = LOW, Row 1-3 = HIGH
        → Check columns → Key "*", "0", "#", or "D" pressed?
```

---

## Hardware Interface

### Component Requirements

**Required Components**:
- **4×4 Matrix Keypad**: ~$3-5
- **I/O Port**: 8-bit port (4 rows + 4 columns)
- **Pull-up Resistors**: 10kΩ × 4 (for columns)
- **Current-limiting Resistors**: 220Ω × 4 (optional, for rows)

**Optional Components**:
- **Decoupling Capacitors**: 0.1µF near I/O port
- **LED Indicators**: Show keypad activity (optional)

### Circuit Connection

**Row Connections** (Output):
```
I/O Port Bit 0 → Row 1 (via 220Ω resistor, optional)
I/O Port Bit 1 → Row 2 (via 220Ω resistor, optional)
I/O Port Bit 2 → Row 3 (via 220Ω resistor, optional)
I/O Port Bit 3 → Row 4 (via 220Ω resistor, optional)
```

**Column Connections** (Input with Pull-ups):
```
Column 1 → I/O Port Bit 4 (via 10kΩ pull-up to 5V)
Column 2 → I/O Port Bit 5 (via 10kΩ pull-up to 5V)
Column 3 → I/O Port Bit 6 (via 10kΩ pull-up to 5V)
Column 4 → I/O Port Bit 7 (via 10kΩ pull-up to 5V)
```

**Circuit Diagram**:
```
I/O Port          Keypad
─────────────────────────────────
Bit 0 (Out) ──→ Row 1
Bit 1 (Out) ──→ Row 2
Bit 2 (Out) ──→ Row 3
Bit 3 (Out) ──→ Row 4

Bit 4 (In) ←── Column 1 ──┐
Bit 5 (In) ←── Column 2 ──┤ (Pull-up to 5V)
Bit 6 (In) ←── Column 3 ──┤ via 10kΩ
Bit 7 (In) ←── Column 4 ──┘
```

### Memory-Mapped I/O

**Address Mapping** (Example):
```
Address      Function
─────────────────────────────
$9000        I/O Port Data Register
$9001        I/O Port Direction Register
```

**Direction Register**:
- **Bit = 0**: Input (columns)
- **Bit = 1**: Output (rows)

**Example Configuration**:
```
Direction Register = $0F  (0000 1111)
                     └─┬─┘ └─┬─┘
                       │     └─ Output (rows 0-3)
                       └─────── Input (columns 4-7)
```

---

## Software Implementation

### Matrix Scanning Algorithm

**Basic Scanning Routine**:
```assembly
; Scan keypad and return key code
; Output: A = key code (0-15) or $FF if no key
KEYPAD_PORT = $9000
KEYPAD_DIR = $9001

scan_keypad:
    ; Configure port: rows = output, columns = input
    LDA #$0F          ; 0000 1111 (rows out, columns in)
    STA KEYPAD_DIR
    
    ; Scan Row 1
    LDA #$FE          ; 1111 1110 (Row 1 LOW)
    STA KEYPAD_PORT
    JSR delay_10us    ; Settle time
    LDA KEYPAD_PORT
    AND #$F0          ; Mask columns
    CMP #$F0          ; All columns HIGH?
    BNE key_found     ; No, key pressed
    
    ; Scan Row 2
    LDA #$FD          ; 1111 1101 (Row 2 LOW)
    STA KEYPAD_PORT
    JSR delay_10us
    LDA KEYPAD_PORT
    AND #$F0
    CMP #$F0
    BNE key_found
    
    ; Scan Row 3
    LDA #$FB          ; 1111 1011 (Row 3 LOW)
    STA KEYPAD_PORT
    JSR delay_10us
    LDA KEYPAD_PORT
    AND #$F0
    CMP #$F0
    BNE key_found
    
    ; Scan Row 4
    LDA #$F7          ; 1111 0111 (Row 4 LOW)
    STA KEYPAD_PORT
    JSR delay_10us
    LDA KEYPAD_PORT
    AND #$F0
    CMP #$F0
    BNE key_found
    
    ; No key pressed
    LDA #$FF
    RTS

key_found:
    ; Determine which column
    LSR A
    LSR A
    LSR A
    LSR A            ; Shift column bits to low nibble
    AND #$0F         ; Mask column (0-3)
    TAX              ; Save column
    
    ; Determine which row
    LDA KEYPAD_PORT
    AND #$0F         ; Mask row bits
    ; Find which bit is LOW
    LDY #0
find_row:
    LSR A
    BCS next_row
    ; Found row
    TYA              ; Row number (0-3)
    ASL A
    ASL A            ; Multiply by 4 (4 columns per row)
    CLC
    ADC X            ; Add column
    RTS              ; Return key code (0-15)
next_row:
    INY
    CPY #4
    BNE find_row
    LDA #$FF         ; Error
    RTS
```

### Debouncing

**Why Debouncing?**
- Mechanical switches "bounce" when pressed
- Multiple rapid on/off transitions
- Software must filter out bounces

**Debouncing Algorithm**:
```assembly
; Wait for stable key press
; Input: A = initial key code
; Output: A = debounced key code
debounce_key:
    PHA              ; Save initial key
    JSR delay_10ms   ; Wait for bounce to settle
    JSR scan_keypad  ; Scan again
    CMP #$FF
    BEQ no_key       ; No key now
    PLA              ; Discard old value
    RTS              ; Return new key
no_key:
    PLA              ; Restore initial
    RTS
```

**Improved Debouncing**:
```assembly
; Debounce with multiple samples
debounce_key_advanced:
    LDX #0           ; Sample counter
    LDY #0           ; Stable count
debounce_loop:
    JSR scan_keypad
    CMP #$FF
    BEQ reset_count
    ; Key pressed
    INY              ; Increment stable count
    CPY #3           ; 3 stable samples?
    BEQ key_stable
    JMP debounce_continue
reset_count:
    LDY #0           ; Reset count
debounce_continue:
    JSR delay_5ms
    INX
    CPX #20          ; Max 20 samples (100ms)
    BNE debounce_loop
    LDA #$FF         ; Timeout
    RTS
key_stable:
    RTS              ; Return key in A
```

### Key Code to Character Conversion

**Key Code Mapping** (4×4 keypad):
```
Key Code  Character  ASCII
─────────────────────────────
0        '1'        0x31
1        '2'        0x32
2        '3'        0x33
3        'A'        0x41
4        '4'        0x34
5        '5'        0x35
6        '6'        0x36
7        'B'        0x42
8        '7'        0x37
9        '8'        0x38
10       '9'        0x39
11       'C'        0x43
12       '*'        0x2A
13       '0'        0x30
14       '#'        0x23
15       'D'        0x44
```

**Conversion Table**:
```assembly
key_to_ascii:
    TAX              ; Use as index
    LDA ascii_table,X
    RTS

ascii_table:
    .byte $31, $32, $33, $41  ; '1', '2', '3', 'A'
    .byte $34, $35, $36, $42  ; '4', '5', '6', 'B'
    .byte $37, $38, $39, $43  ; '7', '8', '9', 'C'
    .byte $2A, $30, $23, $44  ; '*', '0', '#', 'D'
```

### Complete Keypad Input Routine

**Wait for Key Press**:
```assembly
; Wait for key press and return ASCII
; Output: A = ASCII character
get_key:
    JSR scan_keypad
    CMP #$FF
    BEQ get_key      ; No key, keep scanning
    JSR debounce_key ; Debounce
    CMP #$FF
    BEQ get_key      ; Debounce failed
    JSR key_to_ascii ; Convert to ASCII
    RTS
```

**Wait for Key Release**:
```assembly
; Wait for key to be released
wait_key_release:
    JSR scan_keypad
    CMP #$FF
    BNE wait_key_release ; Key still pressed
    RTS
```

**Get Key with Release Detection**:
```assembly
; Get key press and wait for release
get_key_complete:
    JSR get_key      ; Wait for key press
    PHA              ; Save key
    JSR wait_key_release ; Wait for release
    PLA              ; Restore key
    RTS
```

---

## Integration Examples

### Example 1: Numeric Input

**Enter a Number**:
```assembly
; Enter 2-digit number from keypad
; Output: A = number (0-99)
enter_number:
    LDX #0           ; Accumulator
    LDY #2           ; Digit counter
    
digit_loop:
    JSR get_key_complete
    ; Check if digit (0-9)
    CMP #$30         ; '0'
    BCC digit_loop   ; Too low
    CMP #$3A         ; '9'+1
    BCS digit_loop   ; Too high
    
    ; Valid digit
    SEC
    SBC #$30         ; Convert to binary
    PHA              ; Save digit
    
    ; Multiply accumulator by 10
    TXA
    ASL A            ; ×2
    STA temp
    ASL A            ; ×4
    ASL A            ; ×8
    CLC
    ADC temp         ; ×8 + ×2 = ×10
    TAX              ; New accumulator
    
    PLA              ; Restore digit
    CLC
    ADC X            ; Add digit
    TAX              ; Update accumulator
    
    DEY
    BNE digit_loop   ; Get next digit
    
    TXA              ; Return number
    RTS
```

### Example 2: Menu Selection

**Menu with Keypad**:
```assembly
; Display menu and get selection
menu_selection:
    ; Display menu on LCD
    JSR display_menu
    
    ; Wait for key press
menu_wait:
    JSR get_key_complete
    
    ; Check if valid selection (1-9, A-D)
    CMP #$31         ; '1'
    BCC menu_wait    ; Too low
    CMP #$3A         ; '9'+1
    BCC menu_valid   ; Valid number
    
    CMP #$41         ; 'A'
    BCC menu_wait    ; Between 9 and A
    CMP #$45         ; 'D'+1
    BCS menu_wait    ; Too high
    
menu_valid:
    RTS              ; Return selection in A
```

### Example 3: Calculator Input

**Simple Calculator**:
```assembly
; Get calculator input
calculator_input:
    JSR get_key_complete
    
    ; Check type
    CMP #$30         ; '0'
    BCC check_operator
    CMP #$3A         ; '9'+1
    BCC is_digit
    
check_operator:
    CMP #$2A         ; '*'
    BEQ is_operator
    CMP #$2B         ; '+'
    BEQ is_operator
    CMP #$2D         ; '-'
    BEQ is_operator
    CMP #$2F         ; '/'
    BEQ is_operator
    CMP #$23         ; '#'
    BEQ is_equals
    
    ; Invalid
    LDA #$FF
    RTS

is_digit:
    SEC
    SBC #$30         ; Convert to binary
    RTS

is_operator:
    RTS              ; Return operator code

is_equals:
    LDA #$3D         ; '='
    RTS
```

---

## Pascal Interface (Year 5-6)

### Type Definitions

```pascal
type
  KeyCode = 0..15;
  KeypadChar = char;

const
  KEYPAD_PORT = $9000;
  KEYPAD_DIR = $9001;
  
  { Key codes }
  KEY_1 = 0; KEY_2 = 1; KEY_3 = 2; KEY_A = 3;
  KEY_4 = 4; KEY_5 = 5; KEY_6 = 6; KEY_B = 7;
  KEY_7 = 8; KEY_8 = 9; KEY_9 = 10; KEY_C = 11;
  KEY_STAR = 12; KEY_0 = 13; KEY_HASH = 14; KEY_D = 15;
```

### Basic Procedures

**Scan Keypad**:
```pascal
function ScanKeypad: KeyCode;
var
  row, col: byte;
  portValue: byte;
begin
  { Configure port }
  mem[KEYPAD_DIR] := $0F;  { Rows out, columns in }
  
  { Scan each row }
  for row := 0 to 3 do
  begin
    { Set row LOW }
    mem[KEYPAD_PORT] := $FF and not (1 shl row);
    DelayMicroseconds(10);
    
    { Read columns }
    portValue := mem[KEYPAD_PORT] and $F0;
    if portValue <> $F0 then
    begin
      { Key pressed - find column }
      col := 0;
      while (portValue and $80) <> 0 do
      begin
        portValue := portValue shl 1;
        inc(col);
      end;
      ScanKeypad := row * 4 + col;
      exit;
    end;
  end;
  
  ScanKeypad := $FF;  { No key }
end;
```

**Get Key**:
```pascal
function GetKey: KeypadChar;
const
  KeyTable: array[0..15] of char = 
    ('1', '2', '3', 'A',
     '4', '5', '6', 'B',
     '7', '8', '9', 'C',
     '*', '0', '#', 'D');
var
  keyCode: KeyCode;
begin
  repeat
    keyCode := ScanKeypad;
  until keyCode <> $FF;
  
  { Debounce }
  DelayMilliseconds(10);
  keyCode := ScanKeypad;
  if keyCode = $FF then
    GetKey := #0
  else
    GetKey := KeyTable[keyCode];
end;
```

---

## Troubleshooting

### Common Issues

**No Keys Detected**:
- Check I/O port connections
- Verify pull-up resistors on columns
- Check direction register configuration
- Test with multimeter

**Multiple Keys Detected**:
- Check for short circuits
- Verify row/column connections
- Check for damaged keypad

**Intermittent Detection**:
- Add debouncing delay
- Check for loose connections
- Verify power supply stability

**Wrong Keys Detected**:
- Check keypad wiring (row/column order)
- Verify key code mapping table
- Test with known keypad layout

---

## Educational Exercises

### Exercise 1: Matrix Scanning

**Task**: Trace through scanning algorithm for key "5" pressed:
- Which row is set LOW?
- Which column reads LOW?
- What is the key code?

**Answer**: Row 1 (bit 1), Column 1 (bit 5), Key code = 5

### Exercise 2: Debouncing

**Task**: Why is debouncing necessary?
- What happens without debouncing?
- How long should debounce delay be?

**Answer**: Switches bounce 1-10ms, need 10-20ms delay

### Exercise 3: Key Mapping

**Task**: Design key mapping for calculator:
- Numbers 0-9
- Operators +, -, *, /
- Equals =
- Clear C

**Answer**: Use 4×4 keypad with custom mapping

---

## Summary

**Key Concepts**:
1. **Matrix Structure**: Rows and columns reduce wiring
2. **Scanning**: Sequentially activate rows, read columns
3. **Debouncing**: Filter switch bounce
4. **I/O Programming**: Memory-mapped I/O for input

**Educational Value**:
- Progression from buttons to keypad
- Matrix scanning technique
- Debouncing concepts
- I/O port programming
- Foundation for PS/2 keyboard

**When to Use**:
- **Year 4**: Optional enhancement (this guide)
- **Year 5-6**: Can continue using if implemented

**Next Step**: Year 6 PS/2 keyboard (full keyboard interface)

---

**Document Created**: 2025-12-16  
**Purpose**: Matrix keypad interface guide for Year 4  
**Status**: Complete

