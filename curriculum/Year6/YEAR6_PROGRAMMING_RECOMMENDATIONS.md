# Year 6 Programming Content Recommendations

## Overview

This document recommends programming content for Year 6 of the resistor2compiler curriculum, focusing on system-level programming that directly supports and exercises the hardware project.

**Context**: 
- Year 5 already covers: Monitor Program (basic), Assembler Toolchain, Pascal Runtime
- Year 6 Term 1: PCB Design and Final Hardware (hardware focus)
- Year 6 Term 2: Software Stack and Capstone Projects (programming focus)
- SuperPascal compiler development runs parallel (separate project)

**Question**: What programming should be taught in Year 6 that's relevant to the hardware project?

---

## Recommended Programming Topics for Year 6

### 1. Enhanced Monitor Program ✅ **RECOMMENDED**

**Why**: Year 5 covers basic monitor, but Year 6 can enhance it with:
- **Advanced debugging features**: Breakpoints, watchpoints, disassembly
- **Program management**: Load from SD card, execute, terminate
- **System information**: Memory map display, device status
- **Enhanced commands**: More powerful memory operations, register manipulation

**Relevance to Hardware**:
- Exercises all hardware subsystems (CPU, memory, I/O)
- Provides essential debugging tool for hardware testing
- Demonstrates system-level programming
- Directly supports hardware development workflow

**Implementation**:
- Extend Year 5 basic monitor
- Add SD card loading capability
- Add breakpoint support
- Add disassembly command
- Add system information commands

---

### 2. Boot Loader ✅ **RECOMMENDED**

**Why**: Essential for loading programs from storage (SD card) into memory and starting execution.

**Features**:
- **SD Card Interface**: Read from SD card (SPI interface)
- **Program Loading**: Load binary/hex files into RAM
- **Relocation**: Handle program loading at different addresses
- **Verification**: Checksum verification of loaded programs
- **Execution**: Start program execution from loaded address

**Relevance to Hardware**:
- Exercises SD card hardware interface
- Demonstrates storage I/O programming
- Essential for practical program development workflow
- Tests memory management and addressing

**Implementation**:
- SPI driver for SD card
- FAT16/FAT32 file reading (or simple sequential sector reading)
- Binary/hex file parser
- Memory loading routines
- Program execution control

---

### 3. Device Drivers ✅ **HIGHLY RECOMMENDED**

**Why**: Direct interface to hardware peripherals - essential for using the hardware.

#### 3.1 Video Driver
- **Features**: Initialize video chip, set modes, write to video memory, sprite control
- **Hardware**: TMS9918/V9938/V9958, VERA, or microcontroller video solution
- **Relevance**: Exercises video hardware, demonstrates graphics programming

#### 3.2 Audio Driver
- **Features**: Initialize sound chip, play tones, control volume, music playback
- **Hardware**: YM2149F PSG or SAM2695 MIDI synthesizer
- **Relevance**: Exercises audio hardware, demonstrates sound programming

#### 3.3 Keyboard/Input Driver
- **Features**: PS/2 keyboard interface, gamepad support, input buffering
- **Hardware**: PS/2 keyboard, gamepad controllers
- **Relevance**: Exercises input hardware, demonstrates I/O programming

#### 3.4 SD Card Driver
- **Features**: SPI interface, SD card initialization, sector read/write
- **Hardware**: SD card interface (SPI)
- **Relevance**: Exercises storage hardware, essential for program loading

**Implementation**:
- Low-level register access for each device
- Initialization routines
- High-level API for applications
- Error handling and status reporting

---

### 4. System Services / API ✅ **RECOMMENDED**

**Why**: Provides abstraction layer for applications, making hardware easier to use.

**Features**:
- **File System**: Basic file operations (read, write, list directory)
- **I/O Services**: Console I/O, graphics I/O, sound I/O
- **Memory Management**: Allocation, deallocation, memory map
- **System Information**: Get system status, device status
- **Program Management**: Load, execute, terminate programs

**Relevance to Hardware**:
- Exercises all hardware subsystems through unified interface
- Demonstrates OS-level programming concepts
- Makes hardware accessible to high-level programs
- Tests complete system integration

**Implementation**:
- System call interface (software interrupts or function calls)
- Service dispatcher
- Parameter passing conventions
- Error handling and return codes

---

### 5. Interrupt Handlers ✅ **RECOMMENDED**

**Why**: Essential for responsive I/O and system operation.

**Features**:
- **Timer Interrupts**: Periodic timer for system clock, delays
- **I/O Interrupts**: Keyboard input, serial data received
- **Video Interrupts**: Vertical blank, frame sync
- **Interrupt Management**: Enable/disable, priority handling

**Relevance to Hardware**:
- Exercises interrupt hardware (IRQ, NMI)
- Demonstrates real-time programming
- Essential for responsive I/O
- Tests CPU interrupt handling

