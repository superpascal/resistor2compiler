# Week 9-12: Pascal Runtime and Language Prep - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand Pascal runtime requirements
- Design runtime library interface
- Implement basic runtime functions
- Understand compiler-runtime interaction
- Prepare for SuperPascal compiler integration

## Prerequisites

- Assembler and toolchain working (Weeks 5-8)
- Understanding of Pascal language basics
- Understanding of compiler concepts
- Understanding of system architecture
- Access to Malvino & Brown textbook

**Required Reading** (Primary Reference):
- **Malvino & Brown, Chapter 16**: Data Transfer Instructions (for parameter passing)
- **Malvino & Brown, Chapter 20**: Stack Instructions (for stack-based calling conventions)
- **Malvino & Brown, Chapter 19**: Branch Instructions (for control flow in runtime)
- **Malvino & Brown, Chapter 17**: Arithmetic Instructions (for runtime arithmetic operations)

**Book Integration**:
- Study book's stack operations (Chapter 20) - apply to stack-based calling conventions
- Study book's data transfer (Chapter 16) - apply to parameter passing
- Study book's arithmetic (Chapter 17) - apply to runtime arithmetic
- Study book's branches (Chapter 19) - apply to runtime control flow
- Use **65C816 Concept Bridging Guide** for translating concepts

**Note**: The book is the **primary reference** for understanding instruction categories used in runtime library implementation. Use the book for conceptual understanding, then apply to 65C816 runtime implementation.

## Key Concepts

### 1. What is a Runtime Library?

A **runtime library** provides low-level support functions that high-level language programs need but can't generate directly.

**Runtime Functions Include**:
- Memory management
- I/O operations
- String operations
- Math functions
- System calls

**Analogy**: Runtime library is like a toolbox - it provides tools that Pascal programs need but the compiler can't create from scratch.

### 2. Pascal Runtime Requirements

**Core Requirements**:
- **Memory Management**: Heap allocation/deallocation
- **I/O Operations**: Console input/output
- **String Operations**: String manipulation
- **Math Functions**: Basic math operations
- **System Interface**: Access to hardware

### 3. Runtime Library Design

**Interface Design**:
- **Calling Convention**: How Pascal calls runtime functions
- **Parameter Passing**: Register or stack-based
- **Return Values**: How results are returned
- **Error Handling**: How errors are reported

**Function Categories**:
- **Memory**: `malloc`, `free`, `realloc`
- **I/O**: `write`, `read`, `writeln`, `readln`
- **Strings**: `strlen`, `strcpy`, `strcat`
- **Math**: `sin`, `cos`, `sqrt`, etc.

### 4. Compiler-Runtime Interaction

**How Compiler Uses Runtime**:
1. Compiler generates code that calls runtime functions
2. Runtime functions provide actual implementation
3. Linker connects compiler output to runtime
4. Final program includes both compiler code and runtime

**Example**:
```pascal
writeln('Hello');
```
Compiler generates: Call to runtime `writeln` function
Runtime provides: Actual serial output implementation

### 5. Basic Runtime Functions

**I/O Functions**:
- `write(value)`: Output value
- `writeln(value)`: Output value and newline
- `read(var)`: Read input
- `readln(var)`: Read input and newline

**Memory Functions**:
- `new(pointer)`: Allocate memory
- `dispose(pointer)`: Free memory

**String Functions**:
- String assignment
- String comparison
- String concatenation

### 6. Implementation Strategy

**Assembly Implementation**:
- Runtime functions written in assembly
- Optimized for 65C816
- Use system I/O (serial, etc.)
- Integrate with monitor if needed

**Testing Strategy**:
- Test runtime functions individually
- Create test programs
- Verify compiler integration
- Test with simple Pascal programs

## Implementation Approach

### Designing Runtime Interface

1. **Define Function Signatures**:
   - Function names
   - Parameters
   - Return types
   - Calling convention

2. **Implement Core Functions**:
   - Start with I/O functions
   - Add memory management
   - Add string operations
   - Add math functions

3. **Create Runtime Library**:
   - Compile runtime functions
   - Create library file
   - Link with compiler output

### Preparing for Compiler

1. **Document Interface**:
   - Runtime function specifications
   - Calling conventions
   - Memory layout
   - Error handling

2. **Test Integration**:
   - Create simple test programs
   - Verify compiler can call runtime
   - Test end-to-end compilation

## Connections to Previous Learning

- **Assembler**: Runtime written in assembly
- **Monitor**: Runtime may use monitor for I/O
- **System Architecture**: Runtime uses system resources
- **Compiler Concepts**: Runtime supports compiler output

## Next Steps

After completing runtime preparation, students will:
- Begin SuperPascal compiler implementation
- Integrate compiler with runtime
- Compile Pascal programs
- Test complete software stack

---

*Runtime library bridges high-level language and hardware*
