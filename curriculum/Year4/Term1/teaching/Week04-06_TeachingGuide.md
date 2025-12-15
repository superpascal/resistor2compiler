# Week 4-6: Expanded Instruction Set - Teaching Guide

## Overview

This teaching guide supports instruction set expansion over 4 weeks. Students design and implement new instructions for the SAP-1.

## Learning Objectives

By the end of this week-block, students will:
- Design new instructions
- Expand microcode ROM
- Program new microcode
- Test new instructions
- Write programs using new instructions

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 1-3 (Improvements)
- ✅ Understand microcode (Year 3)
- ✅ Can program EEPROM
- ✅ Understand instruction execution

## Week-by-Week Breakdown

### Week 5: Instruction Design

**Theory Session (45 min)**:
- Instruction set expansion concepts
- New instruction examples (LDB, ADI)
- Microcode design for new instructions
- Instruction encoding

**Lab Session (90 min)**:
- Review current instructions
- Design new instructions
- Plan microcode sequences
- Create instruction encoding
- Document designs

**Key Points**:
- Design carefully
- Plan microcode
- Consider encoding
- Document everything

**Common Questions**:
- Q: Which instructions to add? A: Useful ones like LDB, ADI
- Q: How do we design? A: Define behavior, plan microcode
- Q: What about encoding? A: Use available opcodes

### Week 6: Microcode ROM Expansion

**Theory Session (45 min)**:
- Microcode expansion methods
- Adding EEPROMs
- Address formation expansion
- Control signal mapping

**Lab Session (90 min)**:
- Plan expansion
- Add EEPROM (if needed)
- Update address formation
- Expand signal mapping
- Test expansion

**Key Points**:
- Expansion enables more instructions
- Address formation critical
- Signal mapping important
- Test before programming

**Common Questions**:
- Q: How many EEPROMs? A: Depends on signal count
- Q: How to expand? A: Add EEPROM, update address logic
- Q: What if conflicts? A: Review design, check logic

### Week 7: Programming New Instructions

**Theory Session (45 min)**:
- Microcode programming for new instructions
- Microcode table creation
- EEPROM programming
- Testing procedures

**Lab Session (90 min)**:
- Design microcode for LDB
- Design microcode for ADI
- Create microcode tables
- Program EEPROM
- Test new instructions

**Key Points**:
- Design microcode carefully
- Program correctly
- Test thoroughly
- Document microcode

**Common Questions**:
- Q: How do we design microcode? A: Break instruction into steps
- Q: How many steps? A: Depends on instruction, 3-6 typical
- Q: What if wrong? A: Reprogram, verify table

### Week 8: Testing and Programming

**Theory Session (45 min)**:
- Testing new instructions
- Writing programs with new instructions
- Efficiency comparison
- Documentation

**Lab Session (90 min)**:
- Test each new instruction
- Write test programs
- Compare to old method
- Verify efficiency
- Document results

**Key Points**:
- Test thoroughly
- Verify efficiency gains
- Document programs
- Prepare for memory expansion

**Common Questions**:
- Q: How do we test? A: Write programs, verify execution
- Q: Are new instructions better? A: Compare instruction counts
- Q: What if wrong? A: Debug microcode, verify sequences

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide instruction design templates
- Step-by-step microcode guide
- Pre-designed microcode for reference
- Pair with stronger students
- Extra time for programming

**Extension for advanced students**:
- Design more instructions
- Optimize microcode
- Create instruction library
- Help other students

### Common Misconceptions

1. **"More instructions is always better"**
   - Clarify: Balance needed
   - Show complexity trade-offs

2. **"All instructions are equal"**
   - Clarify: Some more useful
   - Show usage patterns

3. **"Expansion is easy"**
   - Clarify: Requires careful design
   - Show microcode complexity

### Assessment Checkpoints

**Week 5**: Can students design new instructions?
**Week 6**: Can students expand microcode ROM?
**Week 7**: Can students program new microcode?
**Week 8**: Can students test and use new instructions?

## Resources

- Instruction design templates
- Microcode programming guides
- Microcode table examples
- Test program templates

## Next Week

After completing instruction expansion, students move to memory expansion (Week 9-12).

---

*Instruction set expansion enhances CPU capabilities*
