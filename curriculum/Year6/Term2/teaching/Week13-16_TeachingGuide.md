# Week 13-16: Enhanced Monitor and Boot Loader - Teaching Guide

## Overview

This teaching guide supports the delivery of enhanced monitor and boot loader development over 4 weeks. Students extend the Year 5 basic monitor with advanced features and implement a boot loader for SD card program loading.

## Learning Objectives

- Extend basic monitor with advanced debugging features
- Implement SD card loading capability
- Add breakpoint and disassembly support
- Design and implement boot loader
- Load programs from SD card into memory
- Execute loaded programs

## Prerequisites

- ✅ Completed Year 5 (basic monitor, assembler, runtime)
- ✅ Working 65C816 system on PCB
- ✅ Basic monitor program from Year 5
- ✅ Understanding of system architecture
- ✅ Assembly programming experience

## Week 13-14: Enhanced Monitor Program

### Week 13: Advanced Debugging Features

#### Day 1: Breakpoints

**Objectives**:
- Understand breakpoint concept
- Implement breakpoint setting
- Implement breakpoint restoration

**Activities**:
1. **Introduction** (30 min):
   - What are breakpoints?
   - Why are they useful?
   - How do they work?

2. **Breakpoint Implementation** (90 min):
   - Design breakpoint data structure
   - Implement breakpoint setting (replace instruction with BRK)
   - Implement breakpoint restoration (restore original instruction)
   - Test breakpoint functionality

3. **Breakpoint Commands** (60 min):
   - Add "bp" command (set breakpoint)
   - Add "bpl" command (list breakpoints)
   - Add "bpd" command (delete breakpoint)
   - Test commands via serial interface

**Assessment**:
- Students set breakpoint at specific address
- Students run program, verify it stops at breakpoint
- Students continue program execution

#### Day 2: Watchpoints

**Objectives**:
- Understand watchpoint concept
- Implement watchpoint monitoring
- Add watchpoint commands

**Activities**:
1. **Introduction** (30 min):
   - What are watchpoints?
   - Difference from breakpoints
   - Use cases

2. **Watchpoint Implementation** (90 min):
   - Design watchpoint data structure
   - Implement watchpoint checking
   - Add watchpoint to execution loop
   - Test watchpoint functionality

3. **Watchpoint Commands** (60 min):
   - Add "wp" command (set watchpoint)
   - Add "wpl" command (list watchpoints)
   - Add "wpd" command (delete watchpoint)
   - Test commands

**Assessment**:
- Students set watchpoint on memory location
- Students modify memory, verify watchpoint triggers
- Students continue execution

#### Day 3: Disassembly

**Objectives**:
- Understand disassembly concept
- Implement instruction decoder
- Add disassembly command

**Activities**:
1. **Introduction** (30 min):
   - What is disassembly?
   - Why is it useful?
   - Instruction format

2. **Instruction Decoder** (90 min):
   - Create opcode lookup table
   - Implement addressing mode decoding
   - Implement operand extraction
   - Test decoder with sample instructions

3. **Disassembly Command** (60 min):
   - Add "dis" command (disassemble memory)
   - Display assembly code with addresses
   - Test with various instructions

**Assessment**:
- Students disassemble memory region
- Students verify disassembly matches source code
- Students use disassembly for debugging

#### Day 4: System Information Commands

**Objectives**:
- Add memory map display
- Add device status display
- Enhance monitor with system info

**Activities**:
1. **Memory Map** (60 min):
   - Design memory map data structure
   - Implement memory map display
   - Add "memmap" command
   - Test memory map display

2. **Device Status** (60 min):
   - Design device status structure
   - Implement device status checking
   - Add "devices" command
   - Test device status display

3. **Integration** (60 min):
   - Integrate all new commands
   - Test complete enhanced monitor
   - Document new commands

**Assessment**:
- Students display memory map
- Students display device status
- Students use enhanced monitor for debugging

### Week 14: SD Card Loading

#### Day 1: SD Card Interface

**Objectives**:
- Understand SPI protocol
- Implement SPI driver
- Initialize SD card

**Activities**:
1. **SPI Introduction** (30 min):
   - SPI protocol overview
   - Signals (MOSI, MISO, SCK, CS)
   - Timing requirements

2. **SPI Driver** (90 min):
   - Implement SPI initialization
   - Implement SPI byte send/receive
   - Test SPI communication
   - Verify with logic analyzer

