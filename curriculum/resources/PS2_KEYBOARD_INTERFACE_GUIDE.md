# PS/2 Keyboard Interface Guide

## Overview

This document provides comprehensive guidance on implementing PS/2 keyboard interface for Year 6 systems (65C816). PS/2 keyboards provide full text input capability, representing the final step in the input device progression from buttons to full keyboard.

**Purpose**: Enable full keyboard input for Year 6 systems, teaching PS/2 protocol, interrupt handling, scan code translation, and device driver development.

**Status**: **REQUIRED** for Year 6 - Essential for complete system functionality.

**Target System**: 65C816 system with interrupt capability

---

## Quick Recommendation

**Best Option**: **Standard PS/2 Keyboard** (AT or PS/2 connector)

- **Cost**: ~$5-15 (or reuse existing keyboard)
- **Interface**: PS/2 connector (6-pin mini-DIN)
- **Protocol**: PS/2 serial protocol (clock + data)
- **Educational Value**: High - teaches serial protocol, interrupts, device drivers
- **Feasibility**: High - standard interface, well-documented

**Hardware Requirements**:
- PS/2 keyboard (AT or PS/2 connector)
- PS/2 interface circuit (clock + data lines)
- Interrupt controller (for keyboard interrupts)
- Pull-up resistors (10kΩ for clock and data)

---

## Why PS/2 Keyboard?

### Educational Benefits

- **Serial Protocol**: Learn PS/2 serial communication protocol
- **Interrupt-Driven I/O**: Understand interrupt-driven input
- **Scan Codes**: Learn keyboard scan code system
- **Device Driver Development**: Practice device driver implementation
- **Full Keyboard**: Complete text input capability
- **Industry Standard**: Real-world interface used in many systems

### Alignment with Curriculum

- **Year 3**: Simple buttons (direct control)
- **Year 4**: Matrix keypad (optional, matrix scanning)
- **Year 6**: PS/2 keyboard (full keyboard interface)

**Progression**: Buttons → Matrix Keypad → PS/2 Keyboard

---

## PS/2 Protocol Fundamentals

### Physical Interface

**PS/2 Connector** (6-pin mini-DIN):
```
Pin 1: Data
Pin 2: Not connected
Pin 3: Ground
Pin 4: +5V
Pin 5: Clock
Pin 6: Not connected
```

**Signals**:
- **Clock (CLK)**: Clock signal from keyboard (11-16.7 kHz typical)
- **Data (DATA)**: Serial data line (bidirectional)
- **Ground**: Common ground
- **+5V**: Power supply (keyboard powered from host)

**Electrical Characteristics**:
- **Logic High**: 3.0V - 5.5V
- **Logic Low**: 0V - 0.5V
- **Open-collector**: Both clock and data are open-collector
- **Pull-up resistors**: 10kΩ to +5V required

### Protocol Overview

**PS/2 Protocol**:
- **Serial**: 2-wire serial protocol
- **Bidirectional**: Host can send commands to keyboard
- **11-bit frames**: Start bit, 8 data bits, parity, stop bit
- **Clock-driven**: Keyboard generates clock signal
- **Asynchronous**: No fixed clock rate (keyboard controls timing)

**Data Frame Format**:
```
Start Bit (0) | D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 | Parity | Stop Bit (1)
     ↓         └─────────────────────────────────────┘      ↓         ↓
  Always LOW   8 Data Bits (LSB first)              Odd Parity  Always HIGH
```

**Timing**:
- **Clock frequency**: 10-16.7 kHz (keyboard controlled)
- **Clock period**: ~60-100µs
- **Data setup**: 5µs before clock falling edge
- **Data hold**: 5µs after clock falling edge

### Communication Direction

**Keyboard → Host (Default)**:
- Keyboard initiates communication
- Keyboard generates clock
- Host reads data on clock falling edge
- Used for key press/release events

**Host → Keyboard (Command Mode)**:
- Host initiates by pulling clock LOW
- Host generates clock
- Keyboard reads data on clock falling edge
- Used for commands (reset, LED control, etc.)

---

