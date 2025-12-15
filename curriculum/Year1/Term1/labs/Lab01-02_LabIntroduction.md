# Lab 1-2: Lab Introduction & First Circuit

## Lab Overview

**Duration**: 2 weeks (4-6 hours total)  
**Prerequisites**: Read theory material on Electricity Basics  
**Outcome**: Build your first working circuit and understand lab safety

## Safety First! ⚠️

**Before starting, you MUST**:
- [ ] Complete safety briefing
- [ ] Sign safety agreement
- [ ] Understand all safety rules
- [ ] Know emergency procedures
- [ ] Have safety glasses (if required)

**Safety Rules** (review these every lab):
1. Never work on circuits above 12V
2. Always check connections before applying power
3. Never short-circuit power supplies
4. Report damaged equipment immediately
5. Keep water away from electronics
6. No food/drinks in lab

## Lab Equipment Introduction

### Part 1: Getting to Know Your Tools (30 min)

#### Breadboard

**What you'll do**:
1. Look at your breadboard
2. Identify power rails (long strips on sides)
3. Identify terminal strips (rows in middle)
4. Practice inserting and removing wires

**Activity**:
- Insert a wire into a hole
- Remove it
- Insert into same row (should be connected)
- Insert into different row (should be separate)

**Check**: Can you identify which holes are connected?

#### Multimeter

**What you'll do**:
1. Turn on multimeter
2. Select voltage mode (V)
3. Measure a battery (1.5V AA battery)
4. Read the display

**Activity**:
- Measure battery: Should read ~1.5V
- If reads negative: Swap the probes
- Practice reading different voltages

**Check**: Can you read voltage correctly?

#### Power Supply

**What you'll do**:
1. Identify 5V power source (USB adapter or bench supply)
2. Connect to breadboard power rails
3. Measure voltage on rails
4. Verify it's 5V (not more, not less)

**Activity**:
- Connect power to breadboard
- Measure voltage on power rail
- Should read ~5.0V
- If different, check connections

**Check**: Is your power supply working correctly?

---

## Lab Session 1: Building Your First Circuit

### Objective

Build a simple LED circuit that lights up correctly.

### Materials Needed

- [ ] 1 breadboard
- [ ] 1 LED (5mm, any color)
- [ ] 1 resistor (220Ω or 330Ω)
- [ ] Jumper wires (2-3 wires)
- [ ] Power supply (5V)
- [ ] Multimeter

### Step-by-Step Instructions

#### Step 1: Prepare Power (5 min)

1. Connect red wire from +5V rail to power supply positive
2. Connect black wire from GND rail to power supply negative/ground
3. **DO NOT turn on power yet!**
4. Have teacher check your connections

**Safety Check**: Teacher verifies before power on

#### Step 2: Place Resistor (5 min)

1. Find your 220Ω resistor
2. Insert one leg into power rail (+5V side)
3. Insert other leg into main breadboard area (row 10, for example)
4. **Note**: Resistors work both ways (no polarity)

**Check**: Is resistor firmly inserted?

#### Step 3: Place LED (5 min)

1. Find your LED
2. **Important**: LEDs have polarity!
   - Longer leg = positive (anode)
   - Shorter leg = negative (cathode)
3. Insert longer leg into same row as resistor (row 10)
4. Insert shorter leg into GND rail

**Check**: Is LED inserted correctly? (long leg = positive)

#### Step 4: Power On and Test (5 min)

1. **Final check**: Review all connections
2. Have teacher verify
3. Turn on power supply
4. **LED should light up!**

**If LED lights**: ✅ Success! You built your first circuit!

**If LED doesn't light**:
- Check LED polarity (try reversing)
- Check all connections
- Check power supply
- Ask teacher for help

#### Step 5: Measure Voltages (10 min)

**What to measure**:
1. Voltage at power supply: Should be ~5V
2. Voltage across LED: Should be ~2-3V
3. Voltage across resistor: Should be ~2-3V
4. Total: LED voltage + Resistor voltage = Power supply voltage

**Activity**:
- Use multimeter to measure each voltage
- Record in your lab notebook
- Verify they add up correctly

**Check**: Do your voltages make sense?

---

## Lab Session 2: Experimentation and Troubleshooting

### Objective

Experiment with different resistor values and learn troubleshooting.

### Materials Needed

- [ ] Your circuit from Session 1
- [ ] Additional resistors: 100Ω, 470Ω, 1kΩ
- [ ] Multimeter

