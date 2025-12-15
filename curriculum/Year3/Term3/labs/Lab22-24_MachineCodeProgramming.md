# Lab 22-24: Machine Code Programming

## Lab Overview

In this lab, students will program the SAP-1 CPU in machine code, develop and test programs, and run complete programs successfully. **Students will also build a RomWriter module as a ROM programming tool that will be used throughout the curriculum.**

## Learning Objectives

- **Build RomWriter ROM programming tool (used throughout curriculum)**
- Integrate 20×4 parallel LCD display with SAP-1
- Understand SAP-1 instruction set
- Program in machine code
- Develop and test programs
- Debug programs
- Run complete programs with LCD output

## Prerequisites

- Completed Lab 19-21 (Bring-up and Testing)
- Working SAP-1 CPU
- **Have 20×4 HD44780 LCD and interface components ready**
- Understanding of instruction set
- Understanding of CPU operation
- **Have read LCD Display Output Guide** (`../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md`)

## Materials

### Components
- **RomWriter Module components (LAB PROJECT - Build in Session 0)**:
  - Interface circuit (may need adaptation for SAP-1/65C816)
  - ROM socket (for target ROM chip)
  - Control logic (for programming protocol)
  - Status LEDs
  - PCB or perfboard
  - Supporting components (resistors, capacitors, buffers)
