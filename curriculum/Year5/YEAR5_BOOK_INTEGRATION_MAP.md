# Year 5 Book Integration Map

## Overview

This document maps **Malvino & Brown, Digital Computer Electronics, Part 3 (Chapters 13-23)** to Year 5 curriculum weeks, providing explicit week-by-week book integration to improve alignment from "Partial" to "Excellent".

**Purpose**: Make the book the **primary assembly programming reference** for Year 5, with specific reading assignments and book-based exercises integrated into each week.

---

## Term 1: Software Stack Development (Weeks 1-12)

### Weeks 1-4: Monitor Program

**Primary Book Reference**: **Chapter 13 (Intro to Microprocessors)** and **Chapter 14 (Programming & Languages)**

**Required Reading**:
- **Chapter 13-1 to 13-5**: Intro to Microprocessors
  - General microprocessor concepts
  - Register models
  - Addressing concepts
  - Instruction types
  - **Purpose**: Understand system-level programming concepts for monitor development
- **Chapter 14-1 to 14-5**: Programming & Languages
  - Assembly language concepts
  - Instruction categories
  - Program structure
  - Addressing modes (general)
  - **Purpose**: Understand assembly language structure for monitor implementation

**Book Integration Activities**:
1. Read Chapter 13 - understand microprocessor concepts for system programming
2. Read Chapter 14 - understand assembly language structure
3. Study book's assembly examples - apply to monitor program implementation
4. Compare book's system programming concepts to monitor requirements

**Book-Based Exercises**:
- Exercise: Study book's microprocessor register models (Chapter 13), design monitor register display
- Exercise: Study book's assembly program structure (Chapter 14), structure monitor code
- Exercise: Compare book's addressing mode examples to 65C816 addressing modes used in monitor

---

### Weeks 5-8: Assembler and Toolchain ⭐ **PRIMARY ASSEMBLY PROGRAMMING**

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - Complete instruction category coverage

**Required Reading** (Week-by-Week):

**Week 5: Data Transfer Instructions**
- **Chapter 16**: Data Transfer Instructions
  - Load, Store, Move operations
  - Examples from 6502, 6800, 8080/8085, 8086/8088
  - **Purpose**: Understand data transfer concepts, translate to 65C816

**Week 6: Arithmetic Instructions**
- **Chapter 17**: Arithmetic Instructions
  - Add, Subtract, Compare operations
  - Examples from multiple CPUs
  - **Purpose**: Understand arithmetic operations, translate to 65C816

**Week 7: Logic and Branch Instructions**
- **Chapter 18**: Logic Instructions (AND, OR, XOR)
- **Chapter 19**: Branch Instructions (Jumps, Conditional branches)
  - Examples from multiple CPUs
  - **Purpose**: Understand logic and program flow control, translate to 65C816

**Week 8: Stack and Control Instructions**
- **Chapter 20**: Stack Instructions (Push, Pull)
- **Chapter 22**: CPU Control Instructions (NOP, HLT, interrupts)
  - Examples from multiple CPUs
  - **Purpose**: Understand stack operations and system control, translate to 65C816

**Book Integration Activities**:
1. **Week 5**: Read Chapter 16, study data transfer examples, translate to 65C816
2. **Week 6**: Read Chapter 17, study arithmetic examples, translate to 65C816
3. **Week 7**: Read Chapters 18-19, study logic and branch examples, translate to 65C816
4. **Week 8**: Read Chapters 20, 22, study stack and control examples, translate to 65C816

**Book-Based Exercises**:
- Exercise: Translate book's data transfer examples (Chapter 16) to 65C816
- Exercise: Translate book's arithmetic examples (Chapter 17) to 65C816
- Exercise: Translate book's logic examples (Chapter 18) to 65C816
- Exercise: Translate book's branch examples (Chapter 19) to 65C816
- Exercise: Translate book's stack examples (Chapter 20) to 65C816
- Exercise: Compare book's addressing modes to 65C816 addressing modes

**Assessment Questions**:
- From Chapter 16: Compare the book's data transfer instruction examples (6502, 8080, 8086) to 65C816 data transfer instructions. What are the similarities and differences?
- From Chapter 19: Explain how conditional branches work in the book's examples. How does 65C816 implement conditional branches?

