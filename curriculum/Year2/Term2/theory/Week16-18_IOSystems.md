# Week 16-18: Input/Output Systems - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand I/O device interfacing
- Design simple input interfaces
- Design simple output interfaces
- Understand data direction control
- Implement I/O timing and synchronization

## Prerequisites

- Completed Weeks 13-15 (Address Decoding)
- Understanding of memory-mapped I/O
- Understanding of address decoding
- Understanding of buses and tri-state

## Key Concepts

### 0. Debugging Tools: TTL Logic Probe ⭐ QUICK WIN LAB PROJECT

**TTL Logic Probe Construction**:
- Students build TTL Logic Probe in Lab Session 0
- Essential debugging tool used throughout curriculum
- Detects digital signal levels (HIGH, LOW, floating, pulse)
- Teaches signal analysis and debugging techniques

**Educational Value**:
- ✅ **Immediate utility**: Tool used in all subsequent labs
- ✅ **Signal understanding**: Teaches digital signal levels
- ✅ **Debugging skills**: Essential for hardware troubleshooting
- ✅ **Reinforcement**: Used across Years 2-6, reinforcing concepts

**Reference**: See `../../../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for design reference

### 1. I/O Device Basics

**What are I/O devices?**
- **Input**: Devices that provide data to the system (switches, buttons, sensors)
- **Output**: Devices that display or act on data (LEDs, displays, motors)
- **Bidirectional**: Devices that can do both (some displays, communication ports)

**Why I/O matters**:
- Computers need to interact with the world
- Input provides data and control
- Output shows results and status
- I/O makes computers useful

### 2. Simple Input Devices

**Switches and buttons**:
- Provide binary input (on/off)
- Need debouncing (learned in Year 1)
- Can be read as memory location
- Simple but essential

**DIP switches**:
- Multiple switches in one package
- Provide multiple bits of input
- Read as byte or word
- Useful for configuration

**Reading input**:
- Address decoder selects input device
- Device drives data bus (via tri-state)
- CPU reads data from bus
- Data represents input state

### 3. Simple Output Devices

**LEDs**:
- Binary output (on/off)
- Can be individual or arrays
- Need current-limiting resistors
- Simple status indication

**7-segment displays**:
- Display digits 0-9 (and some letters)
- Need decoder/driver IC
- Can show numbers and simple text
- Common in embedded systems

**LED arrays**:
- Multiple LEDs in grid
- Can show patterns or simple graphics
- Need row/column scanning
- More complex but versatile

### 4. Data Direction Control

**The problem**:
- Some devices are input only
- Some devices are output only
- Some devices are bidirectional
- Need to control data flow direction

**The solution**:
- **Data Direction Register (DDR)**: Controls I/O direction
- Bit = 0: Input (read from device)
- Bit = 1: Output (write to device)
- Can be changed dynamically

**Implementation**:
- Separate register for direction
- Controls tri-state buffers
- Prevents conflicts
- Enables flexible I/O

### 5. Memory-Mapped I/O Implementation

**I/O as memory**:
- I/O devices at specific addresses
- Read = input operation
- Write = output operation
- Same bus protocol as memory

**Address assignment**:
- I/O space in memory map
- Example: 0x9000-0x9FFF for I/O
- Each device at specific address
- Can have multiple registers per device

**Example I/O map**:
```
0x9000: LED output register
0x9001: Switch input register
0x9002: Display data register
0x9003: Display control register
```

### 6. I/O Timing

**Synchronization**:
- I/O operations take time
- Need to wait for completion
- Polling: Check status until ready
- Interrupts: Device signals when ready (advanced)

**Read timing**:
- Assert address and chip select
- Wait for device to respond
- Read data from bus
- Deassert signals

**Write timing**:
- Put data on bus
- Assert address and chip select
- Assert write enable
- Wait for device to latch
- Deassert signals

### 7. Display Interfaces

**7-segment display**:
- 7 LEDs arranged as segments
- BCD to 7-segment decoder (74HC47)
- Can show 0-9, some letters
- Simple and common

**Character LCD**:
- 16×2 or 20×4 character display
- Parallel interface (8 data bits)
- Control signals (RS, E, R/W)
- Can show text messages

**LED matrix**:
- Grid of LEDs (e.g., 8×8)
- Row/column scanning
- Can show patterns
- More complex control

### 8. Input Interfaces

**Switch matrix**:
- Multiple switches in grid
- Row/column scanning
- Detect which switch pressed
- Efficient for many switches

**Analog input** (conceptual):
- Continuous values (not just on/off)
- Need ADC (Analog-to-Digital Converter)
- More complex
- Advanced topic

**Serial input** (conceptual):
- Data arrives bit by bit
- Need UART or shift register
- More complex
- Advanced topic

## Mathematical Foundations

### I/O Address Space

- **I/O addresses needed** = Number of I/O registers
- **Address bits** = ⌈log₂(number of registers)⌉
- **Example**: 16 I/O registers need 4 address bits

### Display Scanning

For n×m LED matrix:
- **Scan rate** = Refresh rate × (n or m)
- **Duty cycle** = 1/(n or m)
- **Example**: 8×8 matrix, 60Hz refresh = 480Hz scan rate

## Common Misconceptions

1. **"I/O is complex"**: Simple I/O is straightforward
2. **"Need special I/O instructions"**: Memory-mapped I/O is simpler
3. **"All devices are the same"**: Different devices need different interfaces
4. **"I/O is instant"**: I/O operations take time

## Connections to Term 1-2

- **Memory**: I/O uses same addressing
- **Address Decoding**: I/O devices need chip selects
- **Buses**: I/O uses system bus
- **Control Signals**: I/O needs control signals

## Connections to Year 3

- **SAP-1 Output**: Simple output display
- **CPU I/O**: Real CPUs use memory-mapped I/O
- **System Design**: I/O is essential for useful computers
- **Future Systems**: More complex I/O in later years

## Next Steps

After understanding I/O systems, students will:
- Build input interfaces
- Build output interfaces
- Integrate I/O with system
- Move to Term 3: Advanced Integration

---

*I/O systems connect computers to the real world*
