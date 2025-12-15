# Week 16-18: Control Unit Integration - Teaching Guide

## Overview

This teaching guide supports the integration of the control unit with the data path over 4 weeks. Students create a working CPU that executes instructions automatically.

## Learning Objectives

By the end of this week-block, students will:
- Integrate control unit with data path
- Implement fetch-decode-execute cycle
- Test instruction execution
- Debug CPU operation
- Verify complete CPU functionality

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 17-20 (Microcode ROM)
- ✅ Complete data path (Term 1)
- ✅ Complete control components (Weeks 13-20)
- ✅ Understand CPU operation

## Week-by-Week Breakdown

### Week 21: Control-Data Path Integration

**Theory Session (45 min)**:
- Complete CPU architecture
- Control-data path connection
- Signal coordination
- Integration testing

**Lab Session (90 min)**:
- Connect microcode to control signals
- Connect signals to components
- Verify all connections
- Test signal generation
- Verify coordination
- Check for conflicts

**Key Points**:
- All components connected
- Signals coordinated
- No conflicts
- Ready for testing

**Common Questions**:
- Q: How do we connect? A: Microcode outputs → control signals → components
- Q: What if conflicts? A: Check signal coordination, verify only one output
- Q: How do we test? A: Test signals individually, then together

### Week 22: Fetch-Decode-Execute Implementation

**Theory Session (45 min)**:
- CPU cycle overview
- Fetch phase
- Decode phase
- Execute phase

**Lab Session (90 min)**:
- Set up clock circuit
- Add run/halt switch
- Add single-step button
- Load test program
- Test fetch cycle
- Test decode cycle
- Test execute cycle

**Key Points**:
- Three-phase cycle
- Clock synchronizes
- Single-step for debugging
- Test each phase

**Common Questions**:
- Q: What's the cycle? A: Fetch, decode, execute, repeat
- Q: How fast? A: Start slow (single-step), then increase
- Q: How do we debug? A: Single-step, check signals

### Week 23: Instruction Execution Testing

**Theory Session (45 min)**:
- Instruction execution flow
- Testing strategies
- Debugging techniques
- Verification methods

**Lab Session (90 min)**:
- Load simple program
- Run in single-step mode
- Verify each instruction
- Check control signals
- Verify data flow
- Test arithmetic program
- Verify results

**Key Points**:
- Test systematically
- Verify each step
- Check signals
- Verify results

**Common Questions**:
- Q: How do we test? A: Single-step, verify each step
- Q: What if wrong? A: Debug step-by-step, check signals
- Q: How do we verify? A: Check results, check signals, check data

### Week 24: Complete CPU Testing

**Theory Session (45 min)**:
- Complete CPU testing
- Multiple program testing
- Performance testing
- Optimization

**Lab Session (90 min)**:
- Test arithmetic program
- Test control flow program
- Verify all instructions
- Test at different speeds
- Debug issues
- Optimize if needed
- Document system

**Key Points**:
- Test thoroughly
- Multiple programs
- Different speeds
- Document everything

**Common Questions**:
- Q: What programs to test? A: Arithmetic, control flow, simple programs
- Q: What if issues? A: Debug systematically, get help if needed
- Q: How do we optimize? A: Add decoupling, improve timing

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide integration checklist
- Step-by-step connection guide
- Extra time for testing
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Add more instructions
- Optimize performance
- Add debugging features
- Expand capabilities

### Common Misconceptions

1. **"CPU is complex"**
   - Clarify: Built from simple components
   - Show how pieces fit

2. **"Microcode is magic"**
   - Clarify: Simple lookup table
   - Show how it works

3. **"CPU is fast"**
   - Clarify: Our CPU is slow (for learning)
   - Show clock speed

### Assessment Checkpoints

**Week 21**: Can students integrate control unit?
**Week 22**: Can students implement CPU cycle?
**Week 23**: Can students execute instructions?
**Week 24**: Can students test complete CPU?

## Resources

- Integration checklists
- CPU cycle diagrams
- Test program examples
- Debugging guides

## Next Term

After completing control unit, students move to Term 3: SAP-1 Completion and Programming.

---

*Control unit integration creates a working CPU*
