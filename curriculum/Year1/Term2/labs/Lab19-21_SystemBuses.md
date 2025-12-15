# Lab 19-21: System Buses

## Lab Overview

**Duration**: 3 weeks (6-9 hours total)  
**Prerequisites**: Read theory material on System Buses  
**Outcome**: Build bus systems, use tri-state buffers, and understand CPU bus architecture

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Understanding Bus Contention (60-90 min)

### Part 1: The Problem (20 min)

**Activity**: Demonstrate Bus Contention
- Connect two register outputs directly together
- Try to output different values
- Observe: Conflict! Undefined behavior
- **This is why we need tri-state buffers!**

**Check**: Can you see the problem?

### Part 2: Building Simple Bus (40 min)

**Materials**:
- Two 4-bit registers (74HC173)
- Tri-state buffers (74HC125 or 74HC244)
- LEDs (4) for bus display
- Switches for control

**Step-by-step**:
1. Build two 4-bit registers
2. Connect register outputs to tri-state buffers
3. Connect tri-state outputs to bus (shared wires)
4. Connect bus to LEDs (display)
5. Add enable switches for each buffer

**Testing**:
- Enable Register A only → Bus shows Register A
- Enable Register B only → Bus shows Register B
- Enable both → Conflict! (demonstrates problem)
- Enable neither → Bus floating (high-impedance)

**Check**: Does bus system work correctly?

---

## Lab Session 2: Tri-State Buffers (60-90 min)

### Part 1: Testing Tri-State Buffers (30 min)

**Materials**:
- 74HC125 IC (quad tri-state buffer)
- Switches, LEDs

**Step-by-step**:
1. Insert 74HC125
2. Connect input to switch
3. Connect output to LED
4. Connect enable to switch
5. Test all states

**Testing**:
- Enable = 0, Input = 0 → Output? (Should be disconnected)
- Enable = 0, Input = 1 → Output? (Should be disconnected)
- Enable = 1, Input = 0 → Output? (Should be 0)
- Enable = 1, Input = 1 → Output? (Should be 1)

**Check**: Do tri-state buffers work correctly?

### Part 2: Multiple Buffers on Bus (30 min)

**Activity**: Multiple buffers
- Connect multiple buffers to same bus
- Only enable one at a time
- Observe: Only enabled buffer drives bus
- Others are disconnected

**Check**: Can you control which device drives bus?

---

## Lab Session 3: Register-to-Bus System (60-90 min)

### Part 1: Building Register-to-Bus (40 min)

**Materials**:
- Two 4-bit registers
- Tri-state buffers (74HC244)
- Decoder (74HC139) for selection
- LEDs for display

**Step-by-step**:
1. Build two 4-bit registers
2. Connect to tri-state buffers
3. Use decoder to select which register
4. Connect buffers to bus
5. Display bus value

**Testing**:
- Select Register A → Bus shows Register A
- Select Register B → Bus shows Register B
- Verify only one active at a time
- No conflicts!

**Check**: Does register-to-bus system work?

### Part 2: Bus Read/Write (20 min)

**Activity**: Simulate read/write
- Write: Load data into register from bus
- Read: Output register to bus
- Demonstrate both operations
- Show bus protocol

---

## Lab Session 4: Simplified SAP-1 Bus (60-90 min)

### Part 1: Building SAP-1 Bus (40 min)

**Materials**:
- Multiple registers
- ALU (adder)
- Tri-state buffers
- Control logic
- LEDs for display

**Step-by-step**:
1. Build simplified SAP-1 bus
2. Connect registers, ALU to bus
3. Add tri-state buffers
4. Add control logic (decoder)
5. Test bus operations

**Testing**:
- Select different devices
- Verify only one drives bus
- Test data flow
- Verify no conflicts

**Check**: Does SAP-1 bus work correctly?

### Part 2: Bus Operations (20 min)

**Activity**: Demonstrate operations
- Register A → Bus → Register B (transfer)
- Register A → Bus → ALU (operation)
- ALU → Bus → Register (store result)
- Show complete data path

---

## Lab Session 5: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build Bus System** (20 min)
- Build register-to-bus system
- Demonstrate bus operation
- Explain tri-state buffers

**Task 2: Avoid Bus Contention** (20 min)
- Show what happens with contention
- Show how tri-state buffers solve it
- Explain solution

### Written Assessment (20 min)

**Topics**:
- Bus concepts
- Tri-state buffers
- Bus contention
- Bus protocol

### Lab Notebook Entry

**Record**:
1. Bus systems built
2. Tri-state buffer operation
3. Bus contention demonstration
4. Solutions implemented
5. Observations

---

## Troubleshooting Guide

### Bus Contention

**Check**:
1. Multiple enables active?
2. Tri-state buffers working?
3. Control logic correct?

**Fix**:
- Ensure only one enable active
- Verify tri-state buffers
- Check control logic

### Bus Not Working

**Check**:
1. Connections correct?
2. Power connections?
3. Enable signals?

**Fix**:
- Verify connections
- Check power
- Verify enable signals

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build working bus system
- [ ] You understand tri-state buffers
- [ ] You can avoid bus contention
- [ ] You can build register-to-bus connections
- [ ] You understand CPU bus architecture
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build 8-bit bus system
2. Add more devices to bus
3. Research modern bus architectures
4. Build complete SAP-1 bus

---

## Next Lab

After completing this lab:
- Review theory on ALU Subsystem (Week 22-24)
- Read next lab material
- Prepare for ALU integration

---

*Lab work is where theory becomes reality - build to understand!*
