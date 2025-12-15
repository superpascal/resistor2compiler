# Week 22-24: ALU Subsystem - Theory

## Learning Objectives

After reading this material, you will understand:
- What an ALU is and what it does
- How to integrate adder, registers, and bus
- How to build carry and zero flags
- How subtraction works (two's complement)
- How to build a complete data path
- How ALU relates to CPU design

## What is an ALU?

### ALU Definition

**ALU (Arithmetic Logic Unit)**:
- Performs arithmetic and logic operations
- Core of CPU
- Takes two inputs, produces result
- Generates flags (carry, zero, etc.)

### ALU Operations

**Arithmetic**:
- Addition (A + B)
- Subtraction (A - B)
- (Advanced: Multiplication, division)

**Logic**:
- AND (A AND B)
- OR (A OR B)
- XOR (A XOR B)
- NOT (NOT A)

### ALU Components

**Inputs**:
- Register A (first operand)
- Register B (second operand)
- Operation select (which operation)

**Outputs**:
- Result (operation result)
- Flags (carry, zero, overflow, etc.)

## ALU Subsystem Design

### Block Diagram

```
Register A ──┐
             ├──→ Adder ──→ Result ──→ Bus ──→ Register A (store)
Register B ──┘              │
                            ├──→ Flags (Carry, Zero)
                            │
```

### Components Needed

**Registers**:
- Register A: First operand
- Register B: Second operand
- Result can go back to Register A

**Adder**:
- Performs A + B
- 4-bit adder (74HC283)

**Bus**:
- Connects all components
- Tri-state buffers control access

**Flags**:
- Carry flag: Overflow from addition
- Zero flag: Result is zero

## Addition Operation

### How Addition Works

**Operation**:
1. Load Register A with first number
2. Load Register B with second number
3. Enable both to bus
4. Adder adds A + B
5. Result goes to bus
6. Store result in Register A

**Example**: 5 + 3 = 8
- Register A = 0101 (5)
- Register B = 0011 (3)
- Adder output = 1000 (8)
- Result stored in Register A

## Subtraction Operation

### The Problem

**Subtraction is harder**:
- Can't directly subtract in binary
- Need special method

### Two's Complement

**Method**: A - B = A + (-B)

**How to get -B**:
1. Invert all bits (one's complement)
2. Add 1
3. Result is two's complement (negative)

**Example**: 5 - 3 = 5 + (-3)
- 3 = 0011
- Invert = 1100
- Add 1 = 1101 (-3 in two's complement)
- 5 + (-3) = 0101 + 1101 = 10010
- Ignore carry = 0010 (2) ✓

### Building Subtraction

**Circuit**:
- XOR gates: Invert B when subtracting
- Add 1: Use carry-in of adder
- Select: Addition or subtraction

**Operation**:
- Add mode: B passes through, carry-in = 0
- Subtract mode: B inverted, carry-in = 1

## Flags

### Carry Flag

**What it is**:
- Indicates overflow from addition
- Set when result > maximum value
- Example: 15 + 1 = 16 (needs 5 bits, carry = 1)

**How to build**:
- Use carry-out from adder
- Store in flip-flop
- Can be read by CPU

### Zero Flag

**What it is**:
- Indicates result is zero
- Set when all result bits = 0
- Useful for comparisons

**How to build**:
- NOR all result bits
- If all 0 → output = 1 (zero flag set)
- Store in flip-flop

### Why Flags Matter

**CPU uses flags**:
- Conditional jumps (if zero, jump)
- Comparisons (A > B?)
- Overflow detection
- Essential for programming!

## Data Path

### Complete Data Path

**Components**:
- Registers (A, B)
- Adder/ALU
- Bus system
- Flags
- Control logic

**Operation Flow**:
1. Load operands into registers
2. Select operation (add/subtract)
3. Enable registers to bus
4. ALU performs operation
5. Result to bus
6. Store result
7. Update flags

### Control Signals

**Needed signals**:
- Register A enable
- Register B enable
- ALU operation select
- Result store enable
- Flag update enable

**Control logic**:
- Decoder selects operation
- Ensures correct sequence
- Prevents conflicts

## Integration

### Putting It All Together

**Complete subsystem**:
- All components connected
- Bus connects everything
- Control logic coordinates
- Flags provide feedback

**Testing**:
- Test addition: 5 + 3 = 8
- Test subtraction: 5 - 3 = 2
- Test flags: Carry, zero
- Verify all operations

### CPU Connection

**How ALU fits in CPU**:
- Part of execution unit
- Performs calculations
- Flags control flow
- Essential for programs

## Key Concepts Summary

1. **ALU**: Arithmetic Logic Unit
2. **Operations**: Addition, subtraction, logic
3. **Two's complement**: Method for subtraction
4. **Flags**: Carry, zero, etc.
5. **Data path**: Complete operation flow
6. **Integration**: All components together

## Questions to Think About

Before the lab, think about:
1. What operations does ALU perform?
2. How does two's complement work?
3. Why are flags important?
4. How does data flow through ALU?
5. How does ALU relate to CPU?

## Next Steps

After reading this theory:
1. Review the key concepts
2. Understand ALU operation
3. Understand two's complement
4. Read the lab material
5. Come to lab ready to build!

---

*Theory helps you understand - labs help you build!*
