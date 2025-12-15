# Year 5 Book Study Guide

## Overview

This study guide helps students use **Malvino & Brown, Digital Computer Electronics, Part 3 (Chapters 13-23)** as the **primary assembly programming reference** for Year 5. The book provides essential concepts for understanding assembly language programming and instruction sets.

**Purpose**: Make the book actively used throughout Year 5, not just mentioned.

---

## Term 1: Software Stack Development (Weeks 1-12)

### Weeks 1-4: Monitor Program

**Primary Book Reference**: **Chapter 13** and **Chapter 14**

**What to Read**:
- Chapter 13-1 to 13-5: Intro to Microprocessors
  - General microprocessor concepts
  - Register models
  - Addressing concepts
  - Instruction types
- Chapter 14-1 to 14-5: Programming & Languages
  - Assembly language concepts
  - Instruction categories
  - Program structure
  - Addressing modes (general)

**Key Concepts from Book**:
- System-level programming concepts
- Assembly language structure
- Register models for system programming
- Program organization

**How to Use**:
1. Read Chapter 13 - understand microprocessor concepts for monitor
2. Read Chapter 14 - understand assembly structure for monitor code
3. Study book's assembly examples - apply to monitor implementation
4. Compare book's system programming concepts to monitor requirements

**Study Questions**:
- What are the universal microprocessor concepts? (from Chapter 13)
- How is assembly language structured? (from Chapter 14)
- How do you organize system-level code? (from book examples)

---

### Weeks 5-8: Assembler and Toolchain ⭐ **PRIMARY ASSEMBLY PROGRAMMING**

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)**

#### Week 5: Data Transfer Instructions

**What to Read**:
- Chapter 16: Data Transfer Instructions
  - Load, Store, Move operations
  - Examples from 6502, 6800, 8080/8085, 8086/8088

**Key Concepts from Book**:
- Data transfer operations (load, store, move)
- Different addressing modes for data transfer
- Register-to-register vs memory operations

**How to Use**:
1. Read Chapter 16 - understand data transfer concepts
2. Study book examples (different CPUs)
3. Translate examples to 65C816 using bridging guide
4. Practice writing 65C816 data transfer programs

**Study Questions**:
- What are the different types of data transfer? (from Chapter 16)
- How do addressing modes affect data transfer? (from book examples)
- How do you translate book examples to 65C816? (use bridging guide)

---

#### Week 6: Arithmetic Instructions

**What to Read**:
- Chapter 17: Arithmetic Instructions
  - Add, Subtract, Compare operations
  - Examples from multiple CPUs

**Key Concepts from Book**:
- Arithmetic operations (add, subtract, compare)
- Carry flag handling
- Overflow detection
- Comparison operations

**How to Use**:
1. Read Chapter 17 - understand arithmetic concepts
2. Study book examples (different CPUs)
3. Translate examples to 65C816
4. Practice writing 65C816 arithmetic programs

**Study Questions**:
- How do arithmetic operations work? (from Chapter 17)
- How are flags used in arithmetic? (from book examples)
- How do you handle carry in 65C816? (translate from book)

---

#### Week 7: Logic and Branch Instructions

**What to Read**:
- Chapter 18: Logic Instructions (AND, OR, XOR)
- Chapter 19: Branch Instructions (Jumps, Conditional branches)

**Key Concepts from Book**:
- Bitwise logic operations
- Program flow control
- Conditional branches
- Loop implementation

**How to Use**:
1. Read Chapters 18-19 - understand logic and branches
2. Study book examples (different CPUs)
3. Translate examples to 65C816
4. Practice writing 65C816 logic and branch programs

**Study Questions**:
- What are bitwise operations? (from Chapter 18)
- How do conditional branches work? (from Chapter 19)
- How do you implement loops? (from book examples)

---

#### Week 8: Stack and Control Instructions

**What to Read**:
- Chapter 20: Stack Instructions (Push, Pull)
- Chapter 22: CPU Control Instructions (NOP, HLT, interrupts)

**Key Concepts from Book**:
- Stack operations (push, pull)
- Stack pointer management
- System control operations
- Interrupt handling

**How to Use**:
1. Read Chapters 20, 22 - understand stack and control
2. Study book examples (different CPUs)
3. Translate examples to 65C816
4. Practice writing 65C816 stack and control programs

**Study Questions**:
- How do stack operations work? (from Chapter 20)
- What are control instructions? (from Chapter 22)
- How do you use stack for subroutines? (from book examples)

---

### Weeks 9-12: Pascal Runtime

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - For runtime implementation

**What to Read**:
- Chapter 16: Data Transfer (for parameter passing)
- Chapter 20: Stack Instructions (for calling conventions)
- Chapter 19: Branch Instructions (for control flow)
- Chapter 17: Arithmetic Instructions (for arithmetic operations)

**Key Concepts from Book**:
- Stack-based calling conventions
- Parameter passing methods
- Runtime arithmetic operations
- Control flow in runtime

**How to Use**:
1. Review instruction categories from book
2. Apply book concepts to runtime implementation
3. Design calling conventions using book's stack concepts
4. Implement runtime functions using book's instruction patterns

---

## Term 2: High-Level Language & OS (Weeks 13-24)

### Weeks 13-16: Compiler Implementation

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - For code generation

**What to Read**:
- Chapters 16-23: Instruction Sets (review for code generation)
  - Use book's instruction categories when designing code generator
  - Reference book examples when generating assembly code

