# Year 6: Bringing It All Together - The 65C816 Console and System Programming (Age 18)

## Overview

Year 6 is the capstone year. Students fabricate PCBs, complete the hardware, and develop system-level software that directly exercises and supports the hardware. The focus is on **system programming** (monitor, boot loader, device drivers, system services) rather than compiler development, which runs in parallel as the SuperPascal project.

## Learning Outcomes

By the end of Year 6, students will:
- Design and fabricate PCBs
- Assemble final 16-bit computer/console
- Integrate video and audio hardware
- Develop enhanced monitor program with advanced debugging
- Implement boot loader for SD card program loading
- Write device drivers (video, audio, keyboard, storage)
- Create system services API
- Implement interrupt handlers
- Integrate complete software stack
- Document complete system

## Year Structure

- **Term 1**: PCB Design and Final Hardware (Weeks 1-12)
- **Term 2**: System Programming and Integration (Weeks 13-24)

## Key Topics

### Term 1: Final Hardware
- PCB schematic design
- PCB layout
- **PCB fabrication** (Professional manufacturing - see `PCB_FABRICATION_APPROACHES.md`)
  - Option 1: Professional manufacturer (PCBWay/JLCPCB) - **A-Level approach**
  - Option 2: DIY methods taught in formative years (Years 2-4)
- Assembly and testing
- System integration

### Term 2: System Programming
- **Weeks 13-16**: Enhanced Monitor + Boot Loader
  - Extend Year 5 monitor with advanced features
  - SD card loading capability
  - Breakpoints and disassembly
  - Boot loader for program loading
  
- **Weeks 17-20**: Device Drivers
  - Video driver (initialize chip, graphics modes, sprites)
  - Audio driver (initialize chip, play tones/music)
  - Input drivers (keyboard, gamepad)
  - Storage driver (RP2350 co-processor or VIA-based SPI SD card interface)
  
- **Weeks 21-24**: System Services + Integration
  - System services API
  - Interrupt handlers
  - Memory management
  - Complete system integration

## Prerequisites

- Completed Year 5
- Working 16-bit prototype
- Assembly programming experience
- Compiler concepts (introduced)

## Assessment

### Term 1: Hardware
- PCB design review
- Assembly and unit testing
- System integration testing
- Hardware demonstration

### Term 2: System Programming
- Enhanced monitor with 3+ new features
- Boot loader demonstration
- Device driver implementation
- System services API
- Complete system integration
- System documentation

## Programming Focus

**Year 6 focuses on system-level programming** that directly exercises hardware:
- ✅ **Enhanced Monitor** - Advanced debugging and program management
- ✅ **Boot Loader** - SD card program loading
- ✅ **Device Drivers** - Direct hardware interface programming
- ✅ **System Services** - OS-level API for applications
- ✅ **Interrupt Handlers** - Real-time I/O handling
- ✅ **Memory Management** - Heap and memory map

**Note**: Compiler development (SuperPascal) runs in parallel as a separate project. Year 6 focuses on system software that makes the hardware functional and usable.

## Resources

- `YEAR6_PROGRAMMING_RECOMMENDATIONS.md` - Detailed programming recommendations
- `VIDEO_AUDIO_HARDWARE_REFERENCE.md` - Video and audio chip documentation
- `PCB_FABRICATION_APPROACHES.md` - PCB fabrication methods (professional and DIY)
- `../PCB_FABRICATION_INTEGRATION_PLAN.md` - Plan for integrating DIY PCB methods into formative years
- `../resources/PS2_KEYBOARD_INTERFACE_GUIDE.md` - Comprehensive PS/2 keyboard interface guide
- `../resources/KEYBOARD_INPUT_INTERFACE_ANALYSIS.md` - Input device progression analysis
- `../resources/SD_CARD_STORAGE_ANALYSIS.md` - SD card storage options analysis (RP2350 co-processor and VIA-based SPI)

---

*Year 6 culminates in a complete, working 16-bit computer system with full software stack - an incredible achievement!*
