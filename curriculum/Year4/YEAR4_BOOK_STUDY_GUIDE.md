# Year 4 Book Study Guide

## Overview

This study guide helps students use **Malvino & Brown, Digital Computer Electronics** as the **primary conceptual reference** for Year 4. The book provides essential concepts for understanding CPU enhancements and microprocessor systems.

**Purpose**: Make the book actively used throughout Year 4, not just mentioned.

---

## Term 1: SAP-1 Enhancements

### Weeks 1-3: SAP-1 Improvements

**Primary Book Reference**: **Chapter 10 (SAP-1)**

**What to Read**:
- Chapter 10-1: SAP-1 Architecture (review)
- Chapter 10-2: SAP-1 Instruction Set (review)
- Chapter 10-7: SAP-1 Schematic Diagram (reference)

**Key Concepts from Book**:
- SAP-1 architecture components
- SAP-1 instruction set limitations
- SAP-1 design principles

**How to Use**:
1. Review book's SAP-1 description
2. Compare your implementation to book's schematic
3. Identify improvements based on book's design principles

**Study Questions**:
- What are the main components of SAP-1? (from book)
- What limitations does the book mention?
- How does your SAP-1 compare to the book's design?

---

### Weeks 4-6: Expanded Instruction Set

**Primary Book Reference**: **Chapter 11 (SAP-2)** - Enhanced Instructions

**What to Read**:
- Chapter 11-3: Memory-Reference Instructions (LDA, STA, MVI)
- Chapter 11-4: Register Instructions (MOV, ADD/SUB, INR/DCR)
- Chapter 11-6: Logic Instructions (CMA, ANA, ORA, XRA)

**Key Concepts from Book**:
- Why more instructions are useful
- Register-to-register operations
- Bitwise logic operations
- Instruction set expansion principles