- Working SAP-1 CPU
- **LCD Display (REQUIRED)** - Choose one:
  - **Matrix Orbital LCD2041-GW-V-E (20×4 parallel LCD)** - **RECOMMENDED**
    - **Part Number**: Matrix Orbital LCD2041-GW-V-E
    - **Display**: 20 characters × 4 rows
    - **Interface**: Parallel 8-bit (HD44780-compatible)
    - **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
    - **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)
  - **Microtips Technology NMTC-S20200XFYHSAY-10B (20×2 parallel LCD)** - **BUDGET OPTION**
    - **Part Number**: Microtips Technology NMTC-S20200XFYHSAY-10B
    - **Display**: 20 characters × 2 rows
    - **Interface**: Parallel 8-bit (HD44780-compatible)
    - **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
    - **Mouser Link**: [NMTC-S20200XFYHSAY-10B](https://eu.mouser.com/ProductDetail/Microtips-Technology/NMTC-S20200XFYHSAY-10B)
    - **Note**: Budget-friendly alternative with same educational value (parallel interface)
- **LCD interface components**:
  - Tri-state buffers (74HC245) for data bus
  - Address decoder for LCD chip select
  - Pull-up resistors (10kΩ) for control lines
  - Potentiometer (10kΩ) for LCD contrast
  - Decoupling capacitors (0.1µF)
- Memory programming tools
- Debugging tools

**See**: `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for detailed LCD integration guide

### Tools
- EEPROM programmer (if using EEPROM)
- **RomWriter** (after Session 0): Students use the RomWriter they build for programming ROMs
- **TTL Logic Probe** (built in Year 2 Term 2, used here for debugging)
- **Prototype Module** (built in Year 2 Term 3, used here for testing)
- Logic analyzer (optional)
- Documentation materials

## Safety

- Work with powered system carefully
- Verify programs before running
- Use single-step for debugging

## Lab Sessions

### Session 0A: RomWriter Construction (Week 22, Day 1) ⭐ QUICK WIN LAB PROJECT

**Objective**: Build RomWriter ROM programming tool that will be used throughout the curriculum for programming ROM chips

**Learning Value**:
- ✅ **Immediate utility**: Essential tool for ROM programming in all future labs
- ✅ **Interface design**: Teaches interface design and programming protocols
- ✅ **System integration**: Connects software development to hardware programming
- ✅ **Practical skills**: Interface design, programming protocols, ROM technology

**Steps**:
1. **Review RomWriter Design** (30 min):
   - Understand ROM programming process
   - Review programming protocols (parallel, serial, or adapter-based)
   - Plan interface design (may need adaptation for SAP-1/65C816 system)
   - Consider interface options (direct parallel, adapter-based, or USB-serial)

2. **Design RomWriter Interface** (60 min):
   - Design interface circuit (may use existing EEPROM programmer or build custom)
   - Plan ROM socket connection
   - Design control logic (programming enable, verify, status)
   - Add status LEDs (programming, verify, error)
   - Create PCB layout (or perfboard layout)

3. **Build RomWriter Module** (90 min):
   - Fabricate PCB (or prepare perfboard)
   - Solder ROM socket
   - Solder interface circuit
   - Solder control logic
   - Solder status LEDs
   - Add power connections
   - Test power and connections

4. **Test RomWriter** (30 min):
   - Test ROM socket connection
   - Test programming interface (if applicable)
   - Test status LEDs
   - Verify module operation
   - Document interface specifications

**Expected Result**: Working RomWriter module for programming ROM chips

**Troubleshooting**:
- If programming fails: Check interface connections, check programming protocol
- If ROM socket issues: Check socket connections, check pin assignments
- If status LEDs don't work: Check LED connections, check control logic

**Reference**: See `../../../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for RC2014 RomWriter design reference (may need interface adaptation)

**Note**: RomWriter interface may need adaptation for SAP-1/65C816 system. Students may use existing EEPROM programmer with adapter, or build custom interface based on available programming tools.

**Ongoing Use**: This RomWriter will be used in all subsequent labs (Years 3-6) for programming ROM chips with machine code and system software

### Session 0B: LCD Integration with SAP-1 (Week 22, Day 2-3)

**Objective**: Integrate 20×4 parallel LCD display with SAP-1 output port

**Steps**:
1. **Review LCD Guide** (15 min):
   - Read `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md`
   - Understand HD44780 LCD controller
   - Understand parallel interface requirements

2. **Connect LCD to SAP-1** (60 min):
   - Connect LCD D0-D7 to SAP-1 data bus via tri-state buffers (74HC245)
   - Connect LCD RS (Register Select) to address decoder output
   - Connect LCD E (Enable) to control logic
   - Connect LCD R/W to ground (write-only)
   - Connect power (5V, GND)
   - Connect contrast potentiometer (V0)

3. **Implement Address Decoding** (30 min):
   - Design address decoder for LCD registers
   - **Memory Map** (example):
     - `$0E`: LCD Data Register (RS=1)
     - `$0F`: LCD Command Register (RS=0)
   - Connect address decoder to LCD RS line

4. **Initialize LCD** (45 min):
   - Power on LCD (wait 50ms for initialization)
   - Send function set command (8-bit, 2-line, 5×8 font)
   - Send display control (display on, cursor off)
   - Send clear display command
   - Send entry mode set (increment cursor)
   - Verify LCD initializes correctly

5. **Test LCD Display** (30 min):
   - Send test characters to LCD
   - Display "HELLO" message
   - Test cursor positioning
   - Verify all 4 rows work
   - Test character display

**Expected Result**: LCD connected, initialized, and displaying text correctly

**Troubleshooting**:
- If LCD doesn't power on: Check 5V and GND connections
- If no display: Adjust contrast potentiometer
- If garbled text: Check initialization sequence, add delays
- If wrong characters: Check data bus connections
- If not responding: Check address decoding, check control signals

**Reference**: See `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for detailed instructions and code examples

### Session 1: Instruction Set and Programming (Week 22, Day 3-4)

**Objective**: Learn instruction set and program structure

**Steps**:
1. Review SAP-1 instruction set
2. Understand instruction encoding
3. Learn machine code format
4. Design simple program (load and output to LCD)
5. Convert to machine code
6. Plan memory layout
7. **Plan LCD output**: Design how program will display results on LCD
8. Document program

**Expected Result**: Understand instruction set, program design, and LCD output integration

**Troubleshooting**:
- If instructions unclear: Review instruction set, ask questions
- If encoding wrong: Check opcode table, verify format
- If program unclear: Simplify, break into steps

### Session 2: Program Loading and Execution (Week 30)

**Objective**: Load and execute first program

**Steps**:
1. Load program into memory (manual or EEPROM)
2. Verify program loaded correctly
3. Reset CPU (PC = 0)
4. Run program in single-step mode
5. Verify each instruction executes
6. **Check LCD output**: Verify result displays on LCD
7. Debug if needed
8. Document execution

**Expected Result**: First program executes correctly and displays result on LCD

**Troubleshooting**:
- If program doesn't load: Check memory, check programming
- If execution fails: Single-step, check signals, check data
- If results wrong: Trace program, check each step

### Session 3: Arithmetic Program (Week 31)

**Objective**: Develop and test arithmetic program

**Steps**:
1. Design program to add two numbers
2. Convert to machine code
3. Load program and data into memory
4. Execute program
5. **Verify result on LCD**: Sum displayed on LCD (e.g., "SUM=42")
6. Test with different numbers
7. Verify LCD displays correct results
8. Debug if needed
9. Document program

**Expected Result**: Arithmetic program works correctly and displays results on LCD

**Troubleshooting**:
- If addition wrong: Check ALU, check registers, check data
- If result wrong: Trace program, verify each step
- If LCD display wrong: Check LCD initialization, check data bus, check address decoding
- If LCD not showing result: Verify OUT instruction writes to LCD data register, check LCD connections

### Session 4: Complex Program (Week 32)

**Objective**: Develop and test complex program

**Steps**:
1. Design complex program (multiple operations)
2. Convert to machine code
3. Load into memory
4. Execute program
5. **Verify results on LCD**: All results display correctly on LCD
6. Test edge cases
7. Verify LCD shows intermediate and final results
8. Debug if needed
9. Document program

**Expected Result**: Complex program works correctly and displays all results on LCD

**Troubleshooting**:
- If program fails: Debug step-by-step, check logic
- If results wrong: Verify algorithm, check execution
- If issues persist: Simplify, test parts separately

## Assessment

### Practical Assessment
- Successfully integrate 20×4 LCD with SAP-1
- Initialize LCD and display test messages
- Understand instruction set
- Program in machine code
- Develop and test programs
- Debug programs
- Run complete programs with LCD output

### Lab Report
Students should document:
- LCD integration (connections, initialization, testing)
- Program designs
- Machine code listings
- Test results (including LCD output)
- Debugging processes
- Program execution with LCD display

## Extension Activities

- Add more instructions
- Create program library
- Optimize programs
- Add conditional operations

## Next Lab

After completing programming, students will move to system completion (Lab 33-36).

---

*Machine code programming enables CPU use*
