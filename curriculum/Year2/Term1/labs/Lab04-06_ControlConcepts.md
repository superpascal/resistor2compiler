# Lab 5-8: Control Concepts and State Machines

## Lab Overview

In this lab, students will build state machines and sequencers to understand how control signals coordinate system operations.

## Learning Objectives

- Build simple state machines
- Create sequencers using counters and decoders
- Generate control signals in sequence
- Coordinate multiple operations
- Understand microcode concepts (introduction)

## Prerequisites

- Completed memory lab (Lab 1-4)
- Understanding of counters and decoders (Year 1)
- Understanding of control signals

## Materials

### Components
- 1× 74HC161 or 74HC163 (4-bit counter) for state counter
- 1× 74HC139 (2-to-4 decoder) or 74HC138 (3-to-8 decoder)
- Logic gates (AND, OR, NOT) for signal combination
- LEDs (for state and signal display)
- Resistors (220Ω for LEDs)
- Breadboards and jumper wires

### Tools
- Multimeter
- Logic probe (optional)
- Oscilloscope (optional, for timing analysis)

## Safety

- Double-check all connections before powering
- Use current-limiting resistors for LEDs
- Ensure proper power distribution

## Lab Sessions

### Session 1: Building a Simple State Machine (Week 5)

**Objective**: Build a 4-state machine that cycles through states

**Steps**:
1. Place 74HC161 counter on breadboard
2. Connect power and ground
3. Connect clock input (from 555 timer or manual button)
4. Connect counter outputs to decoder inputs
5. Connect decoder outputs to LEDs (one per state)
6. Add reset circuit to return to state 0
7. Test: Clock the counter, observe LEDs cycling through states

**Expected Result**: LEDs cycle through 4 states (0, 1, 2, 3) in sequence

**Troubleshooting**:
- If states don't advance: Check clock connection, check counter enable
- If wrong sequence: Check decoder connections, verify binary counting
- If stuck in one state: Check reset circuit, check power

### Session 2: Generating Control Signals (Week 6)

**Objective**: Generate control signals based on state

**Steps**:
1. Use decoder outputs from previous session
2. Connect decoder outputs to control signal LEDs
3. Add logic gates to combine signals if needed
4. Label signals (e.g., MI, RO, AI, AO)
5. Test: Cycle through states, observe which signals are active
6. Document signal patterns for each state

**Expected Result**: Different control signals active in different states

**Troubleshooting**:
- If signals don't appear: Check decoder connections, check LED connections
- If wrong signals: Check decoder input connections, verify state values
- If signals conflict: Ensure only appropriate signals active per state

### Session 3: Simple Sequencer for Operation (Week 7)

**Objective**: Build sequencer to perform "load A, load B, add" sequence

**Steps**:
1. Build state machine (4 states: Load A, Load B, Add, Store)
2. Connect state outputs to control signal generation
3. State 0: Generate MI (MAR In) signal
4. State 1: Generate RO (RAM Out) and AI (A In) signals
5. State 2: Generate MI and then RO and BI (B In) signals
6. State 3: Generate ALU operation signals
7. Test: Run sequencer, verify signals appear in correct sequence

**Expected Result**: Control signals appear in correct sequence for operation

**Troubleshooting**:
- If sequence wrong: Check state machine logic, check signal connections
- If signals overlap: Add logic to ensure only one bus user at a time
- If timing issues: Check clock speed, may need to slow down

### Session 4: Complete Sequencer System (Week 8)

**Objective**: Integrate sequencer with registers and ALU to perform complete operation

**Steps**:
1. Connect sequencer to existing register/ALU system from Year 1
2. Connect control signals to appropriate components
3. Load test data into memory
4. Run sequencer through complete cycle
5. Verify: Register A and B load correctly, ALU performs operation
6. Observe complete data flow through system
7. Document timing and signal sequence

**Expected Result**: Complete operation executes automatically via sequencer

**Troubleshooting**:
- If components don't respond: Check control signal connections
- If data wrong: Check data path, verify memory contents
- If timing issues: May need to add delays or adjust clock
- If bus conflicts: Ensure only one output enabled per state

## Assessment

### Practical Assessment
- Successfully build and test state machine
- Generate control signals correctly
- Execute complete operation sequence
- Document signal timing and sequence

### Lab Report
Students should document:
- State machine design and implementation
- Control signal generation logic
- Timing diagrams showing signal sequence
- Complete operation demonstration
- Reflection on how sequencers work

## Extension Activities

- Add more states for more complex operations
- Implement conditional state transitions
- Build microcode ROM concept (using EEPROM)
- Create sequencer for multiple instruction types

## Next Lab

After completing this lab, students will move to integration and review (Lab 9-12).

---

*Control signals orchestrate the computer's operations*
