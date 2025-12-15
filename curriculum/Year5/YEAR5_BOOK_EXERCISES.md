# Year 5 Book-Based Exercises

## Overview

This document provides book-based exercises that directly use examples from **Malvino & Brown, Digital Computer Electronics, Part 3 (Chapters 13-23)** to improve alignment and make the book the primary reference for Year 5 assembly programming.

**Purpose**: Students actively use book examples, translating them to 65C816 implementation, making the book essential to learning assembly programming.

---

## Term 1 Exercises

### Weeks 1-4: Monitor Program

**Exercise 1: Microprocessor Concepts Application**
- **Source**: Malvino & Brown, Chapter 13 (Intro to Microprocessors)
- **Task**:
  1. Study book's microprocessor examples (6502, 6800, 8080/8085, 8086/8088)
  2. Identify universal concepts (registers, addressing, instructions)
  3. Map these concepts to 65C816 for monitor design
  4. Design monitor register display using book's register models

**Exercise 2: Assembly Program Structure**
- **Source**: Malvino & Brown, Chapter 14 (Programming & Languages)
- **Task**:
  1. Study book's assembly program structure examples
  2. Apply structure to monitor program implementation
  3. Compare book's program organization to monitor code organization
  4. Use book's concepts for monitor command parsing

---

### Weeks 5-8: Assembler and Toolchain ⭐ **PRIMARY ASSEMBLY PROGRAMMING**

**Exercise 3: Data Transfer Translation** (Week 5)
- **Source**: Malvino & Brown, Chapter 16 (Data Transfer Instructions), Example 16-X
- **Task**:
  1. Study book's data transfer example (e.g., 6502 LDA, 8080 MOV)
  2. Identify the data transfer concept (load, store, move)
  3. Translate to 65C816 using LDA, STA, TAX, etc.
  4. Compare addressing modes: book example vs 65C816
  5. Test translated program on 65C816

**Exercise 4: Arithmetic Translation** (Week 6)
- **Source**: Malvino & Brown, Chapter 17 (Arithmetic Instructions), Example 17-X
- **Task**:
  1. Study book's arithmetic example (e.g., 6502 ADC, 8080 ADD)
  2. Identify the arithmetic operation (add, subtract, compare)
  3. Translate to 65C816 using ADC, SBC, CMP
  4. Compare carry flag handling: book example vs 65C816
  5. Test translated program on 65C816

**Exercise 5: Logic Translation** (Week 7)
- **Source**: Malvino & Brown, Chapter 18 (Logic Instructions), Example 18-X
- **Task**:
  1. Study book's logic example (e.g., 6502 AND, 8080 ANA)
  2. Identify the logic operation (AND, OR, XOR)
  3. Translate to 65C816 using AND, ORA, EOR
  4. Compare bitwise operations: book example vs 65C816
  5. Test translated program on 65C816

**Exercise 6: Branch Translation** (Week 7)
- **Source**: Malvino & Brown, Chapter 19 (Branch Instructions), Example 19-X
- **Task**:
  1. Study book's branch example (e.g., 6502 BEQ, 8080 JZ)
  2. Identify the branch condition (equal, not equal, carry, etc.)
  3. Translate to 65C816 using BEQ, BNE, BCC, etc.
  4. Compare conditional branch implementation: book example vs 65C816
  5. Test translated program on 65C816

**Exercise 7: Stack Translation** (Week 8)
- **Source**: Malvino & Brown, Chapter 20 (Stack Instructions), Example 20-X
- **Task**:
  1. Study book's stack example (e.g., 6502 PHA, 8080 PUSH)
  2. Identify the stack operation (push, pull)
  3. Translate to 65C816 using PHA, PLA, PHX, PLX
  4. Compare stack implementation: book example vs 65C816
  5. Test translated program on 65C816

**Exercise 8: Control Instruction Translation** (Week 8)
- **Source**: Malvino & Brown, Chapter 22 (CPU Control Instructions)
- **Task**:
  1. Study book's control examples (NOP, HLT, interrupts)
  2. Identify the control operation
  3. Translate to 65C816 using NOP, BRK, WAI, STP
  4. Compare control implementation: book example vs 65C816

**Exercise 9: Complete Program Translation**
- **Source**: Malvino & Brown, Chapter 16-23 (any complete program example)
- **Task**:
  1. Study a complete program from book (any CPU)
  2. Identify all instruction categories used
  3. Translate entire program to 65C816
  4. Test and verify translated program works correctly
  5. Compare program structure: book example vs 65C816 version

**Exercise 10: Addressing Mode Comparison**
- **Source**: Malvino & Brown, Chapters 16-23 (addressing mode examples)
- **Task**:
  1. Study addressing modes from book examples (6502, 6800, 8080/8085, 8086/8088)
  2. Compare to 65C816 addressing modes
  3. Create comparison table: Book CPU → 65C816 equivalent
  4. Identify which 65C816 addressing modes cover book's examples
  5. Document addressing mode translation patterns

---

### Weeks 9-12: Pascal Runtime

**Exercise 11: Stack-Based Calling Convention**
- **Source**: Malvino & Brown, Chapter 20 (Stack Instructions)
- **Task**:
  1. Study book's stack operations (push, pull, stack pointer usage)
  2. Design stack-based calling convention for Pascal runtime
  3. Implement parameter passing using stack (from book concepts)
  4. Implement return value handling using stack
  5. Compare to book's stack usage examples

