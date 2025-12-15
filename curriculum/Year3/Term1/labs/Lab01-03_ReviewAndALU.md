# Lab 1-3: Review and ALU Subsystem

## Lab Overview

In this lab, students review Year 1-2 concepts and build the ALU subsystem for the SAP-1 CPU, including adder/subtractor and flags.

## Learning Objectives

- Review and integrate Year 1-2 knowledge
- Build 4-bit adder/subtractor
- Implement carry and zero flags
- Test ALU operations
- Integrate ALU with registers

## Prerequisites

- Completed Years 1-2
- Understanding of:
  - Combinational logic (adders)
  - Sequential logic (registers, flip-flops)
  - Binary arithmetic
  - Two's complement

## Materials

### Components
- 74HC283 (4-bit full adder) or build from gates
- XOR gates (74HC86) for subtraction
- Flip-flops (74HC74) for flags
- NOR gate (74HC02) for zero detection
- Logic gates for control
- LEDs for status display
- Resistors (220Ω for LEDs)

### Tools
- Breadboards
- Multimeter
- Logic probe (optional)

## Safety

- Double-check all connections
- Verify power connections
- Use current-limiting resistors for LEDs

## Lab Sessions

### Session 1: Year 1-2 Review (Week 1)

**Objective**: Review all foundational concepts

**Steps**:
1. Review electronics basics (voltage, current, resistance)
2. Review logic gates and combinational circuits
3. Review sequential circuits (flip-flops, registers)
4. Review memory concepts
5. Review control signals
6. Review system integration
7. Test understanding with simple exercises

**Expected Result**: Solid understanding of all Year 1-2 concepts

**Troubleshooting**:
- If concepts unclear: Review specific topics
- If skills rusty: Practice with simple circuits
- If gaps found: Address before proceeding

### Session 2: Building the Adder (Week 2)

**Objective**: Build 4-bit adder

**Steps**:
1. Place 74HC283 on breadboard
2. Connect power and ground
3. Connect input A (4 bits from switches or register)
4. Connect input B (4 bits from switches or register)
5. Connect carry in (ground for addition)
6. Connect outputs to LEDs
7. Test: Add various number pairs
8. Verify results

**Expected Result**: 4-bit adder works correctly

**Troubleshooting**:
- If no output: Check power, check connections
- If wrong results: Check input connections, verify binary
- If carry wrong: Check carry connections

### Session 3: Implementing Subtraction (Week 3)

**Objective**: Add subtraction capability

**Steps**:
1. Add XOR gates to B inputs (invert when SUB=1)
2. Connect SUB signal to XOR gates
3. Connect SUB to carry in (adds 1 for two's complement)
4. Add SUB control switch
5. Test: Perform subtractions
6. Verify two's complement works
7. Test edge cases (0, negative results)

**Expected Result**: Can add and subtract correctly

**Troubleshooting**:
- If subtraction wrong: Check XOR connections, check carry in
- If results incorrect: Verify two's complement
- If control doesn't work: Check SUB signal connection

### Session 4: Flags and Integration (Week 4)

**Objective**: Add flags and integrate with registers

**Steps**:
1. Build carry flag: Connect carry out to flip-flop
2. Build zero flag: Connect result bits to NOR gate, then flip-flop
3. Add flag display LEDs
4. Test: Operations that set/clear flags
5. Connect ALU to registers (conceptually)
6. Test complete ALU subsystem
7. Document ALU operation

**Expected Result**: ALU with flags working correctly

**Troubleshooting**:
- If flags don't set: Check connections, check logic
- If flags wrong: Verify flag logic, check timing
- If integration issues: Check connections, verify signals

## Assessment

### Practical Assessment
- Successfully build adder
- Implement subtraction
- Add flags correctly
- Test all operations
- Document ALU subsystem

### Lab Report
Students should document:
- ALU circuit diagram
- Test cases and results
- Flag operation verification
- Any issues and solutions
- Reflection on ALU concepts

## Extension Activities

- Add logic operations (AND, OR, XOR)
- Expand to 8-bit ALU
- Add more flags (overflow, sign)
- Optimize ALU design

## Next Lab

After completing this lab, students will move to registers and buses (Lab 5-8).

---

*The ALU is the computational heart of the CPU*
