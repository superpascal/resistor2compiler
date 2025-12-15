# Week 9-12: Teaching Guide

## Overview

This guide links the theory and lab materials for Weeks 9-12, providing a complete teaching roadmap for Combinational Logic Circuits.

## Learning Objectives

Students will:
- Understand binary number representation
- Build half-adder and full-adder circuits
- Use 4-bit binary adder ICs
- Build and use multiplexers
- Build and use decoders
- Apply combinational logic to solve problems

## Suggested Lesson Flow

### Week 9, Session 1: Binary Numbers and Half-Adders (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Binary numbers: 20 min
- Theory: Half-adder: 15 min
- Lab: Build half-adder: 25 min
- Wrap-up: 10 min

**Materials**:
- Theory: `theory/Term1/Week09-12_CombinationalLogic.md`
- Lab: `labs/Term1/Lab09-12_CombinationalLogic.md`
- Logic gate ICs (XOR, AND)

**Key Points**:
1. **Binary numbers**: Base 2 system
2. **Half-adder**: Adds two bits
3. **Sum = XOR, Carry = AND**

**Teaching Tips**:
- Practice binary conversions together
- Build half-adder step-by-step
- Emphasize: This is how computers add!

**Common Questions**:
- "Why binary?" → Easy for electronics
- "Why learn this?" → Foundation of computer arithmetic
- "Is this how real computers add?" → Yes, exactly!

### Week 9, Session 2: Full-Adder (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Full-adder: 20 min
- Lab: Build full-adder: 30 min
- Lab: 2-bit adder: 15 min
- Wrap-up: 10 min

**Materials**:
- Logic gate ICs
- Switches, LEDs

**Key Points**:
1. **Full-adder**: Adds three bits (with carry-in)
2. **Multi-bit adders**: Chain full-adders
3. **Carry propagation**: How carry ripples through

**Teaching Tips**:
- Show limitation of half-adder
- Build full-adder from half-adders
- Demonstrate 2-bit adder
- Celebrate first multi-bit addition!

**Common Issues**:
- Confusing half vs full adder → Emphasize carry-in
- Carry propagation → Show step-by-step
- Wiring complexity → Build carefully

### Week 10, Session 1: 4-bit Binary Adder IC (60-90 min)

**Timing**:
- Review: 5 min
- Theory: 74HC283: 20 min
- Lab: Build circuit: 30 min
- Lab: Practice: 20 min
- Wrap-up: 10 min

**Materials**:
- 74HC283 IC
- DIP switches
- LEDs

**Key Points**:
1. **Why use IC?**: All built-in, fast, reliable
2. **4-bit addition**: Two 4-bit numbers → 4-bit sum
3. **Carry-out**: For overflow

**Teaching Tips**:
- Show IC pinout clearly
- Build along with students
- Test with various numbers
- Show cascading for 8-bit

**Common Issues**:
- Wrong pin connections → Use datasheet
- Confusing inputs → Label clearly
- Overflow → Explain carry-out

### Week 10, Session 2: Carry Propagation and Assessment (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Carry propagation: 20 min
- Assessment: 40 min
- Wrap-up: 10 min

**Materials**:
- Oscilloscope (if available)
- Assessment materials

**Key Points**:
1. **Carry propagation**: How carry ripples through
2. **Why it matters**: Slower for larger numbers
3. **Modern solutions**: Carry look-ahead

**Teaching Tips**:
- Demonstrate with oscilloscope if available
- Show timing relationships
- Discuss modern CPU solutions

### Week 11, Session 1: Multiplexers (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Multiplexers: 20 min
- Lab: Build 2-to-1 MUX: 25 min
- Lab: Use 74HC157: 20 min
- Wrap-up: 10 min

**Materials**:
- Logic gate ICs
- 74HC157 IC
- Switches, LEDs

