# Lab 16-18: Binary Counters

## Lab Overview

**Duration**: 3 weeks (6-9 hours total)  
**Prerequisites**: Read theory material on Binary Counters  
**Outcome**: Build counters, understand program counter concept, and create modulo counters

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Building Simple Counter (60-90 min)

### Part 1: 2-bit Counter from Flip-Flops (30 min)

**Materials**:
- 74HC74 IC (dual D flip-flop)
- 555 timer (for clock)
- LEDs (2) with resistors

**Step-by-step**:
1. Insert 74HC74 into breadboard
2. Use two D flip-flops
3. Connect: Clock → first flip-flop
4. Connect: Q of first → clock of second
5. Connect D inputs to Q̅ (toggle mode)
6. Connect Q outputs to LEDs
7. Pulse clock, observe count

**Testing**:
- Counts: 00 → 01 → 10 → 11 → 00
- Each flip-flop divides by 2
- 2-bit = counts 0-3 (4 states)

**Check**: Does 2-bit counter work correctly?

### Part 2: Using 74HC161 Counter IC (30 min)

**Materials**:
- 74HC161 IC (4-bit counter)
- 555 timer (for clock)
- LEDs (4) with resistors
- Switches (for reset, load, enable)

**Step-by-step**:
1. Insert 74HC161 into breadboard
2. Connect power (check datasheet for pins)
3. Connect clock to 555 timer
4. Connect Q outputs to LEDs
5. Connect reset, load, enable (as needed)
6. Pulse clock, observe count

**Testing**:
- Counts: 0000 → 0001 → ... → 1111 → 0000
- 4-bit = counts 0-15 (16 states)
- Test reset, load, enable functions

**Check**: Does 4-bit counter work correctly?

---

## Lab Session 2: Modulo Counter (60-90 min)

### Part 1: Building Modulo-10 Counter (40 min)

**Materials**:
- 74HC161 counter
- Logic gates (AND, OR)
- LEDs (4) for display

**Step-by-step**:
1. Build 4-bit counter
2. Detect count = 9 (1001 binary)
3. When count = 9, next clock → load 0
4. Counts: 0-9, then wraps to 0

**Testing**:
- Counts: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 0...
- Verify wraps correctly
- Test various modulo values

**Check**: Does modulo-10 counter work correctly?

### Part 2: Display on 7-Segment (20 min)

**Materials**:
- Modulo-10 counter
- 7-segment display
- 74HC47 decoder (BCD to 7-segment)

**Step-by-step**:
1. Connect counter outputs to decoder
2. Connect decoder to 7-segment display
3. Observe decimal counting: 0-9

**Check**: Does display show correct count?

---

## Lab Session 3: Program Counter Concept (60-90 min)

### Part 1: Building Program Counter (40 min)

**Materials**:
- 74HC161 counter (as PC)
- Memory simulation (switches or EEPROM)
- LEDs for address display

**Step-by-step**:
1. Use counter as Program Counter
2. PC outputs = address
3. Simulate fetching instruction from address
4. Increment PC after fetch
5. Demonstrate sequential execution

**Testing**:
- PC = 0: Fetch instruction 0
- PC = 1: Fetch instruction 1
- PC = 2: Fetch instruction 2
- Sequential execution

**Check**: Does program counter work correctly?

### Part 2: Jump Operation (20 min)

**Activity**: Implement jump
- Load new address into PC
- Demonstrate non-sequential execution
- Show how branches work

---

## Lab Session 4: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build Counter** (15 min)
- Build 4-bit counter
- Demonstrate counting
- Explain operation

**Task 2: Build Modulo Counter** (15 min)
- Build modulo-10 counter
- Demonstrate wrapping
- Explain modulo concept

**Task 3: Program Counter** (10 min)
- Build program counter
- Demonstrate sequential execution
- Explain CPU application

### Written Assessment (20 min)

**Topics**:
- Counter operation
- Modulo counting
- Program counter concept
- CPU applications

### Lab Notebook Entry

**Record**:
1. Counter circuits built
2. Modulo counter operation
3. Program counter concept
4. Observations
5. Problems and solutions

---

## Troubleshooting Guide

### Counter Doesn't Count

**Check**:
1. Clock connection
2. Power connections
3. Enable inputs
4. Reset state

**Fix**:
- Verify clock signal
- Check power
- Verify enable inputs
- Check reset

### Modulo Counter Doesn't Wrap

**Check**:
1. Detection logic
2. Load connection
3. Timing

**Fix**:
- Verify detection
- Check load connection
- Verify timing

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build working counter
- [ ] You can build modulo counter
- [ ] You understand program counter concept
- [ ] You can demonstrate counting operations
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build up/down counter
2. Build frequency divider
3. Research CPU program counters
4. Build counter with preset

---

## Next Lab

After completing this lab:
- Review theory on System Buses (Week 19-21)
- Read next lab material
- Prepare for bus systems

---

*Lab work is where theory becomes reality - build to understand!*
