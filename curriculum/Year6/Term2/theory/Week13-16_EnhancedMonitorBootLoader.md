# Week 13-16: Enhanced Monitor and Boot Loader - Theory

## Overview

This 4-week block extends the basic monitor program from Year 5 with advanced debugging features and implements a boot loader for loading programs from SD card storage.

## Learning Objectives

By the end of this block, students will:
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
- ✅ SD card hardware interface available

## Week 13-14: Enhanced Monitor Program

### 1. Extending the Basic Monitor

**Basic Monitor (Year 5)** provides:
- Memory read/write commands
- Register display
- Program execution
- Serial I/O

**Enhanced Monitor (Year 6)** adds:
- **Advanced Debugging**: Breakpoints, watchpoints, step-by-step execution
- **Program Management**: Load from SD card, execute, terminate
- **System Information**: Memory map display, device status
- **Enhanced Commands**: Disassembly, memory search, register modification

### 2. Advanced Debugging Features

#### Breakpoints
- **Concept**: Stop execution at specific address
- **Implementation**: Replace instruction with BRK, save original instruction
- **Usage**: Set breakpoint, run program, monitor stops at breakpoint
- **Restore**: Replace BRK with original instruction when continuing

#### Watchpoints
- **Concept**: Monitor memory location, stop when value changes
- **Implementation**: Check memory value before/after each instruction
- **Usage**: Set watchpoint on variable, monitor stops when variable changes

#### Disassembly
- **Concept**: Convert machine code to assembly mnemonics
- **Implementation**: Instruction decoder, lookup table for opcodes
- **Usage**: Display memory as assembly code for debugging

#### Step-by-Step Execution
- **Concept**: Execute one instruction at a time
- **Implementation**: Single-step mode, return to monitor after each instruction
- **Usage**: Step through program to observe behavior

### 3. Program Management

#### SD Card Loading
- **Interface**: SPI communication with SD card
- **File Format**: Binary or Intel HEX format
- **Loading**: Read file from SD card, write to memory
- **Verification**: Checksum verification of loaded data

#### Program Execution
- **Load Address**: Specify memory address for program
- **Execution**: Jump to program start address
- **Termination**: Return to monitor when program ends
- **Error Handling**: Handle invalid addresses, corrupted files

### 4. System Information Commands

#### Memory Map Display
- **Show**: Used/free memory regions
- **Display**: Monitor, OS, user program locations
- **Purpose**: Understand memory layout

#### Device Status
- **Show**: Status of all devices (video, audio, keyboard, SD card)
- **Display**: Initialization status, error conditions
- **Purpose**: Debug hardware issues

### 5. Enhanced Commands

#### Memory Search
- **Find**: Search memory for specific byte pattern
- **Usage**: Locate data or code in memory

#### Register Modification
- **Modify**: Change register values directly
- **Usage**: Test program behavior with different register values

#### Memory Fill
- **Fill**: Fill memory region with pattern
- **Usage**: Initialize memory, test memory

---

## Week 15-16: Boot Loader

### 1. What is a Boot Loader?

**Boot Loader** is a program that:
- Loads other programs from storage (SD card)
- Initializes program execution environment
- Handles program loading and verification
- Provides program management

**Analogy**: Think of a boot loader like a program launcher - it finds programs on storage, loads them into memory, and starts them running.

### 2. SD Card Interface

#### SPI Communication
- **Protocol**: Serial Peripheral Interface (SPI)
- **Signals**: MOSI, MISO, SCK, CS (Chip Select)
- **Speed**: Configurable clock speed
- **Mode**: SPI Mode 0 (CPOL=0, CPHA=0)

#### SD Card Initialization
1. **Power On**: Apply power to SD card
2. **Clock**: Send 80+ clock pulses
3. **CMD0**: Send reset command (GO_IDLE_STATE)
4. **CMD8**: Check card version (SDHC/SDXC)
5. **ACMD41**: Initialize card (send until ready)
6. **CMD58**: Read OCR register
7. **CMD16**: Set block size (512 bytes)

#### SD Card Reading
- **CMD17**: Read single block (512 bytes)
- **Address**: Block address (sector number)
- **Data**: 512 bytes of data
- **CRC**: Optional CRC verification

### 3. File System Support

#### FAT16/FAT32 (Simplified)
- **Boot Sector**: Read partition information
- **FAT Table**: File allocation table (simplified reading)
- **Root Directory**: Find file entries
- **File Reading**: Read file clusters sequentially

**Note**: Full FAT implementation is complex. Consider:
- Simplified sequential file reading
- Pre-formatted SD card with known file locations
- Using existing FAT library if available

#### Alternative: Simple File System
- **Fixed Locations**: Files at known sector addresses
- **File Table**: Simple table mapping filenames to sectors
- **Sequential Reading**: Read files sequentially

### 4. Program Loading

#### Binary Format
- **Raw Binary**: Direct memory image
- **Loading**: Copy bytes directly to memory
- **Address**: Load at fixed address or relocatable

#### Intel HEX Format
- **Format**: ASCII text with address and data
- **Records**: Extended linear address, data, end of file
- **Parsing**: Parse HEX records, load at specified addresses
- **Advantage**: Supports relocatable code

#### Program Verification
- **Checksum**: Verify file integrity
- **Size Check**: Verify file size matches expected
- **Memory Check**: Verify memory write succeeded

### 5. Program Execution

#### Execution Environment
- **Stack Setup**: Initialize stack pointer
- **Registers**: Set initial register values
- **Interrupts**: Enable/disable interrupts as needed
- **Memory**: Ensure program memory is accessible

#### Program Start
- **Entry Point**: Jump to program start address
- **Return**: Program returns to boot loader when done
- **Error Handling**: Handle program crashes gracefully

### 6. Boot Loader Features

#### Command Interface
- **List Files**: Show available programs on SD card
- **Load Program**: Load program from SD card
- **Execute Program**: Run loaded program
- **System Info**: Show memory usage, device status

#### Error Handling
- **SD Card Errors**: Handle card not present, read errors
- **File Errors**: Handle file not found, corrupted file
- **Memory Errors**: Handle insufficient memory, invalid address
- **User Feedback**: Display error messages

---

## Integration with System

### Monitor + Boot Loader
- **Monitor**: Provides debugging and system control
- **Boot Loader**: Provides program loading and execution
- **Integration**: Boot loader can use monitor for I/O
- **Workflow**: Load program via boot loader, debug via monitor

### Hardware Requirements
- **SD Card Interface**: SPI interface to SD card
- **Memory**: Sufficient RAM for programs
- **Serial I/O**: For monitor communication
- **Interrupts**: For real-time features (optional)

### Software Dependencies
- **Year 5 Monitor**: Base for enhanced monitor
- **SPI Driver**: For SD card communication
- **Serial I/O**: For monitor interface
- **Memory Management**: For program loading

---

## Learning Outcomes

After completing this block, students will:

1. **Enhanced Monitor**:
   - Extend basic monitor with advanced features
   - Implement breakpoints and watchpoints
   - Add disassembly capability
   - Display system information

2. **Boot Loader**:
   - Interface with SD card hardware
   - Load programs from SD card
   - Verify program integrity
   - Execute loaded programs

3. **System Integration**:
   - Integrate monitor and boot loader
   - Use boot loader for program development
   - Debug programs using enhanced monitor

---

## Next Steps

After completing enhanced monitor and boot loader, students move to device drivers (Weeks 17-20), which will use the monitor and boot loader for testing and development.

---

*Enhanced monitor and boot loader provide essential system software for program development and debugging*
