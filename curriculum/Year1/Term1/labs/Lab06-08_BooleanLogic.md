# Lab 6-8: Boolean Logic

## Lab Overview

**Duration**: 3 weeks (6-9 hours total)  
**Prerequisites**: Read theory material on Boolean Logic  
**Outcome**: Build and test logic gates, combine gates, and understand digital logic

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Building Basic Gates (60-90 min)

### Part 1: AND Gate (20 min)

**Materials**:
- 74HC08 IC (quad 2-input AND)
- Toggle switches (2)
- LED with 220Ω resistor
- Power supply (5V)

**Step-by-step**:
1. Insert 74HC08 into breadboard
2. Connect power: Pin 14 (VCC) to +5V, Pin 7 (GND) to ground
3. Use one AND gate (pins 1, 2, 3)
4. Connect switches to inputs (pins 1, 2)
5. Connect LED to output (pin 3) through resistor
6. Test all combinations!

**Testing**:
- Switch 1 = 0, Switch 2 = 0 → LED = ? (Should be OFF)
- Switch 1 = 0, Switch 2 = 1 → LED = ? (Should be OFF)
- Switch 1 = 1, Switch 2 = 0 → LED = ? (Should be OFF)
- Switch 1 = 1, Switch 2 = 1 → LED = ? (Should be ON)
- Record results in truth table

**Check**: Does AND gate work correctly?

### Part 2: OR Gate (20 min)

**Materials**:
- 74HC32 IC (quad 2-input OR)
- Same setup as AND gate

**Step-by-step**:
1. Insert 74HC32 into breadboard
2. Connect power (pins 7, 14)
3. Use one OR gate
4. Connect switches to inputs
5. Connect LED to output
6. Test all combinations!

**Testing**:
- Switch 1 = 0, Switch 2 = 0 → LED = ? (Should be OFF)
- Switch 1 = 0, Switch 2 = 1 → LED = ? (Should be ON)
- Switch 1 = 1, Switch 2 = 0 → LED = ? (Should be ON)
- Switch 1 = 1, Switch 2 = 1 → LED = ? (Should be ON)
- Record results in truth table

**Activity**: Compare AND vs OR
- Build both gates side-by-side
- Same inputs, observe different outputs
- When do they differ? (Only when both inputs = 1)

**Check**: Does OR gate work correctly?

### Part 3: NOT Gate (20 min)

**Materials**:
- 74HC04 IC (hex inverter - 6 NOT gates!)

**Step-by-step**:
1. Insert 74HC04 into breadboard
2. Connect power (pins 7, 14)
3. Use one NOT gate
4. Connect switch to input
5. Connect LED to output
6. Test both states!

**Testing**:
- Switch = 0 → LED = ? (Should be ON - inverted!)
- Switch = 1 → LED = ? (Should be OFF - inverted!)
- Record results

**Activity**: Inverter Chain
- Connect NOT gate output to another NOT gate input
- What happens? (Double negation = original)
- Demonstrates: NOT(NOT A) = A

**Check**: Does NOT gate work correctly?

---

## Lab Session 2: Combined Gates (60-90 min)

### Part 1: NAND Gate (20 min)

**Materials**:
- 74HC00 IC (quad 2-input NAND)
- OR: 74HC08 (AND) + 74HC04 (NOT)

**Method 1: Using NAND IC**:
1. Insert 74HC00
2. Connect power
3. Build and test

**Method 2: From AND + NOT**:
1. Build AND gate (74HC08)
2. Connect output to NOT gate (74HC04)
3. Result: NAND gate
4. Test all combinations

**Testing**:
- Verify truth table matches NAND (opposite of AND)
- 0,0 → 1; 0,1 → 1; 1,0 → 1; 1,1 → 0

**Check**: Does NAND gate work correctly?

### Part 2: NOR Gate (20 min)

**Materials**:
- 74HC02 IC (quad 2-input NOR)
- OR: 74HC32 (OR) + 74HC04 (NOT)

**Step-by-step**:
1. Build OR gate
2. Connect output to NOT gate
3. Result: NOR gate
4. Test all combinations

**Testing**:
- Verify truth table matches NOR (opposite of OR)
- 0,0 → 1; 0,1 → 0; 1,0 → 0; 1,1 → 0

**Check**: Does NOR gate work correctly?

### Part 3: XOR Gate (20 min)

**Materials**:
- 74HC86 IC (quad 2-input XOR)

**Step-by-step**:
1. Insert 74HC86
2. Connect power
3. Build and test

**Testing**:
- 0 XOR 0 = 0 (same)
- 0 XOR 1 = 1 (different)
- 1 XOR 0 = 1 (different)
- 1 XOR 1 = 0 (same)
- "One or the other, but not both"

**Activity**: XOR Puzzle
- "I have two switches. I want LED on when switches are different."
- Students design circuit
- Solution: XOR gate!

**Check**: Does XOR gate work correctly?

---

## Lab Session 3: Complex Logic Circuits (60-90 min)

### Part 1: Security System (25 min)