**Key Concepts from Book**:
- Instruction categories for code generation
- Instruction selection patterns
- Addressing mode selection
- Code generation strategies

**How to Use**:
1. Review instruction categories from book
2. Design code generator using book's categories
3. Reference book examples when generating code
4. Use book's patterns for instruction selection

---

### Weeks 17-20: Pascal Program Development

**Primary Book Reference**: **Chapters 16-23 (Instruction Sets)** - For understanding generated code

**What to Read**:
- Chapters 16-23: Instruction Sets (supplementary reference)
  - Understand generated assembly code
  - Debug generated code using book's concepts

**Key Concepts from Book**:
- Understanding generated assembly
- Debugging using instruction categories
- Code optimization using book patterns

**How to Use**:
1. Review generated assembly using book's categories
2. Debug generated code using book's concepts
3. Optimize generated code using book's examples

---

### Weeks 21-24: OS Extensions

**Primary Book Reference**: **Chapter 14** and **Chapters 16-23**

**What to Read**:
- Chapter 14: Programming & Languages (system-level concepts)
- Chapters 16-23: Instruction Sets (for OS implementation)

**Key Concepts from Book**:
- System-level programming concepts
- OS-level instruction usage
- System interface design

**How to Use**:
1. Study book's system programming concepts
2. Apply book's instruction concepts to OS
3. Reference book examples for OS operations

---

## Study Tips

### 1. Read Before Class
- Always read required book chapters before class
- Take notes on key concepts
- Identify instruction categories
- Note translation patterns

### 2. Use Book Examples
- Study book examples carefully
- Understand the concepts, not just memorize
- Translate book examples to 65C816
- Practice with multiple CPU examples

### 3. Translation Practice
- Regularly translate book examples to 65C816
- Use bridging guide for translation patterns
- Compare your translations to book's approach
- Test translated programs on 65C816

### 4. Reference Book During Activities
- Keep book open during labs
- Reference book when writing assembly
- Use book examples as starting points
- Compare your code to book's examples

### 5. Complete Book Exercises
- Do all book-based exercises
- Translate book examples to 65C816
- Compare your solutions to book's approach
- Test all translated programs

---

## Reading Schedule

### Term 1
- **Week 1-4**: Chapters 13, 14 (Microprocessor and Assembly Concepts)
- **Week 5**: Chapter 16 (Data Transfer Instructions)
- **Week 6**: Chapter 17 (Arithmetic Instructions)
- **Week 7**: Chapters 18, 19 (Logic and Branch Instructions)
- **Week 8**: Chapters 20, 22 (Stack and Control Instructions)
- **Week 9-12**: Chapters 16-23 (Review for Runtime)

### Term 2
- **Week 13-16**: Chapters 16-23 (Instruction Sets for Code Generation)
- **Week 17-20**: Chapters 16-23 (Instruction Sets for Understanding Generated Code)
- **Week 21-24**: Chapter 14 + Chapters 16-23 (OS Extensions)

---

## Key Book Sections Summary

| Week | Primary Book Section | Key Concept |
|------|---------------------|-------------|
| 1-4 | Chapters 13, 14 | Microprocessor and assembly concepts |
| 5 | Chapter 16 | Data transfer instructions |
| 6 | Chapter 17 | Arithmetic instructions |
| 7 | Chapters 18, 19 | Logic and branch instructions |
| 8 | Chapters 20, 22 | Stack and control instructions |
| 9-12 | Chapters 16-23 | Instruction sets for runtime |
| 13-16 | Chapters 16-23 | Instruction sets for code generation |
| 17-20 | Chapters 16-23 | Instruction sets for understanding code |
| 21-24 | Chapter 14, 16-23 | System programming and OS |

---

## Translation Patterns

### Pattern 1: 6502 → 65C816
**Result**: **Usually identical!** 65C816 is 6502-compatible.

**Examples**:
- 6502: `LDA #$42` → 65C816: `LDA #$42` ✅ **Same!**
- 6502: `BEQ label` → 65C816: `BEQ label` ✅ **Same!**
- 6502: `PHA` → 65C816: `PHA` ✅ **Same!**

### Pattern 2: 8080/8085 → 65C816
**Result**: **Different syntax, same concepts**

**Examples**:
- 8080: `MVI A,10H` → 65C816: `LDA #$10`
- 8080: `MOV B,A` → 65C816: `TAX`
- 8080: `ADD B` → 65C816: `ADC $address`
- 8080: `CALL $5000` → 65C816: `JSR $5000`
- 8080: `RET` → 65C816: `RTS`

### Pattern 3: 8086/8088 → 65C816
**Result**: **Different syntax, similar concepts**

**Examples**:
- 8086: `MOV AX,10H` → 65C816: `LDA #$10`
- 8086: `ADD AX,BX` → 65C816: `ADC $address`
- 8086: `JZ label` → 65C816: `BEQ label`

---

## Resources

- **65C816 Concept Bridging Guide** (`../Year4/Term2/65C816_CONCEPT_BRIDGING.md`) - Translation patterns
- **65C816 Instruction Set Reference** (`../../docs/65C816_INSTRUCTION_SET_REFERENCE.md`) - Complete instruction set
- **Book Examples**: Use book's examples as starting points

---

**Document Created**: 2025-12-15  
**Purpose**: Guide students in using Malvino & Brown Part 3 as primary assembly programming reference for Year 5
