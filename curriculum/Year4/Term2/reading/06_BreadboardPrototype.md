# Chapter 6: Breadboard Prototype Construction

## Introduction

Prototypes test designs before final construction. This chapter explains how to build and test a 65C816 breadboard prototype.

## Prototype Development

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

## Minimal System Components

**Essential components**:
- 65C816 CPU
- SRAM (32KB minimum)
- ROM/EEPROM (for monitor)
- Clock oscillator
- Reset circuit
- Address decoder
- Basic I/O (one VIA)

## Construction Strategy

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

## Reset and Clock

**Reset circuit**:
- Power-on reset
- Manual reset button
- Reset supervisor IC (recommended)
- Clean reset pulse to CPU

**Clock circuit**:
- Stable oscillator (1 MHz typical)
- TTL-compatible output
- Single-step capability
- Clock buffering

## Memory Connection

**RAM connection**:
- 32KB or 64KB SRAM
- Connect address bus
- Connect data bus
- Connect control signals
- Address decoding

**ROM connection**:
- EEPROM or ROM chip
- Connect address bus
- Connect data bus
- Connect chip select
- Program with monitor

## Testing the Prototype

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

**Memory test**:
- Write test pattern to RAM
- Read back and verify
- Test ROM access
- Verify address decoding

## Practice Questions

1. What is a prototype?
2. How do we build in stages?
3. How do we test the prototype?
4. What if it doesn't work?
5. How does this prepare for Year 5?

## Key Takeaways

- Prototypes test designs
- Build in stages
- Test at each stage
- Debug systematically
- Foundation for final system

---

*Prototype development tests design and enables learning*
