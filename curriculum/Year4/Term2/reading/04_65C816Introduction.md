# Chapter 4: Introduction to 65C816 CPU

## Introduction

The 65C816 is a 16-bit microprocessor that represents the evolution from simple CPUs like SAP-1 to modern microprocessors. This chapter introduces the 65C816 architecture.

## The 65C816 Microprocessor

**What is the 65C816?**
- 16-bit microprocessor from Western Design Center
- Enhanced version of 6502
- 24-bit addressing (16 MB)
- 16-bit data operations
- Used in Apple IIGS, Super Nintendo

**Key features**:
- 16-bit ALU operations
- 24-bit address space
- Multiple addressing modes
- Stack pointer
- Interrupts
- Emulation and native modes

## Architecture Comparison

**SAP-1 vs 65C816**:

| Component | SAP-1 | 65C816 |
|-----------|-------|--------|
| Data width | 4-bit | 16-bit |
| Address width | 4-bit (8-bit expanded) | 24-bit |
| Registers | A, B | A, X, Y, SP, P |
| Program Counter | 4-bit (8-bit expanded) | 16-bit + bank |
| Flags | C, Z | P register (8 flags) |
| Memory | 16 bytes (256 expanded) | Up to 16 MB |
| Instructions | ~6-8 | 256+ |
| Addressing modes | Direct | Many |

## 65C816 Registers

**Accumulator (A)**:
- 16-bit (can use as 8-bit)
- Primary working register
- Used for arithmetic

**Index Registers (X, Y)**:
- 16-bit (can use as 8-bit)
- Used for indexing
- Used for counting

**Stack Pointer (SP)**:
- 16-bit
- Points to stack
- Auto-increment/decrement

**Program Counter (PC)**:
- 16-bit
- Extended with bank register (K)
- 24-bit effective address

**Status Register (P)**:
- 8 flags
- C, Z, I, D, X, M, V, N

## 24-bit Addressing

**Address space**:
- 24-bit address = 16 MB
- Divided into 256 banks of 64KB each
- Bank register (K) selects bank
- PC + K = 24-bit address

## Addressing Modes

**65C816 addressing modes**:
- **Immediate**: Value in instruction
- **Direct**: Address in instruction
- **Absolute**: Full address
- **Indexed**: Address + index register
- **Indirect**: Address points to address
- **Stack**: Stack-relative
- Many more...

## Practice Questions

1. What is the 65C816?
2. How does it compare to SAP-1?
3. What are the key registers?
4. How does 24-bit addressing work?
5. What are addressing modes?

## Key Takeaways

- 65C816 is 16-bit CPU with 24-bit addressing
- Same concepts as SAP-1, more complex
- More registers and features
- More addressing modes
- Foundation for modern systems

---

*65C816 introduces modern CPU architecture*
