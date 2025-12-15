# Week 1-3: Review and ALU Subsystem - Teaching Guide

## Overview

This teaching guide supports the delivery of Year 1-2 review and ALU subsystem construction over 4 weeks. Students build the computational core of the SAP-1 CPU.

## Learning Objectives

By the end of this week-block, students will:
- Review all Year 1-2 concepts
- Build 4-bit adder/subtractor
- Implement carry and zero flags
- Test ALU operations
- Integrate ALU with registers

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Years 1-2
- ✅ Understand combinational logic
- ✅ Understand sequential logic
- ✅ Understand binary arithmetic
- ✅ Can build circuits on breadboard

## Week-by-Week Breakdown

### Week 1: Year 1-2 Review

**Theory Session (45 min)**:
- Review electronics fundamentals
- Review digital logic
- Review sequential circuits
- Review memory and control
- Review system integration

**Lab Session (90 min)**:
- Review exercises
- Build simple circuits
- Test understanding
- Address any gaps
- Prepare for ALU

**Key Points**:
- Solid foundation is essential
- Review identifies gaps
- Practice reinforces learning
- Ready for CPU construction

**Common Questions**:
- Q: Do we need to remember everything? A: Core concepts, yes
- Q: What if we forgot something? A: Review now, ask questions
- Q: How detailed should review be? A: Focus on concepts needed for CPU

### Week 2: Building the Adder

**Theory Session (45 min)**:
- 4-bit adder design
- Binary addition
- Carry propagation
- Adder IC (74HC283)
- Testing procedures

**Lab Session (90 min)**:
- Place 74HC283 on breadboard
- Connect inputs and outputs
- Test addition operations
- Verify results
- Document circuit

**Key Points**:
- Adder is core of ALU
- Binary addition rules
- Carry propagation important
- Testing verifies correctness

**Common Questions**:
- Q: Why 4-bit? A: Keeps design simple, sufficient for learning
- Q: Can we use gates instead? A: Yes, but IC is simpler
- Q: How do we test? A: Try various number pairs, verify results

### Week 3: Implementing Subtraction

**Theory Session (45 min)**:
- Two's complement method
- Subtraction as addition
- XOR gates for inversion
- Carry in for +1
- Testing subtraction

**Lab Session (90 min)**:
- Add XOR gates to B inputs
- Connect SUB control signal
- Connect SUB to carry in
- Test subtraction operations
- Verify two's complement

**Key Points**:
- Subtraction uses two's complement
- Invert and add 1
- SUB signal controls operation
- Test thoroughly

**Common Questions**:
- Q: Why two's complement? A: Simplifies hardware, standard method
- Q: How does it work? A: Invert bits, add 1, then add
- Q: What about negative results? A: Two's complement represents them

### Week 4: Flags and Integration

**Theory Session (45 min)**:
- Carry flag purpose
- Zero flag purpose
- Flag generation logic
- Flag storage (flip-flops)
- Flag usage

**Lab Session (90 min)**:
- Build carry flag circuit
- Build zero flag circuit
- Test flag operations
- Integrate with ALU
- Test complete ALU

**Key Points**:
- Flags indicate operation results
- Carry: Overflow/underflow
- Zero: Result is zero
- Flags used for conditional operations

**Common Questions**:
- Q: Why flags? A: Indicate operation results, enable conditionals
- Q: How are flags used? A: For conditional jumps (JZ, JC)
- Q: When are flags set? A: After each ALU operation

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide pre-built adder for reference
- Step-by-step construction guide
- Extra time for concepts
- Pair with stronger students
- Review foundational concepts

**Extension for advanced students**:
- Build adder from gates
- Add logic operations (AND, OR, XOR)
- Expand to 8-bit ALU
- Add more flags

### Common Misconceptions

1. **"ALU is just an adder"**
   - Clarify: ALU performs multiple operations
   - Show subtraction, flags, future operations

2. **"Flags are optional"**
   - Clarify: Flags essential for conditionals
   - Show how CPU uses flags

3. **"Subtraction is different"**
   - Clarify: Subtraction is addition with two's complement
   - Show the connection

### Assessment Checkpoints

**Week 1**: Can students recall Year 1-2 concepts?
**Week 2**: Can students build adder correctly?
**Week 3**: Can students implement subtraction?
**Week 4**: Can students add flags and integrate?

## Resources

- Adder circuit diagrams
- Two's complement examples
- Flag logic diagrams
- Test case templates

## Next Week

After completing ALU, students move to registers and buses (Week 4-6).

---

*The ALU is the computational heart of the CPU*
