# Lab 9-12: Combinational Logic Circuits

## Lab Overview

**Duration**: 4 weeks (8-12 hours total)  
**Prerequisites**: Read theory material on Combinational Logic  
**Outcome**: Build adders, multiplexers, decoders, and understand arithmetic circuits

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Binary Numbers and Half-Adder (60-90 min)

### Part 1: Binary Number Practice (15 min)

**Activity**: Binary to Decimal Conversion
- Convert: 1010, 1100, 1111
- Answers: 10, 12, 15
- Practice worksheet

**Activity**: Decimal to Binary Conversion
- Convert: 5, 7, 12, 15
- Answers: 0101, 0111, 1100, 1111
- Practice worksheet

**Check**: Can you convert between binary and decimal?

### Part 2: Building Half-Adder (30 min)

**Materials**:
- 74HC86 IC (XOR)
- 74HC08 IC (AND)
- Switches (2)
- LEDs (2) with resistors

**Step-by-step**:
1. Insert 74HC86 (XOR) and 74HC08 (AND) ICs
2. Connect power (VCC and GND)
3. Use one XOR gate: inputs A and B, output = Sum
4. Use one AND gate: inputs A and B, output = Carry
5. Connect switches to inputs A and B
6. Connect LEDs to Sum and Carry outputs
7. Test all combinations!

**Testing**:
- A=0, B=0 → Sum=?, Carry=? (Should be 0, 0)
- A=0, B=1 → Sum=?, Carry=? (Should be 1, 0)
- A=1, B=0 → Sum=?, Carry=? (Should be 1, 0)
- A=1, B=1 → Sum=?, Carry=? (Should be 0, 1)
- Verify matches truth table

**Check**: Does half-adder work correctly?

---

## Lab Session 2: Full-Adder (60-90 min)

### Part 1: Building Full-Adder (40 min)

**Materials**:
- Logic gate ICs (XOR, AND, OR)
- OR: Two half-adders + OR gate
- Switches (3)
- LEDs (2)

**Method 1: From Half-Adders**:
1. Build first half-adder: A + B → S1, C1
2. Build second half-adder: S1 + Cin → Sum, C2
3. Carry-out = C1 OR C2
4. Connect three input switches (A, B, Cin)
5. Connect two output LEDs (Sum, Cout)
6. Test all 8 combinations

**Method 2: Direct Implementation**:
- More gates but clearer logic
- Follow truth table directly

**Testing**:
- Test all 8 input combinations
- Verify against truth table
- Record results

**Check**: Does full-adder work correctly?

### Part 2: 2-bit Adder (20 min)

**Challenge**:
- Build 2-bit adder using two full-adders
- Add: A₁A₀ + B₁B₀ = S₁S₀
- First full-adder: A₀ + B₀ (no carry-in)
- Second full-adder: A₁ + B₁ (with carry from first)

**Test Cases**:
- 01 + 01 = 10 (1 + 1 = 2)
- 10 + 01 = 11 (2 + 1 = 3)
- 11 + 11 = 110 (3 + 3 = 6, needs 3 bits!)

**Check**: Does 2-bit adder work correctly?

---

## Lab Session 3: 4-bit Binary Adder IC (60-90 min)

### Part 1: Building 4-bit Adder Circuit (40 min)

**Materials**:
- 74HC283 IC (4-bit adder)
- DIP switches (8 switches for inputs)
- LEDs (5: 4 for sum, 1 for carry)

**Step-by-step**:
1. Insert 74HC283 into breadboard
2. Connect power (pin 16 = VCC, pin 8 = GND)
3. Connect 8 input switches:
   - A₀-A₃ (check datasheet for exact pins)
   - B₀-B₃
4. Connect 4 output LEDs (with resistors):
   - Sum outputs
5. Connect carry-out LED (pin 14)
6. Connect carry-in (pin 13) to ground (for now)

**Testing**:
- Set A = 0101 (5), B = 0011 (3)
- Expected: Sum = 1000 (8), Carry = 0
- Verify with LEDs

**More Tests**:
- 7 + 9 = 16 (10000 binary, needs carry!)
- 15 + 1 = 16 (1111 + 0001 = 10000)
- Try various combinations

**Check**: Does 4-bit adder work correctly?

### Part 2: Binary Addition Practice (20 min)

**Worksheet**:
- Students calculate binary additions
- Build circuit to verify
- Record results
- Compare calculated vs measured

**Examples**:
- 5 + 3 = ?
- 7 + 9 = ?
- 12 + 4 = ?
- 15 + 1 = ?

**Check**: Do calculations match circuit results?

