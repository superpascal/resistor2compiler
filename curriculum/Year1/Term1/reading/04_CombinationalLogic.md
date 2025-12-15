# Chapter 4: Combinational Logic Circuits

## Introduction

In this chapter, you'll learn how computers perform arithmetic and select data. You'll build adders, multiplexers, and decoders - the building blocks that make computers work!

---

## Binary Number System

### Why Binary?

**Computers use binary** (base 2) because:
- Easy to represent with electronics (on/off, high/low)
- Reliable (less ambiguity than analog)
- Simple to build circuits for
- Everything in computers uses binary!

### Binary Basics

**Decimal** (base 10): 0, 1, 2, 3, 4, 5, 6, 7, 8, 9  
**Binary** (base 2): 0, 1

**Each position is a power of 2**:
- 2³ 2² 2¹ 2⁰
- 8  4  2  1

### Binary to Decimal

**Method**: Sum powers of 2 for each 1 bit

**Example**: 1011 (binary)
- 1×2³ + 0×2² + 1×2¹ + 1×2⁰
- = 8 + 0 + 2 + 1
- = 11 (decimal)

**More Examples**:
- 0000 = 0
- 0001 = 1
- 0010 = 2
- 0011 = 3
- 0100 = 4
- 0101 = 5
- 0110 = 6
- 0111 = 7
- 1000 = 8
- 1001 = 9
- 1010 = 10
- 1011 = 11
- 1100 = 12
- 1101 = 13
- 1110 = 14
- 1111 = 15

### Decimal to Binary

**Method**: Repeated division by 2

**Example**: 11 (decimal)
- 11 ÷ 2 = 5 remainder 1
- 5 ÷ 2 = 2 remainder 1
- 2 ÷ 2 = 1 remainder 0
- 1 ÷ 2 = 0 remainder 1
- Read remainders backwards: 1011

---

## Addition in Binary

### How Addition Works

**Binary addition** is like decimal addition, but simpler:
- 0 + 0 = 0
- 0 + 1 = 1
- 1 + 0 = 1
- 1 + 1 = 10 (binary) = 2 (decimal)
  - Sum = 0, Carry = 1

**Example**: 5 + 3 = 8
- 0101 (5)
- + 0011 (3)
- = 1000 (8)

### The Problem

When adding two bits:
- Result: Sum bit and Carry bit
- Need circuits to handle this!

---

## Half-Adder

### What is a Half-Adder?

A **half-adder** adds two bits and produces:
- **Sum**: The result bit
- **Carry**: The carry bit (if result > 1)

### Half-Adder Truth Table

| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 |  0  |   0   |
| 0 | 1 |  1  |   0   |
| 1 | 0 |  1  |   0   |
| 1 | 1 |  0  |   1   |

### Logic

**Observation**:
- **Sum** = A XOR B
- **Carry** = A AND B

**Why?**:
- Sum is 1 when inputs differ (XOR)
- Carry is 1 when both inputs are 1 (AND)

### Limitation

**Problem**: Half-adder can't handle carry from previous bit
- Need full-adder for multi-bit addition!

---

## Full-Adder

### What is a Full-Adder?

A **full-adder** adds three bits:
- Two input bits (A, B)
- One carry-in bit (Cin)
- Produces: Sum and Carry-out (Cout)

### Full-Adder Truth Table

| A | B | Cin | Sum | Cout |
|---|---|-----|-----|------|
| 0 | 0 |  0  |  0  |  0   |
| 0 | 0 |  1  |  1  |  0   |
| 0 | 1 |  0  |  1  |  0   |
| 0 | 1 |  1  |  0  |  1   |
| 1 | 0 |  0  |  1  |  0   |
| 1 | 0 |  1  |  0  |  1   |
| 1 | 1 |  0  |  0  |  1   |
| 1 | 1 |  1  |  1  |  1   |

### Logic

**Sum** = A XOR B XOR Cin  
**Cout** = (A AND B) OR (Cin AND (A XOR B))

**How it works**:
- First add A and B (half-adder)
- Then add result to Cin (another half-adder)
- Combine carries

### Building Multi-Bit Adders

**2-bit adder**:
- Use two full-adders
- First: Add A₀ + B₀ (no carry-in)
- Second: Add A₁ + B₁ (with carry from first)

**4-bit adder**:
- Use four full-adders
- Chain them together
- Carry ripples through

