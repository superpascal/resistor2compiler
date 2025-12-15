# Week 10-12: Program Counter and Instruction Register - Teaching Guide

## Overview

This teaching guide supports the delivery of Program Counter and Instruction Register construction over 4 weeks. Students build components that enable automatic instruction fetching.

## Learning Objectives

By the end of this week-block, students will:
- Build the Program Counter (PC)
- Build the Instruction Register (IR)
- Understand instruction format
- Test instruction fetching
- Prepare for microcode (Weeks 17-20)

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Term 1 (Data Path)
- ✅ Understand counters (Year 1-2)
- ✅ Understand registers (Year 1-2)
- ✅ Understand control signals

## Week-by-Week Breakdown

### Week 13: Building the Program Counter

**Theory Session (45 min)**:
- PC function and role
- PC construction
- Control signals (CO, CE, CL)
- PC operation modes

**Lab Session (90 min)**:
- Build PC from counter
- Connect control signals
- Test increment
- Test load (for jumps)
- Test reset

**Key Points**:
- PC tracks instruction address
- Increments automatically
- Can load for jumps
- Connects to MAR

**Common Questions**:
- Q: Why do we need PC? A: Tracks which instruction to fetch
- Q: How does it work? A: Increments after each instruction
- Q: What about jumps? A: Can load new address

### Week 14: Connecting PC to System

**Theory Session (45 min)**:
- PC-MAR connection
- Address bus usage
- Control signal (CO)
- Integration with memory

**Lab Session (90 min)**:
- Connect PC to MAR
- Add control signal
- Test address flow
- Test with memory
- Verify integration

**Key Points**:
- PC provides addresses
- MAR holds addresses
- Control signal coordinates
- Memory uses addresses

**Common Questions**:
- Q: Why connect to MAR? A: MAR interfaces with memory
- Q: How do we control? A: CO signal enables PC output
- Q: What about timing? A: Clock coordinates

### Week 15: Building the Instruction Register

**Theory Session (45 min)**:
- IR function and role
- IR construction (8-bit)
- Instruction format (opcode + operand)
- Control signal (II)

**Lab Session (90 min)**:
- Build IR from registers
- Connect to data bus
- Test instruction loading
- Test opcode/operand extraction
- Verify IR operation

**Key Points**:
- IR holds current instruction
- 8-bit: 4-bit opcode + 4-bit operand
- Loaded during fetch
- Used during execution

**Common Questions**:
- Q: Why 8-bit? A: 4-bit opcode + 4-bit operand
- Q: What's opcode? A: Operation code (what to do)
- Q: What's operand? A: Data/address for operation

### Week 16: Instruction Fetch Testing

**Theory Session (45 min)**:
- Fetch cycle sequence
- Component coordination
- Signal timing
- Testing procedures

**Lab Session (90 min)**:
- Connect all components
- Load test program
- Test fetch cycle
- Verify instruction in IR
- Verify PC increment
- Document fetch

**Key Points**:
- Fetch: PC→MAR→Memory→IR
- PC increments after fetch
- IR holds instruction
- Ready for decode/execute

**Common Questions**:
- Q: What's the sequence? A: PC→MAR, Memory→IR, PC++
- Q: How do we test? A: Single-step, verify each step
- Q: What's next? A: Microcode (Weeks 17-20)

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide PC circuit reference
- Step-by-step connection guide
- Extra time for integration
- Pair with stronger students
- Review counter concepts

**Extension for advanced students**:
- Add jump capability
- Expand PC to 8 bits
- Add instruction decoding
- Optimize fetch cycle

### Common Misconceptions

1. **"PC is just a counter"**
   - Clarify: Tracks program execution
   - Show role in fetch cycle

2. **"IR is just a register"**
   - Clarify: Holds instruction being executed
   - Show opcode/operand separation

3. **"Fetch is simple"**
   - Clarify: Requires coordination
   - Show signal sequence

### Assessment Checkpoints

**Week 13**: Can students build PC?
**Week 14**: Can students connect PC to system?
**Week 15**: Can students build IR?
**Week 16**: Can students test fetch cycle?

## Resources

- PC circuit diagrams
- IR circuit diagrams
- Fetch cycle diagrams
- Instruction format reference

## Next Week

After completing PC and IR, students move to microcode ROM (Week 17-20).

---

*PC and IR enable automatic instruction fetching*
