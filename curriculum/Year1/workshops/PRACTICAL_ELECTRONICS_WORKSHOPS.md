# Practical Electronics for Inventors - Year 1 Workshops

## Overview

This document outlines workshops based on **"Practical Electronics for Inventors, Fourth Edition"** by Paul Scherz and Simon Monk. These workshops are designed to make Year 1 activities more enjoyable while directly building knowledge for the curriculum.

**Integration Strategy**: Workshops complement the main curriculum labs by providing:
- **Additional hands-on practice** with concepts
- **Fun, engaging projects** that reinforce learning
- **Real-world applications** of electronics principles
- **Troubleshooting experience** and practical techniques

**Workshop Format**: Each workshop is 1-2 hours and can be run:
- As **optional enrichment** activities
- During **extended lab sessions**
- As **homework projects** (with supervision)
- In **after-school club** sessions

---

## Term 1 Workshops

### Workshop 1: Voltage Divider Challenge (Weeks 1-2)
**Based on**: Chapter 2 (Theory) - Voltage Dividers  
**Curriculum Connection**: Reinforces Ohm's law, voltage, current concepts from Weeks 1-2

**Objective**: Build and understand voltage dividers, which are fundamental to many circuits.

**Activities**:
1. Build a simple voltage divider (two resistors in series)
2. Measure voltages at different points
3. Calculate expected values using Ohm's law
4. Build a variable voltage divider using a potentiometer
5. Use it to dim an LED (practical application)

**Learning Outcomes**:
- Understand voltage division
- Apply Ohm's law in practice
- See how potentiometers work
- Understand why voltage dividers are used in circuits

**Materials**:
- Resistors: 1kΩ, 10kΩ, 100kΩ potentiometer
- LED with current-limiting resistor
- Multimeter
- Breadboard

