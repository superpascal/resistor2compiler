# Week 16-18: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 16-18, providing a complete teaching roadmap for Binary Counters.

## Learning Objectives

Students will:
- Build binary counters from flip-flops
- Use counter ICs (74HC161, 74HC163)
- Understand modulo counting
- Build a program counter
- Understand how CPUs track instruction addresses

## Suggested Lesson Flow

### Week 16, Session 1: Introduction to Counters (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is counter: 20 min
- Lab: Build 2-bit counter: 25 min
- Lab: Use 74HC161: 20 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term2/Week16-18_Counters.md`
- Lab: `labs/Term2/Lab16-18_Counters.md`
- 74HC74, 74HC161 ICs

**Key Points**:
1. **Counters**: Sequential circuits that count
2. **Binary counters**: Count in binary
3. **Counter ICs**: Ready-made solutions

**Teaching Tips**:
- Build from flip-flops first (understand how)
- Then use IC (practical solution)
- Emphasize program counter concept
- Connect to CPU operation

### Week 16, Session 2: Modulo Counter (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Modulo counting: 20 min
- Lab: Build modulo-10: 40 min
- Lab: Display: 20 min
- Wrap-up: 10 min

**Materials**:
- 74HC161 counter
- Logic gates
- 7-segment display

**Key Points**:
1. **Modulo**: Count to N, then wrap
2. **Detection**: Detect target value
3. **Reset/Load**: Wrap to start

**Teaching Tips**:
- Build modulo-10 first
- Show wrapping behavior
- Add display for visual feedback
- Celebrate working counter!

### Week 17, Session 1: Program Counter (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Program Counter: 20 min
- Lab: Build PC: 40 min
- Lab: Jump operation: 20 min
- Wrap-up: 10 min

**Materials**:
- 74HC161 counter
- Memory simulation
- LEDs

**Key Points**:
1. **Program Counter**: Tracks instruction address
2. **Increment**: Sequential execution
3. **Load**: Jump/branch operations

**Teaching Tips**:
- Emphasize CPU connection
- Show sequential execution
- Demonstrate jumps
- Connect to programming concepts

### Week 17-18: Assessment and Review

**Timing**: As needed for assessment and review

## Differentiation Strategies

### Support for Struggling Students

**Theory**:
- Extra practice with concepts
- Simplified explanations
- More examples

**Lab**:
- Pre-built circuits to analyze
- Step-by-step guidance
- Extra time

### Extension for Advanced Students

**Theory**:
- Research CPU program counters
- Advanced counter designs

**Lab**:
- Build up/down counter
- Build frequency divider
- Advanced: Counter with preset

## Assessment Integration

### Formative Assessment

**During Lessons**:
- Counter building observation
- Understanding checks
- Operation demonstrations

### Summative Assessment

**End of Week 18**:
- Practical: Build counters
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"Counters are complicated"**
   - Actually: Just flip-flops chained
   - Simple when understood

2. **"Program counter is just a counter"**
   - Actually: Special purpose in CPU
   - Essential for execution

3. **"Modulo is hard"**
   - Actually: Just count and wrap
   - Simple concept

## Resources Needed

**For Theory**:
- Theory reading material
- Counter diagrams
- Whiteboard/markers

**For Lab**:
- 74HC74, 74HC161 ICs
- 555 timer
- LEDs, switches
- 7-segment display (optional)

## Connection to Next Week

**Week 19-21 Preview**:
- This week: Counters (sequential)
- Next week: Buses (shared pathways)
- Build on: Sequential logic, registers

---

*This teaching guide links theory understanding with practical building*