**How to Use**:
1. Study SAP-2 instruction set (42 instructions vs SAP-1's 5)
2. Understand why each category is useful
3. Design similar instructions for enhanced SAP-1
4. Reference book examples when implementing

**Study Questions**:
- How many instructions does SAP-2 have? (from book)
- What categories of instructions does SAP-2 add? (from book)
- Which SAP-2 instructions would be most useful for enhanced SAP-1?

---

### Weeks 7-9: Memory Expansion

**Primary Book Reference**: **Chapter 11 (SAP-2)** - Architecture

**What to Read**:
- Chapter 11-1: Bidirectional Registers (bus concepts)
- Chapter 11-2: Architecture (16-bit Addressing)
- Chapter 9: Memories (review)

**Key Concepts from Book**:
- Address space expansion: 4-bit → 16-bit
- Bidirectional bus design
- Memory organization principles

**How to Use**:
1. Study SAP-2 address expansion (4-bit → 16-bit)
2. Understand the progression: SAP-1 → SAP-2 → 65C816
3. Apply bidirectional bus concepts to enhanced SAP-1
4. Plan memory expansion using book's principles

**Study Questions**:
- How does SAP-2 expand addressing? (from book)
- What are bidirectional registers? (from book 11-1)
- How does address space expansion enable larger programs?

---

## Term 2: 16-bit Preparation

### Weeks 10-12: Introduction to 65C816

**Primary Book Reference**: **Chapter 11-5 (SAP-2 Jumps/Calls)** and **Chapter 13 (Microprocessors)**

**What to Read**:
- Chapter 11-5: Jump and Call Instructions ⭐ **MOST IMPORTANT**
  - JMP (unconditional jump)
  - JM, JZ, JNZ (conditional jumps)
  - CALL/RET (subroutines)
- Chapter 13-1 to 13-5: Intro to Microprocessors
  - General microprocessor concepts
  - Register models
  - Addressing concepts

**Key Concepts from Book**:
- Program flow control (jumps, branches)
- Subroutines and code reuse
- Stack-based return addresses
- Universal microprocessor concepts

**How to Use**:
1. Read SAP-2 jump/call examples (11-5) - understand subroutines
2. Compare SAP-2 jumps to 65C816 branches
3. Translate SAP-2 examples to 65C816
4. Study book's microprocessor examples - understand universal concepts

**Study Questions**:
- How does SAP-2 implement subroutines? (from book 11-5)
- How does 65C816 implement the same concept?
- What are the universal microprocessor concepts? (from Chapter 13)

---

### Weeks 13-15: System Design

**Primary Book Reference**: **Chapter 11-2 (SAP-2 Architecture)** and **Chapter 15 (System Overview)**

**What to Read**:
- Chapter 11-2: Architecture (16-bit Addressing) - review
- Chapter 15-1 to 15-5: System Overview
  - Microprocessor architecture patterns
  - Register organization
  - Memory models
  - System design concepts

**Key Concepts from Book**:
- System architecture patterns
- Register organization principles
- Memory model design
- System integration concepts

**How to Use**:
1. Review SAP-2 architecture (11-2) - understand system design
2. Study book's system design patterns (Chapter 15)
3. Apply patterns to 65C816 system design
4. Compare your design to book's examples

**Study Questions**:
- What are the key system architecture patterns? (from Chapter 15)
- How do different CPUs organize registers? (from Chapter 15)
- How did you apply book's patterns to 65C816 system?

---

### Weeks 16-18: Breadboard Prototype

**Primary Book Reference**: **Chapter 10-7 (SAP-1 Schematic)** and **Chapter 11 (SAP-2)**

**What to Read**:
- Chapter 10-7: SAP-1 Schematic Diagram (construction reference)
- Chapter 11-1: Bidirectional Registers (bus design)
- Chapter 11-2: Architecture (system integration)

**Key Concepts from Book**:
- Construction organization principles
- Bus design concepts
- System integration techniques

**How to Use**:
1. Reference SAP-1 schematic for construction techniques
2. Study SAP-2 bus design (11-1)
3. Apply book's principles to 65C816 prototype
4. Compare your layout to book's organization

---

### Weeks 19-21: Memory Banking

**Primary Book Reference**: **Chapter 11-2 (SAP-2 Addressing)** and **Chapter 12-8 (SAP-3 Registers)**

**What to Read**:
- Chapter 11-2: Architecture (16-bit Addressing) - address space concepts
- Chapter 12-8: Extended Registers - register expansion
- Chapter 9: Memories (review) - memory organization

**Key Concepts from Book**:
- Address space expansion progression
- Register expansion concepts
- Memory organization principles

**How to Use**:
1. Study address progression: SAP-1 (4-bit) → SAP-2 (16-bit) → 65C816 (24-bit)
2. Study SAP-3 register expansion (12-8)
3. Apply concepts to 65C816 memory banking
4. Calculate memory banks using book's principles

---

### Weeks 22-24: I/O Subsystems

**Primary Book Reference**: **Chapter 11-7 (SAP-2 I/O)** and **Chapter 12-9 (SAP-3 Indirect Addressing)**

**What to Read**:
- Chapter 11-7: Other Instructions (IN/OUT operations)
- Chapter 12-9: Indirect Addressing - I/O addressing concepts

**Key Concepts from Book**:
- Port-based I/O (SAP-2)
- Indirect addressing for I/O
- I/O method comparison

**How to Use**:
1. Study SAP-2 port-based I/O (11-7)
2. Compare to 65C816 memory-mapped I/O
3. Study SAP-3 indirect addressing (12-9)
4. Apply indirect addressing to 65C816 I/O

---

### Weeks 25-27: Graphics/Sound Selection

**Primary Book Reference**: **Chapter 12 (SAP-3)** - Advanced Features

**What to Read**:
- Chapter 12-10: Stack Instructions - system-level concepts
- Chapter 12-11: Other Advanced Instructions - system capabilities

**Key Concepts from Book**:
- Advanced CPU features
- System-level programming
- Complex I/O support

**How to Use**:
1. Review SAP-3 advanced features
2. Understand how advanced CPUs support complex I/O
3. Plan graphics/sound integration using book's principles
4. Reference book's progression when planning enhancements

---

## Study Tips

### 1. Read Before Class
- Always read required book sections before class
- Take notes on key concepts
- Identify questions to ask

### 2. Use Book Examples
- Study book examples carefully
- Try to understand the concepts, not just memorize
- Translate book examples to 65C816

### 3. Compare and Contrast
- Compare SAP-1 to SAP-2 (from book)
- Compare SAP-2 to 65C816
- Understand the progression: SAP-1 → SAP-2 → 65C816

### 4. Reference Book During Activities
- Keep book open during labs
- Reference book when designing
- Use book examples as starting points

### 5. Complete Book Exercises
- Do all book-based exercises
- Translate book examples to 65C816
- Compare your solutions to book's approach

---

## Reading Schedule

### Term 1
- **Week 1-3**: Chapter 10 (SAP-1 review)
- **Week 4-6**: Chapter 11-3, 11-4, 11-6 (SAP-2 instructions)
- **Week 7-9**: Chapter 11-1, 11-2 (SAP-2 architecture)

### Term 2
- **Week 10-12**: Chapter 11-5 (SAP-2 jumps/calls) + Chapter 13 (Microprocessors)
- **Week 13-15**: Chapter 11-2 (SAP-2 architecture) + Chapter 15 (System Overview)
- **Week 16-18**: Chapter 10-7 (SAP-1 schematic) + Chapter 11-1, 11-2
- **Week 19-21**: Chapter 11-2 (SAP-2 addressing) + Chapter 12-8 (SAP-3 registers)
- **Week 22-24**: Chapter 11-7 (SAP-2 I/O) + Chapter 12-9 (SAP-3 indirect)
- **Week 25-27**: Chapter 12-10, 12-11 (SAP-3 advanced)

---

## Key Book Sections Summary

| Week | Primary Book Section | Key Concept |
|------|---------------------|-------------|
| 1-3 | Chapter 10 (SAP-1) | Review and improvements |
| 4-6 | Chapter 11-3, 11-4, 11-6 | Instruction set expansion |
| 7-9 | Chapter 11-1, 11-2 | Memory expansion, architecture |
| 10-12 | Chapter 11-5, 13 | Jumps, subroutines, microprocessors |
| 13-15 | Chapter 11-2, 15 | System design, architecture patterns |
| 16-18 | Chapter 10-7, 11-1, 11-2 | Construction, bus design |
| 19-21 | Chapter 11-2, 12-8 | Memory banking, register expansion |
| 22-24 | Chapter 11-7, 12-9 | I/O methods, indirect addressing |
| 25-27 | Chapter 12-10, 12-11 | Advanced features, system capabilities |

---

**Document Created**: 2025-12-15  
**Purpose**: Guide students in using Malvino & Brown textbook as primary reference for Year 4
