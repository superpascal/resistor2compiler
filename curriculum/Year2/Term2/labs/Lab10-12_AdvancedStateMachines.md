# Lab 13-16: Advanced State Machines and Microcode

## Lab Overview

In this lab, students will build advanced state machines, implement microcode ROM concepts using EEPROM, and create instruction decoding systems.

## Learning Objectives

- Build complex state machines with multiple operations
- Implement microcode ROM using EEPROM
- Create instruction decoding logic
- Program EEPROM with microcode patterns
- Test instruction execution with microcode

## Prerequisites

- Completed Year 2 Term 1 labs
- Understanding of state machines and sequencers
- Understanding of EEPROM programming
- Understanding of control signals

## Materials

### Components
- EEPROM (28C16 or similar) for microcode ROM
- Counters (74HC161) for microstep counter
- Decoders (74HC138/139) for instruction decoding
- Instruction Register (74HC173 or similar)
- Logic gates for address formation
- LEDs for status display
- Arduino-based EEPROM programmer

### Tools
- EEPROM programmer (Arduino-based)
- Logic analyzer (if available)
- Multimeter

## Safety

- Handle EEPROM carefully (ESD protection)
- Double-check programming before inserting chip
- Verify power connections

## Lab Sessions

### Session 1: Complex State Machine (Week 13)

**Objective**: Build state machine for multiple operations

**Steps**:
1. Design state machine for 3 operations (Load A, Load B, Add)
2. Build counter-based sequencer (6+ states)
3. Add decoder to generate control signals
4. Test each operation sequence
5. Verify state transitions

**Expected Result**: State machine cycles through operations correctly

**Troubleshooting**:
- If states don't advance: Check clock, check counter enable
- If wrong signals: Check decoder connections
- If sequence wrong: Review state machine design

### Session 2: Microcode ROM Setup (Week 14)

**Objective**: Set up EEPROM as microcode ROM

**Steps**:
1. Plan microcode format (address = instruction + step, data = signals)
2. Design address formation logic (opcode bits + step bits)
3. Connect EEPROM address inputs
4. Connect EEPROM data outputs to control signals
5. Test address formation with switches
6. Verify EEPROM outputs

**Expected Result**: EEPROM outputs control signals based on address

**Troubleshooting**:
- If wrong address: Check address formation logic
- If no output: Check EEPROM power, check chip enable
- If wrong data: Verify EEPROM programming

### Session 3: Instruction Decoding (Week 15)

**Objective**: Build instruction register and decoding

**Steps**:
1. Build Instruction Register (IR) from registers
2. Extract opcode bits (upper bits of IR)
3. Connect opcode to microcode address
4. Add microstep counter for step bits
5. Form complete microcode address
6. Test with different instructions

**Expected Result**: Different instructions produce different microcode sequences

**Troubleshooting**:
- If instruction not decoded: Check IR connections, check opcode extraction
- If wrong microcode: Check address formation
- If sequence wrong: Verify microcode programming

### Session 4: Complete Microcode System (Week 16)

**Objective**: Integrate and test complete microcode system

**Steps**:
1. Connect all components (IR, counter, EEPROM, control signals)
2. Program EEPROM with microcode for LDA instruction
3. Load test instruction into IR
4. Run microcode sequence
5. Verify control signals match microcode
6. Test with multiple instructions

**Expected Result**: Instructions execute via microcode correctly

**Troubleshooting**:
- If signals wrong: Check microcode programming, check connections
- If sequence wrong: Verify microstep counter, check address formation
- If instruction fails: Test each component individually

## Assessment

### Practical Assessment
- Successfully build complex state machine
- Implement microcode ROM system
- Program EEPROM with microcode
- Execute instructions via microcode
- Document microcode patterns

### Lab Report
Students should document:
- State machine design
- Microcode format and programming
- Instruction decoding logic
- Test results for each instruction
- Reflection on microcode concepts

## Extension Activities

- Add more instructions to microcode
- Implement conditional microcode (based on flags)
- Optimize microcode for fewer steps
- Design new instruction and microcode

## Next Lab

After completing this lab, students will move to address decoding and memory mapping (Lab 17-20).

---

*Microcode bridges instructions and hardware control*