3. **SD Card Initialization** (60 min):
   - Implement SD card init sequence
   - Send CMD0, CMD8, ACMD41
   - Verify card initialization
   - Test with different SD cards

**Assessment**:
- Students initialize SD card
- Students verify initialization success
- Students handle initialization errors

#### Day 2: File Reading

**Objectives**:
- Read sectors from SD card
- Implement file reading
- Handle file errors

**Activities**:
1. **Sector Reading** (60 min):
   - Implement CMD17 (read block)
   - Read single sector (512 bytes)
   - Verify data integrity
   - Test with known data

2. **File Reading** (90 min):
   - Implement simple file system reading
   - Read file from known location
   - Parse file header (if needed)
   - Test file reading

3. **Error Handling** (30 min):
   - Handle SD card errors
   - Handle file not found
   - Display error messages
   - Test error cases

**Assessment**:
- Students read file from SD card
- Students verify file contents
- Students handle errors gracefully

#### Day 3: Program Loading

**Objectives**:
- Load binary files into memory
- Load Intel HEX files
- Verify loaded programs

**Activities**:
1. **Binary Loading** (60 min):
   - Implement binary file loading
   - Load at fixed address
   - Verify memory write
   - Test binary loading

2. **HEX File Loading** (90 min):
   - Parse Intel HEX format
   - Handle extended addresses
   - Load at specified addresses
   - Test HEX loading

3. **Verification** (30 min):
   - Implement checksum verification
   - Verify file size
   - Verify memory contents
   - Test verification

**Assessment**:
- Students load binary program
- Students load HEX program
- Students verify loaded program

#### Day 4: Integration

**Objectives**:
- Integrate SD card loading into monitor
- Add load commands
- Test complete system

**Activities**:
1. **Monitor Integration** (60 min):
   - Add "load" command to monitor
   - Integrate SD card loading
   - Test loading via monitor

2. **Command Interface** (60 min):
   - Add "list" command (list files)
   - Add "load" command (load program)
   - Add "exec" command (execute program)
   - Test commands

3. **System Testing** (60 min):
   - Test complete workflow
   - Load program from SD card
   - Execute program
   - Debug using enhanced monitor

**Assessment**:
- Students load program from SD card
- Students execute loaded program
- Students use enhanced monitor for debugging

---

## Week 15-16: Boot Loader

### Week 15: Boot Loader Design

#### Day 1: Boot Loader Architecture

**Objectives**:
- Design boot loader architecture
- Plan boot loader features
- Design command interface

**Activities**:
1. **Architecture Design** (60 min):
   - Design boot loader structure
   - Plan module organization
   - Design data structures
   - Review design

2. **Feature Planning** (60 min):
   - List required features
   - Plan command interface
   - Plan error handling
   - Document design

3. **Implementation Plan** (60 min):
   - Break down into modules
   - Plan implementation order
   - Estimate time for each module
   - Create implementation checklist

**Assessment**:
- Students present boot loader design
- Students explain architecture decisions
- Students create implementation plan

#### Day 2: SD Card Driver

**Objectives**:
- Implement SD card driver
- Add file system support
- Test SD card operations

**Activities**:
1. **SD Card Driver** (90 min):
   - Implement SD card functions
   - Add error handling
   - Test driver functions
   - Verify with hardware

2. **File System** (60 min):
   - Implement simple file system reading
   - Read file table
   - Find files by name
   - Test file system

3. **Integration** (30 min):
   - Integrate driver into boot loader
   - Test integration
   - Fix any issues

**Assessment**:
- Students implement SD card driver
- Students test file system reading
- Students verify integration

#### Day 3: Program Loader

**Objectives**:
- Implement program loading
- Handle different file formats
- Verify loaded programs

**Activities**:
1. **Binary Loader** (60 min):
   - Implement binary file loading
   - Load at specified address
   - Verify loading
   - Test binary loader

2. **HEX Loader** (90 min):
   - Implement HEX file parsing
   - Handle extended addresses
   - Load at specified addresses
   - Test HEX loader

3. **Verification** (30 min):
   - Implement checksum verification
   - Verify file integrity
   - Test verification

**Assessment**:
- Students load binary program
- Students load HEX program
- Students verify loaded programs

#### Day 4: Execution Control

**Objectives**:
- Implement program execution
- Handle program termination
- Add execution control

**Activities**:
1. **Program Execution** (90 min):
   - Implement program start
   - Set up execution environment
   - Jump to program entry point
   - Test execution

