# Week 9-12: Pascal Runtime and Language Prep - Teaching Guide

## Overview

This teaching guide supports the delivery of Pascal runtime library preparation over 4 weeks. Students learn to design and implement runtime functions that support high-level language programs.

## Learning Objectives

By the end of this week-block, students will:
- Understand Pascal runtime requirements
- Design runtime library interface
- Implement basic runtime functions
- Understand compiler-runtime interaction
- Prepare for SuperPascal compiler integration

## Prerequisites Check

Before starting, ensure students:
- ✅ Assembler and toolchain working
- ✅ Understand Pascal language basics
- ✅ Understand compiler concepts
- ✅ Understand system architecture
- ✅ Can write assembly functions

## Week-by-Week Breakdown

### Week 9: Runtime Library Concepts and Design

**Theory Session (45 min)**:
- What is a runtime library?
- Pascal runtime requirements
- Runtime function categories
- Interface design principles

**Lab Session (90 min)**:
- Design runtime interface
- Define function signatures
- Create function stubs
- Document interface

**Key Points**:
- Runtime provides low-level support
- Interface must be well-defined
- Functions support compiler output

**Common Questions**:
- Q: Why do we need runtime? A: Provides functions compiler can't generate
- Q: What functions do we need? A: I/O, memory, strings, math
- Q: How do we design interface? A: Define calling convention, parameters, returns

### Week 10: I/O Runtime Functions

**Theory Session (45 min)**:
- I/O function requirements
- Serial I/O implementation
- Format conversion
- Error handling

**Lab Session (90 min)**:
- Implement `write` function
- Implement `writeln` function
- Implement `read` function
- Test I/O functions

**Key Points**:
- I/O functions use serial interface
- Must convert data formats
- Error handling important

**Common Questions**:
- Q: How does write work? A: Converts value to string, sends via serial
- Q: How does read work? A: Receives from serial, converts to value
- Q: What about formatting? A: Runtime handles number formatting

### Week 11: Memory and String Runtime Functions

**Theory Session (45 min)**:
- Memory management functions
- String operation functions
- Heap management
- String representation

**Lab Session (90 min)**:
- Implement `new` and `dispose`
- Implement string functions
- Test memory management
- Test string operations

**Key Points**:
- Memory management for dynamic allocation
- Strings need manipulation functions
- Heap must be managed

**Common Questions**:
- Q: How does new work? A: Allocates memory from heap
- Q: How does dispose work? A: Frees memory back to heap
- Q: How are strings stored? A: Length + data, or null-terminated

### Week 12: Runtime Integration and Testing

**Theory Session (45 min)**:
- Compiler-runtime integration
- Linking runtime with compiler output
- Testing strategies
- Documentation requirements

**Lab Session (90 min)**:
- Create runtime library
- Link with test programs
- Test complete integration
- Document runtime interface
- Prepare for compiler work

**Key Points**:
- Runtime must link with compiler output
- Testing ensures compatibility
- Documentation critical for compiler work

**Common Questions**:
- Q: How does compiler use runtime? A: Generates calls to runtime functions
- Q: How do we test? A: Create test programs, verify behavior
- Q: What documentation needed? A: Function specs, calling conventions

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide runtime function templates
- Step-by-step implementation guides
- Example implementations
- Extra time for concepts

**Extension for advanced students**:
- Implement advanced functions
- Optimize runtime performance
- Add error handling
- Create runtime debugging tools

### Common Misconceptions

1. **"Runtime is the compiler"**
   - Clarify: Runtime supports compiler, compiler generates code
   - Explain: Compiler and runtime work together

2. **"Runtime must be complex"**
   - Clarify: Start with basic functions, add complexity
   - Show: Simple runtime can be effective

3. **"Runtime is optional"**
   - Clarify: High-level languages need runtime
   - Explain: Runtime provides essential services

### Assessment Checkpoints

**Week 9**: Can students design runtime interface?
**Week 10**: Can students implement I/O functions?
**Week 11**: Can students implement memory/string functions?
**Week 12**: Can students integrate and test runtime?

## Resources

- Runtime library examples
- Pascal runtime specifications
- Calling convention documentation
- Test program examples

## Next Week

After completing runtime preparation, students move to SuperPascal compiler implementation (Year 5 Term 2).

---

*Runtime library bridges high-level language and hardware*
