# Week 5-8: Input/Output Subsystems - Theory

## Learning Objectives

By the end of this week-block, students will:
- Integrate ACIA for serial communication
- Integrate VIA for parallel I/O
- Interface LCD display
- Implement timer functions
- Understand I/O subsystem integration

## Prerequisites

- Completed Weeks 1-4 (Memory Banking)
- Expanded 65C816 system
- Understanding of I/O concepts
- Understanding of memory-mapped I/O

## Key Concepts

### 1. Serial Communication with ACIA

**ACIA (65C51)**:
- Asynchronous Communications Interface Adapter
- UART functionality
- RS-232 compatible
- Serial communication

**ACIA features**:
- Transmit and receive
- Baud rate selection
- Status registers
- Interrupt capability

**Integration**:
- Memory-mapped I/O
- Specific address range
- Register access
- Control and data registers

### 2. Parallel I/O with VIA

**VIA (65C22)**:
- Versatile Interface Adapter
- Parallel I/O ports (A and B)
- Timers
- Shift register
- Interrupt capability

**VIA features**:
- Two 8-bit ports
- Programmable direction
- Timer/counter functions
- Shift register mode

**Integration**:
- Memory-mapped I/O
- Port A and Port B
- Control registers
- Timer registers

### 3. LCD Display Interface

**LCD display**:
- Character LCD (2×16 or 4×20)
- Parallel interface
- Simple control
- Text output

**LCD connection**:
- Data bus connection
- Control signals
- Via VIA or direct
- Initialization required

**LCD operation**:
- Send commands
- Send data
- Control cursor
- Display text

### 4. Timer Functions

**VIA timers**:
- Two timers (Timer 1 and Timer 2)
- Programmable intervals
- Interrupt generation
- One-shot or continuous

**Timer uses**:
- Delays
- Periodic interrupts
- Time measurement
- Event timing

**Timer programming**:
- Set timer value
- Configure mode
- Enable interrupts (optional)
- Read timer status

### 5. I/O Address Mapping

**Memory-mapped I/O**:
- I/O devices in address space
- Access like memory
- Register-based interface
- Standard addressing

**I/O map example**:
```
0x9F00 - 0x9F0F: VIA 1
0x9F10 - 0x9F1F: VIA 2
0x9F20 - 0x9F2F: ACIA
0x9F30 - 0x9F3F: Reserved
```

**Address decoding**:
- Higher address bits select device
- Lower address bits select register
- Chip select generation
- Register access

### 6. Serial Terminal Interface

**Terminal communication**:
- PC connected via serial
- Terminal program on PC
- Text input/output
- Interactive interface

**Monitor program**:
- Resides in ROM
- Uses ACIA for I/O
- Accepts commands
- Displays output

**Terminal features**:
- Character echo
- Command parsing
- Memory display
- Program loading

### 7. I/O Programming

**ACIA programming**:
- Initialize ACIA
- Set baud rate
- Send characters
- Receive characters
- Check status

**VIA programming**:
- Configure ports
- Set direction
- Read/write ports
- Use timers
- Handle interrupts

**LCD programming**:
- Initialize LCD
- Send commands
- Send characters
- Control display
- Format output

### 8. I/O Testing

**Test procedures**:
- Test ACIA transmission
- Test ACIA reception
- Test VIA ports
- Test LCD display
- Test timers

**Verification**:
- Serial output works
- Serial input works
- Parallel I/O works
- LCD displays correctly
- Timers function

## Mathematical Foundations

### Baud Rate

**Baud rate calculation**:
- Clock frequency / divisor = baud rate
- Common rates: 9600, 19200, 38400
- Must match on both ends

### Timer Intervals

**Timer value calculation**:
- Desired interval / clock period = count
- Timer counts down
- Interrupt on zero

## Common Misconceptions

1. **"I/O is complex"**
   - Clarify: Register-based, straightforward
   - Show simple examples

2. **"Need many chips"**
   - Clarify: Start with few, expand
   - Show minimal setup

3. **"Serial is difficult"**
   - Clarify: ACIA handles details
   - Show basic usage

## Connections to Weeks 1-4

- **Memory Banking**: Supports I/O space
- **System Expansion**: Part of expansion
- **Address Decoding**: Used for I/O

## Connections to Weeks 9-12

- **Graphics/Sound**: I/O foundation
- **System Integration**: Part of system
- **Year 5**: Foundation for PCB

## Next Steps

After integrating I/O, students will:
- Research graphics options (Weeks 9-12)
- Research sound options (Weeks 9-12)
- Prepare for Year 5

---

*I/O subsystems enable interaction and prepare for complete systems*