**Assessment**: Students calculate expected voltages, measure actual values, and explain why they match (or don't match) theory.

---

### Workshop 2: Capacitor Charging/Discharging Race (Weeks 3-5)
**Based on**: Chapter 3 (Basic Electronic Components) - Capacitors  
**Curriculum Connection**: Reinforces RC timing concepts from Weeks 3-5

**Objective**: Explore capacitor behavior through hands-on experiments.

**Activities**:
1. Build RC charging circuit (resistor + capacitor)
2. Measure charging time with different resistor values
3. Build RC discharging circuit
4. Create a "capacitor timer" that lights an LED after a delay
5. Build a simple "capacitor memory" circuit (holds charge)

**Learning Outcomes**:
- Understand RC time constants
- See how capacitors store energy
- Apply timing concepts to practical circuits
- Understand why capacitors are used for timing

**Materials**:
- Resistors: 1kΩ, 10kΩ, 100kΩ
- Capacitors: 10µF, 100µF electrolytic (watch polarity!)
- LEDs with resistors
- Multimeter
- Stopwatch or oscilloscope

**Assessment**: Students measure time constants, compare calculated vs. measured values, and explain capacitor behavior.

---

### Workshop 3: LED Color Mixing Project (Weeks 3-5)
**Based on**: Chapter 5 (Optoelectronics) - LEDs  
**Curriculum Connection**: Reinforces current limiting, component usage from Weeks 1-5

**Objective**: Build a fun project that teaches LED characteristics and color mixing.

**Activities**:
1. Build RGB LED color mixer (three LEDs: Red, Green, Blue)
2. Use potentiometers to control each color
3. Create different colors by mixing
4. Build a simple "mood light" that cycles through colors
5. Measure current through each LED

**Learning Outcomes**:
- Understand LED forward voltage and current
- Learn about RGB color mixing
- Practice current limiting calculations
- See practical application of LEDs

**Materials**:
- RGB LED (common cathode or common anode)
- Resistors: 220Ω x 3 (one per color)
- Potentiometers: 10kΩ x 3
- Breadboard

**Assessment**: Students calculate resistor values, build working color mixer, and demonstrate color combinations.

---

### Workshop 4: Logic Gate Detective Game (Weeks 6-8)
**Based on**: Chapter 12 (Digital Electronics) - Logic Gates  
**Curriculum Connection**: Reinforces logic gate concepts from Weeks 6-8

**Objective**: Make learning logic gates fun through a detective-style game.

**Activities**:
1. Build mystery logic gate circuits (instructor hides the gate type)
2. Students test inputs and outputs to identify the gate
3. Build a "combination lock" using multiple gates
4. Create a "light chaser" using XOR gates
5. Build a simple "security system" using AND/OR gates

**Learning Outcomes**:
- Reinforce truth table knowledge
- Practice gate identification
- See practical applications of logic gates
- Understand how gates combine to create functions

**Materials**:
- Logic gate ICs: 74HC08 (AND), 74HC32 (OR), 74HC04 (NOT), 74HC86 (XOR)
- Switches or DIP switches
- LEDs with resistors
- Breadboard

**Assessment**: Students correctly identify mystery gates, build working combination lock, and explain how their security system works.

---

### Workshop 5: Binary Calculator Project (Weeks 9-12)
**Based on**: Chapter 12 (Digital Electronics) - Adders and Arithmetic  
**Curriculum Connection**: Directly supports 4-bit adder project from Weeks 9-12

**Objective**: Build a working binary calculator that reinforces adder concepts.

**Activities**:
1. Build 1-bit full adder (from gates or 74HC283)
2. Extend to 4-bit adder
3. Add input switches for two 4-bit numbers
4. Display result on LEDs (binary) or 7-segment display (decimal)
5. Add a "carry indicator" LED
6. Test with multiple number combinations

**Learning Outcomes**:
- Reinforce adder operation
- Understand binary arithmetic
- See how computers perform addition
- Practice troubleshooting digital circuits

**Materials**:
- 74HC283 4-bit adder IC (or build from gates)
- DIP switches (8 total for two 4-bit inputs)
- LEDs (5 total: 4 for sum, 1 for carry)
- 7-segment display decoder (optional, for decimal display)
- Breadboard

**Assessment**: Students build working calculator, test multiple addition problems, and explain how binary addition works.

---

### Workshop 6: Multiplexer Display System (Weeks 9-12)
**Based on**: Chapter 12 (Digital Electronics) - Multiplexers  
**Curriculum Connection**: Reinforces multiplexer concepts from Weeks 9-12

**Objective**: Build a practical display system using multiplexers.

**Activities**:
1. Build 2-to-1 multiplexer from gates
2. Use 74HC157 quad MUX to select between two 4-bit inputs
3. Create a "data selector" that switches between two LED patterns
4. Build a simple "message display" that cycles through patterns
5. Understand how computers use multiplexers for bus selection

**Learning Outcomes**:
- Understand multiplexer operation
- See practical bus selection application
- Reinforce how computers select data sources
- Practice with control signals

**Materials**:
- 74HC157 quad 2-to-1 multiplexer
- DIP switches (8 total for two 4-bit inputs)
- LEDs (4 for output)
- Control switch (for select signal)
- Breadboard

**Assessment**: Students build working multiplexer system, demonstrate data selection, and explain bus selection concept.

---

## Term 2 Workshops

### Workshop 7: Flip-Flop Memory Game (Weeks 13-15)
**Based on**: Chapter 12 (Digital Electronics) - Flip-Flops  
**Curriculum Connection**: Reinforces flip-flop and register concepts from Weeks 13-15

**Objective**: Build a fun memory game using flip-flops.

**Activities**:
1. Build SR latch from NOR gates
2. Build D flip-flop circuit (74HC74)
3. Create a "memory button" that remembers if it was pressed
4. Build a "sequence memory" game (remember button press sequence)
5. Create a 4-bit "score counter" using flip-flops

**Learning Outcomes**:
- Understand how flip-flops store state
- See memory in action
- Reinforce clocked vs. unclocked storage
- Understand why computers need memory

**Materials**:
- 74HC02 (NOR gates for SR latch)
- 74HC74 (dual D flip-flops)
- Push buttons
- LEDs with resistors
- Breadboard

**Assessment**: Students build working memory circuits, demonstrate state storage, and explain how flip-flops work.

---

### Workshop 8: Program Counter Display (Weeks 16-18)
**Based on**: Chapter 12 (Digital Electronics) - Counters  
**Curriculum Connection**: Directly supports Program Counter concept from Weeks 16-18

**Objective**: Build an enhanced Program Counter with visual display.

**Activities**:
1. Build 4-bit counter (74HC161 or 74HC163)
2. Add manual clock button
3. Connect to 7-segment display (shows 0-9, A-F in hex)
4. Add reset button
5. Add "pause" function
6. Create "countdown timer" mode
7. Demonstrate how this relates to CPU Program Counter

**Learning Outcomes**:
- Reinforce counter operation
- Understand Program Counter concept
- See how counters are used in computers
- Practice with display systems

**Materials**:
- 74HC161 or 74HC163 (4-bit counter)
- 74HC4511 (BCD to 7-segment decoder) or similar
- 7-segment display (common cathode)
- Push buttons (clock, reset)
- LEDs (optional, for binary display)
- Breadboard

**Assessment**: Students build working counter display, demonstrate counting, and explain Program Counter concept.

---

### Workshop 9: Bus Communication System (Weeks 19-21)
**Based on**: Chapter 12 (Digital Electronics) - Tri-State Logic  
**Curriculum Connection**: Directly supports bus and tri-state concepts from Weeks 19-21

**Objective**: Build a working bus system that demonstrates data sharing.

**Activities**:
1. Build two 4-bit registers (74HC173 or 74HC574)
2. Add tri-state buffers (74HC125 or 74HC244)
3. Create shared 4-bit bus
4. Demonstrate loading different values into registers
5. Show how only one register can drive the bus at a time
6. Demonstrate bus contention (what happens if both enabled)
7. Build a "data transfer" system (copy from Register A to Register B via bus)

**Learning Outcomes**:
- Understand bus operation
- See why tri-state is needed
- Understand bus contention problems
- Reinforce how computers share data

**Materials**:
- 74HC173 or 74HC574 (4-bit registers)
- 74HC125 or 74HC244 (tri-state buffers)
- DIP switches (for data input)
- LEDs (for bus display)
- Control switches (for enable signals)
- Breadboard

**Assessment**: Students build working bus system, demonstrate data transfer, and explain bus protocol.

---

### Workshop 10: ALU Challenge Project (Weeks 22-24)
**Based on**: Chapter 12 (Digital Electronics) - Arithmetic Logic Units  
**Curriculum Connection**: Directly supports ALU subsystem from Weeks 22-24

**Objective**: Build an enhanced ALU with multiple operations.

**Activities**:
1. Integrate 4-bit adder from Term 1
2. Add subtraction capability (two's complement)
3. Add logic operations (AND, OR, XOR) using gates
4. Build operation selector (multiplexer to choose ADD/SUB/AND/OR/XOR)
5. Add flag indicators (Carry, Zero, Negative)
6. Create a "calculator" that performs multiple operations
7. Test with various number combinations

**Learning Outcomes**:
- Reinforce ALU concepts
- Understand multiple operations
- See how computers perform arithmetic and logic
- Integrate all Term 2 components

**Materials**:
- 74HC283 (4-bit adder) or build from gates
- Logic gates: 74HC08 (AND), 74HC32 (OR), 74HC86 (XOR)
- 74HC157 (multiplexer for operation selection)
- DIP switches (for inputs and operation selection)
- LEDs (for outputs and flags)
- Breadboard

**Assessment**: Students build working multi-operation ALU, test all operations, and explain how it works.

---

## Cross-Term Workshops

### Workshop 11: Power Supply Project (Any Term)
**Based on**: Chapter 11 (Voltage Regulators and Power Supplies)  
**Curriculum Connection**: Supports all labs by teaching power management

**Objective**: Build a regulated power supply for all projects.

**Activities**:
1. Build simple 5V regulator circuit (LM7805)
2. Add input filtering capacitors
3. Add output filtering capacitors
4. Add LED power indicator
5. Add current limiting (fuse or polyfuse)
6. Test with various loads
7. Measure voltage regulation

**Learning Outcomes**:
- Understand power supply design
- Learn about voltage regulation
- Understand decoupling capacitors
- See why clean power is important

**Materials**:
- LM7805 voltage regulator
- Capacitors: 100µF, 0.1µF (input and output)
- LED with resistor (power indicator)
- Breadboard or perfboard

**Assessment**: Students build working power supply, measure regulation, and explain why clean power matters.

---

### Workshop 12: Oscilloscope Skills (Any Term)
**Based on**: Chapter 7 (Hands-on Electronics) - Test Equipment  
**Curriculum Connection**: Supports all labs by teaching measurement skills

**Objective**: Master oscilloscope use for debugging circuits.

**Activities**:
1. Learn oscilloscope controls
2. Measure DC voltage
3. Measure AC signals
4. Capture timing diagrams
5. Measure frequency
6. Debug a "broken" circuit (instructor provides)
7. Document signals from working circuits

**Learning Outcomes**:
- Master oscilloscope operation
- Understand signal measurement
- Learn debugging techniques
- See how professionals troubleshoot

**Materials**:
- Oscilloscope (school lab equipment)
- Function generator (optional)
- Test circuits (provided by instructor)

**Assessment**: Students successfully measure signals, capture timing diagrams, and debug a circuit.

---

## Workshop Integration Guide

### When to Run Workshops

**Option 1: Enrichment Sessions**
- Run workshops as optional after-school activities
- Students who want extra practice can attend
- No pressure, just fun learning

**Option 2: Extended Lab Time**
- Add workshops to extended lab sessions
- Run during "flex time" or "enrichment periods"
- Integrate into regular lab schedule

**Option 3: Homework Projects**
- Assign workshops as optional homework
- Students build at home (with supervision)
- Share results in class

**Option 4: Club Activities**
- Run workshops in electronics club
- More relaxed, social learning environment
- Students can work at their own pace

### Workshop Prerequisites

Each workshop lists:
- **Required knowledge**: What students must know first
- **Materials needed**: Components and equipment
- **Time required**: How long the workshop takes
- **Difficulty level**: Beginner, Intermediate, Advanced

### Assessment Integration

Workshops can be assessed as:
- **Formative**: Practice and reinforcement (no grade)
- **Bonus points**: Extra credit for completing workshops
- **Portfolio items**: Document in Year 1 portfolio
- **Presentation**: Share workshop results with class

---

## Benefits of Workshops

### 1. Increased Engagement
- Fun, hands-on projects make learning enjoyable
- Students see immediate results
- Projects feel like "real" electronics work

### 2. Reinforced Learning
- Extra practice with concepts
- Different approach to same material
- Multiple ways to understand concepts

### 3. Practical Skills
- Real-world troubleshooting experience
- Component selection and usage
- Circuit design thinking

### 4. Confidence Building
- Success with projects builds confidence
- Students feel like "real" engineers
- Motivation for harder concepts

### 5. Direct Curriculum Support
- Every workshop directly supports curriculum topics
- No "busy work" - all activities have purpose
- Builds toward computer construction goals

---

## Workshop Materials List

### Basic Components (for all workshops)
- Resistors: 220Ω, 1kΩ, 10kΩ, 100kΩ
- Potentiometers: 10kΩ
- Capacitors: 0.1µF ceramic, 10µF electrolytic, 100µF electrolytic
- LEDs: Standard, RGB LED
- DIP switches: 4-bit, 8-bit
- Push buttons
- Breadboards
- Jumper wires

### Digital ICs (for Term 1-2 workshops)
- 74HC08 (AND gates)
- 74HC32 (OR gates)
- 74HC04 (NOT gates)
- 74HC86 (XOR gates)
- 74HC02 (NOR gates)
- 74HC283 (4-bit adder)
- 74HC157 (multiplexer)
- 74HC74 (D flip-flops)
- 74HC161/163 (counters)
- 74HC173/574 (registers)
- 74HC125/244 (tri-state buffers)
- 74HC4511 (7-segment decoder)

### Displays
- 7-segment displays (common cathode)
- LED arrays

### Power and Regulation
- LM7805 voltage regulator
- Power supply (5V, 1A minimum)

### Test Equipment
- Multimeters
- Oscilloscopes (school lab)
- Logic analyzers (optional, school lab)

---

## Workshop Schedule Suggestions

### Term 1 Schedule
- **Week 2**: Workshop 1 (Voltage Divider) - After learning Ohm's law
- **Week 4**: Workshop 2 (Capacitor Race) - After learning RC circuits
- **Week 4**: Workshop 3 (LED Color Mixing) - Fun project
- **Week 7**: Workshop 4 (Logic Gate Detective) - After learning gates
- **Week 11**: Workshop 5 (Binary Calculator) - After learning adders
- **Week 11**: Workshop 6 (Multiplexer Display) - After learning multiplexers

### Term 2 Schedule
- **Week 14**: Workshop 7 (Flip-Flop Memory) - After learning flip-flops
- **Week 17**: Workshop 8 (Program Counter Display) - After learning counters
- **Week 20**: Workshop 9 (Bus Communication) - After learning buses
- **Week 23**: Workshop 10 (ALU Challenge) - After learning ALU

### Cross-Term
- **Any time**: Workshop 11 (Power Supply) - Useful for all projects
- **Any time**: Workshop 12 (Oscilloscope Skills) - Useful for debugging

---

## Instructor Notes

### Workshop Management
- **Group size**: 2-3 students per workshop (collaborative learning)
- **Supervision**: Instructor circulates, helps when needed
- **Troubleshooting**: Encourage students to debug before asking for help
- **Documentation**: Students should document their work (photos, notes)

### Differentiation
- **Struggling students**: Provide more guidance, simpler variations
- **Advanced students**: Add challenges, extensions, more complex projects
- **All students**: Focus on understanding, not just building

### Safety
- All workshops use safe, low-voltage circuits (5V)
- Review safety rules before each workshop
- Supervise capacitor handling (polarity, discharge)
- Ensure proper current limiting for LEDs

---

## Summary

These workshops from "Practical Electronics for Inventors" provide:
- ✅ **Direct curriculum support** - Every workshop reinforces Year 1 topics
- ✅ **Engaging activities** - Fun projects that make learning enjoyable
- ✅ **Practical skills** - Real-world electronics experience
- ✅ **Confidence building** - Success with hands-on projects
- ✅ **Flexible integration** - Can be run as enrichment, homework, or club activities

**Result**: Students get extra practice, more engagement, and deeper understanding of electronics concepts that directly support building a computer in later years.

---

**Document Created**: 2025-12-15  
**Purpose**: Provide workshop activities from "Practical Electronics for Inventors" that directly support Year 1 curriculum learning objectives
