# Chapter 3: Memory Expansion and Harvard Architecture

## Introduction

Memory expansion enables larger programs. Harvard architecture separates code and data. This chapter explains how to expand memory and implement Harvard architecture.

## Memory Expansion

**Current limitation**:
- 4-bit address = 16 bytes
- Very limited for programs
- Restricts program complexity

**Expansion goal**:
- 8-bit address = 256 bytes
- 16× more memory
- Enables larger programs
- More realistic system

## Extending Program Counter and MAR

**PC expansion**:
- Current: 4-bit (0-15)
- Expanded: 8-bit (0-255)
- Use two 4-bit counters cascaded
- Lower wraps, upper increments

**MAR expansion**:
- Current: 4-bit
- Expanded: 8-bit
- Use two 4-bit registers
- Connect together

## Larger Memory Chip

**Memory selection**:
- Replace 16-byte RAM
- Use 32KB or 64KB SRAM
- Use only 256 bytes initially
- Room for future expansion

## Harvard Architecture

**What is Harvard architecture?**
- Separate instruction and data memory
- Instructions in ROM
- Data in RAM
- Can fetch simultaneously (conceptually)

**Benefits**:
- Programs can't be overwritten
- Clear separation
- Can optimize each memory type
- Foundation for advanced systems

**Implementation**:
- ROM for program code
- RAM for data
- Address decoder separates them
- Different address ranges

## Memory Map Design

**Example memory map**:
```
0x00 - 0x7F: RAM (data storage)
0x80 - 0xFF: ROM (program code)
```

**Design considerations**:
- Size of each region
- Alignment (power of 2)
- Room for expansion
- I/O space allocation

## Practice Questions

1. Why expand memory?
2. How do we extend PC and MAR?
3. What is Harvard architecture?
4. How do we implement Harvard?
5. What are the benefits?

## Key Takeaways

- Memory expansion enables larger programs
- Cascading extends address range
- Harvard separates code and data
- Address decoding enables separation
- Preparation for 16-bit systems

---

*Memory expansion enables larger programs and prepares for 16-bit systems*
