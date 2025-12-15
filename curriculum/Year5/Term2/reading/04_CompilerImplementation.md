# Chapter 4: SuperPascal Compiler Implementation

## Introduction

A compiler translates high-level language to machine code. This chapter explains how to configure and extend the SuperPascal compiler for the 65C816 system.

## Compiler Overview

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

## SuperPascal Compiler

**SuperPascal**:
- Subset of Pascal
- Based on Per Brinch Hansen's work
- Concise and educational
- Suitable for embedded systems

**Target configuration**:
- Configure for 65C816
- Set calling conventions
- Link runtime library
- Generate assembly code

## Calling Conventions

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

## Runtime Library

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

## Compiler Extensions

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

## Testing the Compiler

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

## Practice Questions

1. What is a compiler?
2. How does it work?
3. How do we configure it?
4. How do we extend it?
5. How do we test it?

## Key Takeaways

- Compiler translates high-level to machine code
- Configuration is critical
- Extensions add functionality
- Testing verifies correctness
- Enables high-level programming

---

*Compiler implementation enables high-level programming on custom hardware*
