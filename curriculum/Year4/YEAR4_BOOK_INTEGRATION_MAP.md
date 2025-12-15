# Year 4 Book Integration Map

## Overview

This document maps **Malvino & Brown, Digital Computer Electronics** chapters to Year 4 curriculum weeks, providing explicit week-by-week book integration to improve alignment from "Partial" to "Excellent".

**Purpose**: Make the book the **primary conceptual reference** for Year 4, with specific reading assignments and book-based exercises integrated into each week.

---

## Term 1: SAP-1 Enhancements (Weeks 1-9)

### Weeks 1-3: SAP-1 Improvements

**Primary Book Reference**: **Chapter 10 (SAP-1)** - Review and enhancement concepts

**Required Reading**:
- **Chapter 10-1**: SAP-1 Architecture (review)
- **Chapter 10-2**: Instruction Set (review)
- **Chapter 10-7**: SAP-1 Schematic Diagram (reference for improvements)

**Book Integration Activities**:
1. Review SAP-1 architecture from book
2. Identify limitations mentioned in book
3. Plan improvements based on book's design principles

**Book-Based Exercises**:
- Exercise: Compare your SAP-1 implementation to book's schematic
- Exercise: Identify which SAP-1 limitations the book discusses

---

### Weeks 4-6: Expanded Instruction Set

**Primary Book Reference**: **Chapter 11 (SAP-2)** - Enhanced instruction set concepts

**Required Reading**:
- **Chapter 11-3**: Memory-Reference Instructions (LDA, STA, MVI)
- **Chapter 11-4**: Register Instructions (MOV, ADD/SUB with registers)
- **Chapter 11-6**: Logic Instructions (CMA, ANA, ORA, XRA)

**Book Integration Activities**:
1. Read SAP-2 instruction set (11-3, 11-4, 11-6)
2. Compare SAP-1 instructions (5) to SAP-2 instructions (42)
3. Understand why more instructions are useful
4. Plan which instructions to add to enhanced SAP-1

**Book-Based Exercises**:
- Exercise: Study SAP-2 register instructions (11-4), design similar for SAP-1
- Exercise: Translate SAP-2 logic instruction example to enhanced SAP-1
- Exercise: Compare SAP-2 addressing modes to SAP-1 addressing

---

### Weeks 7-9: Memory Expansion and Harvard Architecture

**Primary Book Reference**: **Chapter 11 (SAP-2)** - Memory architecture concepts

**Required Reading**:
- **Chapter 11-1**: Bidirectional Registers (bus concepts)
- **Chapter 11-2**: Architecture (16-bit Addressing)
- **Chapter 9**: Memories (review from Year 2)

**Book Integration Activities**:
1. Read SAP-2 architecture (11-2) - 16-bit addressing expansion
2. Understand progression: SAP-1 (4-bit) → SAP-2 (16-bit) → 65C816 (24-bit)
3. Study bidirectional bus concepts (11-1)
4. Plan memory expansion for enhanced SAP-1

**Book-Based Exercises**:
- Exercise: Compare SAP-1 addressing (4-bit, 16 bytes) to SAP-2 (16-bit, 64KB)
- Exercise: Study SAP-2 bidirectional register design (11-1), apply to SAP-1 improvements
- Exercise: Calculate address space for different address bus widths (from book examples)

---

## Term 2: 16-bit Preparation (Weeks 10-27)

### Weeks 10-12: Introduction to 65C816 CPU

**Primary Book Reference**: **Chapter 11 (SAP-2)** and **Chapter 13 (Intro to Microprocessors)**

**Required Reading**:
- **Chapter 11-5**: Jump and Call Instructions ⭐ **KEY CONCEPT**
  - JMP (unconditional jump)
  - JM, JZ, JNZ (conditional jumps)
  - CALL/RET (subroutines)
- **Chapter 13-1 to 13-5**: Intro to Microprocessors
  - General microprocessor concepts
  - Register models
  - Addressing concepts
  - Instruction types

**Book Integration Activities**:
1. Read SAP-2 jump and call instructions (11-5) - understand subroutines
2. Read Chapter 13 - understand general microprocessor concepts
3. Compare SAP-2 jumps to 65C816 branches (JMP, BEQ, BNE, etc.)
4. Compare SAP-2 CALL/RET to 65C816 JSR/RTS
5. Study book's microprocessor examples, understand concepts apply to 65C816

**Book-Based Exercises**:
- Exercise: Translate SAP-2 program using JMP (from book Example 11-3) to 65C816
- Exercise: Translate SAP-2 program using CALL/RET (from book Example 11-4) to 65C816 using JSR/RTS
- Exercise: Compare SAP-2 conditional jumps (JM, JZ, JNZ) to 65C816 branches (BEQ, BNE, BCC, etc.)
- Exercise: Study book's register models (Chapter 13), compare to 65C816 registers

**Assessment Question**:
- From Chapter 11-5: Explain how SAP-2 implements subroutine calls. How does 65C816 implement the same concept?

---

### Weeks 13-15: 65C816 System Design

**Primary Book Reference**: **Chapter 11 (SAP-2)** and **Chapter 15 (System Overview)**

**Required Reading**:
- **Chapter 11-2**: Architecture (16-bit Addressing) - review for system design
- **Chapter 15-1 to 15-5**: System Overview
  - Microprocessor architecture patterns
  - Register organization
  - Memory models
  - System design concepts

**Book Integration Activities**:
1. Review SAP-2 architecture (11-2) - understand system design principles
2. Read Chapter 15 - understand general system architecture patterns
3. Compare book's system examples (6502, 6800, 8080/8085) to 65C816 system design
4. Apply book's system design concepts to 65C816 system