## Scan Codes

### Scan Code Sets

**Three Scan Code Sets**:
- **Set 1**: Original IBM PC/XT (most common)
- **Set 2**: IBM PC/AT (default for most keyboards)
- **Set 3**: IBM PS/2 (less common)

**Recommendation**: Use **Scan Code Set 2** (most common, default)

### Make and Break Codes

**Make Code**: Key pressed
- **Single-byte**: Most keys (0x01-0x83)
- **Two-byte**: Extended keys (0xE0 prefix)

**Break Code**: Key released
- **Prefix**: 0xF0 (break prefix)
- **Followed by**: Make code

**Example - Key 'A' Pressed and Released**:
```
Press:  0x1C (make code for 'A')
Release: 0xF0 0x1C (break prefix + make code)
```

### Scan Code Set 2 Reference

**Common Keys** (Scan Code Set 2):
```
Key      Make Code  Break Code
─────────────────────────────────
A        0x1C       0xF0 0x1C
B        0x32       0xF0 0x32
C        0x21       0xF0 0x21
...
0        0x45       0xF0 0x45
1        0x16       0xF0 0x16
...
Enter    0x5A       0xF0 0x5A
Space    0x29       0xF0 0x29
Shift    0x12       0xF0 0x12
Ctrl     0x14       0xF0 0x14
Alt      0x11       0xF0 0x11
```

**Extended Keys** (E0 prefix):
```
Key      Make Code      Break Code
─────────────────────────────────────
Right Ctrl  0xE0 0x14   0xE0 0xF0 0x14
Right Alt   0xE0 0x11   0xE0 0xF0 0x11
Arrow Up    0xE0 0x75   0xE0 0xF0 0x75
Arrow Down  0xE0 0x72   0xE0 0xF0 0x72
Arrow Left  0xE0 0x6B   0xE0 0xF0 0x6B
Arrow Right 0xE0 0x74   0xE0 0xF0 0x74
```

### Special Codes

**Special Scan Codes**:
- **0xE0**: Extended key prefix
- **0xF0**: Break code prefix
- **0xE1**: Pause/Break key prefix (special)
- **0xFA**: Acknowledge (ACK)
- **0xFE**: Resend request
- **0xFF**: Error/Reset

---

## Hardware Interface

### Circuit Design

**PS/2 Interface Circuit**:
```
PS/2 Connector         65C816 System
─────────────────────────────────────
Pin 1 (Data)  ──→ I/O Pin (with 10kΩ pull-up)
Pin 3 (GND)   ──→ Ground
Pin 4 (+5V)   ──→ +5V (if powering keyboard)
Pin 5 (Clock) ──→ Interrupt Pin (with 10kΩ pull-up)
```

**Interrupt Connection**:
- **Clock line** → Interrupt input (IRQ)
- **Falling edge** triggers interrupt
- **Interrupt handler** reads data bit

**Pull-up Resistors**:
- **10kΩ** on clock line (to +5V)
- **10kΩ** on data line (to +5V)
- Required for open-collector operation

### Memory-Mapped I/O

**Address Mapping** (Example):
```
Address      Function
─────────────────────────────
$9F40        PS/2 Data Register (read/write)
$9F41        PS/2 Status Register (read-only)
$9F42        PS/2 Control Register (write-only)
```

**Status Register Bits**:
- **Bit 0**: Data available (1 = data ready)
- **Bit 1**: Clock state (1 = high, 0 = low)
- **Bit 2**: Data state (1 = high, 0 = low)
- **Bit 3**: Parity error (1 = error)
- **Bit 4**: Frame error (1 = error)

---

## Software Implementation

### Interrupt Handler