2. **Termination Handling** (60 min):
   - Handle program return
   - Handle program crashes
   - Return to boot loader
   - Test termination

3. **Control Interface** (30 min):
   - Add execution commands
   - Add termination commands
   - Test control interface

**Assessment**:
- Students execute loaded program
- Students handle program termination
- Students test execution control

### Week 16: Boot Loader Integration

#### Day 1: Command Interface

**Objectives**:
- Implement boot loader commands
- Add user interface
- Test commands

**Activities**:
1. **Command Parser** (60 min):
   - Implement command parsing
   - Add command routing
   - Test parser
   - Handle invalid commands

2. **Command Implementation** (90 min):
   - Implement "list" command
   - Implement "load" command
   - Implement "exec" command
   - Implement "info" command
   - Test commands

3. **User Interface** (30 min):
   - Design user interface
   - Add help command
   - Test interface
   - Improve usability

**Assessment**:
- Students implement commands
- Students test command interface
- Students demonstrate commands

#### Day 2: Error Handling

**Objectives**:
- Implement error handling
- Add error messages
- Test error cases

**Activities**:
1. **Error Types** (30 min):
   - Identify error types
   - Design error codes
   - Plan error handling

2. **Error Implementation** (90 min):
   - Implement error detection
   - Add error messages
   - Handle errors gracefully
   - Test error cases

3. **Error Recovery** (60 min):
   - Implement error recovery
   - Retry failed operations
   - Test recovery
   - Improve robustness

**Assessment**:
- Students handle SD card errors
- Students handle file errors
- Students handle memory errors

#### Day 3: System Integration

**Objectives**:
- Integrate boot loader with monitor
- Test complete system
- Fix integration issues

**Activities**:
1. **Monitor Integration** (60 min):
   - Integrate boot loader with monitor
   - Share I/O resources
   - Test integration
   - Fix conflicts

2. **System Testing** (90 min):
   - Test complete workflow
   - Load program from SD card
   - Execute program
   - Debug using monitor
   - Test error cases

3. **Performance** (30 min):
   - Measure loading time
   - Optimize if needed
   - Test performance
   - Document performance

**Assessment**:
- Students integrate boot loader
- Students test complete system
- Students demonstrate workflow

#### Day 4: Documentation and Testing

**Objectives**:
- Document boot loader
- Create user guide
- Test complete system

**Activities**:
1. **Documentation** (60 min):
   - Document boot loader API
   - Document commands
   - Document error codes
   - Create user guide

2. **Testing** (90 min):
   - Create test suite
   - Test all features
   - Test error cases
   - Fix any bugs

3. **Presentation** (30 min):
   - Prepare demonstration
   - Show boot loader features
   - Answer questions
   - Gather feedback

**Assessment**:
- Students document boot loader
- Students create test suite
- Students demonstrate boot loader

---

## Teaching Tips

### Common Challenges

1. **SD Card Initialization**:
   - Problem: SD card doesn't initialize
   - Solution: Check SPI timing, verify signals, try different cards
   - Tip: Use logic analyzer to debug SPI communication

2. **Breakpoint Implementation**:
   - Problem: Breakpoints don't work correctly
   - Solution: Ensure BRK instruction is restored, check interrupt handling
   - Tip: Test with simple programs first

3. **File System Complexity**:
   - Problem: FAT implementation is too complex
   - Solution: Use simplified file system or existing library
   - Tip: Start with fixed file locations, add FAT later

4. **Memory Management**:
   - Problem: Programs overwrite monitor/boot loader
   - Solution: Use memory map, protect critical regions
   - Tip: Load programs at safe addresses

### Assessment Strategies

1. **Practical Demonstrations**:
   - Students demonstrate features working
   - Students show debugging workflow
   - Students load and execute programs

2. **Code Reviews**:
   - Review student code
   - Check for best practices
   - Provide feedback

3. **Documentation**:
   - Students document their implementations
   - Students create user guides
   - Students explain design decisions

---

## Resources

- Year 5 Monitor Program (base for extension)
- SD Card Specification (for SPI and initialization)
- Intel HEX Format Specification
- 65C816 Instruction Set Reference
- System Memory Map

---

## Next Steps

After completing enhanced monitor and boot loader, students move to device drivers (Weeks 17-20), which will use the monitor and boot loader for testing and development.

---

*Enhanced monitor and boot loader provide essential system software for program development and debugging*