---

### Weeks 9-12: Pascal Runtime

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - For runtime library implementation

**Required Reading**:
- **Chapter 16**: Data Transfer Instructions (for parameter passing)
- **Chapter 20**: Stack Instructions (for stack-based calling conventions)
- **Chapter 19**: Branch Instructions (for control flow in runtime)
- **Chapter 17**: Arithmetic Instructions (for runtime arithmetic operations)

**Book Integration Activities**:
1. Study book's stack operations (Chapter 20) - apply to stack-based calling conventions
2. Study book's data transfer (Chapter 16) - apply to parameter passing
3. Study book's arithmetic (Chapter 17) - apply to runtime arithmetic
4. Study book's branches (Chapter 19) - apply to runtime control flow

**Book-Based Exercises**:
- Exercise: Design stack-based calling convention using book's stack concepts (Chapter 20)
- Exercise: Implement parameter passing using book's data transfer concepts (Chapter 16)
- Exercise: Implement runtime arithmetic using book's arithmetic concepts (Chapter 17)

---

## Term 2: High-Level Language & OS (Weeks 13-24)

### Weeks 13-16: SuperPascal Compiler Implementation

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - For code generation

**Required Reading**:
- **Chapters 16-23**: Instruction Sets (review for code generation)
  - Use book's instruction categories when designing code generator
  - Reference book examples when generating assembly code
  - **Purpose**: Understand instruction categories for code generation

**Book Integration Activities**:
1. Review instruction categories from book (Chapters 16-23)
2. Design code generator using book's instruction categories
3. Reference book examples when generating assembly code
4. Use book's addressing mode concepts for code generation

**Book-Based Exercises**:
- Exercise: Design code generator instruction selector using book's instruction categories
- Exercise: Generate assembly code for simple expressions using book's arithmetic examples
- Exercise: Generate assembly code for control flow using book's branch examples

---

### Weeks 17-20: Pascal Program Development

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - For understanding generated code

**Required Reading**:
- **Chapters 16-23**: Instruction Sets (supplementary reference)
  - Understand generated assembly code
  - Debug generated code using book's concepts
  - **Purpose**: Understand how high-level code compiles to assembly

**Book Integration Activities**:
1. Review generated assembly code using book's instruction categories
2. Debug generated code using book's concepts
3. Optimize generated code using book's examples

---

### Weeks 21-24: Operating System Extensions

**Primary Book Reference**: **Chapter 14 (Programming & Languages)** and **Chapters 16-23 (Instruction Sets)**

**Required Reading**:
- **Chapter 14**: Programming & Languages (system-level concepts)
- **Chapters 16-23**: Instruction Sets (for OS implementation)
  - **Purpose**: Understand system-level programming concepts

**Book Integration Activities**:
1. Study book's system programming concepts (Chapter 14)
2. Apply book's instruction concepts to OS implementation
3. Reference book examples for OS-level operations

---

## Book Study Guide for Year 5

### Term 1 Focus: Assembly Programming (Chapters 13-23)

**Week 1-4**: Microprocessor and Assembly Concepts (13, 14)
**Week 5**: Data Transfer Instructions (16)
**Week 6**: Arithmetic Instructions (17)
**Week 7**: Logic and Branch Instructions (18, 19)
**Week 8**: Stack and Control Instructions (20, 22)
**Week 9-12**: Instruction Sets Review (16-23) for Runtime

### Term 2 Focus: Code Generation and System Programming

**Week 13-16**: Instruction Sets (16-23) for Code Generation
**Week 17-20**: Instruction Sets (16-23) for Understanding Generated Code
**Week 21-24**: Programming & Languages (14) + Instruction Sets (16-23) for OS

---

## Integration Checklist

- [x] Map Part 3 chapters to Term 1 weeks
- [x] Map Part 3 chapters to Term 2 weeks
- [x] Create week-by-week reading schedule
- [ ] Add required reading to theory materials
- [ ] Add required reading to teaching guides
- [ ] Create book-based exercises
- [ ] Add book integration activities

---

**Document Created**: 2025-12-15  
**Purpose**: Explicit week-by-week mapping of Malvino & Brown Part 3 to Year 5 curriculum for improved alignment
