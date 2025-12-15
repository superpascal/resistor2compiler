# Week 13-15: Sequential Logic - Theory

## Learning Objectives

After reading this material, you will understand:
- The difference between combinational and sequential logic
- How latches and flip-flops store data
- How SR latches work
- How D flip-flops work
- How to build multi-bit registers
- How clocked storage works
- How computers remember data

## Combinational vs Sequential Logic

### Combinational Logic (Review)

**Combinational logic**:
- Output depends **ONLY** on current inputs
- No memory of past states
- Examples: Adders, multiplexers, decoders
- **Key**: Same inputs → same outputs (always)

**Characteristics**:
- No feedback
- No memory
- Instant response
- Output = function of inputs only

### Sequential Logic (New!)

**Sequential logic**:
- Output depends on current inputs **AND** past state
- **Has memory!**
- Examples: Counters, registers, memory
- **Key**: Same inputs → different outputs (depends on history)

**Characteristics**:
- Has feedback
- Has memory
- State-dependent
- Output = function of inputs + state

### Why We Need Sequential Logic

**Computers need to remember**:
- Store data (variables, registers)
- Track state (counters, state machines)
- Remember history (program execution)
- Without memory, computers can't work!

**Real-world Analogy**:
- **Combinational**: Light switch (on/off based on position)
- **Sequential**: Toggle switch (remembers last state)

## The Problem: How to Store a Bit?

### The Challenge

**We need to "remember" a 0 or 1**:
- Combinational logic can't do this
- Need feedback!
- Need controlled storage

### Simple Attempt (Won't Work)

**Connect output back to input**:
- Problem: Creates unstable loop
- Oscillates or settles to wrong state
- Need controlled feedback

### Solution: Latches and Flip-Flops!

**Latches**: Basic storage elements
- Can store one bit
- Simple but can be unstable

**Flip-Flops**: Improved storage elements
- Clocked (controlled timing)
- More stable
- Industry standard

## SR Latch

### What is an SR Latch?

**SR Latch** = Set-Reset latch
- Simplest memory element
- Two inputs: S (Set), R (Reset)
- Two outputs: Q, NOT Q (complementary)
- Stores one bit

### SR Latch Truth Table

| S | R | Q | Q̅ | Action |
|---|---|---|---|--------|
| 0 | 0 | Last | Last | Hold (remember) |
| 0 | 1 | 0 | 1 | Reset (clear) |
| 1 | 0 | 1 | 0 | Set (store 1) |
| 1 | 1 | ? | ? | **Forbidden!** |

### How It Works

**Built from two NOR gates** (or two NAND gates):
- Output of one gate feeds input of other
- Creates feedback loop
- Controlled by S and R inputs

**Behavior**:
- **S=1, R=0**: Sets Q=1 (stores 1)
- **S=0, R=1**: Resets Q=0 (stores 0)
- **S=0, R=0**: Holds current state (remembers!)
- **S=1, R=1**: Forbidden (unstable!)

### The Forbidden State

**S=1, R=1 is forbidden**:
- Both outputs try to be 0
- When both go to 0, state becomes undefined
- Can cause unpredictable behavior
- **Never use this combination!**

### Why Latches Have Problems

**Problems with latches**:
- Can change anytime (no control)
- Forbidden states
- Race conditions
- Not suitable for complex systems

**Solution**: Clocked flip-flops!

## D Flip-Flop

### What is a D Flip-Flop?

**D Flip-Flop** = Data flip-flop
- Improved over latch
- **Clocked** (controlled timing)
- One data input (D)
- One clock input (CLK)
- Two outputs: Q, NOT Q

### How It Works

**Operation**:
- When clock is LOW: Holds current state (ignores D)
- When clock goes HIGH: Samples D input
- When clock goes LOW: Stores sampled value
- **Edge-triggered**: Changes on clock edge

**Truth Table**:
| CLK | D | Q | Q̅ | Action |
|-----|---|---|-----|--------|
| ↓→↑ | 0 | 0 | 1 | Store 0 |
| ↓→↑ | 1 | 1 | 0 | Store 1 |
| Other | X | Last | Last | Hold |

**Key**: Only changes on clock edge!

### Why D Flip-Flops are Better

**Advantages**:
- No forbidden states
- Controlled timing (clocked)
- Stable operation
- Industry standard
- Perfect for registers

**How it solves latch problems**:
- Clock controls when data is stored
- No race conditions
- Predictable behavior
- Safe for complex systems

### Clock Signals

**What is a clock?**:
- Regular pulse signal
- Synchronizes all operations
- Like a heartbeat for the computer

**Clock characteristics**:
- Frequency: How fast (Hz)
- Period: Time for one cycle
- Duty cycle: High vs low time

**Why clocks matter**:
- Synchronizes all flip-flops
- Prevents race conditions
- Makes timing predictable
- Essential for computers!

## Registers

### What is a Register?

A **register** is a group of flip-flops that store multiple bits together.

**Characteristics**:
- Multiple bits (usually 4, 8, 16, 32)
- Common clock (all change together)
- Common control signals
- Used to store data in CPUs

### Building a 4-Bit Register

**Components**:
- 4 D flip-flops
- Common clock line
- Common enable/load signal
- 4 data inputs (D₀-D₃)
- 4 data outputs (Q₀-Q₃)

**Operation**:
- When clocked: All flip-flops sample inputs together
- All bits stored simultaneously
- Outputs available immediately

### Register Applications

**In CPUs**:
- **Program Counter (PC)**: Stores current address
- **Accumulator**: Stores calculation results
- **General Purpose Registers**: Store variables
- **Instruction Register**: Stores current instruction

**Why registers matter**:
- Fast access (faster than memory)
- Temporary storage
- Essential for CPU operation

## Timing Diagrams

### What are Timing Diagrams?

**Timing diagrams** show signals over time:
- Clock signal
- Input signals
- Output signals
- Relationships between them

### Reading Timing Diagrams

**Key elements**:
- **Time axis**: Horizontal (left to right)
- **Signal levels**: Vertical (HIGH/LOW)
- **Clock edges**: Rising (↑) and falling (↓)
- **Setup time**: Data must be stable before clock
- **Hold time**: Data must stay stable after clock

### Example: D Flip-Flop Timing

**What happens**:
1. D input changes
2. Wait for clock edge
3. On clock edge: Q updates to D value
4. Q holds value until next clock edge

**Key timing**:
- Setup time: D must be stable before clock
- Hold time: D must stay stable after clock
- Propagation delay: Time for Q to update

## Key Concepts Summary

1. **Combinational logic**: No memory, instant response
2. **Sequential logic**: Has memory, state-dependent
3. **SR latch**: Basic storage, has problems
4. **D flip-flop**: Clocked storage, industry standard
5. **Registers**: Multiple flip-flops, store data
6. **Clock signals**: Synchronize operations
7. **Timing diagrams**: Show signal relationships

## Questions to Think About

Before the lab, think about:
1. Why do computers need sequential logic?
2. What's the difference between latch and flip-flop?
3. Why is S=1, R=1 forbidden in SR latch?
4. How does clock control flip-flop operation?
5. Why are registers important in CPUs?

## Next Steps

After reading this theory:
1. Review the key concepts
2. Understand latch vs flip-flop
3. Understand clock operation
4. Read the lab material
5. Come to lab ready to build!

---

*Theory helps you understand - labs help you build!*
