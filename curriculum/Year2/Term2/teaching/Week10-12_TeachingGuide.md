# Week 10-12: Advanced State Machines and Microcode - Teaching Guide

## Overview

This teaching guide supports the delivery of advanced state machines and microcode concepts over 4 weeks. Students learn to build complex sequencers and implement microcode ROM systems.

## Learning Objectives

By the end of this week-block, students will:
- Design and build complex state machines
- Understand microcode ROM concepts
- Implement instruction decoding
- Program EEPROM with microcode
- Execute instructions via microcode

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Year 2 Term 1
- ✅ Understand basic state machines
- ✅ Understand EEPROM programming
- ✅ Can use EEPROM programmer

## Week-by-Week Breakdown

### Week 13: Complex State Machines

**Theory Session (45 min)**:
- Beyond simple sequencers
- Multi-operation state machines
- State machine design principles
- Optimization techniques

**Lab Session (90 min)**:
- Design state machine for multiple operations
- Build counter-based sequencer
- Add decoder for control signals
- Test operation sequences

**Key Points**:
- Complex state machines coordinate multiple operations
- Good design minimizes states
- Decoders generate control signals from states

**Common Questions**:
- Q: How many states do we need? A: One per operation step
- Q: Can we reuse states? A: Yes, if operations share steps
- Q: How do we optimize? A: Minimize states, share signals

### Week 14: Microcode ROM Setup

**Theory Session (45 min)**:
- What is microcode?
- Microcode ROM concept
- Address formation (instruction + step)
- Data output (control signals)

**Lab Session (90 min)**:
- Plan microcode format
- Design address formation logic
- Connect EEPROM as microcode ROM
- Test address formation
- Verify EEPROM outputs

**Key Points**:
- Microcode stores control sequences in ROM
- Address = instruction opcode + microstep
- Data = control signals for that step

**Common Questions**:
- Q: Why use microcode? A: Flexible, organized, scalable
- Q: How many EEPROMs? A: Depends on control signal count
- Q: Can we change microcode? A: Yes, EEPROM is programmable

### Week 15: Instruction Decoding

**Theory Session (45 min)**:
- Instruction format (opcode + operand)
- Instruction Register (IR)
- Opcode extraction
- Address formation for microcode

**Lab Session (90 min)**:
- Build Instruction Register
- Extract opcode bits
- Connect to microcode address
- Add microstep counter
- Test instruction decoding

**Key Points**:
- IR holds current instruction
- Opcode selects microcode sequence
- Microstep counter tracks progress

**Common Questions**:
- Q: How do we extract opcode? A: Use upper bits of IR
- Q: What about operand? A: Used during execution, not for microcode address
- Q: How many opcodes? A: Depends on opcode bit width

### Week 16: Complete Microcode System

**Theory Session (45 min)**:
- Integrating all components
- Microcode execution flow
- Testing microcode systems
- Debugging microcode

**Lab Session (90 min)**:
- Connect all components
- Program EEPROM with microcode
- Load test instruction
- Run microcode sequence
- Verify execution
- Test multiple instructions

**Key Points**:
- All components work together
- Microcode automates control
- Testing verifies correctness

**Common Questions**:
- Q: What if microcode is wrong? A: Reprogram EEPROM
- Q: How do we debug? A: Check signals step-by-step
- Q: Can we add instructions? A: Yes, add microcode sequences

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide pre-designed state machine
- Simplify to fewer operations
- Step-by-step microcode programming guide
- Pair with stronger students

**Extension for advanced students**:
- Design more complex state machines
- Implement conditional microcode
- Optimize microcode sequences
- Add new instructions

### Common Misconceptions

1. **"Microcode is programming"**
   - Clarify: It's a lookup table, not a program
   - Show how it maps addresses to signals

2. **"More states is better"**
   - Clarify: Fewer, well-designed states are better
   - Show optimization techniques

3. **"Microcode is complex"**
   - Start simple: One instruction, few steps
   - Build up complexity gradually

### Assessment Checkpoints

**Week 13**: Can students build complex state machine?
**Week 14**: Can students set up microcode ROM?
**Week 15**: Can students implement instruction decoding?
**Week 16**: Can students execute instructions via microcode?

## Resources

- Microcode format templates
- EEPROM programming guides
- Instruction decoding examples
- State machine design templates

## Next Week

After completing microcode, students move to address decoding (Week 13-15).

---

*Microcode bridges instructions and hardware control*