**Implementation**:
- Interrupt vector table setup
- Interrupt service routines (ISRs)
- Interrupt enable/disable control
- Interrupt priority management

---

### 6. Memory Management ✅ **RECOMMENDED**

**Why**: Manages RAM allocation, essential for running multiple programs.

**Features**:
- **Heap Management**: Allocate/free memory blocks
- **Memory Map**: Track used/free memory regions
- **Bank Switching**: Manage 24-bit address space (if using banking)
- **Memory Protection**: Prevent overwriting critical areas (monitor, OS)

**Relevance to Hardware**:
- Exercises memory hardware
- Demonstrates memory organization
- Essential for multi-program support
- Tests addressing and banking

**Implementation**:
- Heap allocator (simple first-fit or best-fit)
- Memory map data structure
- Bank switching routines (if needed)
- Memory protection checks

---

### 7. File System (Basic) ✅ **OPTIONAL BUT USEFUL**

**Why**: Enables program storage and loading from SD card.

**Features**:
- **FAT16/FAT32 Support**: Read directory, read files (or simplified version)
- **File Operations**: Open, read, write, close
- **Directory Listing**: List files on SD card
- **File Metadata**: File size, date, attributes

**Relevance to Hardware**:
- Exercises SD card hardware
- Enables practical program development
- Demonstrates storage programming
- Tests I/O and data structures

**Implementation**:
- FAT16/FAT32 parser (or simplified sequential access)
- Directory reading
- File reading/writing
- Error handling

**Note**: Full FAT implementation is complex - consider simplified version or using existing library.

---

## Recommended Year 6 Programming Structure

### Term 1: Hardware Focus (Weeks 1-12)
- **No new programming** - Focus on PCB design, assembly, hardware integration
- **Use existing software** from Year 5 (monitor, assembler) for hardware testing

### Term 2: System Programming (Weeks 13-24)

**Weeks 13-16: Core System Software**
- **Week 13-14: Enhanced Monitor**
  - Extend Year 5 monitor with advanced features
  - Add SD card loading
  - Add breakpoints and disassembly
  - Add system information commands

- **Week 15-16: Boot Loader**
  - SD card interface and driver
  - Program loading from SD card
  - Program execution control
  - Verification and error handling

**Weeks 17-20: Device Drivers**
- **Week 17: Video Driver**
  - Initialize video chip
  - Set graphics modes
  - Write to video memory
  - Sprite/tile control

- **Week 18: Audio Driver**
  - Initialize sound chip
  - Play tones and music
  - Volume and channel control
  - Sound effects

- **Week 19: Input Drivers**
  - PS/2 keyboard driver
  - Gamepad support
  - Input buffering and processing

- **Week 20: SD Card Driver**
  - SPI interface
  - SD card initialization
  - Sector read/write
  - Error handling

**Weeks 21-24: System Services and Integration**
- **Week 21-22: System Services API**
  - System call interface
  - File system services
  - I/O services
  - Memory management services

- **Week 23: Interrupt Handlers**
  - Timer interrupts
  - I/O interrupts
  - Interrupt management

- **Week 24: Integration and Testing**
  - Integrate all components
  - System testing
  - Documentation
  - Final demonstration

---

## Programming vs. Compiler Development

### What to Teach in Year 6 (resistor2compiler)

**Focus**: **System-level programming** that directly exercises hardware

**Recommended Topics**:
1. ✅ **Enhanced Monitor** - Advanced debugging, program management
2. ✅ **Boot Loader** - SD card loading, program execution
3. ✅ **Device Drivers** - Video, audio, keyboard, SD card
4. ✅ **System Services** - API for applications
5. ✅ **Interrupt Handlers** - Real-time I/O handling
6. ✅ **Memory Management** - Heap, memory map, banking

**Why These Topics**:
- **Directly exercise hardware** - Each topic uses specific hardware components
- **Essential for system operation** - Without these, hardware is unusable
- **Demonstrates system programming** - Shows how OS-level code works
- **Supports application development** - Provides foundation for programs
- **Complements hardware work** - Software that makes hardware useful

### What NOT to Teach in Year 6 (resistor2compiler)

**Compiler Development**:
- ❌ **Full compiler from scratch** - Too complex, covered in SuperPascal project
- ❌ **Compiler internals** - Lexical analysis, parsing, code generation (covered in SuperPascal)
- ✅ **Compiler configuration** - OK, but minimal (just configure existing compiler)

**Rationale**: 
- Compiler development is a separate, parallel project (SuperPascal)
- Year 6 should focus on **system programming** that exercises hardware
- Compiler concepts can be referenced but not deeply implemented

---

## Learning Outcomes

By the end of Year 6 programming, students will:

