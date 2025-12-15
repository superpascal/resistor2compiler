# Lab 13-16: Enhanced Monitor and Boot Loader

## Lab Overview

In this lab, students will extend the Year 5 basic monitor program with advanced debugging features and implement a boot loader for loading programs from SD card storage. This provides essential system software for program development and debugging.

## Learning Objectives

- Extend basic monitor with advanced debugging features
- Implement breakpoints and watchpoints
- Add disassembly capability
- Implement SD card loading
- Design and implement boot loader
- Load programs from SD card into memory
- Execute loaded programs

## Prerequisites

- ✅ Completed Year 5 (basic monitor, assembler, runtime)
- ✅ Working 65C816 system on PCB
- ✅ Basic monitor program from Year 5
- ✅ Understanding of system architecture
- ✅ Assembly programming experience
- ✅ SD card hardware interface available
- ✅ Serial interface functional

## Materials

### Components
- Complete 65C816 system on PCB
- SD card module with SPI interface
- SD card (formatted, with test files)
- Serial interface (ACIA or USB-serial adapter)
- Development PC with serial terminal

### Tools
- Text editor
- Assembler (ca65 or similar)
- Serial terminal software (PuTTY, minicom, etc.)
- Linker (ld65 or similar)
- Logic analyzer (optional, for debugging SPI)
- Oscilloscope (optional, for timing verification)

## Safety

- Ensure correct SD card connections
- Verify SPI voltage levels (3.3V or 5V as appropriate)
- Use proper grounding
- Test SD card interface before starting
- Handle SD cards with care (ESD protection)

## Lab Sessions

### Session 1: Breakpoint Implementation (Week 13, Day 1-2)

**Objective**: Implement breakpoint support in monitor

**Steps**:
1. **Design Breakpoint Data Structure** (30 min):
   - Design breakpoint table structure
   - Plan breakpoint storage (max 8-16 breakpoints)
   - Design breakpoint commands

2. **Implement Breakpoint Setting** (90 min):
   - Implement "bp" command (set breakpoint)
   - Save original instruction at breakpoint address
   - Replace instruction with BRK
   - Add breakpoint to table
   - Test breakpoint setting

3. **Implement Breakpoint Restoration** (60 min):
   - Implement breakpoint removal
   - Restore original instruction
   - Remove breakpoint from table
   - Test breakpoint removal

4. **Implement Breakpoint Commands** (60 min):
   - Add "bpl" command (list breakpoints)
   - Add "bpd" command (delete breakpoint)
   - Test all breakpoint commands
   - Verify breakpoints work with program execution

**Deliverables**:
- Breakpoint implementation code
- Test program demonstrating breakpoints
- Documentation of breakpoint commands

**Assessment**:
- Students set breakpoint at specific address
- Students run program, verify it stops at breakpoint
- Students continue program execution
- Students list and delete breakpoints

---

### Session 2: Watchpoints and Disassembly (Week 13, Day 3-4)

**Objective**: Implement watchpoints and disassembly

**Steps**:
1. **Implement Watchpoints** (90 min):
   - Design watchpoint data structure
   - Implement "wp" command (set watchpoint)
   - Add watchpoint checking to execution loop
   - Implement watchpoint trigger handling
   - Test watchpoints

2. **Implement Disassembly** (90 min):
   - Create opcode lookup table
   - Implement instruction decoder
   - Implement addressing mode decoding
   - Implement operand extraction
   - Add "dis" command (disassemble memory)
   - Test disassembly with various instructions

3. **Integration** (60 min):
   - Integrate watchpoints and disassembly
   - Test with sample programs
   - Fix any issues

**Deliverables**:
- Watchpoint implementation code
- Disassembly implementation code
- Test programs demonstrating features

**Assessment**:
- Students set watchpoint on memory location
- Students modify memory, verify watchpoint triggers
- Students disassemble memory region
- Students verify disassembly matches source code

---

### Session 3: System Information Commands (Week 14, Day 1-2)

**Objective**: Add system information commands to monitor

**Steps**:
1. **Memory Map Display** (90 min):
   - Design memory map data structure
   - Implement memory region tracking
   - Implement "memmap" command
   - Display used/free memory regions
   - Test memory map display

2. **Device Status Display** (90 min):
   - Design device status structure
   - Implement device status checking
   - Implement "devices" command
   - Display device initialization status
   - Test device status display

3. **Enhanced Commands** (60 min):
   - Implement "search" command (memory search)
   - Implement "fill" command (memory fill)
   - Test enhanced commands
   - Document new commands

**Deliverables**:
- System information implementation code
- Enhanced command implementation
- Documentation of new commands

**Assessment**:
- Students display memory map
- Students display device status
- Students use enhanced commands
- Students verify commands work correctly

---

### Session 4: SD Card Interface (Week 14, Day 3-4)

**Objective**: Implement SD card interface and initialization

**Steps**:
1. **SPI Driver Implementation** (120 min):
   - Implement SPI initialization
   - Implement SPI byte send/receive
   - Test SPI communication
   - Verify with logic analyzer (if available)
   - Fix timing issues

2. **SD Card Initialization** (120 min):
   - Implement SD card init sequence
   - Send CMD0 (GO_IDLE_STATE)
   - Send CMD8 (check version)
   - Send ACMD41 (initialize, repeat until ready)
   - Send CMD58 (read OCR)
   - Send CMD16 (set block size)
   - Test initialization with different SD cards
   - Handle initialization errors

3. **Testing** (60 min):
   - Test SD card initialization
   - Verify initialization success
   - Test error handling
   - Document initialization process

