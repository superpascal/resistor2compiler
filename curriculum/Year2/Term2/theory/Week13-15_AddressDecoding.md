# Week 13-15: Address Decoding and Memory Mapping - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand address decoding for multiple devices
- Design memory maps
- Implement chip select generation
- Understand memory-mapped I/O
- Build systems with multiple memory chips

## Prerequisites

- Completed Weeks 10-12 (Advanced State Machines)
- Understanding of memory concepts
- Understanding of address spaces
- Understanding of decoders

## Key Concepts

### 1. Address Decoding Basics

**The problem**:
- Multiple devices (memory chips, I/O devices)
- One address bus
- Need to select which device responds

**The solution**:
- Address decoding logic
- Chip select signals
- Memory mapping

**Basic concept**:
- Higher address bits select device
- Lower address bits select location within device
- Decoder generates chip select signals

### 2. Simple Address Decoding

**2-to-4 decoder example**:
- 2 address bits → 4 chip selects
- Each chip select enables one device
- Devices don't conflict

**Example memory map**:
- Addresses 0x00-0x3F: Device 0 (64 locations)
- Addresses 0x40-0x7F: Device 1 (64 locations)
- Addresses 0x80-0xBF: Device 2 (64 locations)
- Addresses 0xC0-0xFF: Device 3 (64 locations)

### 3. Memory Map Design

**Memory map** defines which addresses correspond to which devices.

**Design considerations**:
- **Size**: How much memory per device?
- **Alignment**: Start addresses (usually power of 2)
- **Gaps**: Reserved addresses for future expansion
- **I/O space**: Where to put I/O devices

**Example map**:
```
0x0000 - 0x7FFF: RAM (32KB)
0x8000 - 0x8FFF: ROM (4KB)
0x9000 - 0x9FFF: I/O devices
0xA000 - 0xFFFF: Reserved
```

### 4. Chip Select Generation

**Using decoders**:
- 74HC138 (3-to-8 decoder): 8 devices
- 74HC139 (2-to-4 decoder): 4 devices
- Higher address bits → decoder inputs
- Decoder outputs → chip select signals

**Logic example**:
- If A15=0 and A14=0: Select RAM
- If A15=0 and A14=1: Select ROM
- If A15=1: Select I/O space

### 5. Memory-Mapped I/O

**Concept**:
- Treat I/O devices like memory locations
- Read/write to I/O addresses
- No special I/O instructions needed
- Simple and flexible

**Advantages**:
- Unified addressing
- Easy to implement
- Flexible device placement
- Simple programming model

**Example**:
- Address 0x9000: LED output register
- Address 0x9001: Switch input register
- Address 0x9002: Display data register

### 6. Multiple Memory Chips

**Expanding memory**:
- Add more RAM chips
- Use address decoding to select chip
- Each chip has its own address range
- System sees continuous address space

**Implementation**:
- Higher address bits → chip select
- Lower address bits → location in chip
- All chips share data bus (with tri-state)
- Only selected chip drives bus

### 7. Address Decoding Logic

**Simple decoding**:
- Direct address bit connections
- Works for simple cases
- Limited flexibility

**Decoder-based**:
- Use decoder ICs
- More flexible
- Easier to modify

**Programmable decoding**:
- Use logic gates
- Custom decoding logic
- Maximum flexibility

### 8. Partial Address Decoding

**Full decoding**:
- All address bits used
- No address conflicts
- Maximum address space usage

**Partial decoding**:
- Some address bits ignored
- Addresses "mirror" (same location multiple addresses)
- Simpler decoding logic
- Acceptable for small systems

**Example**:
- 8-bit address, 4-bit device address
- Lower 4 bits ignored
- Address 0x05 and 0x15 access same location

## Mathematical Foundations

### Address Range Calculation

For n address bits:
- **Total locations** = 2^n
- **Locations per device** = 2^(n-m) where m = address bits for chip select
- **Number of devices** = 2^m

### Memory Map Size

- **Device size** = Number of locations × Bits per location
- **Example**: 64 locations × 8 bits = 512 bits = 64 bytes
- **Total system** = Sum of all device sizes

## Common Misconceptions

1. **"All addresses must be used"**: Gaps are fine, even beneficial
2. **"Decoding is complex"**: Simple decoding works for many cases
3. **"I/O needs special instructions"**: Memory-mapped I/O is simpler
4. **"More chips = more complexity"**: Good decoding makes it manageable

## Connections to Term 1

- **Memory**: Now using multiple memory chips
- **Addresses**: Understanding address spaces
- **Buses**: Shared bus with multiple devices
- **Control**: Chip select as control signal

## Connections to Year 3

- **SAP-1**: Uses address decoding for memory
- **CPU Design**: Address decoding is essential
- **Memory Systems**: Foundation for larger systems
- **I/O Systems**: Memory-mapped I/O used in real CPUs

## Next Steps

After understanding address decoding, students will:
- Build address decoding circuits
- Design memory maps
- Implement multiple device systems
- Move to I/O systems (Weeks 16-18)

---

*Address decoding enables complex memory and I/O systems*
