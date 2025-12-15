# Lab 4-6: Expanded Instruction Set

## Lab Overview

In this lab, students will design and implement new instructions for the SAP-1, expanding the instruction set and microcode ROM.

## Learning Objectives

- Design new instructions
- Expand microcode ROM capacity
- Program new microcode sequences
- Test new instructions
- Write programs using new instructions

## Prerequisites

- Completed Lab 1-4 (SAP-1 Improvements)
- Understanding of microcode (Year 3)
- Understanding of instruction execution
- Experience with EEPROM programming

## Materials

### Components
- Improved SAP-1 system
- Additional EEPROM for expanded microcode (if needed)
- Logic gates for address expansion
- EEPROM programmer

### Tools
- EEPROM programmer
- Logic analyzer
- Documentation materials

## Safety

- Handle EEPROM carefully
- Verify programming before testing
- Test instructions carefully

## Lab Sessions

### Session 1: Instruction Design (Week 5)

**Objective**: Design new instructions

**Steps**:
1. Review current instruction set
2. Identify useful new instructions
3. Design LDB (Load B) instruction
4. Design ADI (Add Immediate) instruction
5. Plan microcode sequences
6. Create instruction encoding
7. Document designs

**Expected Result**: New instruction designs ready

**Troubleshooting**:
- If designs unclear: Simplify, review examples
- If encoding conflicts: Check opcode space
- If microcode complex: Break into steps

### Session 2: Microcode ROM Expansion (Week 6)

**Objective**: Expand microcode ROM capacity

**Steps**:
1. Plan microcode expansion
2. Add third EEPROM (if needed)
3. Update address formation
4. Expand control signal mapping
5. Test address formation
6. Verify ROM expansion
7. Document expansion

**Expected Result**: Expanded microcode ROM working

**Troubleshooting**:
- If expansion fails: Check address formation, check connections
- If signals wrong: Check signal mapping, verify EEPROM
- If conflicts: Review design, check logic

### Session 3: Programming New Instructions (Week 7)

**Objective**: Program microcode for new instructions

**Steps**:
1. Design microcode for LDB
2. Design microcode for ADI
3. Create microcode tables
4. Program EEPROM with new microcode
5. Verify programming
6. Test new instructions
7. Document microcode

**Expected Result**: New instructions programmed and working

**Troubleshooting**:
- If programming fails: Check programmer, check EEPROM
- If instructions don't work: Check microcode, verify sequences
- If signals wrong: Review microcode tables, reprogram

### Session 4: Testing and Programming (Week 8)

**Objective**: Test new instructions and write programs

**Steps**:
1. Test each new instruction
2. Verify correct operation
3. Write test programs using new instructions
4. Compare to old method
5. Verify efficiency gains
6. Document results
7. Prepare for memory expansion

**Expected Result**: New instructions working, programs using them

**Troubleshooting**:
- If instructions fail: Debug microcode, check signals
- If programs wrong: Review instruction usage, verify encoding
- If efficiency unclear: Compare instruction counts

## Assessment

### Practical Assessment
- Successfully design new instructions
- Expand microcode ROM
- Program new microcode
- Test new instructions
- Write programs using them

### Lab Report
Students should document:
- New instruction designs
- Microcode expansion
- Microcode tables
- Test results
- Program examples
- Efficiency comparison

## Extension Activities

- Add more instructions
- Optimize microcode
- Create instruction library
- Design custom instructions

## Next Lab

After completing instruction expansion, students will move to memory expansion (Lab 9-12).

---

*Instruction set expansion enhances CPU capabilities*
