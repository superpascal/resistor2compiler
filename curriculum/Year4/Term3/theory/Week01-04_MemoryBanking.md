# Week 1-4: Memory and Banking on 65C816 - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand memory banking concepts
- Expand RAM beyond 64KB
- Implement bank switching
- Understand 24-bit addressing
- Test memory banking operations

## Prerequisites

- Completed Term 2 (65C816 Prototype)
- Working 65C816 breadboard prototype
- Understanding of 65C816 architecture
- Understanding of address decoding

## Key Concepts

### 1. Memory Banking

**Why banking?**
- 65C816 can address 16 MB (24-bit)
- Bank $00 is 64KB
- Need more than 64KB for larger programs
- Banking enables access to more memory

**Banking concept**:
- 24-bit address = 16 MB total
- Divided into 256 banks of 64KB each
- Bank register (K) selects bank
- Address within bank (PC) selects location

**Bank switching**:
- Switch between banks
- Access different 64KB regions
- Enables larger programs
- More flexible memory use

### 2. Expanding RAM

**Current limitation**:
- Prototype likely has 32-64KB RAM
- Limited for larger programs
- Restricts program complexity

**Expansion goal**:
- 128KB or 512KB RAM
- Multiple banks accessible
- Room for larger programs
- More realistic system

**Expansion methods**:
- Multiple SRAM chips
- Single large SRAM with banking
- Bank register for selection
- Address decoding for banks

### 3. Bank Register Implementation

**65C816 bank registers**:
- Data Bank Register (DBR)
- Program Bank Register (K)
- Can access different banks
- Enables cross-bank operations

**Manual bank switching**:
- I/O register controls bank
- Higher address bits select bank
- Chip select generation
- Bank register latch

**Example**:
- Bank register at I/O address
- Writing to register selects bank
- Address decoding uses bank bits
- Memory access uses selected bank

### 4. Memory Map with Banking

**Example memory map**:
```
Bank $00:
  0x0000 - 0x7FFF: RAM (32KB)
  0x8000 - 0xFFFF: ROM (32KB)

Bank $01:
  0x0000 - 0x7FFF: RAM (32KB)
  0x8000 - 0xFFFF: RAM (32KB)

Bank $02:
  0x0000 - 0xFFFF: RAM (64KB)
...
```

**Design considerations**:
- Which banks for RAM?
- Which banks for ROM?
- I/O space allocation
- Room for expansion

### 5. Address Decoding for Banking

**Decoding requirements**:
- Select bank
- Select device within bank
- Handle 24-bit addressing
- Support bank switching

**Implementation**:
- Bank register selects bank
- Higher address bits select device
- Lower address bits select location
- Chip select generation

**Example**:
- A23-A16: Bank selection
- A15: RAM (0) vs ROM/I/O (1)
- A14-A0: Location within device

### 6. Testing Memory Banking

**Test procedures**:
- Write to different banks
- Read back and verify
- Switch banks
- Verify bank isolation
- Test cross-bank access

**Verification**:
- Can access all banks
- Banks are isolated
- Bank switching works
- No conflicts

### 7. Banking Analogy to SAP-1

**SAP-1 bank register proposal**:
- Similar concept proposed for SAP-1
- 8-bit register to page through RAM
- Same idea, different scale
- Shows continuity of concepts

**65C816 banking**:
- Built-in support
- More sophisticated
- Hardware support
- Software control

### 8. Practical Banking Considerations

**Bank selection**:
- Software-controlled
- I/O register
- Can be changed dynamically
- Enables flexible memory use

**Bank organization**:
- Bank $00: System (zero-page, stack)
- Bank $01+: Application memory
- ROM in high banks
- I/O in specific banks

## Mathematical Foundations

### Address Space

**24-bit address**: 2^24 = 16,777,216 bytes = 16 MB
- 256 banks of 64KB each
- Bank register selects bank
- PC selects location within bank

### Memory Sizing

**128KB RAM**: 2 banks of 64KB
**512KB RAM**: 8 banks of 64KB
**Total**: Multiple banks accessible

## Common Misconceptions

1. **"Banking is complex"**
   - Clarify: Simple bank register
   - Show basic implementation

2. **"Need all 16 MB"**
   - Clarify: Start with few banks
   - Show practical limits

3. **"Banking is automatic"**
   - Clarify: Software-controlled
   - Show bank register usage

## Connections to Term 2

- **Prototype**: Expands prototype memory
- **System Design**: Uses design knowledge
- **Address Decoding**: Extends decoding

## Connections to Weeks 5-12

- **I/O Integration**: Banking supports I/O
- **System Expansion**: Part of overall expansion
- **Year 5**: Foundation for PCB design

## Next Steps

After implementing banking, students will:
- Integrate I/O subsystems (Weeks 5-8)
- Research graphics/sound (Weeks 9-12)
- Prepare for Year 5

---

*Memory banking enables larger programs and prepares for complete systems*
