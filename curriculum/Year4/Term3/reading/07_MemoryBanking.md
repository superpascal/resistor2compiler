# Chapter 7: Memory and Banking on 65C816

## Introduction

Memory banking enables access to more than 64KB of memory. This chapter explains how to expand memory and implement banking on the 65C816.

## Memory Banking

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

## Expanding RAM

**Current limitation**:
- Prototype likely has 32-64KB RAM
- Limited for larger programs
- Restricts program complexity

**Expansion goal**:
- 128KB or 512KB RAM
- Multiple banks accessible
- Room for larger programs
- More realistic system

## Bank Register Implementation

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

## Memory Map with Banking

**Example memory map**:
```
Bank $00:
  0x0000 - 0x7FFF: RAM (32KB)
  0x8000 - 0xFFFF: ROM (32KB)

Bank $01:
  0x0000 - 0xFFFF: RAM (64KB)
...
```

## Testing Memory Banking

**Test procedures**:
- Write to different banks
- Read back and verify
- Switch banks
- Verify bank isolation
- Test cross-bank access

## Practice Questions

1. Why use memory banking?
2. How does banking work?
3. How do we implement bank switching?
4. How do we test banking?
5. What are the benefits?

## Key Takeaways

- Banking enables >64KB memory
- Bank register selects bank
- Address decoding uses bank
- Test thoroughly
- Foundation for larger systems

---

*Memory banking enables larger programs and prepares for complete systems*
