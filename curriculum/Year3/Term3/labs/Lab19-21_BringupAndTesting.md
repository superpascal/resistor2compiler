# Lab 19-21: SAP-1 Bring-up and Testing

## Lab Overview

In this lab, students will bring up the complete SAP-1 system, test all components, debug issues, and verify the CPU works correctly.

## Learning Objectives

- Complete system integration
- Perform initial bring-up
- Test all subsystems
- Debug hardware issues
- Verify CPU operation

## Prerequisites

- Completed Terms 1-2
- Complete SAP-1 system built
- All components connected
- Understanding of system operation

## Materials

### Components
- Complete SAP-1 system
- **Matrix Orbital LCD2041-GW-V-E (20×4 parallel LCD)** - **REQUIRED for Year 3**
  - **Part Number**: Matrix Orbital LCD2041-GW-V-E
  - **Interface**: Parallel 8-bit (HD44780-compatible)
  - **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
  - **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)
- **LCD interface components**:
  - Tri-state buffers (74HC245)
  - Address decoder
  - Pull-up resistors (10kΩ)
  - Potentiometer (10kΩ) for contrast
- Decoupling capacitors (0.1µF)
- Debugging tools
- Test equipment

**Note**: LCD integration is taught in Lab22-24, but LCD can be integrated earlier for testing. See `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for details.

### Tools
- Logic analyzer (highly recommended)
- Oscilloscope (optional)
- Multimeter
- Logic probe

## Safety

- Large system - work carefully
- Verify power before applying
- Check for shorts
- Monitor for overheating

## Lab Sessions

### Session 1: Initial Power-up (Week 25)

**Objective**: Safely power up system

**Steps**:
1. Final connection check
2. Check for shorts (multimeter)
3. Verify power supply voltage
4. Apply power slowly
5. Monitor for overheating
6. Check basic signals
7. Verify clock working
8. Verify reset working

**Expected Result**: System powers up without issues

**Troubleshooting**:
- If shorts: Find and fix before proceeding
- If overheating: Power off, find cause
- If no power: Check connections, check supply
- If clock wrong: Check clock circuit

### Session 2: Subsystem Testing (Week 26)

**Objective**: Test each subsystem

**Steps**:
1. Test data path (registers, ALU, buses)
2. Test memory subsystem
3. Test control unit (PC, IR)
4. Test microcode ROM
5. Test clock and reset
6. **Test LCD display** (if LCD integrated):
   - Connect 20×4 LCD to output port
   - Initialize LCD
   - Test LCD display with test characters
   - Verify LCD shows output correctly
7. Test output display (LCD or 7-segment)
8. Document test results
9. Fix any issues found

**Expected Result**: All subsystems working, LCD (if integrated) displaying correctly

**Troubleshooting**:
- If subsystem fails: Test components individually
- If signals wrong: Check connections, check control
- If timing issues: Check clock, check signal timing

### Session 3: Integration Testing (Week 27)

**Objective**: Test complete system integration

**Steps**:
1. Test fetch cycle
2. Test decode cycle
3. Test execute cycle
4. Test complete instruction execution
5. Test multiple instructions
6. Verify signal coordination
7. Check for conflicts
8. Document integration

**Expected Result**: Complete system integrated and working

**Troubleshooting**:
- If cycle fails: Test each phase, check signals
- If conflicts: Check signal coordination
- If timing wrong: Check clock, check delays

### Session 4: System Verification (Week 28)

**Objective**: Verify complete system operation

**Steps**:
1. Run simple test program
2. Verify instruction execution
3. Verify results
4. Test at different clock speeds
5. Add decoupling capacitors
6. Optimize signal integrity
7. Final system check
8. Document system status

**Expected Result**: Complete system verified and ready for programming

**Troubleshooting**:
- If program fails: Debug systematically
- If optimization needed: Add capacitors, improve timing
- If issues persist: Review design, get help

## Assessment

### Practical Assessment
- Successfully power up system
- Test all subsystems
- Integrate system correctly
- Verify system operation
- Document bring-up process

### Lab Report
Students should document:
- Bring-up procedures
- Test results for each subsystem
- Integration test results
- Issues encountered and solutions
- System verification

## Extension Activities

- Add debugging features
- Optimize system performance
- Add more test programs
- Expand system capabilities

## Next Lab

After completing bring-up, students will move to machine code programming (Lab 29-32).

---

*Bring-up and testing ensure reliable CPU operation*
