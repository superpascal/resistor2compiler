# Lab 16-18: Control Unit Integration

## Lab Overview

In this lab, students will integrate the control unit with the data path, implement the fetch-decode-execute cycle, and test complete CPU operation.

## Learning Objectives

- Integrate control unit with data path
- Implement fetch-decode-execute cycle
- Test instruction execution
- Debug CPU operation
- Verify complete CPU functionality

## Prerequisites

- Completed Lab 17-20 (Microcode ROM)
- Complete data path (Term 1)
- Complete control unit components (Weeks 13-20)
- Understanding of CPU operation

## Materials

### Components
- Complete SAP-1 system
- All components from previous labs
- Clock circuit (555 timer or oscillator)
- Run/halt switch
- Single-step button
- Output display: **20×4 HD44780 LCD (parallel interface, recommended)** or 7-segment/LEDs
  - **See**: `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for LCD integration guide
- Logic analyzer (highly recommended)

### Tools
- Logic analyzer
- Oscilloscope (optional)
- Multimeter
- Debugging tools

## Safety

- Large system - work carefully
- Verify all connections
- Check power distribution
- Use decoupling capacitors

## Lab Sessions

### Session 1: Control-Data Path Integration (Week 21)

**Objective**: Connect control unit to data path

**Steps**:
1. Connect microcode outputs to control signals
2. Connect control signals to components
3. Verify all connections
4. Test: Manual control signals work
5. Test: Microcode generates signals
6. Verify signal coordination
7. Check for conflicts

**Expected Result**: Control unit connected to data path, signals work

**Troubleshooting**:
- If signals don't work: Check connections, check microcode
- If conflicts: Check signal coordination, verify only one output
- If timing issues: Check clock, check signal timing

### Session 2: Fetch-Decode-Execute Implementation (Week 22)

**Objective**: Implement complete CPU cycle

**Steps**:
1. Set up clock circuit
2. Add run/halt switch
3. Add single-step button
4. Load test program into memory
5. Reset CPU (PC = 0)
6. Test: Fetch cycle
7. Test: Decode cycle
8. Test: Execute cycle
9. Test: Complete cycle

**Expected Result**: Complete fetch-decode-execute cycle works

**Troubleshooting**:
- If cycle doesn't work: Test each phase, check signals
- If timing wrong: Check clock, check signal timing
- If sequence wrong: Check microcode, check counter

### Session 3: Instruction Execution Testing (Week 23)

**Objective**: Test instruction execution

**Steps**:
1. Load simple program (LDA, OUT, HLT)
2. Run program in single-step mode
3. Verify each instruction executes
4. Check control signals for each step
5. Verify data flow
6. Test with arithmetic program (LDA, ADD, OUT)
7. Verify results
8. Document execution

**Expected Result**: Instructions execute correctly

**Troubleshooting**:
- If instruction fails: Check microcode, check signals, check data
- If result wrong: Trace data flow, verify each step
- If timing issues: Check clock speed, check signal timing

### Session 4: Complete CPU Testing (Week 24)

**Objective**: Test complete CPU with multiple programs

**Steps**:
1. Test arithmetic program (add two numbers)
2. Test control flow program (JMP or JZ)
3. Verify all instructions work
4. Test at different clock speeds
5. Debug any issues
6. Optimize if needed
7. Document complete system
8. Prepare for Term 3

**Expected Result**: Complete CPU working, ready for programming

**Troubleshooting**:
- If programs fail: Debug systematically, check each component
- If issues persist: Review design, check connections, get help
- If optimization needed: Add decoupling, improve timing

## Assessment

### Practical Assessment
- Successfully integrate control unit
- Implement fetch-decode-execute cycle
- Execute instructions correctly
- Run complete programs
- Document CPU system

### Lab Report
Students should document:
- Complete CPU architecture
- Control unit integration
- Instruction execution examples
- Test results
- Any issues and solutions

## Extension Activities

- Add more instructions
- Optimize CPU performance
- Add debugging features
- Expand CPU capabilities

## Next Lab

After completing this lab, students will move to Term 3: SAP-1 Completion and Programming.

---

*Control unit integration creates a working CPU*
