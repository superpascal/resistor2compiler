# Week 7-9: Memory Expansion and Harvard Architecture - Theory

## Learning Objectives

By the end of this week-block, students will:
- Expand address space from 4-bit to 8-bit (16 to 256 bytes)
- Extend PC and MAR to 8 bits
- Implement address decoding for larger memory
- Understand Harvard architecture concepts
- Implement ROM/RAM separation

## Prerequisites

- Completed Weeks 4-6 (Expanded Instruction Set)
- Understanding of memory systems (Year 2-3)
- Understanding of address decoding (Year 2)
- Understanding of PC and MAR (Year 3)
- Access to Malvino & Brown textbook

**Required Reading** (Primary Reference):
- **Malvino & Brown, Chapter 11-1**: SAP-2 Bidirectional Registers (bus concepts)
- **Malvino & Brown, Chapter 11-2**: SAP-2 Architecture (16-bit Addressing)
- **Malvino & Brown, Chapter 9**: Memories (review from Year 2)

**Book Integration**:
- Study SAP-2 architecture expansion (11-2): SAP-1 (4-bit addressing, 16 bytes) → SAP-2 (16-bit addressing, 64KB)
- Understand the progression: SAP-1 (4-bit) → SAP-2 (16-bit) → 65C816 (24-bit)
- Study SAP-2 bidirectional bus design (11-1) - understand bus concepts
- Review memory concepts (Chapter 9) - apply to memory expansion
- Plan memory expansion for enhanced SAP-1 using book's design principles

**Book-Based Exercise**:
- Exercise: Compare SAP-1 addressing (4-bit, 16 bytes) to SAP-2 (16-bit, 64KB) from book
- Exercise: Study SAP-2 bidirectional register design (11-1), apply concepts to SAP-1 improvements
- Exercise: Calculate address space for different address bus widths (from book progression: 4-bit → 8-bit → 16-bit)

## Key Concepts

### 1. Memory Expansion

**Current limitation**:
- 4-bit address = 16 bytes
- Very limited for programs
- Restricts program complexity

**Expansion goal**:
- 8-bit address = 256 bytes
- 16× more memory
- Enables larger programs
- More realistic system

**Expansion method**:
- Extend PC to 8 bits
- Extend MAR to 8 bits
- Use larger memory chip
- Update address decoding

### 2. Extending Program Counter

**PC expansion**:
- Current: 4-bit (0-15)
- Expanded: 8-bit (0-255)
- Use two 4-bit counters cascaded
- Or use 8-bit counter

**Cascading counters**:
- Lower counter: 0-15, increments normally
- Upper counter: Increments when lower wraps
- Together: 0-255 address range
- Standard technique

**Control signals**:
- Both counters increment together
- Both counters reset together
- Both counters can load (for jumps)
- Outputs combined for 8-bit address

### 3. Extending Memory Address Register

**MAR expansion**:
- Current: 4-bit
- Expanded: 8-bit
- Use two 4-bit registers
- Connect together

**Register connection**:
- Lower register: Lower address bits
- Upper register: Upper address bits
- Loaded together from bus
- Outputs combined to memory

### 4. Larger Memory Chip

**Memory selection**:
- Replace 16-byte RAM
- Use 32KB or 64KB SRAM
- Use only 256 bytes initially
- Room for future expansion

**Connection**:
- 8-bit address from MAR
- 8-bit data bus
- Chip select from decoder
- Read/write control

### 5. Address Decoding for Expansion

**Decoding requirements**:
- Select memory chip
- May need multiple chips later
- Address range selection
- I/O space separation

**Implementation**:
- Use decoders (74HC138)
- Higher address bits select chip/range
- Lower address bits select location
- Standard decoding technique

### 6. Harvard Architecture Concept

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

### 7. Memory Map Design

**Example memory map**:
```
0x00 - 0x7F: RAM (data storage)
0x80 - 0xFF: ROM (program code)
```

**Or**:
```
0x00 - 0x3F: RAM (64 bytes)
0x40 - 0x7F: Reserved
0x80 - 0xBF: ROM (64 bytes)
0xC0 - 0xFF: I/O space
```

**Design considerations**:
- Size of each region
- Alignment (power of 2)
- Room for expansion
- I/O space allocation

### 8. Testing Memory Expansion

**Test procedures**:
- Test 8-bit addressing
- Test all address ranges
- Test ROM/RAM separation
- Test program execution from ROM
- Test data access to RAM
- Verify complete system

**Verification**:
- Can address all 256 locations
- ROM and RAM work correctly
- Programs execute from ROM
- Data stored in RAM
- No conflicts

## Mathematical Foundations

### Address Space

**4-bit address**: 2^4 = 16 locations
**8-bit address**: 2^8 = 256 locations
**Expansion factor**: 16× increase

### Memory Organization

**Harvard separation**:
- Program space: Typically upper half
- Data space: Typically lower half
- Can be adjusted as needed
- Flexible arrangement

## Common Misconceptions

1. **"More memory is always better"**
   - Clarify: Balance with complexity
   - Show practical limits

2. **"Harvard is complex"**
   - Clarify: Simple address decoding
   - Show basic implementation

3. **"Expansion is just adding bits"**
   - Clarify: Requires system changes
   - Show all components affected

## Connections to Weeks 1-6

- **Improved System**: Reliable base for expansion
- **New Instructions**: May use expanded memory
- **System Enhancement**: Part of overall expansion

## Connections to Term 2

- **16-bit Systems**: Understanding memory expansion
- **65C816**: Uses much larger memory
- **System Design**: Memory mapping skills

## Next Steps

After memory expansion, students will:
- Understand larger systems (Term 2)
- Learn 65C816 architecture
- Design 16-bit systems
- Prepare for Year 5

---

*Memory expansion enables larger programs and prepares for 16-bit systems*
