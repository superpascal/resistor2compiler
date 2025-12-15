# Lab 9-12: Pascal Runtime and Language Prep

## Lab Overview

In this lab, students will design and implement a Pascal runtime library. The runtime provides low-level support functions that Pascal programs need but the compiler can't generate directly.

## Learning Objectives

- Design Pascal runtime library interface
- Implement I/O runtime functions
- Implement memory management functions
- Implement string operation functions
- Test runtime library integration
- Prepare for compiler integration

## Prerequisites

- Assembler and toolchain working (Lab 5-8)
- Understanding of Pascal language basics
- Understanding of function calling conventions
- Experience with assembly programming

## Materials

### Components
- Complete 65C816 system
- Serial interface
- Development PC

### Tools
- Assembler (ca65 or similar)
- Linker
- Text editor
- Serial terminal

## Safety

- Test runtime functions individually
- Verify function behavior before integration
- Use monitor to debug runtime functions

## Lab Sessions

### Session 1: Runtime Design and Interface (Week 9)

**Objective**: Design runtime library interface

**Steps**:
1. Review Pascal runtime requirements
2. Define function categories (I/O, memory, strings, math)
3. Design function signatures
4. Define calling convention
5. Create function stubs
6. Document interface
7. Create test plan

**Expected Result**: Complete runtime interface design and documentation

**Troubleshooting**:
- If interface unclear: Review Pascal requirements, compiler needs
- If calling convention wrong: Check 65C816 ABI, compiler expectations

### Session 2: I/O Runtime Functions (Week 10)

**Objective**: Implement I/O runtime functions

**Steps**:
1. Implement `write` function
   - Accept value parameter
   - Convert to string
   - Output via serial
2. Implement `writeln` function
   - Call write, add newline
3. Implement `read` function
   - Read from serial
   - Convert to value
   - Return value
4. Implement `readln` function
   - Read until newline
5. Test I/O functions
6. Test with different data types

**Expected Result**: I/O functions working correctly

**Troubleshooting**:
- If output wrong: Check conversion, serial output
- If input wrong: Check serial input, conversion
- If formatting wrong: Check number formatting logic

### Session 3: Memory and String Functions (Week 11)

**Objective**: Implement memory and string runtime functions

**Steps**:
1. Implement heap management
   - Initialize heap
   - Track free memory
2. Implement `new` function
   - Allocate memory from heap
   - Return pointer
3. Implement `dispose` function
   - Free memory back to heap
4. Implement string functions
   - String length
   - String copy
   - String concatenation
   - String comparison
5. Test memory functions
6. Test string functions

**Expected Result**: Memory and string functions working

**Troubleshooting**:
- If allocation fails: Check heap management, memory available
- If strings wrong: Check string representation, functions
- If memory leaks: Check dispose implementation

### Session 4: Runtime Integration and Testing (Week 12)

**Objective**: Integrate runtime and prepare for compiler

**Steps**:
1. Create runtime library file
2. Link runtime with test programs
3. Test complete integration
4. Create test programs that use runtime
5. Verify compiler can call runtime (if compiler available)
6. Document runtime interface
7. Create runtime usage examples
8. Prepare for compiler work

**Expected Result**: Runtime library complete and ready for compiler integration

**Troubleshooting**:
- If linking fails: Check library format, linker configuration
- If calls wrong: Check calling convention, function signatures
- If integration fails: Verify interface, test individually

## Assessment

### Practical Assessment
- Runtime interface well-designed
- I/O functions working
- Memory functions working
- String functions working
- Runtime integrates correctly
- Documentation complete

### Lab Report
Students should document:
- Runtime interface design
- Function implementations
- Calling conventions
- Testing procedures
- Integration process
- Usage examples
- Preparation for compiler

## Extension Activities

- Implement advanced functions
- Optimize runtime performance
- Add error handling
- Create runtime debugging tools
- Add profiling support
- Implement additional math functions

## Next Lab

After completing runtime preparation, students move to SuperPascal compiler implementation (Year 5 Term 2).

---

*Runtime library bridges high-level language and hardware*