**PS/2 Interrupt Handler** (Assembly):
```assembly
; PS/2 keyboard interrupt handler
; Called on clock falling edge
PS2_IRQ_HANDLER:
    PHA              ; Save registers
    PHX
    PHY
    
    ; Read data bit
    LDA PS2_DATA_REG
    AND #$01        ; Get data bit
    
    ; Store in shift register
    LDX ps2_bit_count
    CPX #11         ; Complete frame?
    BCS frame_complete
    
    ; Shift data into frame
    LSR ps2_frame
    BCC bit_zero
    ORA #$80        ; Set MSB
bit_zero:
    STA ps2_frame
    
    INC ps2_bit_count
    BRA irq_done

frame_complete:
    ; Process complete frame
    JSR process_scan_code
    LDA #0
    STA ps2_bit_count
    STA ps2_frame

irq_done:
    PLY              ; Restore registers
    PLX
    PLA
    RTI              ; Return from interrupt
```

### Scan Code Reception

**Receive Scan Code**:
```assembly
; Receive scan code from keyboard
; Output: A = scan code byte, C = carry (1 = valid)
receive_scan_code:
    LDA ps2_scan_code_buffer
    CMP #$FF
    BEQ no_code
    
    ; Valid code
    PHA
    LDA #$FF
    STA ps2_scan_code_buffer  ; Clear buffer
    PLA
    SEC              ; Set carry (valid)
    RTS

no_code:
    CLC              ; Clear carry (no code)
    RTS
```

### Scan Code Translation

**Translate Scan Code to Key Code**:
```assembly
; Translate scan code to key code
; Input: A = scan code
; Output: A = key code (0-255) or $FF if invalid
translate_scan_code:
    ; Check for break code
    CMP #$F0
    BEQ break_code
    
    ; Check for extended key
    CMP #$E0
    BEQ extended_key
    
    ; Normal key - look up in table
    TAX
    LDA scan_code_table,X
    RTS

break_code:
    ; Next byte is make code
    JSR receive_scan_code
    BCC invalid
    ; Mark key as released
    ORA #$80        ; Set bit 7 for release
    RTS

extended_key:
    ; Next byte is extended make code
    JSR receive_scan_code
    BCC invalid
    ; Look up in extended table
    TAX
    LDA extended_scan_code_table,X
    RTS

invalid:
    LDA #$FF
    RTS

; Scan code to ASCII table (Set 2)
scan_code_table:
    .byte $FF, $FF, $FF, $FF  ; 0x00-0x03
    .byte $FF, $FF, $FF, $FF  ; 0x04-0x07
    .byte $FF, $FF, $FF, $FF  ; 0x08-0x0B
    .byte $FF, $FF, $09, $60  ; 0x0C-0x0F (Tab, `)
    .byte $FF, $FF, $FF, $FF  ; 0x10-0x13
    .byte $FF, $FF, 'q', '1'  ; 0x14-0x17
    .byte $FF, $FF, 'z', 's'  ; 0x18-0x1B
    .byte 'a', 'w', '2', $FF  ; 0x1C-0x1F
    .byte $FF, 'c', 'x', 'd'  ; 0x20-0x23
    .byte 'e', '4', '3', $FF  ; 0x24-0x27
    .byte $FF, ' ', 'v', 'f'  ; 0x28-0x2B
    .byte 't', 'r', '5', $FF  ; 0x2C-0x2F
    .byte $FF, 'n', 'b', 'h'  ; 0x30-0x33
    .byte 'g', 'y', '6', $FF  ; 0x34-0x37
    .byte $FF, $FF, 'm', 'j'  ; 0x38-0x3B
    .byte 'u', '7', '8', $FF  ; 0x3C-0x3F
    .byte $FF, ',', 'k', 'i'  ; 0x40-0x43
    .byte 'o', '0', '9', $FF  ; 0x44-0x47
    .byte $FF, '.', '/', 'l'  ; 0x48-0x4B
    .byte ';', 'p', '-', $FF  ; 0x4C-0x4F
    .byte $FF, $FF, "'", $FF  ; 0x50-0x53
    .byte '[', '=', $FF, $FF  ; 0x54-0x57
    .byte $FF, $FF, $FF, $FF  ; 0x58-0x5B
    .byte $FF, $FF, $0D, ']'  ; 0x5C-0x5F (Enter, ])
    ; ... continue for all keys
```

### Key Buffer

**Circular Key Buffer**:
```assembly
; Key buffer (circular)
KEY_BUFFER_SIZE = 32