**Example**: 5 + 3 = 8
- A = 0101, B = 0011
- Bit 0: 1 + 1 = 0, carry 1
- Bit 1: 0 + 1 + carry = 0, carry 1
- Bit 2: 1 + 0 + carry = 0, carry 1
- Bit 3: 0 + 0 + carry = 1
- Result: 1000 = 8

---

## 4-Bit Adder IC

### Why Use an IC?

**Building 4-bit adder from gates**:
- 4 full-adders = many gates!
- Complex wiring
- Slow to build

**Using IC**:
- All built-in
- Fast, reliable
- Industry standard

### 74HC283 4-Bit Adder

**Features**:
- 4-bit binary addition
- Fast carry propagation
- Two 4-bit inputs
- One 4-bit output
- Carry-in and Carry-out
- Can cascade for 8-bit, 16-bit addition

**How to use**:
- Connect two 4-bit numbers
- Get 4-bit sum
- Carry-out for overflow

**Cascading**:
- Connect carry-out to next adder's carry-in
- Build 8-bit, 16-bit, 32-bit adders!

---

## Multiplexers

### What is a Multiplexer?

A **multiplexer** (MUX) is a "data selector"
- Chooses one input from many
- Like a switch that selects which input to connect to output

### Real-World Analogy

- **TV remote**: Selects which input (HDMI1, HDMI2, etc.)
- **Radio tuner**: Selects which station
- **Computer bus**: Selects which device to read from

### 2-to-1 Multiplexer

**Function**:
- 2 data inputs (I₀, I₁)
- 1 select input (S)
- 1 output (Y)

**Behavior**:
- If S = 0, output = I₀
- If S = 1, output = I₁

**Truth Table**:
| S | Y |
|---|---|
| 0 | I₀ |
| 1 | I₁ |

### Logic

**Y = (NOT S AND I₀) OR (S AND I₁)**

**How it works**:
- When S = 0: Y = I₀ (I₁ is blocked)
- When S = 1: Y = I₁ (I₀ is blocked)

### Applications

**Bus Selection**:
- Select between Register A and Register B
- Common in CPU design!

**Data Routing**:
- Route data to different destinations
- Select which path to use

---

## Decoders

### What is a Decoder?

A **decoder** is an "address selector"
- Takes binary address, selects one output
- Like a "one-hot" selector
- Opposite of multiplexer

### 2-to-4 Decoder

**Function**:
- 2 address inputs (A₀, A₁)
- 4 outputs (Y₀, Y₁, Y₂, Y₃)
- Only one output is active (1) at a time
- Which output = address value

**Truth Table**:
| A₁ | A₀ | Y₃ | Y₂ | Y₁ | Y₀ |
|----|----|----|----|----|----|
| 0  | 0  |  0 |  0 |  0 |  1 |
| 0  | 1  |  0 |  0 |  1 |  0 |
| 1  | 0  |  0 |  1 |  0 |  0 |
| 1  | 1  |  1 |  0 |  0 |  0 |

### Logic

**Y₀ = NOT A₁ AND NOT A₀**  
**Y₁ = NOT A₁ AND A₀**  
**Y₂ = A₁ AND NOT A₀**  
**Y₃ = A₁ AND A₀**

### Applications

**Memory Selection**:
- Use decoder to select memory chips
- Address bits select which chip
- Enable line can disable all

**I/O Device Selection**:
- Select which I/O device to access
- Address maps to device

---

## Key Takeaways

1. **Binary numbers**: Base 2 system
2. **Half-adder**: Adds two bits
3. **Full-adder**: Adds three bits (with carry)
4. **Multi-bit adders**: Chain full-adders
5. **4-bit adder IC**: Ready-made solution
6. **Multiplexers**: Select data
7. **Decoders**: Select addresses
8. **Applications**: Used throughout computers

## Practice Questions

1. Convert 1010 (binary) to decimal.
   - Answer: 10

2. What is the sum and carry for 1 + 1 in binary?
   - Answer: Sum = 0, Carry = 1

3. Why do we need full-adders instead of half-adders?
   - Answer: To handle carry from previous bits

4. What does a multiplexer do?
   - Answer: Selects one input from many

5. What's the difference between multiplexer and decoder?
   - Answer: MUX selects data, decoder selects address

## What's Next?

After reading this chapter:
1. Review the key concepts
2. Practice binary arithmetic
3. Understand adder operation
4. Read the lab material
5. Come to lab ready to build!

---

*Understanding combinational logic helps you understand computer arithmetic!*
