# Week 5-8: Assembler and Toolchain - Teaching Guide

## Overview

This teaching guide supports the delivery of assembler and toolchain setup over 4 weeks. Students learn to set up cross-development tools and create assembly language programs.

## Learning Objectives

By the end of this week-block, students will:
- Understand assembler operation
- Configure 65C816 assembler (ca65 or similar)
- Set up cross-development toolchain
- Create assembly language programs
- Link and load programs

## Prerequisites Check

Before starting, ensure students:
- ✅ Monitor program working
- ✅ Understand 65C816 instruction set
- ✅ Know basic assembly language
- ✅ Understand machine code
- ✅ Can use development PC
- ✅ Have access to Malvino & Brown textbook

## Book Integration

**Primary Reference**: **Malvino & Brown, Digital Computer Electronics, Part 3 (Chapters 16-23)**

This week-block uses the book as the **primary assembly programming reference** for learning instruction categories and assembly programming concepts.

### Week 5: Data Transfer Instructions

**Before Class**:
- **Required Reading**: **Chapter 16** (Data Transfer Instructions)
  - Read sections on Load, Store, Move operations
  - Study examples from 6502, 6800, 8080/8085, 8086/8088
  - Understand data transfer concepts

**During Class**:
- **Discussion**: How do data transfer instructions work? (from book)
- **Demonstration**: Translate book's data transfer example (6502 LDA) to 65C816
- **Practice**: Translate book's 8080 MOV example to 65C816 TAX
- **Reference**: Use **65C816 Concept Bridging Guide** for translation patterns

**After Class**:
- **Assignment**: Translate 3 data transfer examples from book (different CPUs) to 65C816
- **Assessment**: Compare book's addressing modes to 65C816 addressing modes

---

### Week 6: Arithmetic Instructions

**Before Class**:
- **Required Reading**: **Chapter 17** (Arithmetic Instructions)
  - Read sections on Add, Subtract, Compare operations
  - Study examples from multiple CPUs
  - Understand arithmetic concepts

**During Class**:
- **Discussion**: How do arithmetic instructions work? (from book)
- **Demonstration**: Translate book's arithmetic example (6502 ADC) to 65C816
- **Practice**: Translate book's 8080 ADD example to 65C816 ADC
- **Reference**: Use bridging guide for translation

**After Class**:
- **Assignment**: Translate 3 arithmetic examples from book to 65C816
- **Assessment**: Explain how 65C816 arithmetic compares to book's examples

---

### Week 7: Logic and Branch Instructions

**Before Class**:
- **Required Reading**: 
  - **Chapter 18** (Logic Instructions: AND, OR, XOR)
  - **Chapter 19** (Branch Instructions: Jumps, Conditional branches)
  - Study examples from multiple CPUs

**During Class**:
- **Discussion**: How do logic and branch instructions work? (from book)
- **Demonstration**: Translate book's logic example (6502 AND) to 65C816
- **Demonstration**: Translate book's branch example (6502 BEQ) to 65C816
- **Practice**: Translate book's 8080 conditional jump to 65C816 branch

**After Class**:
- **Assignment**: Translate 3 logic examples and 3 branch examples from book to 65C816
- **Assessment**: Explain how conditional branches work in book's examples vs 65C816

---

### Week 8: Stack and Control Instructions

**Before Class**:
- **Required Reading**:
  - **Chapter 20** (Stack Instructions: Push, Pull)
  - **Chapter 22** (CPU Control Instructions: NOP, HLT, interrupts)
  - Study examples from multiple CPUs

**During Class**:
- **Discussion**: How do stack and control instructions work? (from book)
- **Demonstration**: Translate book's stack example (6502 PHA) to 65C816
- **Practice**: Translate book's control example to 65C816
- **Reference**: Use bridging guide for translation

**After Class**:
- **Assignment**: Translate 3 stack examples from book to 65C816
- **Assessment**: Explain how stack operations work in book's examples vs 65C816

---

### Resources

