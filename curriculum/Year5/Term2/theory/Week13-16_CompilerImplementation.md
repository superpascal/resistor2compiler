# Week 13-16: SuperPascal Compiler Implementation - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand compiler structure and operation
- Configure SuperPascal compiler for 65C816
- Extend compiler with new intrinsics
- Test compiler with sample programs
- Verify code generation

## Prerequisites

- Completed Term 1 (PCB System)
- Working 65C816 system
- Understanding of assembly language
- Basic programming concepts
- Understanding of compilers (conceptual)
- Access to Malvino & Brown textbook

**Required Reading** (Primary Reference for Code Generation):
- **Malvino & Brown, Chapters 16-23**: Instruction Sets (review for code generation)
  - Use book's instruction categories when designing code generator
  - Reference book examples when generating assembly code
  - **Purpose**: Understand instruction categories for code generation

**Book Integration**:
- Review instruction categories from book (Chapters 16-23)
- Design code generator instruction selector using book's categories
- Reference book examples when generating assembly code
- Use book's addressing mode concepts for code generation
- Use **65C816 Concept Bridging Guide** for translating book concepts to 65C816

**Note**: The book is the **primary reference** for understanding instruction categories used in code generation. Use the book for conceptual understanding of instruction categories, then apply to 65C816 code generation.

## Key Concepts

### 1. Compiler Overview

**What is a compiler?**
- Translates high-level language to machine code
- Front-end: Parsing and analysis
- Back-end: Code generation
- Enables high-level programming

**Compiler structure**:
- Lexical analysis (tokenization)
- Syntax analysis (parsing)
- Semantic analysis
- Code generation
- Optimization (optional)

**Why use a compiler?**
- Higher productivity than assembly
- Easier to write programs
- Better code organization
- Enables complex programs

### 2. SuperPascal Compiler

**SuperPascal**:
- Subset of Pascal
- Based on Per Brinch Hansen's work
- Concise and educational
- Suitable for embedded systems

**Compiler source**:
- Provided as Pascal or C source
- Can be modified
- Configurable for targets
- Educational value

**Target configuration**:
- Configure for 65C816
- Set calling conventions
- Link runtime library
- Generate assembly code

### 3. Compiler Structure

**Front-end**:
- Lexical analyzer (scanner)
- Parser
- Semantic analyzer
- Symbol table
- Abstract syntax tree

**Back-end**:
- Code generator
- Register allocator
- Instruction selector
- Assembly output
- Linker interface

**Configuration**:
- Target-specific settings
- Calling conventions
- Register usage
- Memory model
- Runtime interface

### 4. Calling Conventions

**ABI (Application Binary Interface)**:
- How functions are called
- Parameter passing
- Return values
- Register usage
- Stack frame layout

**Stack-based calling**:
- Parameters on stack
- Right-to-left push
- Caller cleans stack
- Return value in register
- Standard convention

**Register usage**:
- Which registers for parameters
- Which for return values
- Which preserved
- Which scratch
- Stack pointer usage

### 5. Runtime Library

**Runtime requirements**:
- I/O routines (WriteChar, WriteString)
- Math routines (multiply, divide)
- Memory management (if needed)
- System calls
- Interrupt handling

**Runtime implementation**:
- Written in assembly
- Called from Pascal
- Provides low-level support
- Abstracts hardware
- Standard interface

**Runtime integration**:
- Link with compiler output
- Resolve external calls
- Provide implementations
- Test thoroughly

### 6. Compiler Extensions

**Extension tasks**:
- Add new intrinsic functions
- Add graphics support
- Add sound support
- Add I/O functions
- Custom features

**Example: SOUND(freq)**:
- Add syntax (if needed)
- Generate call to sound routine
- Link with runtime
- Test functionality

**Example: PlotPixel(x,y)**:
- Add procedure
- Generate video memory write
- Link with graphics routine
- Test display

### 7. Code Generation

**Code generation process**:
- Translate AST to assembly
- Allocate registers
- Select instructions
- Generate assembly code
- Output to file

**Assembly output**:
- Compatible with assembler
- Uses correct syntax
- Follows conventions
- Links with runtime
- Can be assembled

### 8. Testing the Compiler

**Test programs**:
- Simple arithmetic
- Variables and assignments
- Control flow (if, while)
- Procedures and functions
- I/O operations

**Testing process**:
- Compile test program
- Assemble output
- Link with runtime
- Load on system
- Run and verify

**Verification**:
- Correct output
- Correct behavior
- No crashes
- Performance acceptable
- All features work

## Mathematical Foundations

### Compiler Theory

**Parsing**:
- Context-free grammars
- Recursive descent
- LL/LR parsing
- Syntax trees

**Code generation**:
- Instruction selection
- Register allocation
- Optimization
- Assembly generation

## Common Misconceptions

1. **"Compilers are magic"**
   - Clarify: Systematic translation
   - Show structure

2. **"Too complex to understand"**
   - Clarify: Built on simple concepts
   - Show progression

3. **"Can't modify compilers"**
   - Clarify: Source provided
   - Show extension process

## Connections to Term 1

- **PCB System**: Target for compiler
- **Hardware**: Runtime uses hardware
- **System**: Compiler produces code for system

## Connections to Weeks 17-24

- **Pascal Programs**: Use compiler
- **Demos**: Compiler enables demos
- **OS Extensions**: Compiler supports OS

## Next Steps

After implementing compiler, students will:
- Develop Pascal programs (Weeks 17-20)
- Create demos and games
- Extend OS functionality (Weeks 21-24)

---

*Compiler implementation enables high-level programming on custom hardware*
