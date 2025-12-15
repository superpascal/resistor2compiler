# Week 5-8: Assembler and Toolchain - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand assembler operation
- Configure 65C816 assembler (ca65 or similar)
- Set up cross-development toolchain
- Create assembly language programs
- Link and load programs

## Prerequisites

- Monitor program working (Weeks 1-4)
- Understanding of 65C816 instruction set
- Basic assembly language knowledge
- Understanding of machine code
- Access to Malvino & Brown textbook

**Required Reading** (Primary Reference - Week-by-Week):

**Week 5: Data Transfer Instructions**
- **Malvino & Brown, Chapter 16**: Data Transfer Instructions
  - Load, Store, Move operations
  - Examples from 6502, 6800, 8080/8085, 8086/8088
  - **Purpose**: Understand data transfer concepts, translate to 65C816
  - **65C816 Concept Bridging Guide**: Use `../../Year4/Term2/65C816_CONCEPT_BRIDGING.md` for translation

**Week 6: Arithmetic Instructions**
- **Malvino & Brown, Chapter 17**: Arithmetic Instructions
  - Add, Subtract, Compare operations
  - Examples from multiple CPUs
  - **Purpose**: Understand arithmetic operations, translate to 65C816
  - **65C816 Concept Bridging Guide**: Use bridging guide for translation

**Week 7: Logic and Branch Instructions**
- **Malvino & Brown, Chapter 18**: Logic Instructions (AND, OR, XOR)
- **Malvino & Brown, Chapter 19**: Branch Instructions (Jumps, Conditional branches)
  - Examples from multiple CPUs
  - **Purpose**: Understand logic and program flow control, translate to 65C816
  - **65C816 Concept Bridging Guide**: Use bridging guide for translation

**Week 8: Stack and Control Instructions**
- **Malvino & Brown, Chapter 20**: Stack Instructions (Push, Pull)
- **Malvino & Brown, Chapter 22**: CPU Control Instructions (NOP, HLT, interrupts)
  - Examples from multiple CPUs
  - **Purpose**: Understand stack operations and system control, translate to 65C816
  - **65C816 Concept Bridging Guide**: Use bridging guide for translation

**Book Integration**: 
- Read book chapters for **conceptual understanding** of instruction categories
- Use **65C816 Concept Bridging Guide** to translate book examples to 65C816
- Practice translating book examples to 65C816 assembly code
- Compare book's addressing modes to 65C816 addressing modes

**Note**: The book is the **primary assembly programming reference** for Year 5. While the book covers different CPUs (6502, 6800, 8080/8085, 8086/8088), the instruction categories and concepts are universal. Use the book for conceptual understanding, then translate to 65C816 using the bridging guide.

## Key Concepts

### 1. What is an Assembler?

An **assembler** converts assembly language source code into machine code (object files).

**Process**:
1. **Parse**: Read assembly source code
2. **Assemble**: Convert instructions to machine code
3. **Resolve**: Handle labels and addresses
4. **Output**: Generate object file

**Analogy**: Assembler is like a translator - it converts human-readable assembly into machine-readable binary.

### 2. Cross-Assembly Toolchain

**Cross-Assembly**: Developing on PC (host) for 65C816 (target)

**Toolchain Components**:
- **Assembler**: ca65 (CC65 suite) or custom assembler
- **Linker**: ld65 (CC65 suite) or custom linker
- **Object File Format**: Object files for linking
- **Hex File Generator**: Convert to loadable format

### 3. Assembly Language Structure

**Basic Structure**:
```assembly
    .segment "CODE"
    .org $2000

start:
    LDA #$42        ; Load immediate value
    STA $1000       ; Store to memory
    RTS             ; Return
```

**Key Elements**:
- **Labels**: Names for addresses
- **Instructions**: CPU instructions
- **Operands**: Instruction parameters
- **Comments**: Documentation
- **Directives**: Assembler commands (.org, .segment)

### 4. Addressing Modes in Assembly

**65C816 Addressing Modes**:
- **Immediate**: `LDA #$42`
- **Absolute**: `LDA $1000`
- **Zero Page**: `LDA $42`
- **Indexed**: `LDA $1000,X`
- **Indirect**: `LDA ($42)`
- **And more...**

### 5. Linking and Loading

**Linking**:
- Combine multiple object files
- Resolve external references
- Create executable image
- Generate memory map

**Loading**:
- Transfer program to target system
- Use monitor program to load
- Set entry point
- Execute program

### 6. Development Workflow

**Typical Workflow**:
1. Write assembly source code (on PC)
2. Assemble to object file
3. Link object files
4. Generate hex/binary file
5. Transfer to target (via serial)
6. Load into memory (via monitor)
7. Execute and debug

## Implementation Approach

### Setting Up CC65 Toolchain

1. **Install CC65**:
   - Download CC65 suite
   - Configure for 65C816 target
   - Set up build environment

2. **Create Configuration**:
   - Define memory map
   - Set up segments (CODE, DATA, BSS)
   - Configure linker script

3. **Test Setup**:
   - Assemble simple program
   - Link and generate hex
   - Load and execute via monitor

### Creating Assembly Programs

1. **Basic Program Structure**:
   - Define entry point
   - Set up segments
   - Write code
   - Define data

2. **Using Monitor Integration**:
   - Programs can call monitor functions
   - Use monitor for I/O
   - Debug via monitor

## Connections to Previous Learning

- **Monitor Program**: Assembler output loaded via monitor
- **65C816 Architecture**: Assembler generates code for 65C816
- **Machine Code**: Assembler produces machine code
- **System Design**: Programs use system memory map

## Next Steps

After completing assembler setup, students will:
- Prepare Pascal runtime library
- Understand compiler requirements
- Design runtime interface
- Prepare for compiler integration

---

*Assemblers enable efficient software development on custom hardware*
