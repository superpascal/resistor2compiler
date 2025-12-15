# Lab 22-24: ALU Subsystem

## Lab Overview

**Duration**: 3 weeks (6-9 hours total)  
**Prerequisites**: Read theory material on ALU Subsystem  
**Outcome**: Build complete ALU subsystem with addition, subtraction, and flags

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: ALU Subsystem Design (60-90 min)

### Part 1: Planning the System (20 min)

**Activity**: Design ALU subsystem
- Draw block diagram
- Identify components needed
- Plan connections
- Plan control signals

**Components**:
- Two 4-bit registers (A, B)
- 4-bit adder (74HC283)
- Tri-state buffers
- Bus system
- Flags (carry, zero)

**Check**: Do you have a clear plan?

### Part 2: Building Basic ALU (40 min)

**Materials**:
- 4-bit adder (74HC283)
- Two 4-bit registers
- Tri-state buffers
- Bus wires
- LEDs for display

**Step-by-step**:
1. Build two 4-bit registers
2. Connect to tri-state buffers
3. Connect buffers to bus
4. Connect bus to adder inputs
5. Connect adder output to bus
6. Add LEDs for display

**Testing**:
- Load Register A = 5
- Load Register B = 3
- Enable both to bus
- Adder should output 8
- Verify on LEDs

**Check**: Does basic ALU work?

---

## Lab Session 2: Addition Operation (60-90 min)

### Part 1: Testing Addition (30 min)

**Activity**: Test addition operations
- 5 + 3 = 8
- 7 + 9 = 16 (with carry)
- 12 + 4 = 16
- Various combinations

**Testing**:
- Load operands
- Enable to bus
- Observe result
- Verify correctness

**Check**: Does addition work correctly?

### Part 2: Building Carry Flag (30 min)

**Materials**:
- Adder carry-out
- D flip-flop (74HC74)
- LED for flag

**Step-by-step**:
1. Connect adder carry-out to flip-flop
2. Clock flip-flop after operation
3. Display carry flag on LED
4. Test with overflow cases

**Testing**:
- 15 + 1 = 16 (carry = 1)
- 7 + 3 = 10 (carry = 0)
- Verify carry flag

**Check**: Does carry flag work?

---

## Lab Session 3: Subtraction Operation (60-90 min)

### Part 1: Building Subtraction Circuit (40 min)

**Materials**:
- XOR gates (74HC86) for inversion
- Adder with carry-in
- Operation select switch

**Step-by-step**:
1. Add XOR gates before adder (invert B)
2. Connect operation select to XOR
3. Connect operation select to adder carry-in
4. Add mode: B passes, carry-in = 0
5. Subtract mode: B inverted, carry-in = 1

**Testing**:
- Add mode: 5 + 3 = 8
- Subtract mode: 5 - 3 = 2
- Verify both operations

**Check**: Does subtraction work correctly?

### Part 2: Testing Subtraction (20 min)

**Activity**: Test subtraction operations
- 5 - 3 = 2
- 10 - 4 = 6
- 3 - 5 = -2 (two's complement)
- Various combinations

**Check**: Do all subtractions work?

---

## Lab Session 4: Zero Flag and Integration (60-90 min)

### Part 1: Building Zero Flag (30 min)

**Materials**:
- NOR gates (74HC02)
- D flip-flop
- LED for flag

**Step-by-step**:
1. NOR all result bits together
2. If all 0 → output = 1 (zero flag)
3. Store in flip-flop
4. Display on LED

**Testing**:
- 5 - 5 = 0 (zero flag = 1)
- 5 - 3 = 2 (zero flag = 0)
- Verify zero flag

**Check**: Does zero flag work?

### Part 2: Complete Integration (30 min)

**Activity**: Integrate all components
- Registers
- Adder
- Subtraction circuit
- Carry flag
- Zero flag
- Bus system
- Control logic

**Testing**:
- Test all operations
- Test all flags
- Verify complete system
- Document operation

**Check**: Does complete ALU work?

---

## Lab Session 5: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build ALU** (20 min)
- Build complete ALU subsystem
- Demonstrate addition
- Demonstrate subtraction
- Show flags

**Task 2: Test Operations** (20 min)
- Perform various calculations
- Verify results
- Test flags
- Document findings

### Written Assessment (20 min)

**Topics**:
- ALU operation
- Two's complement
- Flags
- Data path

### Lab Notebook Entry

**Record**:
1. ALU design
2. All operations tested
3. Flag operation
4. Problems and solutions
5. Complete documentation

---

## Troubleshooting Guide

### ALU Doesn't Work

**Check**:
1. All connections correct?
2. Power connections?
3. Control signals?
4. Bus operation?

**Fix**:
- Verify all connections
- Check power
- Verify control signals
- Test bus operation

### Subtraction Wrong

**Check**:
1. XOR gates correct?
2. Carry-in correct?
3. Two's complement correct?

**Fix**:
- Verify XOR operation
- Check carry-in
- Verify two's complement

### Flags Don't Work

**Check**:
1. Flag circuits correct?
2. Clock timing?
3. Connections?

**Fix**:
- Verify flag circuits
- Check clock timing
- Verify connections

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build complete ALU subsystem
- [ ] You can perform addition
- [ ] You can perform subtraction
- [ ] You can generate carry flag
- [ ] You can generate zero flag
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Add logic operations (AND, OR, XOR)
2. Build 8-bit ALU
3. Add more flags (overflow, sign)
4. Research modern ALU designs

---

## Next Lab

After completing this lab:
- Review theory on Memory (Term 3, Week 25-28)
- Read next lab material
- Prepare for memory systems

---

*Lab work is where theory becomes reality - build to understand!*
