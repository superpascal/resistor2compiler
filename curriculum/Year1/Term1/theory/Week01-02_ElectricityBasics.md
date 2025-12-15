# Week 1-2: Electricity Basics - Theory

## Learning Objectives

After reading this material, you will understand:
- What electricity is at a fundamental level
- Voltage, current, and resistance
- How these relate to each other (Ohm's law)
- Why circuits need certain components
- How to think about electrical circuits

## What is Electricity?

### The Basics

**Electricity** is the flow of **electrons** through a conductor (like a wire).

Think of it like water in a pipe:
- **Voltage** = Water pressure (pushes the water)
- **Current** = Water flow rate (how much flows)
- **Resistance** = Pipe narrowness (restricts flow)

### Voltage (V)

**Voltage** is the "push" that makes electrons move.

- Measured in **Volts (V)**
- Like water pressure in a pipe
- Higher voltage = stronger push
- Our circuits use **5 Volts** (safe, low voltage)

**Examples**:
- AA battery: 1.5 Volts
- USB power: 5 Volts
- Car battery: 12 Volts
- Wall outlet: 120 Volts (dangerous! We don't use this)

**Key Point**: Voltage is the **potential** to push electrons. It exists even when nothing is connected.

### Current (I)

**Current** is the actual flow of electrons.

- Measured in **Amperes (A)** or **milliamperes (mA)**
- 1 A = 1000 mA
- Like water flow rate
- Higher current = more electrons flowing

**Examples**:
- LED needs: ~20 mA (0.020 A)
- Phone charger: ~1-2 A
- Car starter: ~100-200 A

**Key Point**: Current only flows when there's a complete circuit (path for electrons).

### Resistance (R)

**Resistance** opposes the flow of current.

- Measured in **Ohms (Ω)**
- Like a narrow pipe that restricts water
- Higher resistance = less current flows
- Components have resistance (resistors, LEDs, wires)

**Examples**:
- Wire: Very low resistance (~0.001 Ω)
- Resistor: 220 Ω, 1kΩ, 10kΩ
- LED: ~100-200 Ω (when lit)
- Air: Very high resistance (insulator)

**Key Point**: Resistance controls how much current flows for a given voltage.

## Ohm's Law

### The Relationship

**Ohm's Law** shows how voltage, current, and resistance relate:

**V = I × R**

Where:
- **V** = Voltage (Volts)
- **I** = Current (Amperes)
- **R** = Resistance (Ohms)

### Understanding the Formula

**If voltage is fixed** (like 5V from power supply):
- Larger resistance → Less current
- Smaller resistance → More current

**If resistance is fixed**:
- Higher voltage → More current
- Lower voltage → Less current

### Examples

**Example 1**: 5V power, 220Ω resistor
- I = V / R = 5V / 220Ω = 0.023 A = 23 mA
- This is good for an LED!

**Example 2**: 5V power, 10Ω resistor
- I = V / R = 5V / 10Ω = 0.5 A = 500 mA
- This is too much for an LED! It would burn out.

**Example 3**: 5V power, 1kΩ (1000Ω) resistor
- I = V / R = 5V / 1000Ω = 0.005 A = 5 mA
- This might be too little for an LED (too dim)

### Why This Matters

Ohm's law helps us:
- Choose the right resistor for LEDs
- Understand why components need certain values
- Design circuits that work correctly
- Avoid damaging components

## Power Calculations

### What is Power?

**Power** is the rate at which energy is used or converted.

- Measured in **Watts (W)**
- Like how fast water flows (current) × pressure (voltage)
- Higher power = more energy used per second

**Key Point**: Power tells us how much energy a circuit uses!

### Power Formula

**Power = Voltage × Current**

**P = V × I**

Where:
- **P** = Power (Watts)
- **V** = Voltage (Volts)
- **I** = Current (Amperes)

### Understanding Power

**If voltage is fixed** (like 5V):
- More current → More power
- Less current → Less power

**If current is fixed**:
- Higher voltage → More power
- Lower voltage → Less power

### Examples

**Example 1**: LED Circuit
- Voltage: 5V
- Current: 20mA (0.020A)
- Power: P = 5V × 0.020A = 0.1W (100mW)
- **Note**: LEDs use very little power!

**Example 2**: Resistor Circuit
- Voltage: 5V
- Current: 0.1A (100mA)
- Power: P = 5V × 0.1A = 0.5W
- **Note**: Resistor must handle 0.5W (use 1W resistor for safety)

**Example 3**: High-Power Circuit
- Voltage: 12V
- Current: 2A
- Power: P = 12V × 2A = 24W
- **Note**: High power = needs heat sink!

### Power in Resistors

**Resistor Power Dissipation**:
- Resistors convert electrical energy to heat
- Power = V × I = I² × R = V² / R
- **Resistor Rating**: Must exceed power dissipation

**Example**:
- Resistor: 100Ω
- Voltage: 5V
- Current: I = V / R = 5V / 100Ω = 0.05A
- Power: P = V × I = 5V × 0.05A = 0.25W
- **Use**: 0.5W or 1W resistor (safety margin)

**Key Point**: Resistors get hot - always check power rating!

### Power Rating

**Component Power Ratings**:
- **Resistors**: 0.25W, 0.5W, 1W, 5W, etc.
- **LEDs**: Usually < 1W
- **ICs**: Check datasheet
- **Rule**: Component rating must exceed power dissipation

**Safety Margin**:
- Use component rated for 2× actual power (safety)
- Example: 0.25W actual → use 0.5W or 1W component

**Key Point**: Always check power ratings - components can overheat!

### Power Calculations Summary

**Formulas**:
- P = V × I (basic formula)
- P = I² × R (using current and resistance)
- P = V² / R (using voltage and resistance)

**When to Calculate**:
- Selecting component ratings
- Checking if component can handle power
- Understanding heat generation
- Designing power supplies

**Key Point**: Power calculations are essential for safe circuit design!

## Circuits: The Complete Path

### What is a Circuit?

A **circuit** is a complete path for electrons to flow.

**Essential Parts**:
1. **Power source** (battery, power supply) - provides voltage
2. **Conductors** (wires) - path for electrons
3. **Components** (LEDs, resistors) - use the electricity
4. **Return path** - back to power source

**Key Point**: Without a complete path, current cannot flow!

### Series vs Parallel (Introduction)

**Series Circuit**:
- Components connected one after another
- Same current flows through all
- Voltage is shared
- Example: Battery → Resistor → LED → Back to battery

**Parallel Circuit**:
- Components connected side-by-side
- Same voltage across all
- Current is shared
- (We'll learn more about this later)

## Why Components Need Resistors

### The LED Example

**LEDs (Light Emitting Diodes)**:
- Need specific current to work (usually 20-30 mA)
- Too little current → LED is dim or off
- Too much current → LED burns out!

**The Problem**:
- Power supply provides 5V
- LED might only need 2V
- Without resistor, too much current flows
- LED burns out immediately

**The Solution**:
- Add a resistor
- Resistor "uses up" extra voltage
- Resistor limits current to safe level
- LED gets right amount of current

**Calculation**:
- LED needs: 2V, 20 mA
- Power supply: 5V
- Resistor must drop: 5V - 2V = 3V
- Resistor value: R = V / I = 3V / 0.020A = 150Ω
- Use 220Ω (standard value, close enough, safer)

## Safety: Why It Matters

### Electrical Safety Rules

**Why Safety?**:
- Even 5V can cause problems if misused
- Short circuits can overheat and cause fires
- Damaged components can be dangerous
- Proper procedures prevent accidents

**Key Rules**:
1. **Never work on live high-voltage circuits** (we only use 5V - safe!)
2. **Check connections before powering on**
3. **Never short-circuit power supplies** (connect + directly to -)
4. **Report damaged equipment immediately**
5. **Keep water away from electronics**
6. **No food/drinks in lab**

**Why These Rules?**:
- Prevents fires
- Prevents component damage
- Prevents injury
- Protects equipment

## Tools: What They Do

### Multimeter

**What it measures**:
- **Voltage**: How much "push" (Volts)
- **Current**: How much flow (Amperes)
- **Resistance**: How much opposition (Ohms)

**How to use**:
- Select correct mode (V, A, or Ω)
- Connect probes correctly
- Read the display
- **Always start with voltage measurements** (safest)

### Breadboard

**What it is**:
- Reusable circuit building platform
- No soldering needed
- Components plug in
- Connections made with wires

**How it works**:
- **Power rails**: Long strips for +5V and GND
- **Terminal strips**: Rows of 5 connected holes
- Components in same row = connected
- Different rows = separate (unless connected)

## Key Concepts Summary

1. **Voltage** = The push (like water pressure)
2. **Current** = The flow (like water flow rate)
3. **Resistance** = The restriction (like narrow pipe)
4. **Ohm's Law**: V = I × R (they're all related!)
5. **Circuits** need complete paths
6. **Resistors** protect components by limiting current
7. **Safety** is always first priority

## Questions to Think About

Before the lab, think about:
1. Why does an LED need a resistor?
2. What happens if we use a resistor that's too small?
3. What happens if we use a resistor that's too large?
4. Why can't current flow without a complete circuit?
5. How does a multimeter measure voltage?

## Next Steps

After reading this theory:
1. Review the key concepts
2. Try the practice problems
3. Read the lab material
4. Come to lab ready to build!

---

*Theory helps you understand - labs help you build!*
