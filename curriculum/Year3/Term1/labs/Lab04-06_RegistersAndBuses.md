# Lab 4-6: Register File and Buses

## Lab Overview

In this lab, students will build Register A and Register B, implement tri-state bus connections, and integrate registers with the ALU.

## Learning Objectives

- Build Register A and Register B
- Implement tri-state bus connections
- Build bus control logic
- Test register operations
- Integrate registers with ALU

## Prerequisites

- Completed Lab 1-4 (Review and ALU)
- Understanding of registers (Year 1-2)
- Understanding of tri-state buffers
- Understanding of buses

## Materials

### Components
- 2× 74HC173 (4-bit registers) or 74HC574
- 74HC125 or 74HC244 (tri-state buffers)
- Logic gates for control
- LEDs for status display
- Resistors (220Ω for LEDs)
- DIP switches for data input

### Tools
- Breadboards
- Multimeter
- Logic probe (optional)

## Safety

- Verify power connections
- Check for shorts
- Use current-limiting resistors

## Lab Sessions

### Session 1: Building Register A (Week 5)

**Objective**: Construct Register A

**Steps**:
1. Place 74HC173 on breadboard
2. Connect power and ground
3. Connect data inputs (from switches or bus)
4. Connect clock input
5. Connect enable/load control
6. Connect outputs to LEDs
7. Test: Load values, verify storage
8. Test: Output values, verify tri-state

**Expected Result**: Register A loads and stores values correctly

**Troubleshooting**:
- If doesn't load: Check enable signal, check clock
- If doesn't store: Check clock connection, check data
- If output wrong: Check tri-state enable, check connections

### Session 2: Building Register B (Week 6)

**Objective**: Construct Register B

**Steps**:
1. Build Register B (same as Register A)
2. Use separate control signals
3. Connect to same bus
4. Test: Load values independently
5. Test: Output values independently
6. Verify no conflicts with Register A
7. Test both registers together

**Expected Result**: Register B works independently, no conflicts

**Troubleshooting**:
- If conflicts: Check tri-state enables, ensure only one active
- If wrong values: Check connections, verify control signals
- If timing issues: Check clock, check signal timing

### Session 3: Bus Integration (Week 7)

**Objective**: Integrate registers with bus

**Steps**:
1. Connect Register A to bus (via tri-state)
2. Connect Register B to bus (via tri-state)
3. Connect ALU output to bus (via tri-state)
4. Add bus control logic
5. Test: Only one output enabled at a time
6. Test: Data flows correctly
7. Verify bus protocol

**Expected Result**: Bus works correctly, no conflicts

**Troubleshooting**:
- If bus conflicts: Check tri-state enables, verify only one active
- If data wrong: Check connections, verify source
- If timing issues: Check signal coordination

### Session 4: Register-ALU Integration (Week 8)

**Objective**: Integrate registers with ALU

**Steps**:
1. Connect Register A output to ALU input A
2. Connect Register B output to ALU input B
3. Connect ALU output to bus
4. Connect bus to Register A input
5. Test: Load A and B, add, store in A
6. Test: Load A and B, subtract, store in A
7. Verify complete operation
8. Document data path

**Expected Result**: Complete register-ALU data path works

**Troubleshooting**:
- If operation fails: Check each connection, verify signals
- If data wrong: Trace data flow, check each step
- If timing issues: Check clock, check signal timing

## Assessment

### Practical Assessment
- Successfully build both registers
- Implement bus correctly
- Integrate with ALU
- Test complete data path
- Document system

### Lab Report
Students should document:
- Register circuit diagrams
- Bus connection diagram
- Control signal table
- Test results
- Data path verification

## Extension Activities

- Add more registers
- Expand bus width
- Add register file
- Optimize bus design

## Next Lab

After completing this lab, students will move to memory subsystem (Lab 9-12).

---

*Registers and buses form the data path foundation*