1. **Enhanced Monitor**:
   - Extend basic monitor with advanced features
   - Load programs from SD card
   - Use breakpoints and disassembly for debugging
   - Display system information

2. **Boot Loader**:
   - Interface with SD card hardware
   - Load programs from storage
   - Initialize and execute programs
   - Handle errors and verification

3. **Device Drivers**:
   - Write drivers for video, audio, keyboard, storage
   - Interface directly with hardware registers
   - Provide high-level APIs for applications
   - Handle device initialization and errors

4. **System Services**:
   - Design system call interface
   - Implement file system operations
   - Provide I/O and memory services
   - Create unified API for applications

5. **Interrupt Handlers**:
   - Set up interrupt vectors
   - Write interrupt service routines
   - Manage interrupt priorities
   - Handle real-time events

6. **Memory Management**:
   - Implement heap allocator
   - Manage memory map
   - Handle bank switching (if needed)
   - Protect critical memory regions

---

## Assessment

### Practical Projects

1. **Enhanced Monitor**:
   - Extend Year 5 monitor with 3+ new features
   - Demonstrate SD card loading
   - Show breakpoint and disassembly working

2. **Boot Loader**:
   - Load program from SD card
   - Verify program integrity
   - Execute loaded program successfully

3. **Device Driver**:
   - Write driver for one device (video, audio, or keyboard)
   - Demonstrate driver initialization
   - Show driver being used by application

4. **System Integration**:
   - Integrate monitor, boot loader, and drivers
   - Demonstrate complete system working
   - Show program loading and execution

### Documentation

- Driver API documentation
- System services documentation
- Integration guide
- User manual for complete system

---

## Comparison with Current Year 6 Plan

### Current Plan (from Roadmap)
- Weeks 13-16: SuperPascal Compiler Implementation
- Weeks 17-20: Pascal Program Development & Demos
- Weeks 21-24: Operating System/Monitor Extensions

### Recommended Plan
- Weeks 13-16: Enhanced Monitor + Boot Loader
- Weeks 17-20: Device Drivers (Video, Audio, Input, Storage)
- Weeks 21-24: System Services + Interrupt Handlers + Integration

### Key Differences

**Current**: Focus on compiler and Pascal programs
**Recommended**: Focus on system programming that exercises hardware

**Rationale**:
- Compiler development is complex and better suited to SuperPascal project
- System programming directly exercises and validates hardware
- Device drivers are essential for using hardware
- Boot loader enables practical program development workflow

---

## Integration with SuperPascal Project

**SuperPascal Project** (parallel):
- Compiler development (lexical analysis, parsing, code generation)
- Language features and extensions
- Compiler optimization
- Advanced compiler topics

**resistor2compiler Year 6** (this curriculum):
- System programming (monitor, boot loader, drivers)
- Hardware interface programming
- OS-level services
- System integration

**Relationship**:
- SuperPascal compiler generates code that runs on resistor2compiler hardware
- resistor2compiler system software (monitor, boot loader, drivers) supports SuperPascal programs
- Both projects complement each other but serve different educational purposes

---

## Recommended Implementation

### Priority 1: Essential (Must Have)
1. ✅ **Enhanced Monitor** - Critical for debugging and program management
2. ✅ **Boot Loader** - Essential for loading programs from SD card
3. ✅ **SD Card Driver** - Required for boot loader and file system

### Priority 2: Important (Should Have)
4. ✅ **Video Driver** - Enables graphics programs
5. ✅ **Audio Driver** - Enables sound programs
6. ✅ **System Services API** - Makes hardware accessible

### Priority 3: Useful (Nice to Have)
7. ✅ **Interrupt Handlers** - Improves system responsiveness
8. ✅ **Memory Management** - Enables multi-program support
9. ✅ **Keyboard/Input Driver** - Enables interactive programs
10. ⚠️ **File System** - Useful but complex (consider simplified version)

---

## Conclusion

**Recommended Year 6 Programming Focus**:

1. **Enhanced Monitor** - Extend Year 5 monitor with advanced features
2. **Boot Loader** - Load programs from SD card
3. **Device Drivers** - Video, audio, keyboard, SD card
4. **System Services** - API for applications
5. **Interrupt Handlers** - Real-time I/O
6. **Memory Management** - Heap and memory map

**Why These Topics**:
- ✅ Directly exercise hardware components
- ✅ Essential for system operation
- ✅ Demonstrate system programming concepts
- ✅ Support application development
- ✅ Complement hardware work in Term 1
- ✅ Provide practical, hands-on programming experience

**Result**: Students learn system-level programming that makes their hardware useful and functional, while compiler development happens in parallel SuperPascal project.

---

**Document Created**: 2025-12-15  
**Purpose**: Recommend Year 6 programming content relevant to hardware project