**Deliverables**:
- SPI driver code
- SD card initialization code
- Test results and documentation

**Assessment**:
- Students initialize SD card successfully
- Students handle initialization errors
- Students verify initialization with different cards

---

### Session 5: SD Card Reading (Week 15, Day 1-2)

**Objective**: Implement SD card block reading

**Steps**:
1. **Block Reading** (90 min):
   - Implement CMD17 (read single block)
   - Read 512-byte block from SD card
   - Verify data integrity
   - Test with known data on SD card
   - Handle read errors

2. **File Reading** (90 min):
   - Implement simple file system reading
   - Read file from known location
   - Parse file header (if needed)
   - Test file reading
   - Handle file errors

3. **Integration** (60 min):
   - Integrate file reading with monitor
   - Add "load" command to monitor
   - Test file loading
   - Fix any issues

**Deliverables**:
- Block reading implementation
- File reading implementation
- Monitor integration code

**Assessment**:
- Students read block from SD card
- Students read file from SD card
- Students verify file contents
- Students handle errors gracefully

---

### Session 6: Program Loading (Week 15, Day 3-4)

**Objective**: Implement program loading from SD card

**Steps**:
1. **Binary File Loading** (90 min):
   - Implement binary file loading
   - Load at fixed address
   - Verify memory write
   - Test binary loading
   - Handle loading errors

2. **HEX File Loading** (90 min):
   - Parse Intel HEX format
   - Handle extended addresses
   - Load at specified addresses
   - Test HEX loading
   - Verify loaded program

3. **Program Verification** (60 min):
   - Implement checksum verification
   - Verify file size
   - Verify memory contents
   - Test verification
   - Handle verification errors

**Deliverables**:
- Binary loader implementation
- HEX loader implementation
- Verification code

**Assessment**:
- Students load binary program
- Students load HEX program
- Students verify loaded program
- Students handle loading errors

---

### Session 7: Boot Loader Implementation (Week 16, Day 1-2)

**Objective**: Implement complete boot loader

**Steps**:
1. **Boot Loader Architecture** (60 min):
   - Design boot loader structure
   - Plan command interface
   - Design error handling
   - Review design

2. **Command Interface** (90 min):
   - Implement command parser
   - Add "list" command (list files)
   - Add "load" command (load program)
   - Add "exec" command (execute program)
   - Add "info" command (system info)
   - Test commands

3. **Program Execution** (90 min):
   - Implement program start
   - Set up execution environment
   - Jump to program entry point
   - Handle program termination
   - Return to boot loader
   - Test program execution

**Deliverables**:
- Boot loader implementation code
- Command interface code
- Program execution code

**Assessment**:
- Students implement boot loader commands
- Students test command interface
- Students execute loaded programs
- Students handle program termination

---

### Session 8: Boot Loader Integration and Testing (Week 16, Day 3-4)

**Objective**: Integrate boot loader with system and test

**Steps**:
1. **System Integration** (90 min):
   - Integrate boot loader with monitor
   - Share I/O resources
   - Test integration
   - Fix any conflicts

2. **Complete Testing** (90 min):
   - Test complete workflow
   - Load program from SD card
   - Execute program
   - Debug using monitor
   - Test error cases
   - Fix any issues

3. **Documentation** (60 min):
   - Document boot loader API
   - Document commands
   - Document error codes
   - Create user guide
   - Create test suite

**Deliverables**:
- Integrated boot loader
- Test suite
- Documentation (API, commands, user guide)

**Assessment**:
- Students integrate boot loader
- Students test complete system
- Students demonstrate workflow
- Students document boot loader

---

## Lab Assessment

### Formative Assessment

- Weekly progress checks
- Code reviews
- Peer demonstrations
- Instructor feedback

### Summative Assessment

**Enhanced Monitor** (40%):
- Breakpoint implementation (10%)
- Watchpoint implementation (10%)
- Disassembly implementation (10%)
- System information commands (10%)

**Boot Loader** (40%):
- SD card interface (10%)
- File reading (10%)
- Program loading (10%)
- Boot loader integration (10%)

**Documentation and Testing** (20%):
- Code documentation (10%)
- User guide (5%)
- Test suite (5%)

### Assessment Criteria

**Excellent (A)**:
- All features implemented correctly
- Clean, well-documented code
- Comprehensive testing
- Complete documentation

**Good (B)**:
- Most features implemented
- Code mostly correct
- Adequate testing
- Good documentation

**Satisfactory (C)**:
- Basic features implemented
- Code has some issues
- Basic testing
- Basic documentation

---

## Troubleshooting

### Common Issues

1. **SD Card Not Initializing**:
   - Check SPI connections
   - Verify SPI timing
   - Check voltage levels
   - Try different SD card
   - Use logic analyzer to debug

2. **Breakpoints Not Working**:
   - Check BRK instruction placement
   - Verify interrupt vector
   - Check breakpoint restoration
   - Verify breakpoint table

3. **Disassembly Errors**:
   - Check opcode lookup table
   - Verify addressing mode decoding
   - Test with known instructions
   - Check operand extraction

4. **Program Loading Fails**:
   - Verify file format
   - Check memory addresses
   - Verify checksum
   - Check memory protection

---

## Resources

- Year 5 Monitor Program (base for extension)
- SD Card Physical Layer Specification
- Intel HEX Format Specification
- 65C816 Instruction Set Reference
- System Memory Map
- SPI Protocol Reference

---

## Next Steps

After completing enhanced monitor and boot loader, students move to device drivers (Lab 17-20), which will use the monitor and boot loader for testing and development.

---

*Enhanced monitor and boot loader provide essential system software for program development and debugging*
