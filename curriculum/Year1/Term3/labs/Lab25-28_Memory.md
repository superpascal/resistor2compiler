# Lab 25-28: Memory and MAR

## Lab Overview

**Duration**: 4 weeks (8-12 hours total)  
**Prerequisites**: Read theory material on Memory and MAR  
**Outcome**: Build memory system, MAR, and understand memory operations

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Introduction to Memory (60-90 min)

### Part 1: Understanding Memory (20 min)

**Activity**: Memory concept
- Draw memory as post office boxes
- Show addresses and data
- Explain read/write operations
- Understand organization

**Check**: Do you understand memory concept?

### Part 2: Building Simple Memory Interface (40 min)

**Materials**:
- 74LS189 RAM (16x4) OR similar
- Switches (4 for address, 4 for data)
- LEDs (4) for data display
- Control switches

**Step-by-step** (using 74LS189):
1. Insert 74LS189 RAM
2. Connect address inputs (4 switches)
3. Connect data inputs (4 switches for writing)
4. Connect data outputs (4 LEDs for reading)
5. Connect control: Write Enable (WE)
6. Connect power

**Testing**:
- Set address: 0000
- Set data: 0101
- Enable write
- Change address
- Read back: Set address to 0000, enable read
- Data should be 0101!

**Check**: Does memory interface work?

---

## Lab Session 2: Memory Address Register (60-90 min)

### Part 1: Building MAR (40 min)

**Materials**:
- 4-bit register (74HC173)
- Memory chip
- Control switches
- LEDs for address display

**Step-by-step**:
1. Build 4-bit register (MAR)
2. Connect MAR outputs to memory address inputs
3. Connect bus to MAR inputs (for loading address)
4. Add control: MI (MAR In)
5. Add LEDs to show MAR value

**Testing**:
- Load address 5 into MAR
- Verify MAR shows 5
- Verify memory address inputs show 5
- Test various addresses

**Check**: Does MAR work correctly?

### Part 2: MAR to Memory Connection (20 min)

**Activity**: Connect MAR to memory
- MAR outputs → Memory address
- Verify address flows correctly
- Test address changes
- Verify memory responds

**Check**: Does MAR control memory address?

---

## Lab Session 3: Reading from Memory (60-90 min)

### Part 1: Building Read Circuit (40 min)

**Materials**:
- MAR
- Memory chip
- Tri-state buffer (74HC125 or 74HC244)
- Bus
- LEDs for display

**Step-by-step**:
1. Connect MAR to memory address
2. Connect memory data outputs to tri-state buffer
3. Connect tri-state to bus
4. Add control: RO (RAM Out)
5. Add LEDs to display data

**Testing**:
- Write data to address 5 (e.g., 1010)
- Load address 5 into MAR
- Enable RO (read)
- Verify data appears on bus
- Verify LEDs show correct data

**Check**: Does read operation work?

### Part 2: Testing Read Operations (20 min)

**Activity**: Test various reads
- Write different data to different addresses
- Read back and verify
- Test all addresses
- Document results

**Check**: Can you read from all addresses?

---

## Lab Session 4: Writing to Memory (60-90 min)

### Part 1: Building Write Circuit (40 min)

**Materials**:
- MAR
- Memory chip
- Bus (for data)
- Control logic

**Step-by-step**:
1. Connect MAR to memory address
2. Connect bus to memory data inputs
3. Add control: WE (Write Enable)
4. Add control: WI (Write Input - data to bus)

**Testing**:
- Load address 3 into MAR
- Put data 0110 on bus
- Assert WE (write)
- Release WE
- Read back and verify

**Check**: Does write operation work?

### Part 2: Testing Write Operations (20 min)

**Activity**: Test various writes
- Write different data to different addresses
- Read back and verify
- Test all addresses
- Document results

**Check**: Can you write to all addresses?

---

## Lab Session 5: Complete Memory System (60-90 min)

### Part 1: Integration (40 min)

**Activity**: Integrate all components
- MAR
- Memory
- Read circuit
- Write circuit
- Bus connections
- Control signals

**Testing**:
- Test complete read operation
- Test complete write operation
- Verify all connections
- Debug any issues

**Check**: Does complete memory system work?

### Part 2: Memory Operations (20 min)

**Activity**: Perform operations
- Write sequence of data
- Read sequence of data
- Verify data persistence
- Test address decoding (if multiple chips)

---

## Lab Session 6: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build Memory System** (20 min)
- Build complete memory system
- Demonstrate read operation
- Demonstrate write operation
- Explain MAR function

**Task 2: Memory Operations** (20 min)
- Write data to multiple addresses
- Read data from multiple addresses
- Verify data correctness
- Document operations

### Written Assessment (20 min)

**Topics**:
- Memory concepts
- MAR operation
- Read/write operations
- Address decoding
- Timing

### Lab Notebook Entry

**Record**:
1. Memory system built
2. MAR operation
3. Read/write operations
4. Observations
5. Problems and solutions

---

## Troubleshooting Guide

### Memory Doesn't Work

**Check**:
1. Power connections?
2. Address connections?
3. Data connections?
4. Control signals?

**Fix**:
- Verify power
- Check address connections
- Verify data connections
- Check control signals

### Read Doesn't Work

**Check**:
1. MAR address correct?
2. Read signal asserted?
3. Tri-state enabled?
4. Data connections?

**Fix**:
- Verify MAR
- Check read signal
- Verify tri-state
- Check connections

### Write Doesn't Work

**Check**:
1. MAR address correct?
2. Data on bus?
3. Write signal asserted?
4. Timing correct?

**Fix**:
- Verify MAR
- Check data on bus
- Verify write signal
- Check timing

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build working memory interface
- [ ] You can build working MAR
- [ ] You can read from memory
- [ ] You can write to memory
- [ ] You understand memory operations
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build larger memory system
2. Add address decoding for multiple chips
3. Research memory types
4. Build memory with address decoding

---

## Next Lab

After completing this lab:
- Review theory on Control Concepts (Week 29-32)
- Read next lab material
- Prepare for control systems

---

*Lab work is where theory becomes reality - build to understand!*
