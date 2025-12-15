# Lab 9-12: Integration and Review

## Lab Overview

In this lab, students will integrate all Year 1-2 components into a complete "manual computer" and learn to manually execute simple programs.

## Learning Objectives

- Integrate all system components
- Understand complete system architecture
- Manually execute simple programs
- Coordinate all control signals
- Prepare for automatic CPU construction

## Prerequisites

- Completed all Year 1 labs
- Completed memory lab (Lab 1-4)
- Completed control concepts lab (Lab 5-8)
- Understanding of all system components

## Materials

### Components
- All components from previous labs:
  - Registers (A, B, MAR)
  - ALU (adder/subtractor)
  - Memory (RAM/EEPROM)
  - Buses and tri-state buffers
  - Control signal generation
- Manual switches for control signals
- LEDs for status display
- 7-segment display (optional, for output)

### Tools
- Multimeter
- Logic probe
- Oscilloscope (optional)
- Breadboards (may need multiple)

## Safety

- Large system - double-check all connections
- Ensure proper power distribution
- Use decoupling capacitors near ICs
- Work systematically to avoid errors

## Lab Sessions

### Session 1: System Integration (Week 9)

**Objective**: Connect all components into complete system

**Steps**:
1. Review all components: Registers, ALU, Memory, Buses
2. Plan system layout on breadboards
3. Connect data bus to all components
4. Connect address bus (MAR to memory)
5. Connect control signals to all components
6. Add status LEDs for key signals
7. Power up and verify no shorts or overheating
8. Test each subsystem individually

**Expected Result**: All components connected, system powers up without issues

**Troubleshooting**:
- If power issues: Check for shorts, verify power distribution
- If components don't respond: Check connections, verify power
- If bus conflicts: Ensure only one output enabled
- If signals wrong: Check control signal connections

### Session 2: Manual Control Setup (Week 10)

**Objective**: Set up manual switches for all control signals

**Steps**:
1. Identify all control signals needed:
   - MI (MAR In), RO (RAM Out), WE (Write Enable)
   - AI (A In), AO (A Out), BI (B In), BO (B Out)
   - ALU operation signals
   - Clock and reset
2. Connect manual switches for each signal
3. Add LEDs to show signal states
4. Label all switches clearly
5. Test: Toggle each signal, verify component responds
6. Create control signal reference card

**Expected Result**: Can manually control all system operations

**Troubleshooting**:
- If switches don't work: Check connections, check pull-up resistors
- If components don't respond: Check signal connections, verify enable pins
- If signals conflict: Review control logic, ensure proper sequencing

### Session 3: Manual Program Execution (Week 11)

**Objective**: Manually execute a simple program (add two numbers)

**Program**: Add numbers from memory addresses 0x05 and 0x06, store result at 0x07

**Execution Steps**:
1. **Load first number**:
   - Set MAR switches to 0x05
   - Toggle MI (MAR In) signal
   - Toggle RO (RAM Out) signal
   - Toggle AI (A In) signal
   - Verify Register A contains first number

2. **Load second number**:
   - Set MAR switches to 0x06
   - Toggle MI signal
   - Toggle RO signal
   - Toggle BI (B In) signal
   - Verify Register B contains second number

3. **Perform addition**:
   - Enable AO and BO signals (A and B to ALU)
   - Set ALU to ADD operation
   - Toggle AI signal to load result into A
   - Verify result in Register A

4. **Store result**:
   - Set MAR switches to 0x07
   - Toggle MI signal
   - Enable AO signal (A to bus)
   - Toggle WE (Write Enable) signal
   - Verify result written to memory

5. **Verify**:
   - Read back address 0x07
   - Confirm result is correct

**Expected Result**: Program executes correctly, result stored in memory

**Troubleshooting**:
- If data wrong: Check each step, verify memory contents
- If signals wrong: Review control sequence, check timing
- If operations fail: Test each component individually
- If timing issues: Slow down, ensure signals stable

### Session 4: System Demonstration and Documentation (Week 12)

**Objective**: Demonstrate complete system and document architecture

**Steps**:
1. Run complete program execution
2. Demonstrate different operations (add, subtract, load, store)
3. Show data flow through system
4. Document system architecture:
   - Component diagram
   - Signal connections
   - Control signal table
   - Timing diagrams
5. Create user guide for manual operation
6. Prepare presentation of system

**Expected Result**: Complete system documented and demonstrated

**Documentation Requirements**:
- System block diagram
- Component list and connections
- Control signal reference
- Program execution procedures
- Troubleshooting guide
- Reflection on system operation

## Assessment

### Practical Assessment
- Successfully integrate all components
- Manually execute program correctly
- Demonstrate understanding of data flow
- Document system architecture

### Final Project
Students must:
- Build complete manual computer
- Execute at least two different programs
- Document system architecture
- Present system to class
- Reflect on learning journey

## Extension Activities

- Execute more complex programs
- Add output display (7-segment or LEDs)
- Implement conditional operations
- Design new instructions
- Prepare for automatic control (Year 3)

## Reflection Questions

1. How do all the components work together?
2. What would make this system automatic?
3. What challenges did you face in integration?
4. How does this prepare you for CPU construction?
5. What would you improve or add?

## Next Steps

After completing this lab, students are ready for Year 3: CPU Construction, where they will build the SAP-1 8-bit computer with automatic control.

---

*Integration brings all the pieces together into a working computer system*
