# Year 4 Book-Based Exercises

## Overview

This document provides book-based exercises that directly use examples from **Malvino & Brown, Digital Computer Electronics** to improve alignment and make the book the primary reference for Year 4.

**Purpose**: Students actively use book examples, translating and comparing them to 65C816 implementation, making the book essential to learning.

---

## Term 1 Exercises

### Weeks 1-3: SAP-1 Improvements

**Exercise 1: SAP-1 Schematic Comparison**
- **Source**: Malvino & Brown, Chapter 10-7 (SAP-1 Schematic Diagram)
- **Task**: 
  1. Compare your SAP-1 implementation to the book's schematic
  2. Identify any differences in component connections
  3. Document which differences are intentional improvements vs. errors
  4. Reference book's design principles when planning improvements

**Exercise 2: SAP-1 Limitations Analysis**
- **Source**: Malvino & Brown, Chapter 10 (SAP-1 sections)
- **Task**:
  1. Review book's SAP-1 description
  2. List limitations mentioned in the book
  3. Identify additional limitations you've discovered
  4. Prioritize improvements based on book's design principles

---

### Weeks 4-6: Expanded Instruction Set

**Exercise 3: SAP-2 Register Instructions Translation**
- **Source**: Malvino & Brown, Chapter 11-4 (SAP-2 Register Instructions)
- **Task**:
  1. Study SAP-2 register instructions from book (MOV, ADD/SUB with registers, INR/DCR)
  2. Design similar instructions for enhanced SAP-1
  3. Write microcode for new register instructions
  4. Compare your design to SAP-2's approach (from book)

**Exercise 4: SAP-2 Logic Instructions Translation**
- **Source**: Malvino & Brown, Chapter 11-6 (SAP-2 Logic Instructions), Example 11-X
- **Task**:
  1. Study SAP-2 logic instruction example from book (CMA, ANA, ORA, XRA)
  2. Translate the example to enhanced SAP-1 microcode
  3. Implement one logic instruction (e.g., AND)
  4. Test and verify against book's expected behavior