---

## Lab Session 4: Multiplexers (60-90 min)

### Part 1: Building 2-to-1 Multiplexer (30 min)

**Materials**:
- Logic gate ICs (NOT, AND, OR)
- Switches (3: 2 data, 1 select)
- LED

**Step-by-step**:
1. Use NOT gate for S
2. Use AND gates: (NOT S) AND I₀, S AND I₁
3. Use OR gate to combine
4. Connect switches for inputs
5. Connect LED for output
6. Test: Toggle S, observe output follows selected input

**Testing**:
- S=0, I₀=1, I₁=0 → Output? (Should be 1)
- S=1, I₀=0, I₁=1 → Output? (Should be 1)
- Verify all combinations

**Check**: Does multiplexer work correctly?

### Part 2: Using 74HC157 Quad Multiplexer (30 min)

**Materials**:
- 74HC157 IC
- Switches (9: 8 data, 1 select)
- LEDs (4)

**Step-by-step**:
1. Insert 74HC157
2. Connect two 4-bit inputs (switches)
3. Connect select line (switch)
4. Connect 4-bit output (LEDs)
5. Test: Toggle select, observe output switches

**Application Example**:
- Select between Register A and Register B
- Common in CPU design!

**Check**: Does 74HC157 work correctly?

---

## Lab Session 5: Decoders (60-90 min)

### Part 1: Building 2-to-4 Decoder (30 min)

**Materials**:
- Logic gate ICs (NOT, AND)
- Switches (2)
- LEDs (4)

**Step-by-step**:
1. Use NOT gates for A₀ and A₁
2. Use AND gates for each output:
   - Y₀ = NOT A₁ AND NOT A₀
   - Y₁ = NOT A₁ AND A₀
   - Y₂ = A₁ AND NOT A₀
   - Y₃ = A₁ AND A₀
3. Connect address switches
4. Connect output LEDs
5. Test: Change address, observe one LED lights

**Testing**:
- Address 00 → Y₀? (Should be 1)
- Address 01 → Y₁? (Should be 1)
- Address 10 → Y₂? (Should be 1)
- Address 11 → Y₃? (Should be 1)

**Check**: Does decoder work correctly?

### Part 2: Using 74HC139 Dual Decoder (30 min)

**Materials**:
- 74HC139 IC
- Switches (2)
- LEDs (4)

**Step-by-step**:
1. Insert 74HC139
2. Connect address inputs (2 switches)
3. Connect 4 output LEDs
4. Test: Address 00, 01, 10, 11
5. Observe: Only one output active

**Application: Memory Selection**:
- Use decoder to select memory chips
- Address bits select which chip
- Enable line can disable all

**Check**: Does 74HC139 work correctly?

---

## Lab Session 6: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build Multiplexer Circuit** (15 min)
- Build 2-to-1 multiplexer
- Demonstrate data selection
- Explain how it works

**Task 2: Build Decoder Circuit** (15 min)
- Build 2-to-4 decoder
- Demonstrate address selection
- Explain application

**Task 3: Build 4-bit Adder** (10 min)
- Build 4-bit adder circuit
- Add: 7 + 9
- Verify result (should be 16, with carry)

### Written Assessment (20 min)

**Topics**:
- Binary arithmetic
- Adder operation
- Multiplexer/decoder concepts
- Circuit design

### Lab Notebook Entry

**Record**:
1. Binary conversions
2. Adder circuits and results
3. Multiplexer/decoder circuits
4. Observations and measurements
5. Problems and solutions

---

## Troubleshooting Guide

### Adder Doesn't Work

**Check**:
1. IC orientation
2. Power connections
3. Input connections
4. Output connections
5. Carry connections

**Fix**:
- Verify IC pinout
- Check power supply
- Verify connections
- Test with multimeter

### Multiplexer/Decoder Doesn't Work

**Check**:
1. Gate connections
2. Select/address inputs
3. Output connections
4. Logic levels

**Fix**:
- Verify gate connections
- Check select/address
- Verify outputs
- Measure logic levels

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can convert between binary and decimal
- [ ] You built working half-adder
- [ ] You built working full-adder
- [ ] You built working 4-bit adder
- [ ] You built working multiplexer
- [ ] You built working decoder
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build 8-bit adder from 4-bit adders
2. Design custom combinational circuits
3. Research advanced adder designs (carry look-ahead)
4. Build BCD adder

---

## Next Lab

After completing this lab:
- Review theory on Sequential Logic (Term 2)
- Read next lab material
- Prepare for flip-flops and registers

---

*Lab work is where theory becomes reality - build to understand!*
