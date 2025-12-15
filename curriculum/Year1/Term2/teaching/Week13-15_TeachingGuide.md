# Week 13-15: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 13-15, providing a complete teaching roadmap for Sequential Logic (Flip-Flops and Registers).

## Learning Objectives

Students will:
- Understand combinational vs sequential logic
- Build SR latches from gates
- Build and use D flip-flops
- Create multi-bit registers
- Understand clocked storage
- Build timing diagrams

## Suggested Lesson Flow

### Week 13, Session 1: Sequential vs Combinational (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Combinational vs Sequential: 20 min
- Theory: Storage problem: 15 min
- Lab: Build SR latch: 25 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term2/Week13-15_SequentialLogic.md`
- Lab: `labs/Term2/Lab13-15_FlipFlopsRegisters.md`
- Logic gate ICs (74HC02)

**Key Points**:
1. **Combinational**: No memory, instant response
2. **Sequential**: Has memory, state-dependent
3. **SR latch**: Basic storage element
4. **S=1, R=1**: Forbidden!

**Teaching Tips**:
- Contrast with combinational logic
- Use analogies (light switch vs toggle)
- Build SR latch step-by-step
- Emphasize forbidden state

**Common Questions**:
- "Why do we need sequential logic?" → Computers need memory
- "What's the difference?" → Sequential has memory
- "Why is S=1, R=1 forbidden?" → Creates unstable state

### Week 13, Session 2: D Flip-Flop (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Problem with latches: 15 min
- Theory: D flip-flop: 20 min
- Lab: Build circuit: 30 min
- Lab: Timing diagrams: 15 min
- Wrap-up: 10 min

**Materials**:
- 74HC74 IC
- 555 timer or manual clock
- Switches, LEDs

**Key Points**:
1. **Problem with latches**: No control, race conditions
2. **D flip-flop**: Clocked storage
3. **Clock edge**: Only changes on edge
4. **Synchronous**: All flip-flops change together

**Teaching Tips**:
- Show problem with latches first
- Then show D flip-flop solution
- Emphasize clock control
- Practice timing diagrams

**Common Issues**:
- Confusing latch vs flip-flop → Emphasize clock
- Clock timing → Show with oscilloscope if available
- When Q changes → Only on clock edge

### Week 14, Session 1: Building Registers (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is register: 15 min
- Lab: Build 4-bit register: 30 min
- Lab: Register operations: 20 min
- Wrap-up: 10 min

**Materials**:
- Two 74HC74 ICs
- 555 timer
- DIP switches, LEDs

**Key Points**:
1. **Register**: Multiple flip-flops together
2. **Common clock**: All change together
3. **Operations**: Load, hold, read
4. **Applications**: CPU registers

**Teaching Tips**:
- Build step-by-step
- Emphasize common clock
- Demonstrate operations
- Connect to CPU concepts

**Common Issues**:
- Clock not common → Check connections
- Bits not synchronized → Verify clock
- Operations confusing → Demonstrate clearly

### Week 14, Session 2: Register Applications (60-90 min)

**Timing**:
- Review: 5 min
- Lab: Data storage: 20 min
- Lab: Pipeline: 20 min
- Lab: Shift register intro: 20 min
- Assessment: 20 min
- Wrap-up: 10 min

**Materials**:
- Registers from previous session
- Additional circuits for applications

**Key Points**:
1. **Data storage**: Store results
2. **Pipeline**: Stage-by-stage processing
3. **Shift register**: Shift bits
4. **Real applications**: Used in CPUs

**Teaching Tips**:
- Build real applications
- Show practical uses
- Connect to CPU concepts
- Celebrate understanding!

### Week 15, Session 1: Assessment (60-90 min)

**Timing**:
- Review: 10 min
- Practical assessment: 30 min
- Written assessment: 20 min
- Portfolio review: 10 min
- Wrap-up: 10 min

**Materials**:
- Assessment materials
- Components for building

**Assessment Tasks**:
1. Build SR latch
2. Build D flip-flop
3. Build 4-bit register
4. Written quiz

## Differentiation Strategies

### Support for Struggling Students

**Theory**:
- Extra practice with concepts
- Simplified explanations
- More analogies
- One-on-one support

**Lab**:
- Pre-built circuits to analyze
- Step-by-step guidance
- Extra time
- Pair with stronger student

### Extension for Advanced Students

**Theory**:
- Research different flip-flop types
- Advanced timing concepts
- Pipeline architectures

**Lab**:
- Build 8-bit register
- Build shift register
- Advanced: Register file
- Research projects

## Assessment Integration

### Formative Assessment

**During Lessons**:
- Concept understanding checks
- Circuit building observation
- Timing diagram practice
- Operation demonstrations

### Summative Assessment

**End of Week 15**:
- Practical: Build circuits
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"Flip-flops are complicated"**
   - Actually: They're just controlled latches
   - Clock makes them predictable

2. **"Clock makes things faster"**
   - Actually: Clock synchronizes, doesn't speed up
   - It coordinates operations

3. **"Registers are the same as memory"**
   - Actually: Registers are faster, smaller
   - Different uses

4. **"Sequential logic is hard"**
   - Actually: It's just logic with memory
   - Build on combinational understanding

## Resources Needed

**For Theory**:
- Theory reading material
- Timing diagram examples
- Whiteboard/markers

**For Lab**:
- Logic gate ICs (74HC02)
- 74HC74 ICs (D flip-flops)
- 555 timer (for clock)
- Switches, LEDs
- Oscilloscope (if available)

## Connection to Next Week

**Week 16-18 Preview**:
- This week: Storage (registers)
- Next week: Counters (registers that count)
- Build on: Flip-flop understanding, clock operation

---

*This teaching guide links theory understanding with practical building*
