# Lab 22-24: Input/Output Subsystems

## Lab Overview

In this lab, students will integrate ACIA for serial communication, VIA for parallel I/O, LCD display, and timer functions into the 65C816 system.

## Learning Objectives

- Integrate ACIA for serial communication
- Integrate VIA for parallel I/O
- Interface LCD display
- Implement timer functions
- Test I/O subsystems

## Prerequisites

- Completed Lab 1-4 (Memory Banking)
- Expanded 65C816 system
- Understanding of I/O concepts
- Understanding of memory-mapped I/O

## Materials

### Components
- ACIA (65C51) chip
- Additional VIA (65C22) chips
- LCD display (2×16 or 4×20)
- Serial interface (FTDI or USB-serial)
- Resistors for LCD
- Decoupling capacitors
- **4×4 Matrix Keypad (OPTIONAL)**: ~$3-5 - For optional keypad interface
- **Pull-up resistors (10kΩ × 4) (OPTIONAL)**: For keypad columns

### Tools
- Serial terminal software
- Logic analyzer
- Oscilloscope
- Multimeter

## Safety

- Handle chips carefully (ESD protection)
- Verify connections before power
- Check for shorts

## Lab Sessions

### Session 1: ACIA Integration (Week 5)

**Objective**: Integrate ACIA for serial communication

**Steps**:
1. Place ACIA on breadboard
2. Connect to address/data buses
3. Implement address decoding
4. Connect serial interface
5. Initialize ACIA
6. Test transmission
7. Test reception

**Expected Result**: ACIA working for serial I/O

**Troubleshooting**:
- If ACIA doesn't work: Check connections, check decoding
- If serial wrong: Check baud rate, check interface
- If communication fails: Check wiring, verify settings

### Session 2: VIA Integration (Week 6)

**Objective**: Integrate VIA for parallel I/O

**Steps**:
1. Place additional VIA on breadboard
2. Connect to address/data buses
3. Implement address decoding
4. Configure ports
5. Test port input
6. Test port output
7. Test timers

**Expected Result**: VIA working for parallel I/O

**Troubleshooting**:
- If VIA doesn't work: Check connections, check decoding
- If ports wrong: Check configuration, check direction
- If timers fail: Check programming, verify settings

### Session 3: LCD Display Interface (Week 7)

**Objective**: Interface LCD display

**Steps**:
1. Connect LCD to VIA or direct
2. Implement LCD control
3. Initialize LCD
4. Send test characters
5. Display messages
6. Test cursor control
7. Verify display

**Expected Result**: LCD displaying text correctly

**Troubleshooting**:
- If LCD doesn't work: Check connections, check power
- If display wrong: Check initialization, check data
- If characters wrong: Check encoding, verify data

### Session 3B: Matrix Keypad Interface (OPTIONAL - Week 7, if time permits)

**Status**: ⚠️ **OPTIONAL ENHANCEMENT** - Valuable but not required

**Objective**: Interface 4×4 matrix keypad for text/numeric input

**Steps**:
1. **Connect Keypad** (30 min):
   - Connect 4×4 keypad to VIA Port A or B
   - Connect rows to output bits (0-3)
   - Connect columns to input bits (4-7) with pull-up resistors (10kΩ)
   - Verify connections

2. **Implement Scanning** (60 min):
   - Write matrix scanning algorithm
   - Test row activation
   - Test column reading
   - Verify key detection

3. **Add Debouncing** (30 min):
   - Implement debouncing logic
   - Test with key presses
   - Verify stable key detection
   - Adjust delay if needed

4. **Key Code Mapping** (30 min):
   - Create key code to ASCII conversion table
   - Test key code mapping
   - Verify correct character output
   - Test all 16 keys

5. **Integration Test** (30 min):
   - Test keypad with LCD display
   - Enter numbers and display
   - Test simple calculator input
   - Verify complete input system

**Expected Result**: Keypad working, can enter numbers/characters

**Troubleshooting**:
- If no keys detected: Check connections, verify pull-ups, check scanning algorithm
- If multiple keys detected: Check for short circuits, verify wiring
- If wrong keys: Check key mapping table, verify row/column order
- If intermittent: Add debouncing delay, check connections

**Reference**: See `../../../resources/MATRIX_KEYPAD_INTERFACE_GUIDE.md` for detailed guide

**Note**: This is **OPTIONAL** - System works fine with buttons only. Keypad is valuable educational progression but not essential.

### Session 4: Complete I/O Integration (Week 8)

**Objective**: Integrate all I/O and test complete system

**Steps**:
1. Integrate all I/O subsystems
2. Test serial communication
3. Test parallel I/O
4. Test LCD display
5. Test timers
6. **Test keypad (if implemented)**: Verify keypad input works
7. Create I/O test program
8. Verify complete I/O system

**Expected Result**: Complete I/O system working (including keypad if implemented)

**Troubleshooting**:
- If integration fails: Test each subsystem, verify connections
- If conflicts: Check address decoding, verify I/O map
- If issues persist: Debug systematically
- If keypad issues: See Session 3B troubleshooting

## Assessment

### Practical Assessment
- Successfully integrate ACIA
- Successfully integrate VIA
- Successfully interface LCD
- Test all I/O subsystems
- Verify complete system

### Lab Report
Students should document:
- ACIA integration
- VIA integration
- LCD interface
- Timer implementation
- Test results
- I/O map
- System verification

## Extension Activities

- Additional I/O devices
- Advanced I/O features
- Optimize I/O code
- Help other students

## Next Lab

After completing I/O integration, students will move to graphics/sound research (Lab 9-12).

---

*I/O subsystems enable interaction and prepare for complete systems*