- **65C816 Concept Bridging Guide** (`../../Year4/Term2/65C816_CONCEPT_BRIDGING.md`) - Detailed translation patterns
- **65C816 Instruction Set Reference** (`../../../../docs/65C816_INSTRUCTION_SET_REFERENCE.md`) - Complete instruction set
- **Book Examples**: Use book's examples as starting points for 65C816 programs

**Key Principle**: Read book chapters for **conceptual understanding** (what are data transfer instructions?), then translate book examples to 65C816 using the bridging guide.

## Week-by-Week Breakdown

### Week 5: Assembler Concepts and Setup

**Theory Session (45 min)**:
- What is an assembler?
- Cross-assembly concepts
- CC65 toolchain overview
- Toolchain setup process

**Lab Session (90 min)**:
- Install CC65 suite
- Configure for 65C816 target
- Set up build environment
- Test assembler with simple program

**Key Points**:
- Assembler converts assembly to machine code
- Cross-assembly develops on PC for target
- CC65 provides 65C816 support

**Common Questions**:
- Q: Why cross-assembly? A: Develop on PC, run on target
- Q: What is CC65? A: C compiler and assembler for 6502/65C816
- Q: How do we configure it? A: Set target to 65C816, configure memory map

### Week 6: Assembly Language Programming

**Theory Session (45 min)**:
- Assembly language structure
- Labels and directives
- Addressing modes
- Program organization

**Lab Session (90 min)**:
- Write simple assembly program
- Use labels and directives
- Test different addressing modes
- Assemble and verify output

**Key Points**:
- Assembly has structure (labels, instructions, comments)
- Directives control assembler (.org, .segment)
- Addressing modes determine operand access

**Common Questions**:
- Q: What are labels? A: Names for addresses
- Q: What are directives? A: Assembler commands
- Q: How do addressing modes work? A: Different ways to specify operands

### Week 7: Linking and Memory Maps

**Theory Session (45 min)**:
- Linking concepts
- Object files and linking
- Memory map design
- Linker configuration

**Lab Session (90 min)**:
- Create memory map configuration
- Link multiple object files
- Generate executable image
- Verify memory layout

**Key Points**:
- Linker combines object files
- Memory map defines address space
- Linker resolves external references

**Common Questions**:
- Q: Why do we need linking? A: Combine multiple files, resolve references
- Q: What is a memory map? A: Defines where code/data goes
- Q: How do we configure linker? A: Use linker configuration file

### Week 8: Program Loading and Execution

**Theory Session (45 min)**:
- Program loading process
- Hex file formats
- Monitor integration
- Program execution

**Lab Session (90 min)**:
- Generate hex file from linked program
- Transfer to target system
- Load into memory via monitor
- Execute and debug program
- Create complete workflow

**Key Points**:
- Programs must be loaded into memory
- Monitor can load programs
- Complete workflow: assemble → link → load → execute

**Common Questions**:
- Q: How do we load programs? A: Use monitor memory write or file transfer
- Q: What format for loading? A: Hex or binary format
- Q: How do we debug? A: Use monitor step and memory commands

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide example programs
- Step-by-step toolchain setup
- Pre-configured build scripts
- Extra time for setup

**Extension for advanced students**:
- Create custom linker scripts
- Optimize assembly code
- Create library of functions
- Build reusable components

### Common Misconceptions

1. **"Assembler is the same as compiler"**
   - Clarify: Assembler is 1:1 with machine code, compiler is higher level
   - Explain: Assembly is closer to hardware

2. **"Cross-assembly is complicated"**
   - Clarify: Once set up, workflow is straightforward
   - Provide clear setup instructions

3. **"Assembly is too hard"**
   - Clarify: Start simple, build complexity
   - Show that assembly is just instructions

### Assessment Checkpoints

**Week 5**: Can students set up toolchain?
**Week 6**: Can students write assembly programs?
**Week 7**: Can students link programs?
**Week 8**: Can students load and execute programs?

## Resources

- CC65 documentation
- Assembly language tutorials
- Memory map examples
- Linker configuration examples
- Example assembly programs

## Next Week

After completing assembler setup, students move to Pascal runtime preparation (Week 9-12).

---

*Assemblers enable efficient software development*
