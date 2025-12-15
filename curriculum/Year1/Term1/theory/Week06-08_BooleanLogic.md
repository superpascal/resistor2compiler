# Week 6-8: Boolean Logic - Theory

## Learning Objectives

After reading this material, you will understand:
- What Boolean logic is and why it matters
- How logic gates work (AND, OR, NOT, NAND, NOR, XOR)
- How to build truth tables
- How to combine gates for complex logic
- How to build gates from diodes
- How Boolean algebra simplifies circuits

## Boolean Logic Fundamentals

### What is Boolean Logic?

**Boolean logic** is the mathematics of true and false, on and off, 1 and 0. It's named after George Boole, a mathematician who developed this system in the 1800s.

**Why it matters**:
- Computers work with only 0 and 1
- All digital circuits use Boolean logic
- Foundation of computer science
- Everything in computers is built from this!

### Binary World

**Binary** = Base 2 number system
- Only two values: 0 and 1
- 0 = False, Low, Off, No
- 1 = True, High, On, Yes

**Why binary?**:
- Easy to represent with electronics (on/off)
- Reliable (less ambiguity than analog)
- Simple to build circuits for
- Everything in computers uses binary!

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
- Output = 1 only if ALL inputs = 1
- Output = 0 if ANY input = 0

**Truth Table** (2 inputs):
| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   0    |
| 1 | 0 |   0    |
| 1 | 1 |   1    |

**Real-world**: "Both conditions must be true"

#### OR Gate

**Symbol**: Curved shape

**Behavior**:
- Output = 1 if ANY input = 1
- Output = 0 only if ALL inputs = 0

**Truth Table** (2 inputs):
| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   1    |

**Real-world**: "Either condition is true"

#### NOT Gate (Inverter)

**Symbol**: Triangle with circle on output

**Behavior**:
- Output = opposite of input
- Only one input

**Truth Table**:
| Input | Output |
|-------|--------|
|   0   |   1    |
|   1   |   0    |

**Real-world**: "Opposite of input"

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

**Important**: NAND is "universal" - you can build ANY gate from NAND gates!

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
- Output = 1 if inputs are DIFFERENT
- Output = 0 if inputs are SAME

**Truth Table**:
| A | B | Output |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   0    |

**Applications**: Parity checking, addition (half-adder)

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

### Gate Combinations

**AND + NOT = NAND**:
- Build AND gate
- Connect output to NOT gate
- Result: NAND gate

**OR + NOT = NOR**:
- Build OR gate
- Connect output to NOT gate
- Result: NOR gate

**Multiple Gates**:
- Connect outputs of one gate to inputs of another
- Build complex functions
- Create complete systems

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

**Commutative Laws**:
- A AND B = B AND A
- A OR B = B OR A

**Associative Laws**:
- (A AND B) AND C = A AND (B AND C)
- (A OR B) OR C = A OR (B OR C)

**Distributive Laws**:
- A AND (B OR C) = (A AND B) OR (A AND C)
- A OR (B AND C) = (A OR B) AND (A OR C)

### Simplification

**Goal**: Reduce number of gates needed

**Example 1**:
- Original: (A AND B) OR (A AND C)
- Simplified: A AND (B OR C)
- Saves: One AND gate!

**Example 2**:
- Original: (A OR B) AND (A OR C)
- Simplified: A OR (B AND C)
- Saves: One OR gate!

**Why simplify?**:
- Fewer components
- Lower cost
- Faster operation
- Less power

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

### Limitations

**Problems**:
- Voltage drop
- Can't make AND easily
- Not as reliable as ICs
- Slower

**Why ICs are Better**:
- Precise voltage levels
- Fast switching
- Reliable
- Many gates in one package

## Key Concepts Summary

1. **Boolean logic**: Mathematics of true/false
2. **Logic gates**: Electronic circuits for Boolean operations
3. **Truth tables**: Complete description of logic functions
4. **Combining gates**: Build complex logic
5. **Boolean algebra**: Simplify circuits
6. **Diode logic**: Simple gate construction
7. **IC gates**: Better than diode logic

## Questions to Think About

Before the lab, think about:
1. Why do computers use binary?
2. How does AND differ from OR?
3. Why is NAND "universal"?
4. How do truth tables help design circuits?
5. Why simplify Boolean expressions?

## Next Steps

After reading this theory:
1. Review the key concepts
2. Practice truth tables
3. Understand gate behavior
4. Read the lab material
5. Come to lab ready to build!

---

*Theory helps you understand - labs help you build!*
