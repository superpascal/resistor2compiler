# Lab 13-15: Microcode ROM System

## Lab Overview

In this lab, students will build the microcode ROM system using EEPROM, program microcode for SAP-1 instructions, and generate control signals automatically.

## Learning Objectives

- Design microcode format
- Build microcode ROM using EEPROM
- Program microcode for instructions
- Test microcode execution
- Verify control signal generation

## Prerequisites

- Completed Lab 13-16 (PC and IR)
- Understanding of microcode concepts (Year 2)
- Understanding of EEPROM programming
- Understanding of instruction format

## Materials

### Components
- EEPROM (28C16 or similar) × 1-2 for microcode
- Microstep counter (74HC161)
- Logic gates for address formation
- Instruction Register (from previous lab)
- LEDs for control signal display
- Arduino-based EEPROM programmer

### Tools
- EEPROM programmer (Arduino-based)
- Logic analyzer (highly recommended)
- Multimeter

## Safety

- Handle EEPROM carefully (ESD protection)
- Verify programming before inserting
- Double-check connections

## Lab Sessions

### Session 1: Microcode Format Design (Week 17)

**Objective**: Design microcode format and address formation

**Steps**:
1. Plan microcode format (address = opcode + step, data = signals)
2. Design address formation logic
3. Map control signals to EEPROM bits
4. Create microcode table template
5. Design address formation circuit
6. Test address formation with switches
7. Verify address logic

**Expected Result**: Microcode format designed, address formation works

**Troubleshooting**:
- If address wrong: Check logic, check connections
- If format unclear: Simplify, document clearly
- If signals don't map: Review signal count, adjust format

### Session 2: Building Microcode ROM (Week 18)

**Objective**: Construct microcode ROM system

**Steps**:
1. Place EEPROM on breadboard
2. Connect address formation circuit
3. Connect IR opcode to address
4. Connect microstep counter to address
5. Connect EEPROM data outputs
6. Add control signal LEDs
7. Test address formation
8. Verify EEPROM responds

**Expected Result**: Microcode ROM system built and responding

**Troubleshooting**:
- If EEPROM doesn't respond: Check power, check address
- If address wrong: Check address formation logic
- If no output: Check chip enable, check connections

### Session 3: Programming Microcode (Week 19)

**Objective**: Program EEPROM with microcode

**Steps**:
1. Design microcode for LDA instruction
2. Create microcode table
3. Program EEPROM with microcode
4. Verify programming
5. Test: Load LDA instruction, run microcode
6. Verify control signals match microcode
7. Test with other instructions
8. Document microcode

**Expected Result**: Microcode programmed and working correctly

**Troubleshooting**:
- If programming fails: Check programmer, check EEPROM
- If signals wrong: Check microcode table, reprogram
- If sequence wrong: Review microcode design, verify steps

### Session 4: Microcode Execution Testing (Week 20)

**Objective**: Test complete microcode execution

**Steps**:
1. Program microcode for multiple instructions
2. Load test instruction into IR
3. Run microcode sequence
4. Verify control signals
5. Verify instruction execution
6. Test with different instructions
7. Debug any issues
8. Document execution

**Expected Result**: Microcode executes instructions correctly

**Troubleshooting**:
- If execution fails: Check microcode, check signals, check timing
- If signals wrong: Verify microcode programming, check connections
- If timing issues: Check clock, check signal coordination

## Assessment

### Practical Assessment
- Successfully design microcode format
- Build microcode ROM system
- Program microcode correctly
- Execute instructions via microcode
- Document microcode system

### Lab Report
Students should document:
- Microcode format design
- Address formation circuit
- Microcode table
- Test results for each instruction
- Control signal verification

## Extension Activities

- Add more instructions to microcode
- Optimize microcode sequences
- Add conditional microcode
- Design new instructions

## Next Lab

After completing this lab, students will move to control unit integration (Lab 21-24).

---

*Microcode automates control signal generation*
