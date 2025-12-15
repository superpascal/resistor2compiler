# Week 16-18: Breadboard Prototype Construction - Teaching Guide

## Overview

This teaching guide supports breadboard prototype construction over 4 weeks. Students build and test a minimal 65C816 system.

## Learning Objectives

By the end of this week-block, students will:
- Build minimal 65C816 system
- Connect CPU, memory, and basic I/O
- Test reset and clock circuits
- Test basic memory access
- Verify CPU operation

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 13-15 (System Design)
- ✅ Complete system design
- ✅ Understand 65C816 architecture
- ✅ Have construction experience (from SAP-1)

## Week-by-Week Breakdown

### Week 21: Power, Clock, and Reset

**Theory Session (45 min)**:
- Power supply design
- Clock circuit design
- Reset circuit design
- Initial testing

**Lab Session (90 min)**:
- Place 65C816
- Connect power
- Add decoupling
- Connect clock
- Build reset circuit
- Test power/clock/reset

**Key Points**:
- Power must be stable
- Clock must be stable
- Reset must work correctly
- Test before proceeding

**Common Questions**:
- Q: What voltage? A: 5V for 65C816
- Q: What clock speed? A: Start with 1 MHz for prototype
- Q: How to test? A: Check signals with scope/analyzer

### Week 22: Memory Connection

**Theory Session (45 min)**:
- Memory connection
- Address bus connection
- Data bus connection
- Control signals
- Address decoding

**Lab Session (90 min)**:
- Place SRAM
- Connect address bus
- Connect data bus
- Connect control
- Implement decoding
- Test RAM
- Program and test ROM

**Key Points**:
- Memory is critical
- Address decoding essential
- Test thoroughly
- Verify access

**Common Questions**:
- Q: Which memory? A: 32KB or 64KB SRAM
- Q: How to connect? A: Follow datasheet, use design
- Q: What if doesn't work? A: Check connections, check decoding

### Week 23: Basic I/O and Integration

**Theory Session (45 min)**:
- I/O interface design
- VIA connection
- I/O address decoding
- System integration

**Lab Session (90 min)**:
- Place VIA
- Connect to buses
- Implement I/O decoding
- Connect basic I/O
- Test I/O
- Integrate system
- Test integration

**Key Points**:
- I/O enables interaction
- Address decoding needed
- Test I/O access
- Verify integration

**Common Questions**:
- Q: Which I/O? A: Start with one VIA, basic I/O
- Q: How to connect? A: Memory-mapped, follow datasheet
- Q: What if doesn't work? A: Check connections, check decoding

### Week 24: CPU Verification

**Theory Session (45 min)**:
- CPU testing procedures
- Reset vector verification
- Instruction execution
- Debugging techniques

**Lab Session (90 min)**:
- Program test in ROM
- Reset CPU
- Monitor address lines
- Verify reset vector
- Verify execution
- Test memory/I/O
- Document prototype

**Key Points**:
- Verify CPU works
- Test systematically
- Document everything
- Prepare for Year 5

**Common Questions**:
- Q: How do we verify? A: Monitor signals, check execution
- Q: What if doesn't work? A: Debug systematically, check design
- Q: Ready for Year 5? A: Yes, if prototype working

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide construction checklist
- Step-by-step connection guide
- Extra time for work
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Add more I/O
- Test at higher speeds
- Add features
- Help other students

### Common Misconceptions

1. **"Prototype must be perfect"**
   - Clarify: Minimal but functional
   - Show learning value

2. **"Can't build on breadboard"**
   - Clarify: Many have done it
   - Show it's possible

3. **"Too complex to debug"**
   - Clarify: Systematic approach works
   - Show debugging method

### Assessment Checkpoints

**Week 21**: Can students get CPU powered and clocked?
**Week 22**: Can students connect and test memory?
**Week 23**: Can students integrate system?
**Week 24**: Is CPU verified and working?

## Resources

- Construction checklists
- Connection guides
- Testing procedures
- Debugging guides

## Next Year

After completing prototype, students move to Year 5: Complete 16-bit system construction.

---

*Prototype development tests design and enables learning*