**Key Points**:
1. **Multiplexer**: Data selector
2. **2-to-1 MUX**: Selects between two inputs
3. **74HC157**: Quad multiplexer for buses

**Teaching Tips**:
- Use analogies (TV remote, radio tuner)
- Build from gates first
- Then use IC
- Show bus selection application

**Common Questions**:
- "Why use multiplexers?" → Select data sources
- "Where used?" → Bus selection, data routing
- "How does it work?" → Select line chooses input

### Week 11, Session 2: Multiplexer Applications (60-90 min)

**Timing**:
- Review: 5 min
- Lab: Bus selection: 20 min
- Lab: Data routing: 20 min
- Lab: Function selection: 20 min
- Wrap-up: 10 min

**Materials**:
- 74HC157 IC
- Multiple circuits for applications

**Key Points**:
1. **Bus selection**: Choose data source
2. **Data routing**: Route to destination
3. **Function selection**: Choose operation

**Teaching Tips**:
- Build real applications
- Show practical uses
- Connect to CPU concepts

### Week 12, Session 1: Decoders (60-90 min)

**Timing**:
- Review: 5 min
- Theory: Decoders: 20 min
- Lab: Build 2-to-4 decoder: 25 min
- Lab: Use 74HC139: 20 min
- Wrap-up: 10 min

**Materials**:
- Logic gate ICs
- 74HC139 IC
- Switches, LEDs

**Key Points**:
1. **Decoder**: Address selector
2. **2-to-4 decoder**: One output active
3. **74HC139**: Dual decoder

**Teaching Tips**:
- Contrast with multiplexer
- Show address decoding
- Demonstrate memory selection

**Common Questions**:
- "What's the difference from MUX?" → Opposite function
- "Where used?" → Memory selection, I/O selection
- "Why one-hot?" → Only one active at a time

### Week 12, Session 2: Assessment (60-90 min)

**Timing**:
- Review: 10 min
- Practical assessment: 40 min
- Written assessment: 20 min
- Wrap-up: 10 min

**Materials**:
- Assessment materials
- Components for building

**Assessment Tasks**:
1. Build multiplexer
2. Build decoder
3. Build 4-bit adder
4. Written quiz

## Differentiation Strategies

### Support for Struggling Students

**Theory**:
- Extra practice with binary
- Simplified explanations
- More examples
- One-on-one support

**Lab**:
- Pre-built circuits to analyze
- Step-by-step guidance
- Extra time
- Pair with stronger student

### Extension for Advanced Students

**Theory**:
- Advanced adder designs
- Research applications
- Boolean algebra

**Lab**:
- Build 8-bit adder
- Design custom circuits
- Research carry look-ahead
- Build BCD adder

## Assessment Integration

### Formative Assessment

**During Lessons**:
- Binary conversion practice
- Circuit building observation
- Understanding checks
- Problem-solving ability

### Summative Assessment

**End of Week 12**:
- Practical: Build circuits
- Written: Concepts quiz
- Portfolio: Lab notebook

## Common Misconceptions

1. **"Binary is complicated"**
   - Actually: It's just base 2
   - Practice makes it easy

2. **"Adders are only for math"**
   - Actually: Fundamental to CPUs
   - Used everywhere

3. **"Multiplexers and decoders are the same"**
   - Actually: Opposite functions
   - MUX selects data, decoder selects address

4. **"Combinational logic is easy"**
   - Actually: Gets complex quickly
   - But foundation is simple

## Resources Needed

**For Theory**:
- Theory reading material
- Binary arithmetic reference
- Whiteboard/markers

**For Lab**:
- Logic gate ICs
- 74HC283 (adder)
- 74HC157 (multiplexer)
- 74HC139 (decoder)
- Switches, LEDs

## Connection to Next Week

**Term 2 Preview**:
- This week: Combinational logic (no memory)
- Next week: Sequential logic (with memory)
- Build on: Gate understanding, circuit building

---

*This teaching guide links theory understanding with practical building*
