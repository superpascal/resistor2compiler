# Week 13-15: Microcode ROM System - Teaching Guide

## Overview

This teaching guide supports the delivery of microcode ROM system construction over 4 weeks. Students build the system that automates control signal generation.

## Learning Objectives

By the end of this week-block, students will:
- Design microcode format
- Build microcode ROM using EEPROM
- Program microcode for instructions
- Test microcode execution
- Generate control signals automatically

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 13-16 (PC and IR)
- ✅ Understand microcode concepts (Year 2)
- ✅ Can program EEPROM
- ✅ Understand instruction format

## Week-by-Week Breakdown

### Week 17: Microcode Format Design

**Theory Session (45 min)**:
- Microcode concept review
- Address formation (opcode + step)
- Data format (control signals)
- Signal mapping

**Lab Session (90 min)**:
- Design microcode format
- Plan address formation
- Map control signals
- Create microcode table
- Design address circuit
- Test address formation

**Key Points**:
- Address = instruction opcode + microstep
- Data = control signals
- Format must be clear
- Address formation critical

**Common Questions**:
- Q: How do we form address? A: IR opcode + microstep counter
- Q: How many signals? A: Depends on design, 8-16 typical
- Q: How many EEPROMs? A: 1-2 depending on signal count

### Week 18: Building Microcode ROM

**Theory Session (45 min)**:
- EEPROM selection
- Address formation circuit
- Data output connections
- Signal buffering

**Lab Session (90 min)**:
- Place EEPROM
- Build address formation
- Connect IR opcode
- Connect microstep counter
- Connect data outputs
- Test ROM system

**Key Points**:
- Address formation is critical
- EEPROM must respond correctly
- Data outputs drive control signals
- Test before programming

**Common Questions**:
- Q: Which EEPROM? A: 28C16 or similar, enough capacity
- Q: How to connect? A: Address from logic, data to signals
- Q: What if wrong? A: Check address formation, check connections

### Week 19: Programming Microcode

**Theory Session (45 min)**:
- Microcode design for LDA
- Microcode table creation
- EEPROM programming
- Verification procedures

**Lab Session (90 min)**:
- Design LDA microcode
- Create microcode table
- Program EEPROM
- Verify programming
- Test LDA execution
- Verify control signals

**Key Points**:
- Design microcode carefully
- Program correctly
- Verify before testing
- Test thoroughly

**Common Questions**:
- Q: How do we design? A: Break instruction into steps, assign signals
- Q: How many steps? A: Depends on instruction, 3-6 typical
- Q: What if wrong? A: Reprogram EEPROM, verify table

### Week 20: Microcode Execution Testing

**Theory Session (45 min)**:
- Microcode execution flow
- Signal verification
- Testing procedures
- Debugging microcode

**Lab Session (90 min)**:
- Program multiple instructions
- Test each instruction
- Verify control signals
- Verify execution
- Debug issues
- Document microcode

**Key Points**:
- Test each instruction
- Verify signals match microcode
- Debug systematically
- Document everything

**Common Questions**:
- Q: How do we test? A: Load instruction, run, verify signals
- Q: What if signals wrong? A: Check microcode, reprogram
- Q: How do we debug? A: Check signals step-by-step, verify microcode

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide microcode format template
- Step-by-step programming guide
- Pre-designed microcode for reference
- Pair with stronger students
- Extra time for programming

**Extension for advanced students**:
- Design more instructions
- Optimize microcode sequences
- Add conditional microcode
- Create instruction set

### Common Misconceptions

1. **"Microcode is programming"**
   - Clarify: It's a lookup table
   - Show address → data mapping

2. **"Microcode is complex"**
   - Clarify: Simple format
   - Show basic example

3. **"Need many EEPROMs"**
   - Clarify: 1-2 sufficient
   - Show signal count calculation

### Assessment Checkpoints

**Week 17**: Can students design microcode format?
**Week 18**: Can students build microcode ROM?
**Week 19**: Can students program microcode?
**Week 20**: Can students execute instructions via microcode?

## Resources

- Microcode format templates
- EEPROM programming guides
- Microcode table examples
- Control signal reference

## Next Week

After completing microcode, students move to control unit integration (Week 21-24).

---

*Microcode automates control signal generation*
