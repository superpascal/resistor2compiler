# Lab 13-15: Flip-Flops and Registers

## Lab Overview

**Duration**: 3 weeks (6-9 hours total)  
**Prerequisites**: Read theory material on Sequential Logic  
**Outcome**: Build latches, flip-flops, and registers to understand computer memory

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Sequential vs Combinational (60-90 min)

### Part 1: Understanding the Difference (20 min)

**Activity**: Compare Combinational vs Sequential
- Build simple combinational circuit (AND gate)
- Observe: Same inputs → same outputs
- Build simple sequential circuit (SR latch)
- Observe: Same inputs → different outputs (depends on state)

**Key Observation**:
- Combinational: No memory
- Sequential: Has memory!

### Part 2: Building SR Latch (40 min)

**Materials**:
- 74HC02 IC (quad NOR gates)
- Switches (2)
- LEDs (2) with resistors

**Step-by-step**:
1. Insert 74HC02 into breadboard
2. Use two NOR gates
3. Connect: Q output → R input of other gate
4. Connect: Q̅ output → S input of other gate
5. Add switches for S and R
6. Add LEDs for Q and Q̅
7. Test: Set, Reset, Hold

**Testing**:
- Set (S=1, R=0): Q becomes 1, stays 1
- Reset (S=0, R=1): Q becomes 0, stays 0
- Hold (S=0, R=0): Q stays as it was (memory!)
- **Forbidden (S=1, R=1)**: Unpredictable! Don't do this!

**Check**: Does SR latch remember state?

---

## Lab Session 2: D Flip-Flop (60-90 min)

### Part 1: Building D Flip-Flop Circuit (40 min)

**Materials**:
- 74HC74 IC (dual D flip-flop)
- 555 timer (for clock) OR debounced manual clock
- Switches
- LEDs

**Step-by-step**:
1. Insert 74HC74 into breadboard
2. Connect power (pin 14 = VCC, pin 7 = GND)
3. Use one flip-flop (pins 2, 3, 5, 6)
4. Connect:
   - D input: Switch
   - CLK: 555 timer or manual clock
   - Q output: LED
   - Q̅ output: LED (optional)
5. Connect Preset and Clear to +5V (disable)

**Testing**:
- Set D = 0, pulse clock → Q = ? (Should be 0)
- Set D = 1, pulse clock → Q = ? (Should be 1)
- Change D while clock low → Q = ? (Shouldn't change!)
- Change D, then pulse clock → Q = D

**Key Observation**:
- Q only changes on clock edge
- Between edges, Q holds value
- This is "synchronous" operation

**Check**: Does D flip-flop work correctly?

### Part 2: Timing Diagram Practice (20 min)

**Activity**: Draw timing diagrams
- Clock signal
- D input
- Q output
- Show when Q changes (only on clock edge)

**Observations**:
- Q only changes on clock edge
- Between edges, Q holds value
- This is "synchronous" operation

---

## Lab Session 3: Building Registers (60-90 min)

### Part 1: Building 4-bit Register (40 min)

**Materials**:
- Two 74HC74 ICs (4 flip-flops total)
- 555 timer (for clock)
- DIP switches (4 switches)
- LEDs (4) with resistors

**Step-by-step**:
1. Insert two 74HC74 ICs
2. Connect all CLK pins together (common clock)
3. Connect 4 D inputs to switches
4. Connect 4 Q outputs to LEDs
5. Connect Preset/Clear to +5V
6. Connect clock to 555 timer or manual

**Testing**:
- Set D inputs: 0101
- Pulse clock → Q outputs = 0101
- Change D inputs: 1010
- Q outputs = ? (should still be 0101!)
- Pulse clock → Q outputs = 1010
- **Key**: Only changes on clock edge!

**Check**: Does 4-bit register work correctly?

### Part 2: Register Operations (20 min)

**Operation 1: Load**
- Set D inputs to value
- Pulse clock
- Value stored in register

**Operation 2: Hold**
- Don't pulse clock
- Change D inputs
- Q outputs don't change (memory!)

**Operation 3: Read**
- Q outputs always show stored value
- Can read without clock

**Check**: Can you perform all operations?

---

## Lab Session 4: Register Applications (60-90 min)

### Part 1: Data Storage (30 min)

**Problem**: Store result from adder

**Circuit**:
- 4-bit adder output → Register D inputs
- Register Q outputs → Display (LEDs)
- Clock pulse stores result

**Activity**:
- Add two numbers
- Store result in register
- Result persists even after adder inputs change

**Check**: Does data storage work?

### Part 2: Pipeline (30 min)

**Concept**: Process data in stages

**Example Circuit**:
- Stage 1: Add A + B
- Register: Store intermediate
- Stage 2: Add result + C
- Final result

**Activity**: Build simple pipeline
- Observe intermediate storage
- Understand stage-by-stage processing

---

## Lab Session 5: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build SR Latch** (15 min)
- Build from NOR gates
- Demonstrate set, reset, hold
- Explain operation

**Task 2: Build D Flip-Flop Circuit** (15 min)
- Use 74HC74
- Demonstrate clocked operation
- Show timing relationship

**Task 3: Build 4-bit Register** (10 min)
- Build from D flip-flops
- Demonstrate load and hold
- Explain application

### Written Assessment (20 min)

**Topics**:
- Combinational vs sequential
- SR latch truth table
- D flip-flop operation
- Register construction
- Timing diagrams

### Lab Notebook Entry

**Record**:
1. SR latch observations
2. D flip-flop timing
3. Register operations
4. Applications
5. Problems and solutions

---

## Troubleshooting Guide

### Latch Doesn't Work

**Check**:
1. Gate connections
2. Feedback connections
3. Input connections
4. Power connections

**Fix**:
- Verify gate connections
- Check feedback loop
- Verify inputs
- Check power

### Flip-Flop Doesn't Work

**Check**:
1. IC orientation
2. Clock connection
3. D input connection
4. Preset/Clear connections

**Fix**:
- Verify IC pinout
- Check clock signal
- Verify D input
- Check Preset/Clear (should be HIGH)

### Register Doesn't Work

**Check**:
1. All flip-flops connected
2. Common clock
3. Input connections
4. Output connections

**Fix**:
- Verify all connections
- Check clock is common
- Verify inputs
- Check outputs

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build working SR latch
- [ ] You can build working D flip-flop
- [ ] You can build working 4-bit register
- [ ] You understand clocked operation
- [ ] You can demonstrate register operations
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build 8-bit register
2. Research different flip-flop types (JK, T)
3. Build shift register
4. Advanced: Build register file

---

## Next Lab

After completing this lab:
- Review theory on Binary Counters (Week 16-18)
- Read next lab material
- Prepare for counter circuits

---

*Lab work is where theory becomes reality - build to understand!*
