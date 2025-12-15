# Week 25-28: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 25-28, providing a complete teaching roadmap for Memory and MAR.

## Learning Objectives

Students will:
- Understand how memory chips work
- Build memory address registers
- Read and write data to memory
- Understand address decoding
- Connect memory to bus system
- Understand memory timing

## Suggested Lesson Flow

### Week 25, Session 1: Introduction to Memory (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is memory: 20 min
- Theory: Memory chips: 25 min
- Lab: Build interface: 25 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term3/Week25-28_Memory.md`
- Lab: `labs/Term3/Lab25-28_Memory.md`
- Memory chip (74LS189 or similar)

**Key Points**:
1. **Memory**: Stores data at addresses
2. **Read/Write**: Two operations
3. **Address**: Selects location

**Teaching Tips**:
- Use post office analogy
- Show memory organization
- Build simple interface first
- Emphasize address concept

**Common Questions**:
- "How does memory work?" → Stores data at addresses
- "What's the difference from registers?" → Memory is larger, slower
- "Why addresses?" → Need to select location

### Week 25, Session 2: Memory Address Register (60-90 min)

**Timing**:
- Review: 5 min
- Theory: What is MAR: 15 min
- Lab: Build MAR: 30 min
- Lab: Connect to memory: 20 min
- Wrap-up: 10 min

**Materials**:
- 4-bit register (74HC173)
- Memory chip
- Control switches

**Key Points**:
1. **MAR**: Holds address
2. **Separates**: Address from data
3. **Standard**: CPU component

**Teaching Tips**:
- Show why MAR is needed
- Build step-by-step
- Connect to memory
- Test address control

**Common Issues**:
- MAR not loading → Check control signal
- Address not reaching memory → Verify connections
- Timing issues → Check clock

### Week 26, Session 1: Reading from Memory (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Read operation: 20 min
- Lab: Build read circuit: 40 min
- Lab: Test reads: 20 min
- Wrap-up: 10 min

**Materials**:
- MAR, memory, tri-state buffers
- Bus, LEDs

**Key Points**:
1. **Read**: Get data from address
2. **Tri-state**: Controls bus access
3. **Timing**: Address must be stable

**Teaching Tips**:
- Show read sequence
- Build read circuit
- Test thoroughly
- Emphasize timing

**Common Issues**:
- No data → Check read signal
- Wrong data → Verify address
- Bus conflict → Check tri-state

### Week 26, Session 2: Writing to Memory (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Write operation: 20 min
- Lab: Build write circuit: 40 min
- Lab: Test writes: 20 min
- Wrap-up: 10 min

**Materials**:
- MAR, memory, bus
- Control logic

**Key Points**:
1. **Write**: Put data at address
2. **Data on bus**: Before write
3. **Timing**: Critical

**Teaching Tips**:
- Show write sequence
- Build write circuit
- Test thoroughly
- Emphasize timing

**Common Issues**:
- Data not stored → Check write signal
- Wrong address → Verify MAR
- Timing issues → Check sequence

### Week 27-28: Integration and Assessment

**Timing**: As needed for integration and assessment

## Differentiation Strategies

### Support for Struggling Students

**Theory**:
- Extra analogies
- Simplified explanations
- More examples

**Lab**:
- Pre-built components
- Step-by-step guidance
- Extra time

### Extension for Advanced Students

**Theory**:
- Research memory types
- Advanced timing concepts

**Lab**:
- Build larger memory
- Add address decoding
- Research modern memory

## Assessment Integration

### Formative Assessment

**During Lessons**:
- Memory building observation
- Operation testing
- Understanding checks

### Summative Assessment

**End of Week 28**:
- Practical: Build memory system
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"Memory is like registers"**
   - Actually: Larger, slower, different use
   - Registers are faster, smaller

2. **"Read and write are the same"**
   - Actually: Different operations
   - Different signals, different timing

3. **"MAR is optional"**
   - Actually: Standard CPU component
   - Separates address from data

## Resources Needed

**For Theory**:
- Theory reading material
- Memory diagrams
- Whiteboard/markers

**For Lab**:
- Memory chip (74LS189 or similar)
- Registers (74HC173)
- Tri-state buffers
- LEDs, switches

## Connection to Next Week

**Week 29-32 Preview**:
- This week: Memory (storage)
- Next week: Control (coordination)
- Build on: All subsystems

---

*This teaching guide links theory understanding with practical building*
