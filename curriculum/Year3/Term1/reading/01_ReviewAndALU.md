# Chapter 1: Review and ALU Subsystem

## Introduction

The Arithmetic Logic Unit (ALU) is the computational heart of the CPU. This chapter reviews Year 1-2 foundations and explains how to build the ALU for the SAP-1 CPU.

## Year 1-2 Foundations Review

**What we've built**:
- Logic gates and combinational circuits
- Sequential circuits (flip-flops, registers, counters)
- Memory systems (MAR, read/write operations)
- Control signals and state machines
- Bus protocols and tri-state buffers

**What we need for CPU**:
- All of the above, integrated together
- Automatic control (coming in Term 2)
- Instruction execution (coming in Term 2-3)

## The Arithmetic Logic Unit (ALU)

The **ALU** performs arithmetic and logic operations.

**Functions**:
- **Addition**: Add two numbers
- **Subtraction**: Subtract two numbers (using two's complement)
- **Flags**: Generate carry and zero flags

**Inputs**:
- Operand A (from Register A)
- Operand B (from Register B)
- Operation select (ADD or SUB)

**Outputs**:
- Result (sum or difference)
- Carry flag (C)
- Zero flag (Z)

## Building the Adder

**4-bit adder**:
- Use 74HC283 4-bit full adder IC
- Handles 4-bit binary addition
- Produces 4-bit sum and carry out

**Operation**:
- Input A: 4 bits from Register A
- Input B: 4 bits from Register B
- Output: 4-bit sum, carry out

## Implementing Subtraction

**Two's complement method**:
- Invert all bits of B (using XOR gates)
- Add 1 (using carry in)
- Result is A - B

**Control signal**:
- **SUB**: When high, perform subtraction
- When low, perform addition

## Flags: Carry and Zero

**Carry Flag (C)**:
- Set when addition produces carry out
- Set when subtraction produces borrow
- Indicates overflow in unsigned arithmetic

**Zero Flag (Z)**:
- Set when result is zero (all bits = 0)
- Detected using NOR gate on result bits
- Used for conditional operations

## Practice Questions

1. What is the ALU's role in a CPU?
2. How does two's complement subtraction work?
3. Why do we need flags?
4. How are flags generated?
5. How does the ALU integrate with registers?

## Key Takeaways

- ALU performs arithmetic operations
- Two's complement enables subtraction
- Flags indicate operation results
- ALU is core of CPU computation
- Foundation for complete CPU

---

*The ALU is the computational heart of the CPU*
