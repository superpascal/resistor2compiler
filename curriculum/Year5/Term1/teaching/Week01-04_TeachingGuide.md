# Week 1-4: Monitor Program and Machine Code Monitor - Teaching Guide

## Overview

This teaching guide supports the delivery of monitor program development over 4 weeks. Students learn to create a low-level debugging and control program for their 65C816 system.

## Learning Objectives

By the end of this week-block, students will:
- Understand monitor program concepts
- Design a monitor for 65C816 system
- Implement memory inspection and editing
- Implement register display and modification
- Implement program execution control

## Prerequisites Check

Before starting, ensure students:
- ✅ Have working 65C816 hardware system
- ✅ Understand 65C816 architecture
- ✅ Know basic assembly language
- ✅ Understand serial communication
- ✅ Can use serial terminal software
- ✅ Have access to Malvino & Brown textbook

## Book Integration

**Primary Reference**: **Malvino & Brown, Digital Computer Electronics, Part 3 (Chapters 13-14)**

This week-block uses the book as the **primary reference** for understanding system-level programming concepts for monitor development.

### Before Class

**Required Reading** (assign 1 week before):
- **Chapter 13** (Intro to Microprocessors): Sections 13-1 to 13-5
  - General microprocessor concepts
  - Register models
  - Addressing concepts
  - Instruction types
- **Chapter 14** (Programming & Languages): Sections 14-1 to 14-5
  - Assembly language concepts
  - Instruction categories
  - Program structure
  - Addressing modes (general)

**Pre-Class Assignment**:
- Read Chapter 13 - identify universal microprocessor concepts
- Read Chapter 14 - understand assembly language structure
- Compare book's system programming concepts to monitor requirements

### During Class

**Discussion Points** (link book to monitor implementation):

1. **Microprocessor Concepts → Monitor Design**:
   - Book shows: Register models, addressing concepts, instruction types
   - Monitor needs: Register display, memory access, instruction execution
   - **Key Insight**: Book's concepts apply to monitor design

2. **Assembly Structure → Monitor Code**:
   - Book shows: Assembly program structure, labels, directives
   - Monitor code: Uses same structure, labels for commands, directives for organization
   - **Key Insight**: Book's assembly structure applies to monitor implementation

3. **System Programming → Monitor Features**:
   - Book shows: System-level programming concepts
   - Monitor features: Memory access, register access, execution control
   - **Key Insight**: Book's system programming concepts guide monitor design

**Demonstration**:
- Show how book's register models (Chapter 13) inform monitor register display
- Show how book's assembly structure (Chapter 14) applies to monitor code organization
- Compare book's system programming examples to monitor requirements

**Practice Exercise**:
- Design monitor register display using book's register models
- Structure monitor code using book's assembly program structure
- Plan monitor commands using book's system programming concepts

### After Class

**Assignment**:
- Design monitor register display based on book's register models (Chapter 13)
- Structure monitor code using book's assembly program structure (Chapter 14)
- Compare your monitor design to book's system programming concepts

**Assessment Question**:
- From Chapter 13: What universal microprocessor concepts apply to monitor design? How did you use these concepts in your monitor implementation?

**Resources**:
- **65C816 Concept Bridging Guide** (`../../Year4/Term2/65C816_CONCEPT_BRIDGING.md`) - For translating concepts
- **Book Examples**: Use book's system programming examples as reference

## Week-by-Week Breakdown

### Week 1: Monitor Program Concepts and Design

**Theory Session (45 min)**:
- What is a monitor program?
- Monitor program structure
- Command interface design
- Serial communication for monitor

**Lab Session (90 min)**:
- Set up serial communication
- Create basic command loop
- Implement simple echo command
- Test serial interface

**Key Points**:
- Monitor provides low-level system control
- Command-line interface via serial
- Simple command parser needed

**Common Questions**:
- Q: Why do we need a monitor? A: Provides debugging and control capabilities
- Q: How does monitor communicate? A: Via serial interface
- Q: What commands do we need? A: Memory, register, execution commands

### Week 2: Memory Inspection and Editing

**Theory Session (45 min)**:
- Memory inspection commands
- Memory editing commands
- Address formats (hex, decimal)
- Memory range operations

**Lab Session (90 min)**:
- Implement memory read command (`M <addr>`)
- Implement memory write command (`M <addr> <data>`)
- Implement memory range display
- Test memory commands

**Key Points**:
- Memory commands allow inspection and modification
- Addresses can be in hex or decimal
- Memory operations must be safe

**Common Questions**:
- Q: How do we read memory? A: Use CPU load instructions
- Q: How do we write memory? A: Use CPU store instructions
- Q: What if address is invalid? A: Check address range, handle errors

### Week 3: Register Display and Modification

**Theory Session (45 min)**:
- CPU register structure
- Register display commands
- Register modification commands
- Processor status flags

**Lab Session (90 min)**:
- Implement register display command (`R`)
- Display all registers (A, X, Y, S, PC, P)
- Implement register modification (`R <reg> <value>`)
- Test register commands

**Key Points**:
- Registers hold CPU state
- Can display and modify registers
- Status flags show processor state

**Common Questions**:
- Q: How do we read registers? A: Save registers, display, restore
- Q: Can we modify PC? A: Yes, changes execution flow
- Q: What are status flags? A: Condition codes (carry, zero, etc.)

### Week 4: Program Execution Control

**Theory Session (45 min)**:
- Execution control commands
- Run, step, stop operations
- Program loading
- Breakpoint concepts (introduction)

**Lab Session (90 min)**:
- Implement go command (`G <addr>`)
- Implement step command (`S`)
- Implement break/stop command
- Test execution control
- Load and run simple program

**Key Points**:
- Can control program execution
- Step allows instruction-by-instruction execution
- Break stops execution

**Common Questions**:
- Q: How does step work? A: Execute one instruction, return to monitor
- Q: Can we resume after break? A: Yes, continue from current PC
- Q: How do we load programs? A: Use memory write commands or file transfer

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide monitor skeleton code
- Step-by-step implementation guides
- Pair programming approach
- Extra time for concepts

**Extension for advanced students**:
- Implement breakpoints
- Add disassembly command
- Add memory search
- Add program save/load

### Common Misconceptions

1. **"Monitor is the operating system"**
   - Clarify: Monitor is a debugging tool, not full OS
   - Explain: OS provides more services

2. **"Monitor must be complex"**
   - Clarify: Basic monitor can be simple
   - Start with essential commands, add features

3. **"Monitor runs instead of programs"**
   - Clarify: Monitor can run programs
   - Explain: Monitor loads and executes programs

### Assessment Checkpoints

**Week 1**: Can students create basic command loop?
**Week 2**: Can students read and write memory?
**Week 3**: Can students display and modify registers?
**Week 4**: Can students execute programs?

## Resources

- Monitor program examples
- Serial communication guides
- 65C816 instruction reference
- Command interface examples

## Next Week

After completing monitor program, students move to assembler and toolchain (Week 5-8).

---

*Monitor programs enable software development on custom hardware*