key_buffer:     .res KEY_BUFFER_SIZE
key_buffer_head: .byte 0
key_buffer_tail: .byte 0

; Add key to buffer
; Input: A = key code
add_key_to_buffer:
    PHA
    LDX key_buffer_head
    STA key_buffer,X
    INX
    CPX #KEY_BUFFER_SIZE
    BNE no_wrap
    LDX #0
no_wrap:
    CPX key_buffer_tail
    BEQ buffer_full    ; Buffer full
    STX key_buffer_head
    PLA
    RTS

buffer_full:
    PLA              ; Discard key
    RTS

; Get key from buffer
; Output: A = key code, C = carry (1 = valid)
get_key_from_buffer:
    LDX key_buffer_tail
    CPX key_buffer_head
    BEQ buffer_empty
    
    LDA key_buffer,X
    INX
    CPX #KEY_BUFFER_SIZE
    BNE no_wrap_get
    LDX #0
no_wrap_get:
    STX key_buffer_tail
    SEC              ; Valid key
    RTS

buffer_empty:
    CLC              ; No key
    RTS
```

### Keyboard Initialization

**Initialize Keyboard**:
```assembly
; Initialize PS/2 keyboard
init_keyboard:
    ; Clear key buffer
    LDA #0
    STA key_buffer_head
    STA key_buffer_tail
    
    ; Set up interrupt
    ; Configure IRQ for PS/2 clock
    ; Enable interrupts
    
    ; Reset keyboard
    JSR keyboard_reset
    
    ; Wait for ACK
    JSR wait_for_ack
    
    ; Set scan code set 2
    LDA #$F0
    JSR send_keyboard_command
    LDA #$02        ; Set 2
    JSR send_keyboard_command
    JSR wait_for_ack
    
    ; Enable keyboard
    LDA #$F4        ; Enable scanning
    JSR send_keyboard_command
    JSR wait_for_ack
    
    RTS

; Reset keyboard
keyboard_reset:
    LDA #$FF        ; Reset command
    JSR send_keyboard_command
    JSR wait_for_ack
    ; Wait for reset complete (0xAA)
    JSR receive_scan_code
    CMP #$AA
    BEQ reset_ok
    ; Reset failed
    RTS
reset_ok:
    RTS
```

### Send Command to Keyboard

**Send Command**:
```assembly
; Send command to keyboard
; Input: A = command byte
send_keyboard_command:
    PHA
    
    ; Pull clock LOW for 100µs
    LDA PS2_CTRL_REG
    AND #$FE        ; Clear clock bit (LOW)
    STA PS2_CTRL_REG
    JSR delay_100us
    
    ; Pull data LOW
    AND #$FD        ; Clear data bit (LOW)
    STA PS2_CTRL_REG
    
    ; Release clock (keyboard takes over)
    ORA #$01        ; Set clock bit (HIGH)
    STA PS2_CTRL_REG
    
    ; Send data bits
    PLA
    LDX #8
send_bits:
    ROR A           ; Get bit in carry
    BCC bit_low
    ; Bit HIGH - release data line
    LDA PS2_CTRL_REG
    ORA #$02        ; Set data bit
    BRA set_bit
bit_low:
    ; Bit LOW - pull data line LOW
    LDA PS2_CTRL_REG
    AND #$FD        ; Clear data bit
set_bit:
    STA PS2_CTRL_REG
    JSR delay_10us  ; Wait for clock
    
    DEX
    BNE send_bits
    
    ; Send parity
    ; Calculate odd parity
    ; Send parity bit
    
    ; Send stop bit (release data)
    LDA PS2_CTRL_REG
    ORA #$02        ; Set data bit (HIGH)
    STA PS2_CTRL_REG
    
    ; Wait for ACK
    JSR wait_for_ack
    RTS
```

---

## Pascal Interface (Year 6)

### Type Definitions

```pascal
type
  ScanCode = byte;
  KeyCode = byte;
  KeyState = (KeyPressed, KeyReleased);

