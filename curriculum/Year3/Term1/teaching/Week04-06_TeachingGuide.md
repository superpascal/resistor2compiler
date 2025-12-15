# Week 4-6: Register File and Buses - Teaching Guide

## Overview

This teaching guide supports the delivery of register file and bus construction over 4 weeks. Students build the data storage and transfer system for the SAP-1 CPU.

## Learning Objectives

By the end of this week-block, students will:
- Build Register A and Register B
- Implement tri-state bus connections
- Build bus control logic
- Test register operations
- Integrate registers with ALU

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 1-3 (ALU)
- ✅ Understand registers (Year 1-2)
- ✅ Understand tri-state buffers
- ✅ Understand buses

## Week-by-Week Breakdown

### Week 5: Building Register A

**Theory Session (45 min)**:
- Register A function
- Register construction
- Control signals (AI, AO)
- Clocked operation
- Testing procedures

**Lab Session (90 min)**:
- Build Register A
- Connect control signals
- Test loading
- Test output
- Verify operation

**Key Points**:
- Register A is primary accumulator
- Can load from bus
- Can output to bus
- Clocked operation

**Common Questions**:
- Q: Why Register A? A: Primary accumulator, stores results
- Q: How does it work? A: Loads on clock when enabled
- Q: What are control signals? A: AI (in), AO (out)

### Week 6: Building Register B

**Theory Session (45 min)**:
- Register B function
- Same construction as A
- Independent control
- Bus sharing
- No conflicts

**Lab Session (90 min)**:
- Build Register B
- Use separate controls
- Test independently
- Test with Register A
- Verify no conflicts

**Key Points**:
- Register B provides second operand
- Independent from Register A
- Shares bus with A
- Tri-state prevents conflicts

**Common Questions**:
- Q: Why two registers? A: Need two operands for ALU
- Q: Do they conflict? A: No, tri-state prevents conflicts
- Q: Can we have more? A: Yes, but two is sufficient for SAP-1

### Week 7: Bus Integration

**Theory Session (45 min)**:
- Bus protocol
- Tri-state control
- Only one output at a time
- Bus control logic
- Signal coordination

**Lab Session (90 min)**:
- Connect registers to bus
- Connect ALU to bus
- Build bus control
- Test bus protocol
- Verify no conflicts

**Key Points**:
- Bus is shared resource
- Only one output enabled
- Tri-state prevents conflicts
- Control logic coordinates

**Common Questions**:
- Q: Why tri-state? A: Prevents bus conflicts
- Q: What if two enabled? A: Conflict, wrong data, possible damage
- Q: How do we control? A: Control logic ensures only one active

### Week 8: Register-ALU Integration

**Theory Session (45 min)**:
- Complete data path
- Register-ALU connection
- Operation sequence
- Signal coordination
- Testing integration

**Lab Session (90 min)**:
- Connect registers to ALU
- Connect ALU to bus
- Connect bus to registers
- Test complete operation
- Verify data path

**Key Points**:
- All components connected
- Data flows correctly
- Signals coordinated
- Complete data path works

**Common Questions**:
- Q: How does data flow? A: Registers → ALU → Bus → Registers
- Q: What's the sequence? A: Load, operate, store
- Q: How do we test? A: Complete operation, verify result

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide register circuit reference
- Step-by-step connection guide
- Extra time for integration
- Pair with stronger students
- Review bus concepts

**Extension for advanced students**:
- Add more registers
- Expand bus width
- Optimize bus design
- Add register file

### Common Misconceptions

1. **"Registers are just storage"**
   - Clarify: Active components with control
   - Show input/output capabilities

2. **"Bus is just wires"**
   - Clarify: Has protocol, requires coordination
   - Show tri-state control

3. **"Any component can use bus"**
   - Clarify: Only one output at a time
   - Show bus protocol

### Assessment Checkpoints

**Week 5**: Can students build Register A?
**Week 6**: Can students build Register B?
**Week 7**: Can students implement bus correctly?
**Week 8**: Can students integrate registers with ALU?

## Resources

- Register circuit diagrams
- Bus connection diagrams
- Control signal tables
- Integration checklists

## Next Week

After completing registers and buses, students move to memory subsystem (Week 7-9).

---

*Registers and buses form the data path foundation*