**Exercise 5: Instruction Set Comparison**
- **Source**: Malvino & Brown, Chapter 10-2 (SAP-1) vs Chapter 11-3, 11-4, 11-6 (SAP-2)
- **Task**:
  1. Compare SAP-1 instruction set (5 instructions) to SAP-2 (42 instructions)
  2. Categorize new SAP-2 instructions by type (from book)
  3. Identify which categories you're adding to enhanced SAP-1
  4. Explain why each category is useful (reference book's explanations)

---

### Weeks 7-9: Memory Expansion

**Exercise 6: Address Space Comparison**
- **Source**: Malvino & Brown, Chapter 11-2 (SAP-2 Architecture: 16-bit Addressing)
- **Task**:
  1. Study SAP-2 address space expansion from book: 4-bit (16 bytes) → 16-bit (64KB)
  2. Calculate address space for different widths: 4-bit, 8-bit, 16-bit, 24-bit
  3. Compare your enhanced SAP-1 expansion (4-bit → 8-bit) to SAP-2 expansion (4-bit → 16-bit)
  4. Understand the progression: SAP-1 → SAP-2 → 65C816

**Exercise 7: Bidirectional Bus Design**
- **Source**: Malvino & Brown, Chapter 11-1 (SAP-2 Bidirectional Registers)
- **Task**:
  1. Study SAP-2 bidirectional register design from book
  2. Understand why bidirectional buses are used (reduced wiring, simpler design)
  3. Apply bidirectional bus concepts to your enhanced SAP-1
  4. Compare your bus design to SAP-2's approach (from book)

---

## Term 2 Exercises

### Weeks 10-12: Introduction to 65C816

**Exercise 8: SAP-2 Jump Translation** ⭐ **KEY EXERCISE**
- **Source**: Malvino & Brown, Chapter 11-5 (SAP-2 Jump and Call Instructions), Example 11-3
- **Task**:
  1. Study SAP-2 program using JMP from book Example 11-3
  2. Identify the jump instruction and its purpose
  3. Translate the program to 65C816 using JMP
  4. Compare addressing modes: SAP-2 vs 65C816
  5. Test the translated program on 65C816

**Exercise 9: SAP-2 Subroutine Translation** ⭐ **KEY EXERCISE**
- **Source**: Malvino & Brown, Chapter 11-5 (SAP-2 Jump and Call Instructions), Example 11-4
- **Task**:
  1. Study SAP-2 program using CALL/RET from book Example 11-4
  2. Understand how CALL saves return address (from book explanation)
  3. Translate the program to 65C816 using JSR/RTS
  4. Compare: How does 65C816 save return address? (stack-based, automatic)
  5. Test the translated program on 65C816

**Exercise 10: Conditional Jump Comparison**
- **Source**: Malvino & Brown, Chapter 11-5 (SAP-2 Conditional Jumps: JM, JZ, JNZ)
- **Task**:
  1. Study SAP-2 conditional jumps from book (JM, JZ, JNZ)
  2. Compare to 65C816 branches (BEQ, BNE, BCC, BCS, etc.)
  3. Create translation table: SAP-2 → 65C816
  4. Translate SAP-2 conditional jump example to 65C816

**Exercise 11: Microprocessor Concepts Application**
- **Source**: Malvino & Brown, Chapter 13 (Intro to Microprocessors)
- **Task**:
  1. Study book's microprocessor examples (6502, 6800, 8080/8085, 8086/8088)
  2. Identify universal concepts (registers, addressing, instructions)
  3. Map these concepts to 65C816
  4. Create comparison table: Book CPU → 65C816 equivalent

---

### Weeks 13-15: System Design

**Exercise 12: System Architecture Comparison**
- **Source**: Malvino & Brown, Chapter 11-2 (SAP-2 Architecture) and Chapter 15 (System Overview)
- **Task**:
  1. Study SAP-2 system architecture from book (11-2)
  2. Study book's system design patterns (Chapter 15)
  3. Design 65C816 system using book's principles
  4. Compare your design to book's examples

**Exercise 13: Register Organization Study**
- **Source**: Malvino & Brown, Chapter 15 (System Overview: Register Organization)
- **Task**:
  1. Study book's register organization examples (6502, 6800, 8080/8085, 8086/8088)
  2. Compare to 65C816 register model
  3. Identify similarities and differences
  4. Explain why 65C816's register model is effective

---

### Weeks 16-18: Breadboard Prototype

**Exercise 14: Construction Reference**
- **Source**: Malvino & Brown, Chapter 10-7 (SAP-1 Schematic Diagram)
- **Task**:
  1. Reference SAP-1 schematic from book for construction techniques
  2. Apply book's organization principles to 65C816 prototype
  3. Compare your layout to book's schematic organization
  4. Document improvements based on book's design principles

---

### Weeks 19-21: Memory Banking

**Exercise 15: Address Space Progression**
- **Source**: Malvino & Brown, Chapter 11-2 (SAP-2: 16-bit Addressing) and Chapter 12-8 (SAP-3: Extended Registers)
- **Task**:
  1. Study address space progression from book: SAP-1 (4-bit) → SAP-2 (16-bit)
  2. Extend progression: SAP-2 (16-bit) → 65C816 (24-bit)
  3. Calculate memory banks for 65C816 (256 banks of 64KB each)
  4. Compare to book's memory organization concepts

**Exercise 16: Register Expansion Concepts**
- **Source**: Malvino & Brown, Chapter 12-8 (SAP-3: Extended Registers)
- **Task**:
  1. Study SAP-3 extended register concepts from book
  2. Compare to 65C816 8/16-bit register modes
  3. Understand why register expansion is useful (from book)
  4. Apply concepts to 65C816 memory banking

---

### Weeks 22-24: I/O Subsystems

**Exercise 17: I/O Method Comparison**
- **Source**: Malvino & Brown, Chapter 11-7 (SAP-2: IN/OUT Instructions)
- **Task**:
  1. Study SAP-2 port-based I/O from book (IN/OUT instructions)
  2. Understand 65C816 uses memory-mapped I/O (different method)
  3. Compare advantages/disadvantages of each method
  4. Translate SAP-2 I/O program to 65C816 memory-mapped I/O

**Exercise 18: Indirect Addressing for I/O**
- **Source**: Malvino & Brown, Chapter 12-9 (SAP-3: Indirect Addressing)
- **Task**:
  1. Study SAP-3 indirect addressing from book
  2. Use indirect addressing for 65C816 I/O register access
  3. Compare SAP-3 indirect addressing to 65C816 indirect modes
  4. Implement I/O routine using indirect addressing

---

### Weeks 25-27: Graphics/Sound Selection

**Exercise 19: Advanced System Features**
- **Source**: Malvino & Brown, Chapter 12-10 (SAP-3: Stack Instructions) and Chapter 12-11 (Other Advanced Instructions)
- **Task**:
  1. Review SAP-3 advanced features from book (stack, advanced instructions)
  2. Understand how advanced CPUs support complex I/O (graphics/sound)
  3. Plan graphics/sound integration using book's system design principles
  4. Reference book's progression (SAP-1 → SAP-2 → SAP-3) when planning 65C816 enhancements

---

## Assessment Questions (Book-Based)

### Term 1 Assessment

1. **From Chapter 11-4**: Explain how SAP-2 implements register-to-register operations. How would you implement similar operations in enhanced SAP-1?

2. **From Chapter 11-2**: Compare SAP-1 addressing (4-bit) to SAP-2 addressing (16-bit). What are the benefits of address space expansion? How does this relate to your enhanced SAP-1 expansion?

3. **From Chapter 11-6**: Study SAP-2 logic instructions from the book. Why are bitwise operations useful? Which logic instruction would be most valuable to add to enhanced SAP-1?

### Term 2 Assessment

1. **From Chapter 11-5**: Explain how SAP-2 implements subroutine calls. How does 65C816 implement the same concept? What are the similarities and differences?

2. **From Chapter 13**: Compare the book's microprocessor examples (6502, 6800, 8080/8085, 8086/8088) to 65C816. What universal concepts apply to all microprocessors?

3. **From Chapter 15**: Study the book's system design patterns. How did you apply these patterns to your 65C816 system design?

---

## Exercise Completion Checklist

### Term 1
- [ ] Exercise 1: SAP-1 Schematic Comparison
- [ ] Exercise 2: SAP-1 Limitations Analysis
- [ ] Exercise 3: SAP-2 Register Instructions Translation
- [ ] Exercise 4: SAP-2 Logic Instructions Translation
- [ ] Exercise 5: Instruction Set Comparison
- [ ] Exercise 6: Address Space Comparison
- [ ] Exercise 7: Bidirectional Bus Design

### Term 2
- [ ] Exercise 8: SAP-2 Jump Translation ⭐
- [ ] Exercise 9: SAP-2 Subroutine Translation ⭐
- [ ] Exercise 10: Conditional Jump Comparison
- [ ] Exercise 11: Microprocessor Concepts Application
- [ ] Exercise 12: System Architecture Comparison
- [ ] Exercise 13: Register Organization Study
- [ ] Exercise 14: Construction Reference
- [ ] Exercise 15: Address Space Progression
- [ ] Exercise 16: Register Expansion Concepts
- [ ] Exercise 17: I/O Method Comparison
- [ ] Exercise 18: Indirect Addressing for I/O
- [ ] Exercise 19: Advanced System Features

---

**Document Created**: 2025-12-15  
**Purpose**: Provide book-based exercises that directly use Malvino & Brown examples to improve Year 4 alignment
