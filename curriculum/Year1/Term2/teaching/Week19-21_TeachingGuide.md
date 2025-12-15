# Week 19-21: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 19-21, providing a complete teaching roadmap for System Buses.

## Learning Objectives

Students will:
- Understand what a system bus is
- Build a shared bus system
- Use tri-state buffers to control bus access
- Understand bus contention and how to avoid it
- Build register-to-bus connections
- Understand how CPUs use buses

## Suggested Lesson Flow

### Week 19, Session 1: Introduction to System Buses (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is bus: 20 min
- Theory: Bus contention problem: 20 min
- Lab: Demonstrate problem: 20 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term2/Week19-21_SystemBuses.md`
- Lab: `labs/Term2/Lab19-21_SystemBuses.md`
- Registers, wires

**Key Points**:
1. **Bus**: Shared pathway for data
2. **Problem**: Multiple outputs conflict
3. **Solution**: Tri-state buffers

**Teaching Tips**:
- Use highway analogy
- Demonstrate bus contention first
- Then show solution
- Emphasize why buses are needed

**Common Questions**:
- "Why use buses?" → Saves wires, flexible
- "What's bus contention?" → Multiple drivers conflict
- "How to solve?" → Tri-state buffers

### Week 19, Session 2: Tri-State Buffers (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Tri-state buffers: 20 min
- Lab: Test buffers: 30 min
- Lab: Multiple buffers: 30 min
- Wrap-up: 10 min

**Materials**:
- 74HC125, 74HC244 ICs
- Switches, LEDs

**Key Points**:
1. **Tri-state**: HIGH, LOW, or DISCONNECTED
2. **Enable**: Controls connection
3. **Only one active**: Prevents conflicts

**Teaching Tips**:
- Test buffers individually first
- Then show multiple on bus
- Emphasize high-impedance state
- Show how it solves contention

**Common Issues**:
- Confusing enable logic → Show truth table
- High-impedance concept → Explain floating
- Multiple buffers → Show only one active

### Week 20, Session 1: Register-to-Bus System (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Register-to-bus: 20 min
- Lab: Build system: 40 min
- Lab: Test operations: 20 min
- Wrap-up: 10 min

**Materials**:
- Registers, tri-state buffers
- Decoder for selection
- LEDs

**Key Points**:
1. **Register outputs**: Through tri-state to bus
2. **Enable selects**: Which register drives
3. **Decoder**: Ensures only one active

**Teaching Tips**:
- Build step-by-step
- Show decoder selection
- Demonstrate operations
- Connect to CPU concepts

**Common Issues**:
- Wrong enable logic → Check decoder
- Bus not working → Verify connections
- Conflicts → Check only one enable

### Week 20, Session 2: Bus Operations (60-90 min)

**Timing**:
- Review: 5 min
- Lab: Read operations: 25 min
- Lab: Write operations: 25 min
- Lab: Complete system: 20 min
- Wrap-up: 10 min

**Materials**:
- Complete bus system
- Control logic

**Key Points**:
1. **Read**: Device outputs to bus
2. **Write**: Bus writes to device
3. **Protocol**: Sequence of operations

**Teaching Tips**:
- Show read operation
- Show write operation
- Demonstrate complete cycle
- Connect to CPU operation

### Week 21: SAP-1 Bus and Assessment

**Timing**: As needed for SAP-1 bus and assessment

## Differentiation Strategies

### Support for Struggling Students

**Theory**:
- Extra analogies
- Simplified explanations
- More examples

**Lab**:
- Pre-built circuits
- Step-by-step guidance
- Extra time

### Extension for Advanced Students

**Theory**:
- Research modern buses
- Advanced protocols

**Lab**:
- Build 8-bit bus
- Add more devices
- Complete SAP-1

## Assessment Integration

### Formative Assessment

**During Lessons**:
- Bus building observation
- Understanding checks
- Operation demonstrations

### Summative Assessment

**End of Week 21**:
- Practical: Build bus system
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"Buses are complicated"**
   - Actually: Just shared wires
   - Simple when understood

2. **"Multiple devices can talk at once"**
   - Actually: Only one at a time
   - Tri-state prevents conflicts

3. **"Tri-state is hard"**
   - Actually: Just enable/disable
   - Simple concept

## Resources Needed

**For Theory**:
- Theory reading material
- Bus diagrams
- Whiteboard/markers

**For Lab**:
- Registers (74HC173)
- Tri-state buffers (74HC125, 74HC244)
- Decoders (74HC139)
- LEDs, switches

## Connection to Next Week

**Week 22-24 Preview**:
- This week: Buses (communication)
- Next week: ALU (computation)
- Build on: Buses, registers, adders

---

*This teaching guide links theory understanding with practical building*
