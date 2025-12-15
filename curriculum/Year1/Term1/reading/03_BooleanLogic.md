# Chapter 3: Boolean Logic

## Introduction

Welcome to the world of Boolean logic! This is the foundation of all digital circuits and computers. In this chapter, you'll learn how computers think in terms of true and false, on and off, 1 and 0.

---

## What is Boolean Logic?

### The Binary World

**Binary** = Base 2 number system
- Only two values: **0** and **1**
- 0 = False, Low, Off, No
- 1 = True, High, On, Yes

**Why binary?**:
- Easy to represent with electronics (on/off)
- Reliable (less ambiguity than analog)
- Simple to build circuits for
- Everything in computers uses binary!

### Boolean Logic

**Boolean logic** is the mathematics of true and false. It's named after George Boole, a mathematician who developed this system.

**Why it matters**:
- Computers work with only 0 and 1
- All digital circuits use Boolean logic
- Foundation of computer science
- Everything in computers is built from this!

### Real-World Analogies

**AND**: "Both must be true"
- Like a security system needing two keys
- Both keys needed to open door

**OR**: "Either one is true"
- Like a door that opens with key OR code
- Either method works

**NOT**: "Opposite"
- Like a light switch (on becomes off)
- Inverts the input

---

## Logic Gates

### What is a Logic Gate?

A **logic gate** is an electronic circuit that performs a Boolean operation. It takes inputs (0 or 1) and produces an output (0 or 1).

**Key properties**:
- Digital (only 0 or 1, no in-between)
- Fast switching
- Reliable operation
- Building blocks of computers

### Basic Logic Gates

#### AND Gate

**Symbol**: D-shaped with inputs on left, output on right

**Behavior**:
- Output = 1 only if **ALL** inputs = 1
- Output = 0 if **ANY** input = 0

**Truth Table** (2 inputs):
| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   0    |
| 1 | 0 |   0    |
| 1 | 1 |   1    |

**Real-world**: "Both conditions must be true"

**Example**: Security system
- Door closed AND Motion detected → Alarm
- Both must be true for alarm

#### OR Gate

**Symbol**: Curved shape

**Behavior**:
- Output = 1 if **ANY** input = 1
- Output = 0 only if **ALL** inputs = 0

**Truth Table** (2 inputs):
| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   1    |

**Real-world**: "Either condition is true"

**Example**: Door lock
- Key OR Code → Door opens
- Either method works

#### NOT Gate (Inverter)

**Symbol**: Triangle with circle on output

**Behavior**:
- Output = **opposite** of input
- Only one input

**Truth Table**:
| Input | Output |
|-------|--------|
|   0   |   1    |
|   1   |   0    |

**Real-world**: "Opposite of input"

**Example**: Light switch
- Switch ON → Light OFF (if inverted)
- Switch OFF → Light ON (if inverted)

### Combined Gates

#### NAND Gate (NOT AND)

**Behavior**: Opposite of AND
- Output = 0 only if ALL inputs = 1
- Output = 1 otherwise

**Truth Table**:
| A | B | Output |
|---|---|--------|
| 0 | 0 |   1    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   0    |

**Important**: NAND is "universal" - you can build **ANY** gate from NAND gates!

#### NOR Gate (NOT OR)

**Behavior**: Opposite of OR
- Output = 1 only if ALL inputs = 0
- Output = 0 otherwise

**Truth Table**:
| A | B | Output |
|---|---|--------|
| 0 | 0 |   1    |
| 0 | 1 |   0    |
| 1 | 0 |   0    |
| 1 | 1 |   0    |

**Important**: NOR is also "universal"!

#### XOR Gate (Exclusive OR)

**Behavior**: "One or the other, but not both"
- Output = 1 if inputs are **DIFFERENT**
- Output = 0 if inputs are **SAME**

**Truth Table**:
| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   0    |

**Real-world**: "Either one, but not both"

**Example**: Parity checking, addition

---

## Truth Tables

### What is a Truth Table?

A **truth table** shows all possible input combinations and their corresponding outputs. It's a complete description of a logic function.

### How to Build Truth Tables

**For 2 inputs** (A, B):
- 2² = 4 possible combinations
- List all: 00, 01, 10, 11
- Calculate output for each

