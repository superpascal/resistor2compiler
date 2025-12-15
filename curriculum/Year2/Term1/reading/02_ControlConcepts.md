# Chapter 2: Control Concepts and State Machines

## Introduction

Control signals tell components what to do. State machines coordinate these signals in sequence. Understanding control is essential for understanding how computers coordinate operations.

## What are Control Signals?

**Control signals** are binary signals that tell components what to do.

**Examples**:
- **MI** (MAR In): Tells MAR to load from bus
- **RO** (RAM Out): Tells memory to output data to bus
- **AI** (A Register In): Tells Register A to load from bus
- **AO** (A Register Out): Tells Register A to output to bus

**Why we need them**:
- Components need to know when to act
- Multiple components share the bus (only one can use it at a time)
- Operations must be coordinated in sequence

## The Coordination Problem

**The problem**:
- Many components, one bus
- Operations must happen in the right order
- Only one component can use the bus at a time

**The solution**:
- Control signals enable/disable components
- Signals are coordinated in time
- Signals follow a sequence (state machine)

## State Machines

A **state machine** is a system that moves through a sequence of states, with each state producing specific outputs (control signals).

**Key components**:
- **States**: Different conditions the system can be in
- **Transitions**: How the system moves between states
- **Outputs**: Control signals produced in each state
- **Inputs**: Conditions that affect state transitions

**Simple example**: Traffic light
- State 1: Red light (output: red=on, green=off, yellow=off)
- State 2: Green light (output: red=off, green=on, yellow=off)
- State 3: Yellow light (output: red=off, green=off, yellow=on)
- Transitions: Move to next state after timer expires

## Building a Sequencer

A **sequencer** is a state machine that cycles through states in order.

**Basic construction**:
- Use a counter to track current state
- Use a decoder to convert state number to control signals
- Clock advances to next state
- Reset returns to initial state

**Example**: 4-step sequencer
- Step 0: Load address into MAR (MI=1)
- Step 1: Read from memory (RO=1)
- Step 2: Load data into Register A (AI=1)
- Step 3: Output Register A (AO=1)

## Microcode Concepts

**Microcode** is low-level instructions that control the CPU's internal operations.

**Concept**:
- Each CPU instruction (like "ADD") is broken down into micro-operations
- Each micro-operation produces control signals
- Microcode ROM stores the sequence of control signals for each instruction

**Example**: LDA (Load A) instruction
- Micro-step 1: CO (Counter Out), MI (MAR In) - fetch instruction address
- Micro-step 2: RO (RAM Out), II (Instruction In) - load instruction
- Micro-step 3: (decode instruction - determine it's LDA)
- Micro-step 4: CO, MI - fetch data address
- Micro-step 5: RO, AI - load data into A

**Why it matters**:
- This is how real CPUs work internally
- Understanding microcode helps understand CPU operation
- We'll build this in Year 3 (SAP-1)

## Control Signal Timing

**Timing is critical**:
- Signals must be active at the right time
- Signals must not conflict (only one bus user at a time)
- Clock edges coordinate when signals change

**Common timing issues**:
- **Race conditions**: Signals changing at wrong time
- **Bus conflicts**: Multiple components trying to use bus
- **Setup/hold violations**: Signals not stable when needed

## State Machine Design

**Design process**:
1. **Identify states**: What distinct conditions exist?
2. **Define transitions**: When does system move to next state?
3. **Define outputs**: What control signals in each state?
4. **Implement**: Build with counters, decoders, logic gates

**Example**: Simple "load and add" operation
- State 0: Load address 1 into MAR
- State 1: Read memory, load into Register A
- State 2: Load address 2 into MAR
- State 3: Read memory, load into Register B
- State 4: Add A and B, store result in A
- State 5: Output result

## Practice Questions

1. What is a control signal?
2. Why do we need state machines?
3. How does a sequencer work?
4. What is microcode?
5. Why is timing important for control signals?

## Key Takeaways

- Control signals tell components what to do
- State machines coordinate signals in sequence
- Sequencers automate signal generation
- Microcode stores signal sequences for instructions
- Timing is critical for proper operation

---

*Control signals are the conductor of the computer orchestra*