const
  PS2_DATA_REG = $9F40;
  PS2_STATUS_REG = $9F41;
  PS2_CTRL_REG = $9F42;
  
  KEY_BUFFER_SIZE = 32;
  
  { Special scan codes }
  SCAN_BREAK = $F0;
  SCAN_EXTENDED = $E0;
  SCAN_ACK = $FA;
  
  { Keyboard commands }
  CMD_RESET = $FF;
  CMD_ENABLE = $F4;
  CMD_SET_SCANCODE = $F0;
```

### Basic Procedures

**Initialize Keyboard**:
```pascal
procedure KeyboardInit;
begin
  { Clear key buffer }
  KeyBufferHead := 0;
  KeyBufferTail := 0;
  
  { Set up interrupt }
  { Configure IRQ for PS/2 clock }
  { Enable interrupts }
  
  { Reset keyboard }
  KeyboardReset;
  
  { Set scan code set 2 }
  SendKeyboardCommand(CMD_SET_SCANCODE);
  SendKeyboardCommand(2);
  
  { Enable keyboard }
  SendKeyboardCommand(CMD_ENABLE);
end;
```

**Get Key**:
```pascal
function GetKey: KeyCode;
var
  keyCode: KeyCode;
begin
  { Wait for key in buffer }
  while KeyBufferHead = KeyBufferTail do
    { Wait };
  
  { Get key from buffer }
  keyCode := KeyBuffer[KeyBufferTail];
  KeyBufferTail := (KeyBufferTail + 1) mod KEY_BUFFER_SIZE;
  
  GetKey := keyCode;
end;
```

**Check Key Available**:
```pascal
function KeyAvailable: boolean;
begin
  KeyAvailable := KeyBufferHead <> KeyBufferTail;
end;
```

---

## Troubleshooting

### Common Issues

**No Keys Detected**:
- Check PS/2 connections (clock, data, ground, power)
- Verify pull-up resistors (10kΩ)
- Check interrupt configuration
- Verify clock signal

**Wrong Keys Detected**:
- Check scan code table
- Verify scan code set (should be Set 2)
- Check for extended keys (E0 prefix)
- Verify break code handling

**Intermittent Detection**:
- Check for loose connections
- Verify power supply stability
- Check interrupt timing
- Add debouncing if needed

**Keyboard Not Responding**:
- Check keyboard power (+5V)
- Verify initialization sequence
- Check for ACK responses
- Test with known-good keyboard

---

## Educational Exercises

### Exercise 1: Protocol Timing

**Task**: Calculate timing for PS/2 protocol:
- Clock frequency: 12 kHz
- What is clock period?
- How long to receive one byte?

**Answer**: Period = 83µs, Byte = 11 bits × 83µs = 913µs

### Exercise 2: Scan Code Translation

**Task**: Translate scan code sequence:
- Received: 0x1C 0xF0 0x1C
- What key was pressed/released?

**Answer**: Key 'A' pressed (0x1C), then released (0xF0 0x1C)

### Exercise 3: Buffer Design

**Task**: Design circular buffer for 32 keys:
- Head pointer: 5
- Tail pointer: 2
- How many keys in buffer?

**Answer**: 3 keys (indices 2, 3, 4)

---

## Summary

**Key Concepts**:
1. **PS/2 Protocol**: Serial 2-wire protocol with clock and data
2. **Scan Codes**: Key press/release codes (Set 2 recommended)
3. **Interrupts**: Clock falling edge triggers interrupt
4. **Translation**: Convert scan codes to key codes/ASCII
5. **Buffering**: Circular buffer for key presses

**Educational Value**:
- Serial protocol implementation
- Interrupt-driven I/O
- Device driver development
- Full keyboard support
- Industry-standard interface

**When to Use**:
- **Year 6**: Required for complete system (this guide)
- **Prerequisites**: Interrupt capability, I/O ports

**Progression**:
- Year 3: Buttons
- Year 4: Matrix Keypad (optional)
- Year 6: PS/2 Keyboard ✅

---

**Document Created**: 2025-12-16  
**Purpose**: PS/2 keyboard interface guide for Year 6  
**Status**: Complete