**Book-Based Exercises**:
- Exercise: Study SAP-2 system architecture (11-2), design similar structure for 65C816
- Exercise: Compare book's register organization examples (Chapter 15) to 65C816 register model
- Exercise: Study book's memory model examples, design 65C816 memory map

---

### Weeks 16-18: Breadboard Prototype Construction

**Primary Book Reference**: **Chapter 10 (SAP-1)** and **Chapter 11 (SAP-2)**

**Required Reading**:
- **Chapter 10-7**: SAP-1 Schematic Diagram (reference for construction)
- **Chapter 11-1**: Bidirectional Registers (bus design)
- **Chapter 11-2**: Architecture (system integration)

**Book Integration Activities**:
1. Reference SAP-1 schematic (10-7) for construction techniques
2. Study SAP-2 bidirectional bus design (11-1)
3. Apply book's construction principles to 65C816 prototype

**Book-Based Exercises**:
- Exercise: Compare your 65C816 prototype layout to SAP-1 schematic organization
- Exercise: Study SAP-2 bus design (11-1), verify your 65C816 bus implementation

---

### Weeks 19-21: Memory Banking

**Primary Book Reference**: **Chapter 11 (SAP-2)** and **Chapter 12 (SAP-3)**

**Required Reading**:
- **Chapter 11-2**: Architecture (16-bit Addressing) - address space concepts
- **Chapter 12-8**: Extended Registers - register expansion concepts
- **Chapter 9**: Memories (review) - memory organization

**Book Integration Activities**:
1. Study SAP-2 address space expansion (11-2): 4-bit → 16-bit
2. Understand 65C816 expansion: 16-bit → 24-bit (same concept, larger scale)
3. Study SAP-3 extended registers (12-8) - understand register expansion
4. Apply memory banking concepts to 65C816

**Book-Based Exercises**:
- Exercise: Compare SAP-2 address space (16-bit, 64KB) to 65C816 (24-bit, 16MB)
- Exercise: Study SAP-3 extended register concepts (12-8), compare to 65C816 8/16-bit modes
- Exercise: Calculate memory banks for different address bus configurations (from book progression)

---

### Weeks 22-24: I/O Subsystems

**Primary Book Reference**: **Chapter 11 (SAP-2)** and **Chapter 12 (SAP-3)**

**Required Reading**:
- **Chapter 11-7**: Other Instructions (IN/OUT operations)
- **Chapter 12-9**: Indirect Addressing - I/O addressing concepts

**Book Integration Activities**:
1. Study SAP-2 IN/OUT instructions (11-7) - port-based I/O
2. Understand 65C816 uses memory-mapped I/O (different method, same concept)
3. Study SAP-3 indirect addressing (12-9) - useful for I/O operations
4. Compare book's I/O methods to 65C816 memory-mapped I/O

**Book-Based Exercises**:
- Exercise: Compare SAP-2 port-based I/O (11-7) to 65C816 memory-mapped I/O
- Exercise: Study SAP-3 indirect addressing (12-9), use for 65C816 I/O register access
- Exercise: Translate SAP-2 I/O program to 65C816 memory-mapped I/O

---

### Weeks 25-27: Graphics/Sound Selection

**Primary Book Reference**: **Chapter 12 (SAP-3)** - Advanced concepts

**Required Reading**:
- **Chapter 12-10**: Stack Instructions - system-level concepts
- **Chapter 12-11**: Other Advanced Instructions - system capabilities

**Book Integration Activities**:
1. Review SAP-3 advanced features (12-10, 12-11)
2. Understand how advanced CPUs support complex I/O (graphics/sound)
3. Plan graphics/sound integration using book's system design principles

**Book-Based Exercises**:
- Exercise: Study SAP-3 stack operations (12-10), understand system-level programming
- Exercise: Review book's progression (SAP-1 → SAP-2 → SAP-3), plan 65C816 enhancements

---

## Book Study Guide for Year 4

### Term 1 Focus: SAP-2 Concepts (Chapter 11)

**Week 1-3**: Review SAP-1 (Chapter 10)
**Week 4-6**: SAP-2 Instructions (11-3, 11-4, 11-6)
**Week 7-9**: SAP-2 Architecture (11-1, 11-2)

### Term 2 Focus: SAP-2/SAP-3 + Microprocessor Concepts

**Week 10-12**: SAP-2 Jumps/Calls (11-5) + Microprocessor Intro (13)
**Week 13-15**: SAP-2 Architecture (11-2) + System Overview (15)
**Week 16-18**: SAP-1/SAP-2 Construction (10-7, 11-1, 11-2)
**Week 19-21**: SAP-2/SAP-3 Memory (11-2, 12-8)
**Week 22-24**: SAP-2/SAP-3 I/O (11-7, 12-9)
**Week 25-27**: SAP-3 Advanced (12-10, 12-11)

---

## Integration Checklist

- [x] Map SAP-2 sections to Term 1 weeks
- [x] Map SAP-2/SAP-3 sections to Term 2 weeks
- [x] Map Part 3 chapters to Term 2 weeks
- [x] Create week-by-week reading schedule
- [ ] Add required reading to theory materials
- [ ] Add required reading to teaching guides
- [ ] Create book-based exercises
- [ ] Add book integration activities

---

**Document Created**: 2025-12-15  
**Purpose**: Explicit week-by-week mapping of Malvino & Brown book to Year 4 curriculum for improved alignment