**For 3 inputs** (A, B, C):
- 2³ = 8 possible combinations
- List all: 000, 001, 010, 011, 100, 101, 110, 111
- Calculate output for each

**Pattern**: n inputs = 2ⁿ combinations

### Example: Complex Logic

**Function**: (A AND B) OR (NOT C)

**Truth Table**:
| A | B | C | A AND B | NOT C | Output |
|---|---|---|---------|--------|--------|
| 0 | 0 | 0 |    0    |   1   |   1    |
| 0 | 0 | 1 |    0    |   0   |   0    |
| 0 | 1 | 0 |    0    |   1   |   1    |
| 0 | 1 | 1 |    0    |   0   |   0    |
| 1 | 0 | 0 |    0    |   1   |   1    |
| 1 | 0 | 1 |    0    |   0   |   0    |
| 1 | 1 | 0 |    1    |   1   |   1    |
| 1 | 1 | 1 |    1    |   0   |   1    |

---

## Combining Gates

### Building Complex Logic

**Example 1**: Security System
- "Alarm sounds if (door open AND motion detected) OR (window open)"
- Circuit: (Door AND Motion) OR Window

**Example 2**: Voting Machine
- "Motion passes if at least 2 of 3 agree"
- Circuit: (A AND B) OR (A AND C) OR (B AND C)

**Example 3**: Light Control
- "Light on if (switch A OR switch B) AND NOT (override switch)"
- Circuit: (A OR B) AND NOT Override

### How to Combine

1. **Break problem into parts**
2. **Build each part with gates**
3. **Connect parts together**
4. **Test thoroughly**

---

## Boolean Algebra

### Basic Laws

**Identity Laws**:
- A AND 0 = 0
- A AND 1 = A
- A OR 0 = A
- A OR 1 = 1

**Complement Laws**:
- A AND (NOT A) = 0 (always false)
- A OR (NOT A) = 1 (always true)

### Simplification

**Goal**: Reduce number of gates needed

**Example**:
- Original: (A AND B) OR (A AND C)
- Simplified: A AND (B OR C)
- **Saves**: One AND gate!

**Why simplify?**:
- Fewer components
- Lower cost
- Faster operation
- Less power

---

## Diode Logic

### What is Diode Logic?

**Diode logic** uses diodes to build logic gates. It's a simple way to understand how gates work.

### Diodes

**What is a diode?**:
- One-way current flow
- Forward bias: Conducts (like closed switch)
- Reverse bias: Blocks (like open switch)

### Diode-OR Gate

**Simplest logic gate**:
- Two diodes, one resistor
- Output = A OR B (simplified)

**How it works**:
- If input A = HIGH: Diode conducts, output = HIGH
- If input B = HIGH: Diode conducts, output = HIGH
- If both LOW: Resistor pulls output LOW

**Limitations**:
- Voltage drop across diodes
- Not perfect logic levels
- Can't easily make AND gate

### Why Learn Diode Logic?

- Understand how gates work inside
- Historical importance
- Shows gates are just components!
- Foundation for understanding ICs

### Why ICs are Better

**Problems with diode logic**:
- Voltage drop
- Can't make AND easily
- Not as reliable
- Slower

**Why ICs are better**:
- Precise voltage levels
- Fast switching
- Reliable
- Many gates in one package

---

## Key Takeaways

1. **Boolean logic**: Mathematics of true/false
2. **Logic gates**: Electronic circuits for Boolean operations
3. **Truth tables**: Complete description of logic functions
4. **Combining gates**: Build complex logic
5. **Boolean algebra**: Simplify circuits
6. **Diode logic**: Simple gate construction
7. **IC gates**: Better than diode logic

## Practice Questions

1. What is the output of AND gate when inputs are 1 and 0?
   - Answer: 0 (AND needs both to be 1)

2. What is the difference between OR and XOR?
   - Answer: OR = either, XOR = one or the other (not both)

3. Why is NAND "universal"?
   - Answer: You can build any gate from NAND gates

4. How many combinations for 3 inputs?
   - Answer: 2³ = 8 combinations

5. Why do computers use binary?
   - Answer: Easy for electronics, reliable, simple

## What's Next?

After reading this chapter:
1. Review the key concepts
2. Practice truth tables
3. Understand gate behavior
4. Read the lab material
5. Come to lab ready to build!

---

*Understanding Boolean logic helps you understand computers!*
