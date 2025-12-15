# Lab 29-32: Control Concepts

## Lab Overview

**Duration**: 4 weeks (8-12 hours total)  
**Prerequisites**: Read theory material on Control Concepts  
**Outcome**: Build control systems, state machines, and sequencers

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify IC orientation (notch indicates pin 1)
- [ ] Never short-circuit power supplies
- [ ] Use correct voltage (5V for 74HC series)

---

## Lab Session 1: Introduction to Control (60-90 min)

### Part 1: Understanding Control (20 min)

**Activity**: Manual control demonstration
- Show subsystems (registers, ALU, memory)
- Demonstrate manual control with switches
- Show how signals coordinate operations
- Understand control concept

**Check**: Do you understand why control is needed?

### Part 2: Manual Control Circuit (40 min)

**Materials**:
- All subsystems from previous labs
- Switches for control signals
- LEDs for signal display

**Step-by-step**:
1. Add switches for: AI, AO, BI, BO, EO, MI, RO
2. Connect to subsystems
3. Manually execute: A = A + B
4. Observe: Each step needs different signals

**Testing**:
- Step 1: Enable AO → A to bus
- Step 2: Enable BO → B to bus
- Step 3: ALU computes
- Step 4: Enable EO → Result to bus
- Step 5: Enable AI → Load result

**Check**: Can you manually control operations?

---

## Lab Session 2: Simple Sequencer (60-90 min)

### Part 1: Building Sequencer (40 min)

**Materials**:
- Counter (74HC161)
- Decoder (74HC139)
- Clock source
- LEDs for state display

**Step-by-step**:
1. Build 2-bit counter (4 states)
2. Connect to 2-to-4 decoder
3. Each decoder output = one state
4. Connect states to control signals
5. Add clock to advance states

**Testing**:
- State 0: AO = 1
- State 1: BO = 1
- State 2: ALU active
- State 3: EO = 1, AI = 1
- Verify sequence

**Check**: Does sequencer work correctly?

### Part 2: Testing Sequencer (20 min)

**Activity**: Test sequencer
- Run through sequence
- Verify each state
- Test with actual operation
- Verify complete operation

**Check**: Can sequencer execute operations?

---

## Lab Session 3: State Machine (60-90 min)

### Part 1: Building State Machine (40 min)

**Materials**:
- Flip-flops (74HC74)
- Logic gates
- Decoder
- Clock source

**Step-by-step**:
1. Build state register (flip-flops)
2. Build state transitions (logic)
3. Build output decoder
4. Connect to subsystems
5. Test state machine

**Testing**:
- Verify states
- Verify transitions
- Verify outputs
- Test complete operation

**Check**: Does state machine work?

### Part 2: State Machine Operations (20 min)

**Activity**: Test operations
- Execute different operations
- Verify state sequences
- Test state transitions
- Document behavior

---

## Lab Session 4: Control Integration (60-90 min)

### Part 1: Integrating Control (40 min)

**Activity**: Integrate control with all subsystems
- Connect sequencer to subsystems
- Add all control signals
- Test complete operations
- Verify coordination

**Testing**:
- Test add operation
- Test subtract operation
- Test memory operations
- Verify all work correctly

**Check**: Does integrated control work?

### Part 2: Complete System (20 min)

**Activity**: Test complete system
- All subsystems connected
- Control coordinates all
- Execute full operations
- Verify end-to-end

---

## Lab Session 5: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build Sequencer** (20 min)
- Build sequencer
- Demonstrate operation
- Explain how it works

**Task 2: Control Operations** (20 min)
- Execute operations with control
- Demonstrate coordination
- Explain control signals

### Written Assessment (20 min)

**Topics**:
- Control signals
- State machines
- Sequencers
- Control coordination

### Lab Notebook Entry

**Record**:
1. Control systems built
2. Sequencer operation
3. State machine behavior
4. Integration results
5. Observations

---

## Troubleshooting Guide

### Sequencer Doesn't Work

**Check**:
1. Counter working?
2. Decoder connections?
3. Clock signal?
4. State outputs?

**Fix**:
- Verify counter
- Check decoder
- Verify clock
- Check outputs

### Control Signals Wrong

**Check**:
1. Decoder outputs?
2. Signal connections?
3. Timing?
4. Conflicts?

**Fix**:
- Verify decoder
- Check connections
- Verify timing
- Check for conflicts

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can build working sequencer
- [ ] You can build state machine
- [ ] You can coordinate subsystems
- [ ] You understand control signals
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Build more complex sequencer
2. Add multiple operations
3. Research microcode
4. Build programmable sequencer

---

## Next Lab

After completing this lab:
- Review theory on Integration (Week 33-36)
- Read next lab material
- Prepare for final integration

---

*Lab work is where theory becomes reality - build to understand!*
