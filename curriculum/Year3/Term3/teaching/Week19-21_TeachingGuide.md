# Week 19-21: SAP-1 Bring-up and Testing - Teaching Guide

## Overview

This teaching guide supports the bring-up and testing of the complete SAP-1 system over 4 weeks. Students get their CPU working and verify operation.

## Learning Objectives

By the end of this week-block, students will:
- Complete system integration
- Perform initial bring-up
- Test all subsystems
- Debug hardware issues
- Verify CPU operation

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Terms 1-2
- ✅ Complete system built
- ✅ All components connected
- ✅ Understand system operation

## Week-by-Week Breakdown

### Week 25: Initial Power-up

**Theory Session (45 min)**:
- Bring-up procedures
- Safety considerations
- Initial checks
- Power-up sequence

**Lab Session (90 min)**:
- Final connection check
- Check for shorts
- Verify power supply
- Apply power carefully
- Monitor system
- Check basic signals

**Key Points**:
- Safety first
- Check before powering
- Monitor carefully
- Fix issues immediately

**Common Questions**:
- Q: What if something smokes? A: Power off immediately, find cause
- Q: How do we check for shorts? A: Multimeter between power and ground
- Q: What if no power? A: Check connections, check supply

### Week 26: Subsystem Testing

**Theory Session (45 min)**:
- Testing strategies
- Subsystem testing
- Test procedures
- Documentation

**Lab Session (90 min)**:
- Test data path
- Test memory
- Test control unit
- Test microcode
- Test clock/reset
- Document results

**Key Points**:
- Test systematically
- Test each subsystem
- Document results
- Fix issues found

**Common Questions**:
- Q: How do we test? A: Test each component, verify operation
- Q: What if subsystem fails? A: Test components individually
- Q: How do we document? A: Record test, result, any issues

### Week 27: Integration Testing

**Theory Session (45 min)**:
- Integration testing
- Component interaction
- Signal coordination
- System verification

**Lab Session (90 min)**:
- Test fetch cycle
- Test decode cycle
- Test execute cycle
- Test complete operations
- Verify coordination
- Document integration

**Key Points**:
- Test components together
- Verify coordination
- Check for conflicts
- Verify timing

**Common Questions**:
- Q: How do we test integration? A: Test complete operations
- Q: What if conflicts? A: Check signal coordination
- Q: How do we verify? A: Check results, check signals

### Week 28: System Verification

**Theory Session (45 min)**:
- System verification
- Optimization techniques
- Signal integrity
- Final checks

**Lab Session (90 min)**:
- Run test program
- Verify execution
- Add optimizations
- Final system check
- Document system
- Prepare for programming

**Key Points**:
- Verify system works
- Optimize if needed
- Document status
- Ready for programming

**Common Questions**:
- Q: How do we verify? A: Run programs, check results
- Q: What optimizations? A: Decoupling, signal integrity
- Q: Ready for programming? A: Yes, if system verified

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide testing checklist
- Step-by-step testing guide
- Extra time for debugging
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Advanced optimizations
- Performance testing
- Reliability testing
- Help other students

### Common Misconceptions

1. **"If it doesn't work, it's broken"**
   - Clarify: Usually wiring or timing
   - Show debugging approach

2. **"Debugging is guessing"**
   - Clarify: Systematic approach works
   - Show methodology

3. **"More power is better"**
   - Clarify: Correct voltage important
   - Show power requirements

### Assessment Checkpoints

**Week 25**: Can students power up safely?
**Week 26**: Can students test subsystems?
**Week 27**: Can students test integration?
**Week 28**: Is system verified and ready?

## Resources

- Testing checklists
- Debugging guides
- Optimization guides
- Documentation templates

## Next Week

After completing bring-up, students move to machine code programming (Week 29-32).

---

*Bring-up and testing ensure reliable CPU operation*
