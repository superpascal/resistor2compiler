# Week 1-3: Review and ALU Subsystem - Theory

## Learning Objectives

By the end of this week-block, students will:
- Review all Year 1-2 concepts relevant to CPU construction
- Understand the ALU's role in a CPU
- Know how to build an adder/subtractor with flags
- Understand how the ALU integrates with registers
- Be ready to build the ALU subsystem

## Prerequisites

- Completed Years 1-2
- Understanding of:
  - Combinational logic (adders)
  - Sequential logic (registers, flip-flops)
  - Binary arithmetic
  - Two's complement

## Key Concepts

### 1. Review: Year 1-2 Foundations

**What we've built so far**:
- Logic gates and combinational circuits
- Sequential circuits (flip-flops, registers, counters)
- Memory systems (MAR, read/write operations)
- Control signals and state machines
- Bus protocols and tri-state buffers

**What we need for CPU**:
- All of the above, integrated together
- Automatic control (coming in Term 2)
- Instruction execution (coming in Term 2-3)

### 2. The Arithmetic Logic Unit (ALU)

The **ALU** is the component that performs arithmetic and logic operations.

**Functions**:
- **Addition**: Add two numbers
- **Subtraction**: Subtract two numbers (using two's complement)
- **Logic operations**: AND, OR, XOR (optional for SAP-1)
- **Flags**: Generate carry and zero flags

**Inputs**:
- Operand A (from Register A)
- Operand B (from Register B)
- Operation select (ADD or SUB)

**Outputs**:
- Result (sum or difference)
- Carry flag (C)
- Zero flag (Z)

### 3. Building the Adder

**4-bit adder**:
- Use 74HC283 4-bit full adder IC
- Or build from half-adders and full-adders
- Handles 4-bit binary addition
- Produces 4-bit sum and carry out

**Operation**:
- Input A: 4 bits from Register A
- Input B: 4 bits from Register B
- Output: 4-bit sum, carry out

### 4. Implementing Subtraction

**Two's complement method**:
- Invert all bits of B (using XOR gates)
- Add 1 (using carry in)
- Result is A - B

**Control signal**:
- **SUB**: When high, perform subtraction
- When low, perform addition

**Implementation**:
- XOR gates on B inputs (invert when SUB=1)
- Carry in = SUB (adds 1 for subtraction)

### 5. Flags: Carry and Zero

**Carry Flag (C)**:
- Set when addition produces carry out
- Set when subtraction produces borrow
- Indicates overflow in unsigned arithmetic
- Stored in a flip-flop

**Zero Flag (Z)**:
- Set when result is zero (all bits = 0)
- Detected using NOR gate on result bits
- Stored in a flip-flop

**Why flags matter**:
- Used for conditional operations (JZ - jump if zero)
- Indicate arithmetic results
- Enable program control flow

### 6. ALU Integration

**Connecting to registers**:
- Register A output → ALU input A
- Register B output → ALU input B
- ALU result → Bus → Destination register

**Control signals**:
- **AO** (A Out): Enable Register A to bus
- **BO** (B Out): Enable Register B to bus
- **SUB**: Select addition or subtraction
- **EO** (Enable Out): Enable ALU result to bus
- **AI** (A In): Load result into Register A

### 7. SAP-1 ALU Design

**SAP-1 ALU characteristics**:
- 4-bit operations (limited but sufficient)
- ADD and SUB operations only
- Carry and Zero flags
- Result always goes to Register A

**Simplifications**:
- No logic operations (AND, OR, XOR)
- Fixed 4-bit width
- Simple flag generation

**Why these choices**:
- Keeps design manageable
- Teaches core concepts
- Can be extended later

### 8. Testing the ALU

**Test cases**:
- Addition: 5 + 3 = 8 (C=0, Z=0)
- Addition with carry: 8 + 9 = 1 (C=1, Z=0)
- Subtraction: 8 - 3 = 5 (C=0, Z=0)
- Subtraction to zero: 8 - 8 = 0 (C=1, Z=1)
- Subtraction with borrow: 3 - 5 = -2 (two's complement)

**Verification**:
- Check result matches expected
- Check flags are correct
- Test edge cases (0, maximum values)

## Mathematical Foundations

### Binary Addition

**Rules**:
- 0 + 0 = 0
- 0 + 1 = 1
- 1 + 0 = 1
- 1 + 1 = 0 with carry 1

**Example**: 5 + 3
```
  0101  (5)
+ 0011  (3)
------
  1000  (8)
```

### Two's Complement Subtraction

**Method**:
1. Invert all bits of subtrahend
2. Add 1
3. Add to minuend

**Example**: 8 - 3
```
  1000  (8)
+ 1101  (-3, two's complement of 3)
------
  0101  (5, with carry out = 1)
```

## Common Misconceptions

1. **"ALU is just an adder"**: It performs multiple operations (add, subtract, flags)
2. **"Flags are optional"**: They're essential for conditional operations
3. **"Subtraction is different from addition"**: It's addition with two's complement
4. **"ALU needs to be complex"**: Simple ALU teaches core concepts

## Connections to Year 1-2

- **Adders**: Built in Year 1, now integrated
- **Registers**: Built in Year 1, now connected to ALU
- **Buses**: Learned in Year 1, now used for ALU connections
- **Control signals**: Learned in Year 2, now controlling ALU

## Connections to Term 2-3

- **Control Unit**: Will generate ALU control signals automatically
- **Instructions**: ADD and SUB will be CPU instructions
- **Programs**: Will use ALU for calculations
- **Complete CPU**: ALU is core component of data path

## Next Steps

After building the ALU, students will:
- Build register file (Weeks 5-8)
- Build memory subsystem (Weeks 9-12)
- Integrate everything into complete data path
- Prepare for control unit (Term 2)

---

*The ALU is the computational heart of the CPU*