**Problem**: "Alarm sounds if (door open AND motion detected) OR (window open)"

**Design**:
- Door switch AND Motion sensor → OR → Window switch

**Step-by-step**:
1. Build AND gate: Door AND Motion
2. Build OR gate: (Door AND Motion) OR Window
3. Connect LED to output (alarm indicator)
4. Test all combinations

**Testing**:
- Door=0, Motion=0, Window=0 → Alarm? (No)
- Door=1, Motion=1, Window=0 → Alarm? (Yes)
- Door=0, Motion=0, Window=1 → Alarm? (Yes)
- Test all 8 combinations

**Check**: Does security system work correctly?

### Part 2: Voting Machine (25 min)

**Problem**: "Motion passes if at least 2 of 3 agree"
- (A AND B) OR (A AND C) OR (B AND C)

**Step-by-step**:
1. Build three AND gates:
   - A AND B
   - A AND C
   - B AND C
2. Build OR gate to combine
3. Connect LED to output
4. Test all 8 combinations

**Testing**:
- 0,0,0 → Pass? (No - 0 votes)
- 1,1,0 → Pass? (Yes - 2 votes)
- 1,1,1 → Pass? (Yes - 3 votes)
- Verify all combinations

**Check**: Does voting machine work correctly?

### Part 3: Light Control (20 min)

**Problem**: "Light on if (switch A OR switch B) AND NOT (override switch)"

**Design**:
- (A OR B) AND NOT Override

**Step-by-step**:
1. Build OR gate: A OR B
2. Build NOT gate: NOT Override
3. Build AND gate: (A OR B) AND NOT Override
4. Connect LED to output
5. Test all combinations

**Testing**:
- A=1, B=0, Override=0 → Light? (Yes)
- A=1, B=0, Override=1 → Light? (No - overridden)
- Test all 8 combinations

**Check**: Does light control work correctly?

---

## Lab Session 4: Diode Logic (60-90 min)

### Part 1: Building Diode-OR Gate (30 min)

**Materials**:
- Diodes (1N4148 or similar, 2)
- 10kΩ resistor
- Switches
- LED

**Step-by-step**:
1. Place diodes: Anode to input switch, Cathode to common point
2. Add pull-down resistor: Common point to GND (10kΩ)
3. Output LED: Common point to LED to GND
4. Test all combinations

**How it works**:
- If input A = HIGH: Diode conducts, output = HIGH
- If input B = HIGH: Diode conducts, output = HIGH
- If both LOW: Resistor pulls output LOW

**Note**: Not perfect OR (voltage drop), but demonstrates concept

**Activity**: Compare to IC OR gate
- Build both
- Same inputs, compare outputs
- Discuss differences (voltage levels, speed)

**Check**: Does diode-OR gate work?

### Part 2: Limitations Demonstration (20 min)

**Activity**: Show limitations
- Measure voltage drop across diodes
- Compare to IC gate voltage levels
- Discuss why ICs are better

**Observations**:
- Diode logic: Voltage drop, slower
- IC logic: Precise levels, faster

---

## Lab Session 5: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build and Test Gates** (20 min)
- Build: AND, OR, NOT, XOR
- Must verify truth tables
- Must document with photos/diagrams

**Task 2: Design Logic Circuit** (20 min)
- Given problem: "Design circuit for X"
- Students design, build, test
- Must explain how it works

### Written Assessment (20 min)

**Topics**:
- Truth table completion
- Boolean expression evaluation
- Gate identification
- Circuit design questions

### Lab Notebook Entry

**Record**:
1. Truth tables for all gates
2. Complex circuit designs
3. Observations and measurements
4. Problems encountered and solutions

---

## Troubleshooting Guide

### Gate Doesn't Work

**Check**:
1. IC orientation (notch indicates pin 1)
2. Power connections (pins 7, 14)
3. Input connections
4. Output connections
5. Component values

**Fix**:
- Verify IC pinout
- Check power supply
- Verify connections
- Test with multimeter

### Wrong Output

**Check**:
1. Truth table understanding
2. Gate type (AND vs OR, etc.)
3. Input connections
4. Logic levels

**Fix**:
- Review truth table
- Verify gate type
- Check connections
- Measure logic levels

### Complex Circuit Doesn't Work

**Check**:
1. Each gate individually
2. Connections between gates
3. Power to all ICs
4. Logic flow

**Fix**:
- Test gates one at a time
- Verify interconnections
- Check all power connections
- Trace logic flow

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build all basic gates (AND, OR, NOT)
- [ ] You can build combined gates (NAND, NOR, XOR)
- [ ] You can build complex logic circuits
- [ ] You can verify truth tables
- [ ] You can design circuits from problems
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build 3-input gates
2. Design custom logic functions
3. Research logic gate families (TTL, CMOS, ECL)
4. Advanced: Build logic gate from transistors

---

## Next Lab

After completing this lab:
- Review theory on Combinational Logic (Week 9-12)
- Read next lab material
- Prepare for adders and arithmetic circuits

---

*Lab work is where theory becomes reality - build to understand!*
