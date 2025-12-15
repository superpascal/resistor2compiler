# Week 1-4: Monitor Program and Machine Code Monitor - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand monitor program concepts
- Design a monitor for 65C816 system
- Implement memory inspection and editing
- Implement register display and modification
- Implement program execution control

## Prerequisites

- Working 65C816 hardware system
- Understanding of 65C816 architecture
- Basic assembly language knowledge
- Serial communication concepts
- Access to Malvino & Brown textbook

**Required Reading** (Primary Reference):
- **Malvino & Brown, Chapter 13** (Intro to Microprocessors): Sections 13-1 to 13-5
  - General microprocessor concepts
  - Register models
  - Addressing concepts
  - Instruction types
  - **Purpose**: Understand system-level programming concepts for monitor development
- **Malvino & Brown, Chapter 14** (Programming & Languages): Sections 14-1 to 14-5
  - Assembly language concepts
  - Instruction categories
  - Program structure
  - Addressing modes (general)
  - **Purpose**: Understand assembly language structure for monitor implementation

**Book Integration**:
- Read Chapter 13 - understand microprocessor concepts for system programming
- Read Chapter 14 - understand assembly language structure
- Study book's assembly examples - apply to monitor program implementation
- Compare book's system programming concepts to monitor requirements
- Use **65C816 Concept Bridging Guide** (`../../Year4/Term2/65C816_CONCEPT_BRIDGING.md`) for translating concepts

**Note**: The book is the **primary reference** for understanding system-level programming concepts. Use the book for conceptual understanding, then apply to 65C816 monitor implementation.

## Key Concepts

### 1. What is a Monitor Program?

A **monitor program** is a low-level debugging and control program that provides:
- Memory inspection and editing
- Register display and modification
- Program loading and execution
- Single-step execution
- Breakpoint support (advanced)

**Analogy**: Think of a monitor like a control panel for your computer - you can see what's happening inside and control it directly.

### 2. Monitor Program Structure

**Core Components**:
- **Command Parser**: Interprets user commands
- **Memory Access**: Read/write memory locations
- **Register Access**: Display/modify CPU registers
- **Execution Control**: Run, step, stop programs
- **I/O Interface**: Serial communication for user interaction

### 3. Memory Inspection and Editing

**Memory Inspection**:
- Display memory contents at specific addresses
- Show ranges of memory
- Display in different formats (hex, decimal, ASCII)

**Memory Editing**:
- Modify memory locations
- Load data into memory
- Fill memory ranges with patterns

### 4. Register Display and Modification

**Register Display**:
- Show all CPU registers (A, X, Y, S, PC, P)
- Display register values in hex and decimal
- Show processor status flags

**Register Modification**:
- Change register values
- Set program counter
- Modify status flags

### 5. Program Execution Control

**Execution Modes**:
- **Run**: Execute program from current PC
- **Step**: Execute one instruction
- **Stop**: Halt execution
- **Continue**: Resume from breakpoint

### 6. Serial Communication Interface

**Command Interface**:
- Simple command-line interface via serial
- Commands like: `M 1000` (memory at 1000), `R` (registers), `G 2000` (go to 2000)
- Echo and error handling

## Implementation Approach

### Basic Monitor Features

1. **Command Loop**:
   - Wait for serial input
   - Parse command
   - Execute command
   - Return to command loop

2. **Memory Commands**:
   - `M <addr>` - Display memory at address
   - `M <addr> <data>` - Write data to address
   - `F <start> <end> <data>` - Fill memory range

3. **Register Commands**:
   - `R` - Display all registers
   - `R <reg> <value>` - Set register value

4. **Execution Commands**:
   - `G <addr>` - Go (execute from address)
   - `S` - Step (execute one instruction)
   - `B` - Break (stop execution)

## Connections to Previous Learning

- **Year 4 Hardware**: Monitor runs on completed hardware
- **Assembly Language**: Monitor uses assembly for implementation
- **I/O Systems**: Monitor uses serial I/O for communication
- **System Architecture**: Monitor understands CPU and memory layout

## Next Steps

After completing monitor program, students will:
- Set up assembler and toolchain
- Create assembly language programs
- Use monitor to debug programs
- Prepare for Pascal runtime

---

*Monitor programs provide the foundation for software development*
