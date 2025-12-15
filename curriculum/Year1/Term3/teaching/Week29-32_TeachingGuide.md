# Week 29-32: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 29-32, providing a complete teaching roadmap for Control Concepts.

## Learning Objectives

Students will:
- Understand control signals and their role
- Build simple state machines
- Create sequencers that generate control signals
- Understand microcode concepts (introduction)
- Build control logic for simple operations
- Coordinate multiple subsystems with control

## Suggested Lesson Flow

### Week 29, Session 1: Introduction to Control (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is control: 20 min
- Theory: Why control needed: 20 min
- Lab: Manual control: 30 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term3/Week29-32_Control.md`
- Lab: `labs/Term3/Lab29-32_Control.md`
- All subsystems from previous labs

**Key Points**:
1. **Control signals**: Tell subsystems what to do
2. **Coordination**: Multiple subsystems must work together
3. **Sequencing**: Operations must be ordered

**Teaching Tips**:
- Start with manual control
- Show why automation needed
- Demonstrate coordination
- Emphasize sequencing

**Common Questions**:
- "Why control?" → Coordinate subsystems
- "What are control signals?" → Tell devices what to do
- "How complex?" → Start simple, build up

### Week 29, Session 2: Simple Sequencer (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Sequencers: 20 min
- Lab: Build sequencer: 40 min
- Lab: Test sequencer: 20 min
- Wrap-up: 10 min

**Materials**:
- Counter, decoder
- Clock source
- LEDs

**Key Points**:
1. **Sequencer**: Generates signal sequence
2. **Counter**: Tracks state
3. **Decoder**: Generates signals

**Teaching Tips**:
- Build step-by-step
- Show state progression
- Test with operations
- Celebrate automation!

**Common Issues**:
- Sequencer not advancing → Check clock
- Wrong signals → Verify decoder
- Timing issues → Check synchronization

### Week 30-31: State Machines and Integration

**Timing**: As needed for state machines and integration

### Week 32: Assessment

**Timing**: As needed for assessment

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
- Research microcode
- Advanced state machines

**Lab**:
- Build complex sequencer
- Add multiple operations
- Research modern control

## Assessment Integration

### Formative Assessment

**During Lessons**:
- Control building observation
- Operation testing
- Understanding checks

### Summative Assessment

**End of Week 32**:
- Practical: Build control system
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"Control is complicated"**
   - Actually: Just signals coordinating devices
   - Start simple, build up

2. **"Sequencers are hard"**
   - Actually: Just counter + decoder
   - Simple when understood

3. **"Microcode is advanced"**
   - Actually: Just stored control patterns
   - Concept is simple

## Resources Needed

**For Theory**:
- Theory reading material
- Control diagrams
- Whiteboard/markers

**For Lab**:
- Counters, decoders
- Logic gates
- Flip-flops
- LEDs, switches

## Connection to Next Week

**Week 33-36 Preview**:
- This week: Control (coordination)
- Next week: Integration (everything together)
- Build on: All previous concepts

---

*This teaching guide links theory understanding with practical building*
