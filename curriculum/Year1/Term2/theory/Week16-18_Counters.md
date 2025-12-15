# Week 16-18: Binary Counters - Theory

## Learning Objectives

After reading this material, you will understand:
- What counters are and how they work
- How to build counters from flip-flops
- How counter ICs work
- What modulo counting is
- How program counters work in CPUs
- How counters relate to CPU operation

## What is a Counter?

### Counter Definition

A **counter** is a sequential circuit that counts:
- Outputs represent count value
- Increments on each clock pulse
- Can count up, down, or both
- Stores current count value

### Types of Counters

**Binary Counter**:
- Counts in binary (0, 1, 2, 3, 4...)
- Most common type
- Used in CPUs

**Decimal Counter**:
- Counts 0-9, then wraps to 0
- Used in displays

**Modulo Counter**:
- Counts 0 to N-1, then wraps
- Can count to any number
- Example: Modulo-10 counts 0-9

### Applications

**In Computers**:
- **Program Counter (PC)**: Tracks instruction address
- **Frequency dividers**: Divide clock frequency
- **Timers**: Measure time intervals
- **Event counters**: Count events

**Real-world**:
- Digital clocks
- Frequency counters
- Event timers
- Address generation

## Building Counters from Flip-Flops

### Basic Concept

**Chain D flip-flops**:
- Each flip-flop divides frequency by 2
- Q output of one → clock of next
- Creates binary counting pattern

### 2-bit Counter

**How it works**:
- Two D flip-flops
- First: Toggles on each clock
- Second: Toggles when first wraps
- Counts: 00 → 01 → 10 → 11 → 00

**Pattern**:
- Bit 0: Toggles every clock (0, 1, 0, 1...)
- Bit 1: Toggles every 2 clocks (0, 0, 1, 1...)
- 2-bit = counts 0-3 (4 states)

### 4-bit Counter

**How it works**:
- Four D flip-flops chained
- Each divides by 2
- Counts: 0000 → 0001 → ... → 1111 → 0000
- 4-bit = counts 0-15 (16 states)

**Pattern**:
- Bit 0: Every clock
- Bit 1: Every 2 clocks
- Bit 2: Every 4 clocks
- Bit 3: Every 8 clocks

## Counter ICs

### Why Use Counter ICs?

**Building from flip-flops**:
- Complex wiring
- Many components
- Time-consuming

**Using ICs**:
- All built-in
- Additional features
- Fast, reliable
- Industry standard

### 74HC161 4-bit Counter

**Features**:
- 4-bit binary counter
- Counts 0-15
- Synchronous operation
- Load input (preset value)
- Reset input (clear to 0)
- Enable inputs (control counting)
- Ripple carry output

**Operation**:
- Counts up on clock edge
- Can load preset value
- Can reset to 0
- Can enable/disable counting

### 74HC163 4-bit Counter

**Similar to 74HC161**:
- Synchronous reset (vs asynchronous)
- More predictable timing
- Better for complex systems

## Modulo Counting

### What is Modulo?

**Modulo** = Count to N, then wrap to 0

**Examples**:
- Modulo-4: Counts 0, 1, 2, 3, 0, 1, 2, 3...
- Modulo-10: Counts 0-9, then wraps
- Modulo-16: Counts 0-15, then wraps (4-bit counter)

### How to Create Modulo Counter

**Method 1: Reset on Count**
- Count until target
- Detect target value
- Reset to 0
- Repeat

**Method 2: Load on Count**
- Count until target
- Detect target value
- Load 0 (or start value)
- Repeat

**Example: Modulo-10 Counter**
- Count 0-9
- When count = 9, next clock → load 0
- Counts: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 0...

## Program Counter

### What is a Program Counter?

**Program Counter (PC)**:
- Special register in CPU
- Stores address of current instruction
- Increments after each instruction
- Points to next instruction to execute

### How It Works

**Operation**:
1. PC holds current address
2. CPU fetches instruction from that address
3. PC increments (points to next)
4. Repeat

**Example**:
- PC = 0: Fetch instruction at address 0
- PC = 1: Fetch instruction at address 1
- PC = 2: Fetch instruction at address 2
- PC = 3: Fetch instruction at address 3

### Program Counter Features

**Increment**:
- Normal operation: PC = PC + 1
- Sequential execution

**Load**:
- Jump instruction: PC = new address
- Branch to different location

**Reset**:
- Start of program: PC = 0
- Begin execution

### Why Program Counter Matters

**Essential for CPU**:
- Tracks execution
- Enables sequential programs
- Enables jumps and branches
- Without PC, CPU can't execute programs!

## Counter Timing

### Timing Diagrams

**What they show**:
- Clock signal
- Counter outputs
- When counter changes
- Counting sequence

### Synchronous vs Asynchronous

**Synchronous Counters**:
- All flip-flops change together
- Controlled by common clock
- More predictable
- Better for complex systems

**Asynchronous Counters**:
- Flip-flops change sequentially
- Ripple through
- Simpler but slower
- Can have timing issues

## Key Concepts Summary

1. **Counters**: Sequential circuits that count
2. **Binary counters**: Count in binary
3. **Counter ICs**: Ready-made solutions
4. **Modulo counting**: Count to N, then wrap
5. **Program Counter**: Tracks instruction address
6. **Timing**: Synchronous vs asynchronous

## Questions to Think About

Before the lab, think about:
1. How do counters relate to registers?
2. Why do CPUs need program counters?
3. How does modulo counting work?
4. What's the difference between synchronous and asynchronous?
5. How do counters divide frequency?

## Next Steps

After reading this theory:
1. Review the key concepts
2. Understand counter operation
3. Understand program counter concept
4. Read the lab material
5. Come to lab ready to build!

---

*Theory helps you understand - labs help you build!*
