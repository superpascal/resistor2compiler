# Week 4-6: Control Concepts and State Machines - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand how control signals orchestrate operations
- Understand state machines and how they work
- Know how to build simple sequencers
- Understand the concept of microcode (introduction)
- Know how control signals coordinate system operations

## Prerequisites

- Understanding of memory and MAR (Weeks 1-3)
- Understanding of counters and decoders (Year 1)
- Understanding of combinational and sequential logic (Year 1)

## Key Concepts

### 1. What are Control Signals?

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

### 2. Control Signal Coordination

**The Problem**: 
- Many components, one bus
- Operations must happen in the right order
- Only one component can use the bus at a time

**The Solution**: 
- Control signals enable/disable components
- Signals are coordinated in time
- Signals follow a sequence (state machine)

### 3. State Machines

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

### 4. Building a Sequencer

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

### 5. Microcode Concepts (Introduction)

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

### 6. Control Signal Timing

**Timing is critical**:
- Signals must be active at the right time
- Signals must not conflict (only one bus user at a time)
- Clock edges coordinate when signals change

**Common timing issues**:
- **Race conditions**: Signals changing at wrong time
- **Bus conflicts**: Multiple components trying to use bus
- **Setup/hold violations**: Signals not stable when needed

### 7. State Machine Design

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

### 8. Control Logic Implementation

**Methods**:
1. **Hardwired**: Logic gates directly generate signals
2. **Microcoded**: ROM stores signal patterns
3. **Programmable**: FPGA or microcontroller generates signals

**For our projects**: 
- Start with simple hardwired logic
- Progress to microcoded approach (Year 3)
- Understand that real CPUs use microcode

## Mathematical Foundations

### State Count

For n states:
- **Number of flip-flops needed** = ⌈log₂(n)⌉
- **Example**: 4 states need 2 flip-flops (2² = 4)
- **Example**: 8 states need 3 flip-flops (2³ = 8)

### Control Signal Count

- **Number of control signals** = Number of components to control
- **Example**: If controlling MAR, RAM, Register A, Register B, ALU
  - That's 5 components, each may need 2 signals (in/out)
  - Total: ~10 control signals

## Common Misconceptions

1. **"Control signals are just on/off"**: They must be timed correctly
2. **"Any signal can be active anytime"**: Signals must be coordinated
3. **"State machines are complex"**: Simple ones are quite straightforward
4. **"Microcode is programming"**: It's more like a lookup table

## Connections to Year 1

- **Counters**: Used to track state in sequencers
- **Decoders**: Convert state number to control signals
- **Logic gates**: Combine signals and conditions
- **Registers**: Store state information

## Connections to Year 3

- **SAP-1 Control Unit**: Uses microcode ROM
- **Instruction execution**: Each instruction has microcode sequence
- **CPU operation**: Control unit orchestrates all CPU operations
- **Fetch-decode-execute**: The fundamental CPU cycle

## Next Steps

After understanding control concepts, students will:
- Build simple state machines
- Create sequencers for operations
- Understand how this leads to CPU control units
- Prepare for building the SAP-1 in Year 3

---

*Control signals are the conductor of the computer orchestra*
