# Week 22-24: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 22-24, providing a complete teaching roadmap for ALU Subsystem.

## Learning Objectives

Students will:
- Integrate adder, registers, and bus into ALU subsystem
- Build carry and zero flags
- Perform addition and subtraction operations
- Understand two's complement for subtraction
- Build a complete data path
- Understand how this relates to CPU design

## Suggested Lesson Flow

### Week 22, Session 1: ALU Subsystem Design (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is ALU: 20 min
- Theory: ALU design: 25 min
- Lab: Planning: 20 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term2/Week22-24_ALU.md`
- Lab: `labs/Term2/Lab22-24_ALU.md`
- Components for building

**Key Points**:
1. **ALU**: Arithmetic Logic Unit
2. **Components**: Registers, adder, bus, flags
3. **Integration**: All together

**Teaching Tips**:
- Start with block diagram
- Show how components connect
- Plan before building
- Emphasize integration

**Common Questions**:
- "What is ALU?" → Performs calculations
- "Why integrate?" → Complete system
- "How complex?" → Build step-by-step

### Week 22, Session 2: Addition Operation (60-90 min)

**Timing**:
- Review: 5 min
- Lab: Build basic ALU: 40 min
- Lab: Test addition: 30 min
- Wrap-up: 10 min

**Materials**:
- Registers, adder, bus
- LEDs for display

**Key Points**:
1. **Addition**: A + B
2. **Data flow**: Registers → Bus → Adder → Result
3. **Testing**: Verify operations

**Teaching Tips**:
- Build step-by-step
- Test each component
- Verify addition works
- Celebrate progress!

**Common Issues**:
- Bus not working → Check tri-state buffers
- Wrong results → Verify connections
- Timing issues → Check clock

### Week 23, Session 1: Subtraction Operation (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Two's complement: 20 min
- Lab: Build subtraction: 40 min
- Lab: Test subtraction: 20 min
- Wrap-up: 10 min

**Materials**:
- XOR gates
- Adder with carry-in
- Operation select

**Key Points**:
1. **Two's complement**: Method for subtraction
2. **Inversion**: XOR gates invert B
3. **Carry-in**: Adds 1 for two's complement

**Teaching Tips**:
- Explain two's complement clearly
- Show how it works
- Build circuit step-by-step
- Test thoroughly

**Common Issues**:
- Two's complement confusing → Use examples
- Wrong results → Check XOR and carry-in
- Operation select → Verify logic

### Week 23, Session 2: Flags (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Flags: 20 min
- Lab: Build carry flag: 20 min
- Lab: Build zero flag: 20 min
- Lab: Test flags: 20 min
- Wrap-up: 10 min

**Materials**:
- Flip-flops for flags
- NOR gates for zero
- LEDs for display

**Key Points**:
1. **Carry flag**: Overflow from addition
2. **Zero flag**: Result is zero
3. **Why flags**: CPU uses for decisions

**Teaching Tips**:
- Build flags one at a time
- Test each flag
- Show CPU applications
- Connect to programming

**Common Issues**:
- Flags not updating → Check clock timing
- Wrong flag values → Verify logic
- Timing issues → Synchronize with operation

### Week 24: Integration and Assessment

**Timing**: As needed for integration and assessment

## Differentiation Strategies

### Support for Struggling Students

**Theory**:
- Extra examples
- Simplified explanations
- More practice

**Lab**:
- Pre-built components
- Step-by-step guidance
- Extra time

### Extension for Advanced Students

**Theory**:
- Research modern ALUs
- Advanced operations

**Lab**:
- Add logic operations
- Build 8-bit ALU
- Add more flags

## Assessment Integration

### Formative Assessment

**During Lessons**:
- ALU building observation
- Operation testing
- Understanding checks

### Summative Assessment

**End of Week 24**:
- Practical: Build ALU
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"ALU is complicated"**
   - Actually: Just adder + registers + bus
   - Build step-by-step

2. **"Two's complement is hard"**
   - Actually: Just invert and add 1
   - Simple when understood

3. **"Flags are optional"**
   - Actually: Essential for CPU
   - Used for decisions

## Resources Needed

**For Theory**:
- Theory reading material
- ALU diagrams
- Whiteboard/markers

**For Lab**:
- Registers, adder
- XOR gates
- Flip-flops
- Tri-state buffers
- LEDs, switches

## Connection to Next Week

**Term 3 Preview**:
- This week: ALU (computation)
- Next week: Memory (storage)
- Build on: All previous concepts

---

*This teaching guide links theory understanding with practical building*
