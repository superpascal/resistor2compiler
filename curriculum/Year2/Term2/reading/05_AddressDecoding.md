# Chapter 5: Address Decoding and Memory Mapping

## Introduction

Address decoding selects which device responds to an address. Memory mapping organizes the address space. This chapter explains how to design and implement these systems.

## Address Decoding Basics

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

## Memory Map Design

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

## Chip Select Generation

**Using decoders**:
- 74HC138 (3-to-8 decoder): 8 devices
- 74HC139 (2-to-4 decoder): 4 devices
- Higher address bits → decoder inputs
- Decoder outputs → chip select signals

**Logic example**:
- If A15=0 and A14=0: Select RAM
- If A15=0 and A14=1: Select ROM
- If A15=1: Select I/O space

## Memory-Mapped I/O

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

## Multiple Memory Chips

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

## Practice Questions

1. What is address decoding?
2. Why do we need memory maps?
3. How does chip select work?
4. What is memory-mapped I/O?
5. How do we expand memory?

## Key Takeaways

- Address decoding selects devices
- Memory maps organize address space
- Chip selects enable devices
- Memory-mapped I/O is simple and flexible
- Multiple chips expand system capabilities

---

*Address decoding enables complex memory and I/O systems*