### Experiment 1: Different Resistor Values (20 min)

**What to do**:
1. Keep LED in place
2. Replace 220Ω resistor with 100Ω
3. Observe LED brightness
4. Replace with 470Ω
5. Observe LED brightness
6. Replace with 1kΩ
7. Observe LED brightness

**Record observations**:
- 100Ω: Brightness = ? (very bright, might be too bright!)
- 220Ω: Brightness = ? (normal)
- 470Ω: Brightness = ? (dimmer)
- 1kΩ: Brightness = ? (very dim, might be too dim)

**What you learned**:
- Smaller resistor = more current = brighter LED
- Larger resistor = less current = dimmer LED
- Too small = LED might burn out
- Too large = LED might be too dim

### Experiment 2: Measure Everything (15 min)

**What to measure**:
- Voltage at each point in circuit
- Current (if multimeter supports it)
- Calculate current using Ohm's law

**Activity**:
1. Measure voltage across resistor
2. Calculate current: I = V / R
3. Compare to LED's needs (20-30 mA)
4. Is your circuit working correctly?

**Record results**:
- Resistor voltage: ______ V
- Calculated current: ______ mA
- Is this safe for LED? Yes / No

### Experiment 3: Troubleshooting Practice (20 min)

**Teacher will introduce "broken" circuits**:
- LED backwards
- Missing resistor
- Loose connection
- Wrong power voltage

**Your task**:
- Diagnose the problem
- Fix it
- Explain what was wrong

**Skills practiced**:
- Systematic troubleshooting
- Using multimeter to find problems
- Understanding circuit behavior

---

## Lab Session 3: Assessment

### Practical Assessment (30 min)

**Task**: Build LED Circuit from Scratch

**Requirements**:
1. Build complete circuit
2. LED must light correctly
3. Measure and record voltages
4. Explain why resistor is needed

**Assessment Criteria**:
- Circuit built correctly
- Safety procedures followed
- Measurements accurate
- Explanation clear

### Written Assessment (20 min)

**Topics**:
- Safety rules
- Ohm's law
- Circuit components
- Troubleshooting

---

## Lab Notebook Requirements

**For each lab session, record**:
1. **Date and session number**
2. **What you built**
3. **Measurements taken**
4. **Observations**
5. **Problems encountered**
6. **Solutions found**
7. **What you learned**

**Example Entry**:
```
Date: [Date]
Lab: First LED Circuit

Built: LED circuit with 220Ω resistor
Measurements:
- Power supply: 5.02V
- LED voltage: 2.1V
- Resistor voltage: 2.9V
- Calculated current: 13.2 mA

Observations:
- LED lit up correctly
- Not too bright, not too dim
- Circuit worked on first try!

Problems: None
Solutions: N/A
Learning: Resistor protects LED by limiting current
```

---

## Troubleshooting Guide

### LED Doesn't Light

**Check**:
1. Is LED backwards? (Try reversing)
2. Is power supply on?
3. Are all connections tight?
4. Is resistor in place?
5. Is LED burned out? (Try new LED)

**Common fixes**:
- Reverse LED (most common issue!)
- Check power connections
- Verify resistor value

### LED Very Dim

**Possible causes**:
- Resistor too large
- Power supply voltage too low
- LED damaged

**Fix**:
- Try smaller resistor
- Check power supply
- Try new LED

### LED Very Bright (Then Burns Out)

**Possible causes**:
- Resistor too small or missing
- Power supply voltage too high

**Fix**:
- Add larger resistor
- Check power supply voltage
- Replace LED

### Multimeter Reads Wrong

**Check**:
- Is multimeter in correct mode? (Voltage, not current)
- Are probes connected correctly?
- Is multimeter battery good?
- Are you measuring the right points?

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build LED circuit correctly
- [ ] You can measure voltages accurately
- [ ] You can explain why resistor is needed
- [ ] You can troubleshoot common problems
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build circuit with 3 LEDs in parallel
2. Calculate resistor for each LED
3. Measure current through each
4. Compare to single LED circuit

**Challenge**:
- Design circuit that lights LED only when button pressed
- Requires: Button, resistor, LED
- Hint: Button connects/disconnects circuit

---

## Next Lab

After completing this lab:
- Review theory on components (Week 3-5)
- Read next lab material
- Prepare for 555 timer circuit

---

*Lab work is where theory becomes reality - build to understand!*
