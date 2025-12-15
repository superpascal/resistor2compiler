# Lab 21-24: Input/Output Systems

## Lab Overview

In this lab, students will build input and output interfaces, implement memory-mapped I/O, and create systems that interact with external devices. **Students will also build a TTL Logic Probe as a debugging tool that will be used throughout the curriculum.**

## Learning Objectives

- **Build TTL Logic Probe debugging tool (used throughout curriculum)**
- Build simple input interfaces (switches, buttons)
- Build simple output interfaces (LEDs, displays)
- Implement data direction control
- Interface with 7-segment displays
- Test I/O timing and synchronization

## Prerequisites

- Completed Lab 17-20 (Address Decoding)
- Understanding of memory-mapped I/O
- Understanding of address decoding
- Understanding of tri-state buffers

## Materials

### Components
- **TTL Logic Probe components (LAB PROJECT - Build in Session 0)**:
  - Comparators (LM339 or similar)
  - LEDs (red, green, yellow)
  - Resistors (current-limiting, pull-up)
  - Probe tip and ground clip
  - Enclosure (optional)
  - PCB or perfboard
- Switches and buttons (for input)
- LEDs and current-limiting resistors (for output)
- 7-segment displays and decoders (74HC47)
- Character LCD (optional, 16×2)
- Registers for I/O data and direction
- Address decoder for I/O space

### Tools
- Multimeter
- Logic analyzer (optional)
- **TTL Logic Probe (after Session 0)**: Students use the probe they build for debugging

## Safety

- Use current-limiting resistors for LEDs
- Verify power requirements for displays
- Check for proper connections

## Lab Sessions

### Session 0: TTL Logic Probe Construction (Week 16, Day 1-2) ⭐ QUICK WIN LAB PROJECT

**Objective**: Build TTL Logic Probe debugging tool that will be used throughout the curriculum

**Learning Value**:
- ✅ **Immediate utility**: Essential debugging tool for all future labs
- ✅ **PCB skills**: Simple PCB project (or perfboard), good for early success
- ✅ **Signal understanding**: Teaches digital signal levels (HIGH, LOW, floating)
- ✅ **Reinforcement**: Tool used throughout Years 2-6, reinforcing debugging concepts

**Steps**:
1. **Review Logic Probe Design** (30 min):
   - Understand digital signal levels (HIGH = 5V, LOW = 0V, floating = undefined)
   - Review comparator-based detection circuit
   - Plan PCB layout (or perfboard layout)

2. **Build Logic Probe Circuit** (90 min):
   - Solder comparators (LM339) to PCB/perfboard
   - Connect LEDs (red for HIGH, green for LOW, yellow for pulse)
   - Add current-limiting resistors
   - Add pull-up/pull-down resistors for proper detection
   - Connect probe tip and ground clip
   - Add power connections (5V, GND)

3. **Test Logic Probe** (30 min):
   - Test with known HIGH signal (5V)
   - Test with known LOW signal (0V)
   - Test with floating signal (should show neither HIGH nor LOW)
   - Test with clock signal (should show pulse detection)
   - Verify all LEDs work correctly

4. **Use Logic Probe for I/O Debugging** (30 min):
   - Use probe to debug I/O interfaces in subsequent sessions
   - Practice signal analysis techniques
   - Document probe operation

**Expected Result**: Working TTL Logic Probe that detects HIGH, LOW, and pulse signals

**Troubleshooting**:
- If LEDs don't light: Check power, check resistor values, check connections
- If wrong signals detected: Check comparator connections, check pull-up/pull-down resistors
- If probe doesn't respond: Check probe tip connection, check ground clip

**Reference**: See `../../../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for RC2014 TTL Logic Probe design reference

**Ongoing Use**: This logic probe will be used in all subsequent labs (Years 2-6) for debugging digital circuits

### Session 1: Simple Input Interface (Week 17)

**Objective**: Build input interface for switches

**Steps**:
1. Design input register at I/O address
2. Connect switches to input register
3. Connect input register to data bus (via tri-state)
4. Add address decoder for I/O read
5. Test: Read switch states from I/O address
6. Verify correct switch values read
7. Test with multiple switches (byte input)

**Expected Result**: Can read switch states as memory location

**Troubleshooting**:
- If switches not readable: Check connections, check tri-state enable
- If wrong values: Check switch connections, verify pull-up resistors
- If address wrong: Check I/O address decoding

### Session 2: Simple Output Interface (Week 18)

**Objective**: Build output interface for LEDs

**Steps**:
1. Design output register at I/O address
2. Connect output register to data bus
3. Connect LEDs to output register (with resistors)
4. Add address decoder for I/O write
5. Test: Write values to I/O address, verify LEDs
6. Test with LED array (8 LEDs = byte output)
7. Create patterns by writing different values

**Expected Result**: Can control LEDs by writing to I/O address

**Troubleshooting**:
- If LEDs don't light: Check connections, check resistors, check power
- If wrong LEDs: Check register connections
- If not responding: Check write enable, check address decoding

### Session 3: Data Direction Control (Week 19)

**Objective**: Implement bidirectional I/O with direction control

**Steps**:
1. Design Data Direction Register (DDR)
2. Connect DDR to control tri-state buffers
3. Build bidirectional I/O port
4. Test: Set direction to input, read switches
5. Test: Set direction to output, control LEDs
6. Test: Change direction dynamically
7. Verify no conflicts

**Expected Result**: Can control I/O direction and use port for input or output

**Troubleshooting**:
- If direction doesn't work: Check DDR connections, check tri-state control
- If conflicts: Ensure only one direction active
- If data wrong: Check port connections

### Session 4: Display Interfaces (Week 20)

**Objective**: Interface with 7-segment display

**Steps**:
1. Connect 7-segment display to breadboard
2. Add BCD to 7-segment decoder (74HC47)
3. Connect decoder to output register
4. Test: Write BCD values (0-9), verify display
5. Create counter that displays count
6. Optional: Add second display for 2-digit numbers
7. Optional: Interface with character LCD

**Expected Result**: Can display numbers on 7-segment display

**Troubleshooting**:
- If display doesn't work: Check power, check decoder connections
- If wrong segments: Check decoder to display connections
- If numbers wrong: Check BCD input to decoder

## Assessment

### Practical Assessment
- Successfully build input interface
- Successfully build output interface
- Implement data direction control
- Interface with display device
- Document I/O system

### Lab Report
Students should document:
- I/O interface designs
- Device connections
- Address assignments
- Test results
- Reflection on I/O concepts

## Extension Activities

- Add more I/O devices
- Implement LED matrix display
- Create input scanning for switch matrix
- Design I/O system with multiple ports

## Next Lab

After completing this lab, students will move to Term 3: Advanced Integration.

---

*I/O systems connect computers to the real world*