**Exercise 12: Parameter Passing Implementation**
- **Source**: Malvino & Brown, Chapter 16 (Data Transfer Instructions)
- **Task**:
  1. Study book's data transfer concepts (load, store, move)
  2. Implement parameter passing using data transfer operations
  3. Use book's addressing mode concepts for parameter access
  4. Compare parameter passing methods: register vs stack (from book examples)

**Exercise 13: Runtime Arithmetic**
- **Source**: Malvino & Brown, Chapter 17 (Arithmetic Instructions)
- **Task**:
  1. Study book's arithmetic operations (add, subtract, compare)
  2. Implement runtime arithmetic functions using book's concepts
  3. Handle overflow/underflow using book's flag concepts
  4. Compare arithmetic implementation: book examples vs runtime

---

## Term 2 Exercises

### Weeks 13-16: Compiler Implementation

**Exercise 14: Instruction Category Mapping**
- **Source**: Malvino & Brown, Chapters 16-23 (Instruction Sets)
- **Task**:
  1. Study book's instruction categories (data transfer, arithmetic, logic, branches, stack, control)
  2. Design code generator instruction selector using book's categories
  3. Map high-level operations to book's instruction categories
  4. Generate assembly code using book's instruction patterns

**Exercise 15: Code Generation for Expressions**
- **Source**: Malvino & Brown, Chapter 17 (Arithmetic Instructions)
- **Task**:
  1. Study book's arithmetic examples
  2. Generate assembly code for arithmetic expressions using book's patterns
  3. Handle operator precedence using book's instruction sequences
  4. Compare generated code to book's arithmetic examples

**Exercise 16: Code Generation for Control Flow**
- **Source**: Malvino & Brown, Chapter 19 (Branch Instructions)
- **Task**:
  1. Study book's branch examples (conditional jumps, loops)
  2. Generate assembly code for if/while statements using book's patterns
  3. Handle condition evaluation using book's compare/branch sequences
  4. Compare generated code to book's control flow examples

---

### Weeks 17-20: Pascal Program Development

**Exercise 17: Understanding Generated Code**
- **Source**: Malvino & Brown, Chapters 16-23 (Instruction Sets)
- **Task**:
  1. Compile a Pascal program to assembly
  2. Review generated assembly using book's instruction categories
  3. Identify which book chapters cover each generated instruction type
  4. Debug generated code using book's concepts
  5. Optimize generated code using book's examples

---

### Weeks 21-24: OS Extensions

**Exercise 18: System-Level Programming**
- **Source**: Malvino & Brown, Chapter 14 (Programming & Languages) and Chapters 16-23
- **Task**:
  1. Study book's system programming concepts (Chapter 14)
  2. Apply book's instruction concepts to OS implementation
  3. Reference book examples for OS-level operations
  4. Compare OS implementation to book's system programming examples

---

## Assessment Questions (Book-Based)

### Term 1 Assessment

1. **From Chapter 16**: Compare the book's data transfer instruction examples (6502, 8080, 8086) to 65C816 data transfer instructions. What are the similarities and differences?

2. **From Chapter 19**: Explain how conditional branches work in the book's examples. How does 65C816 implement conditional branches? What are the similarities and differences?

3. **From Chapter 20**: Study the book's stack operation examples. How does 65C816 implement stack operations? How would you use stack operations for subroutine calls?

4. **From Chapters 16-23**: Translate a complete program from the book (any CPU) to 65C816. Explain your translation choices and how you mapped book concepts to 65C816.

### Term 2 Assessment

1. **From Chapters 16-23**: How would you use the book's instruction categories when designing a code generator? Give examples of mapping high-level operations to book's instruction categories.

2. **From Chapter 17**: How would you generate assembly code for arithmetic expressions using the book's arithmetic instruction examples? Show an example.

3. **From Chapter 19**: How would you generate assembly code for control flow (if/while) using the book's branch instruction examples? Show an example.

---

## Exercise Completion Checklist

### Term 1
- [ ] Exercise 1: Microprocessor Concepts Application
- [ ] Exercise 2: Assembly Program Structure
- [ ] Exercise 3: Data Transfer Translation (Week 5)
- [ ] Exercise 4: Arithmetic Translation (Week 6)
- [ ] Exercise 5: Logic Translation (Week 7)
- [ ] Exercise 6: Branch Translation (Week 7)
- [ ] Exercise 7: Stack Translation (Week 8)
- [ ] Exercise 8: Control Instruction Translation (Week 8)
- [ ] Exercise 9: Complete Program Translation
- [ ] Exercise 10: Addressing Mode Comparison
- [ ] Exercise 11: Stack-Based Calling Convention
- [ ] Exercise 12: Parameter Passing Implementation
- [ ] Exercise 13: Runtime Arithmetic

### Term 2
- [ ] Exercise 14: Instruction Category Mapping
- [ ] Exercise 15: Code Generation for Expressions
- [ ] Exercise 16: Code Generation for Control Flow
- [ ] Exercise 17: Understanding Generated Code
- [ ] Exercise 18: System-Level Programming

---

**Document Created**: 2025-12-15  
**Purpose**: Provide book-based exercises that directly use Malvino & Brown Part 3 examples to improve Year 5 alignment
