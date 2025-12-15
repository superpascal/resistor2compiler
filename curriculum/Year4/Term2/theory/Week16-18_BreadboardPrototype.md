# Week 16-18: Breadboard Prototype Construction - Theory

## Learning Objectives

By the end of this week-block, students will:
- Build minimal 65C816 system on breadboard
- Connect CPU, memory, and basic I/O
- Test reset and clock circuits
- Test basic memory access
- Verify CPU operation
- Understand prototype development

## Prerequisites

- Completed Weeks 17-20 (System Design)
- Complete system design
- Understanding of 65C816 architecture
- Understanding of system components

## Key Concepts

### 1. Prototype Development

**What is a prototype?**
- Working model of final system
- Tests design concepts
- Verifies operation
- Identifies issues early

**Prototype goals**:
- Minimal but functional
- Tests essential features
- Verifies design
- Enables learning

**Breadboard prototype**:
- Build on breadboards
- Test before PCB
- Easy to modify
- Learn from building

### 2. Minimal System Components

**Essential components**:
- 65C816 CPU
- SRAM (32KB minimum)
- ROM/EEPROM (for monitor)
- Clock oscillator
- Reset circuit
- Address decoder
- Basic I/O (one VIA, optional ACIA)

**Optional for prototype**:
- Second VIA
- ACIA (can add later)
- Advanced I/O
- Expansion features

### 3. Construction Strategy

**Build in stages**:
1. **Power and clock**: Get CPU powered and clocked
2. **Reset**: Get reset working
3. **Memory**: Connect and test memory
4. **Basic I/O**: Connect minimal I/O
5. **Integration**: Test complete system

**Testing at each stage**:
- Test before proceeding
- Verify each component
- Fix issues immediately
- Document progress

### 4. Reset and Clock

**Reset circuit**:
- Power-on reset
- Manual reset button
- Reset supervisor IC (recommended)
- Clean reset pulse to CPU
- CPU loads reset vector

**Reset vector**:
- Located at $FFFC/$FFFD (bank $FF)
- Contains startup address
- CPU jumps here on reset
- Points to monitor program

**Clock circuit**:
- Stable oscillator (1 MHz typical for prototype)
- TTL-compatible output
- Single-step capability
- Clock buffering

### 5. Memory Connection

**RAM connection**:
- 32KB or 64KB SRAM
- Connect address bus (A0-A14 for 32KB)
- Connect data bus (D0-D15)
- Connect control (CS, OE, WE)
- Address decoding

**ROM connection**:
- EEPROM or ROM chip
- Connect address bus
- Connect data bus
- Connect chip select
- Program with monitor

### 6. Basic I/O

**VIA connection**:
- One VIA for basic I/O
- Memory-mapped
- Parallel ports for LEDs/switches
- Timers for delays
- Interrupts (if used)

**ACIA (optional)**:
- Serial communication
- Terminal interface
- Useful for debugging
- Can add later

### 7. Testing the Prototype

**Initial power-up**:
- Check for shorts
- Verify power supply
- Monitor for overheating
- Check basic signals

**Reset test**:
- Apply reset
- Verify CPU loads reset vector
- Check address lines
- Verify CPU responds

**Clock test**:
- Verify clock signal
- Check frequency
- Test single-step
- Verify CPU advances

**Memory test**:
- Write test pattern to RAM
- Read back and verify
- Test ROM access
- Verify address decoding

### 8. Debugging the Prototype

**Debugging tools**:
- Logic analyzer (essential)
- Oscilloscope
- LEDs on buses
- Serial output (if ACIA available)

**Common issues**:
- Wrong connections
- Address decoding errors
- Timing problems
- Power issues
- Component failures

**Debugging process**:
- Observe behavior
- Check signals
- Verify connections
- Test components
- Fix issues
- Retest

## Mathematical Foundations

### Address Space

**32KB RAM**: 2^15 = 32,768 bytes
- Addresses 0x0000-0x7FFF
- A15=0 selects RAM
- A14-A0 select location

**32KB ROM**: 2^15 = 32,768 bytes
- Addresses 0x8000-0xFFFF
- A15=1 selects ROM
- A14-A0 select location

## Common Misconceptions

1. **"Prototype must be perfect"**
   - Clarify: Minimal but functional
   - Show learning value

2. **"Can't build on breadboard"**
   - Clarify: Many have done it
   - Show it's possible

3. **"Too complex to debug"**
   - Clarify: Systematic approach works
   - Show debugging method

## Connections to Weeks 17-20

- **Design**: Prototype implements design
- **Schematic**: Guide for construction
- **Planning**: Applied in building

## Connections to Year 5

- **PCB Design**: Prototype informs PCB
- **System Completion**: Foundation for final system
- **Integration**: Skills used in Year 5

## Next Steps

After building prototype, students will:
- Complete 65C816 system in Year 5
- Design PCBs
- Integrate advanced features
- Build final system

---

*Prototype development tests design and enables learning*
