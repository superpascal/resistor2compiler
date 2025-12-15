# Week 19-21: Memory and Banking on 65C816 - Teaching Guide

## Overview

This teaching guide supports memory expansion and banking implementation over 4 weeks. Students expand the 65C816 system beyond 64KB.

## Learning Objectives

By the end of this week-block, students will:
- Understand memory banking concepts
- Expand RAM beyond 64KB
- Implement bank switching
- Test memory banking
- Document memory map

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Term 2 (65C816 Prototype)
- ✅ Have working prototype
- ✅ Understand 65C816 architecture
- ✅ Understand address decoding

## Week-by-Week Breakdown

### Week 1: Memory Expansion Planning

**Theory Session (45 min)**:
- Memory banking concepts
- 24-bit addressing
- Bank organization
- Memory map design

**Lab Session (90 min)**:
- Review current memory
- Plan expansion
- Design memory map
- Plan address decoding
- Document plan

**Key Points**:
- Banking enables >64KB
- Plan before building
- Document everything
- Consider future expansion

**Common Questions**:
- Q: How much memory? A: Start with 128KB, can expand
- Q: How many banks? A: Depends on memory size
- Q: How to organize? A: Plan map, consider usage

### Week 2: Bank Register Implementation

**Theory Session (45 min)**:
- Bank register concepts
- Bank switching logic
- Address decoding for banks
- Implementation methods

**Lab Session (90 min)**:
- Build bank register circuit
- Implement bank selection
- Test bank register
- Verify selection
- Document implementation

**Key Points**:
- Bank register selects bank
- Address decoding uses bank
- Test before proceeding
- Document implementation

**Common Questions**:
- Q: How to implement? A: I/O register, address decoding
- Q: How to test? A: Write to register, verify selection
- Q: What if wrong? A: Check logic, verify connections

### Week 3: Memory Connection and Testing

**Theory Session (45 min)**:
- Memory connection
- Address decoding for banks
- Bank testing procedures
- Verification methods

**Lab Session (90 min)**:
- Connect additional memory
- Implement bank decoding
- Test each bank
- Write/read test patterns
- Verify bank isolation

**Key Points**:
- Connect carefully
- Test each bank
- Verify isolation
- Document results

**Common Questions**:
- Q: How to connect? A: Follow design, check datasheet
- Q: How to test? A: Write patterns, read back, verify
- Q: What if conflicts? A: Check decoding, verify isolation

### Week 4: Complete Banking System

**Theory Session (45 min)**:
- Complete system testing
- Cross-bank access
- System verification
- Documentation

**Lab Session (90 min)**:
- Complete expansion
- Test all banks
- Test bank switching
- Test cross-bank access
- Document system

**Key Points**:
- Test completely
- Verify all banks
- Document memory map
- Prepare for I/O

**Common Questions**:
- Q: How to verify? A: Test all banks, verify switching
- Q: Ready for I/O? A: Yes, if banking working
- Q: What next? A: I/O integration

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide expansion checklist
- Step-by-step connection guide
- Extra time for work
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Further memory expansion
- Advanced banking features
- Optimize bank organization
- Help other students

### Common Misconceptions

1. **"Banking is complex"**
   - Clarify: Simple bank register
   - Show basic implementation

2. **"Need all 16 MB"**
   - Clarify: Start with few banks
   - Show practical limits

3. **"Banking is automatic"**
   - Clarify: Software-controlled
   - Show bank register usage

### Assessment Checkpoints

**Week 1**: Can students plan expansion?
**Week 2**: Can students implement bank register?
**Week 3**: Can students connect and test memory?
**Week 4**: Is banking system complete?

## Resources

- Memory expansion guides
- Bank switching examples
- Address decoding guides
- Memory map templates

## Next Week

After completing banking, students move to I/O subsystems (Week 22-24).

---

*Memory banking enables larger programs and prepares for complete systems*
