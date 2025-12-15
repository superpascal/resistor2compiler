# Lab 17-20: Device Drivers

## Lab Overview

In this lab, students will write device drivers for video, audio, input, and storage devices. Students learn to interface directly with hardware peripherals and provide high-level APIs for applications.

## Learning Objectives

- Write device drivers for video hardware
- Write device drivers for audio hardware
- Write device drivers for input devices (keyboard, gamepad)
- Write device drivers for storage (SD card)
- Provide high-level APIs for applications
- Handle device initialization and errors

## Prerequisites

- ✅ Completed Weeks 13-16 (Enhanced Monitor + Boot Loader)
- ✅ Working 65C816 system on PCB
- ✅ Video hardware integrated (TMS9918/V9938/V9958 or microcontroller solution)
- ✅ Audio hardware integrated (YM2149F or SAM2695)
- ✅ Input hardware available (PS/2 keyboard, gamepad)
- ✅ SD card interface available
- ✅ Understanding of I/O addressing and interrupts
- ✅ Enhanced monitor working for debugging

## Materials

### Components
- Complete 65C816 system on PCB
- Video chip (TMS9918/V9938/V9958 or microcontroller solution)
- Audio chip (YM2149F PSG or SAM2695)
- PS/2 keyboard or gamepad
- **Storage System** (RP2350 Co-Processor Approach):
  - **RP2350 Board**: LILYGO T-PICO-2350 (with built-in SD slot) or Raspberry Pi Pico 2 (RP2350) + SD card breakout
  - **SD Card Breakout**: [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682) (if using Pico 2)
  - **MicroSD Card**: FAT32 formatted, 32GB recommended
  - **Interface**: SPI/UART/I2C connection to 65C816
- Display (monitor, TV, or LCD)
- Speaker or headphones
- Development PC with serial terminal

### Tools
- Text editor
- Assembler (ca65 or similar)
- Serial terminal software
- Linker (ld65 or similar)
- Oscilloscope (for timing verification)
- Logic analyzer (for protocol debugging)
- Video/Audio hardware datasheets

## Safety

- Verify voltage levels for all devices
- Use proper grounding
- Check power requirements
- Test connections before powering on
- Handle chips with ESD protection

## Lab Sessions

### Session 1: Video Driver - Initialization and Basic Graphics (Week 17, Day 1-2)

**Objective**: Initialize video chip and implement basic graphics primitives

**Steps**:
1. **Video Hardware Review** (30 min):
   - Review video chip datasheet
   - Understand register map
   - Plan initialization sequence

2. **Video Initialization** (90 min):
   - Implement video chip reset
   - Configure video registers
   - Set graphics mode
   - Configure color palette
   - Clear video memory
   - Test initialization

3. **Basic Graphics Primitives** (90 min):
   - Implement SetPixel function
   - Implement GetPixel function
   - Implement ClearScreen function
   - Test pixel operations
   - Draw test pattern

**Deliverables**:
- Video initialization code
- Basic graphics primitive code
- Test program demonstrating graphics

**Assessment**:
- Students initialize video chip
- Students set graphics mode
- Students draw pixels and clear screen
- Students verify graphics display

---

### Session 2: Video Driver - Advanced Graphics (Week 17, Day 3-4)

**Objective**: Implement advanced graphics primitives and sprite operations

**Steps**:
1. **Line Drawing** (90 min):
   - Implement Bresenham line algorithm
   - Draw lines between points
   - Test line drawing
   - Optimize if needed

2. **Rectangle Drawing** (60 min):
   - Implement rectangle drawing
   - Draw filled rectangles
   - Draw outlined rectangles
   - Test rectangle drawing

3. **Sprite Operations** (90 min):
   - Implement sprite creation
   - Implement sprite movement
   - Implement sprite show/hide
   - Test sprite operations
   - Create sprite demo

**Deliverables**:
- Line drawing code
- Rectangle drawing code
- Sprite operation code
- Graphics demo program

**Assessment**:
- Students draw lines and rectangles
- Students create and move sprites
- Students demonstrate graphics capabilities

---

### Session 3: Video Driver - Text Output and Integration (Week 18, Day 1-2)

**Objective**: Implement text output and integrate video driver

**Steps**:
1. **Character Rendering** (90 min):
   - Design character set
   - Create font data
   - Implement character drawing
   - Implement string drawing
   - Test text output

2. **Graphics Library** (60 min):
   - Organize graphics functions
   - Create graphics API
   - Document API
   - Test API

3. **System Integration** (60 min):
   - Integrate video driver with system
   - Add video initialization to boot
   - Test integration
   - Create demo program

**Deliverables**:
- Text output code
- Graphics library code
- Integrated video driver
- Demo program

**Assessment**:
- Students display text
- Students use graphics library
- Students integrate video driver
- Students demonstrate video driver

---

### Session 4: Audio Driver - Initialization and Tone Generation (Week 18, Day 3-4)

**Objective**: Initialize audio chip and implement tone generation

**Steps**:
1. **Audio Hardware Review** (30 min):
   - Review audio chip datasheet
   - Understand register map
   - Plan initialization sequence

2. **Audio Initialization** (90 min):
   - Implement audio chip reset
   - Configure audio registers
   - Set initial volumes
   - Test initialization

3. **Tone Generation** (90 min):
   - Implement frequency to period conversion
   - Implement tone playing function
   - Test different frequencies
   - Test volume control
   - Test multiple channels

**Deliverables**:
- Audio initialization code
- Tone generation code
- Test program demonstrating tones

**Assessment**:
- Students initialize audio chip
- Students generate tones
- Students control volume
- Students use multiple channels

---

### Session 5: Audio Driver - Music and Sound Effects (Week 19, Day 1-2)

**Objective**: Implement music playback and sound effects

**Steps**:
1. **Music Format Design** (60 min):
   - Design music data format
   - Create music data structure
   - Test format

2. **Music Sequencer** (90 min):
   - Implement music playback engine
   - Handle note durations
   - Control tempo
   - Test sequencer
   - Play music sequence

3. **Sound Effects** (90 min):
   - Design sound effects
   - Create sound effect data
   - Implement sound effect playback
   - Test sound effects
   - Create sound demo

**Deliverables**:
- Music sequencer code
- Sound effect code
- Music and sound demo

**Assessment**:
- Students design music format
- Students implement sequencer
- Students play music
- Students create sound effects

---

### Session 6: Input Drivers - PS/2 Keyboard (Week 19, Day 3-4)

**Objective**: Implement PS/2 keyboard driver

**Reference**: See `../../../resources/PS2_KEYBOARD_INTERFACE_GUIDE.md` for comprehensive PS/2 keyboard guide

**Steps**:
1. **PS/2 Protocol Understanding** (30 min):
   - Review PS/2 protocol fundamentals
   - Understand physical interface (6-pin mini-DIN)
   - Study protocol timing (clock, data, frames)
   - Review scan code sets (Set 2 recommended)
   - Plan implementation approach

2. **Hardware Connection** (30 min):
   - Connect PS/2 keyboard to system
   - Connect clock line to interrupt input (IRQ)
   - Connect data line to I/O port
   - Add pull-up resistors (10kΩ) to clock and data
   - Verify connections with multimeter

3. **Interrupt Setup** (30 min):
   - Configure interrupt for PS/2 clock falling edge
   - Set up interrupt vector
   - Write interrupt handler stub
   - Test interrupt triggering
   - Verify interrupt fires on clock edge

4. **Keyboard Initialization** (60 min):
   - Implement keyboard reset command (0xFF)
   - Wait for ACK (0xFA) and reset complete (0xAA)
   - Set scan code set 2 (0xF0 0x02)
   - Enable keyboard scanning (0xF4)
   - Test initialization sequence
   - Verify keyboard responds correctly

5. **Scan Code Reception** (90 min):
   - Implement interrupt handler for data reception
   - Read data bit on clock falling edge
   - Shift bits into 11-bit frame register
   - Detect frame complete (11 bits received)
   - Validate frame (start bit, parity, stop bit)
   - Extract 8-bit data byte
   - Test scan code reception
   - Verify scan codes received correctly

6. **Key Processing** (90 min):
   - Implement scan code to key code translation
   - Create scan code lookup table (Set 2)
   - Handle make codes (key pressed)
   - Handle break codes (0xF0 prefix, key released)
   - Handle extended keys (0xE0 prefix)
   - Track key states (pressed/released)
   - Implement circular key buffer (32 keys)
   - Test key processing
   - Verify correct key translation

7. **Driver API Implementation** (60 min):
   - Implement GetKey() function (blocking)
   - Implement KeyAvailable() function (non-blocking)
   - Implement GetKeyState() function (check specific key)
   - Implement FlushBuffer() function
   - Test API functions
   - Create test program using API

**Deliverables**:
- PS/2 hardware interface (connected and tested)
- Keyboard initialization code
- Interrupt handler code
- Scan code reception code
- Scan code translation code
- Key buffer implementation
- Driver API code
- Test program demonstrating keyboard input

**Assessment**:
- Students successfully connect PS/2 keyboard hardware
- Students initialize keyboard and receive ACK
- Students receive scan codes via interrupt
- Students translate scan codes to key codes correctly
- Students implement and use key buffer
- Students create working keyboard driver API
- Students demonstrate keyboard input in test program

**Troubleshooting**:
- **No scan codes**: Check connections, verify interrupt, check pull-up resistors
- **Wrong scan codes**: Verify scan code set (should be Set 2), check translation table
- **Missing keys**: Check for extended keys (E0 prefix), verify break code handling
- **Buffer overflow**: Increase buffer size or handle overflow gracefully
- **Keyboard not responding**: Check power, verify initialization sequence, test with known-good keyboard

**Reference Materials**:
- `../../../resources/PS2_KEYBOARD_INTERFACE_GUIDE.md` - Comprehensive guide
- `../../../resources/KEYBOARD_INPUT_INTERFACE_ANALYSIS.md` - Input device analysis
- PS/2 Protocol Specification (scan code set 2 reference)

---

### Session 7: Input Drivers - Gamepad and Input API (Week 20, Day 1-2)

**Objective**: Implement gamepad driver and create unified input API

**Steps**:
1. **Gamepad Interface** (60 min):
   - Understand gamepad interface
   - Implement interface setup
   - Test interface

2. **Gamepad Reading** (90 min):
   - Implement gamepad state reading
   - Read button states
   - Read direction states
   - Test gamepad reading

3. **Input Processing** (60 min):
   - Process gamepad input
   - Generate input events
   - Test input processing

4. **Input API** (90 min):
   - Design input API
   - Implement input API
   - Integrate keyboard and gamepad
   - Test API
   - Create input demo

**Deliverables**:
- Gamepad driver code
- Input API code
- Integrated input system
- Input demo

**Assessment**:
- Students interface with gamepad
- Students read gamepad state
- Students create input API
- Students demonstrate input system

---

### Session 8: Storage Driver - RP2350 Co-Processor (Week 20, Day 3-4)

**Objective**: Implement storage driver using RP2350 co-processor with file system interface

**Reference**: See `../../../resources/SD_CARD_STORAGE_ANALYSIS.md` for comprehensive storage options analysis.

**Steps**:
1. **RP2350 Storage Co-Processor Setup** (60 min):
   - Review RP2350 storage co-processor architecture
   - Connect RP2350 to 65C816 (SPI/UART/I2C)
   - Connect SD card breakout to RP2350
   - Verify RP2350 firmware is loaded (storage firmware)
   - Test RP2350 communication

2. **Communication Protocol Implementation** (90 min):
   - Design command protocol (OPEN, READ, WRITE, CLOSE, LIST, etc.)
   - Implement SendCommand function (65C816 → RP2350)
   - Implement ReceiveResponse function (RP2350 → 65C816)
   - Test communication protocol
   - Verify command/response format

3. **Storage Initialization** (60 min):
   - Implement StorageInit function
   - Send mount command to RP2350
   - Verify SD card is mounted
   - Check file system (FAT32)
   - Verify partitions (system + user)
   - Test initialization

4. **File Operations Implementation** (90 min):
   - Implement FileOpen function (send OPEN command)
   - Implement FileRead function (send READ command)
   - Implement FileWrite function (send WRITE command)
   - Implement FileClose function (send CLOSE command)
   - Implement FileSeek function (send SEEK command)
   - Test file operations (open, read, write, close)

5. **Directory Operations** (60 min):
   - Implement DirList function (send LIST command)
   - Implement DirCreate function (send MKDIR command)
   - Implement FileDelete function (send DELETE command)
   - Test directory operations
   - Create test files and directories

6. **Storage Driver API** (60 min):
   - Organize file system functions
   - Create storage driver API
   - Document API functions
   - Test complete API
   - Create file system demo program

**Deliverables**:
- RP2350 communication code
- Storage initialization code
- File operations code (open, read, write, close, seek)
- Directory operations code (list, create, delete)
- Storage driver API
- File system demo program

**Assessment**:
- Students successfully connect RP2350 storage co-processor
- Students implement communication protocol
- Students initialize storage system
- Students implement file operations
- Students implement directory operations
- Students create working storage driver API
- Students demonstrate file system operations

**Troubleshooting**:
- **RP2350 not responding**: Check connections, verify firmware, test communication
- **SD card not mounting**: Check SD card format (FAT32), verify connections, check power
- **File operations failing**: Verify command format, check file permissions, verify file system
- **Communication errors**: Check protocol implementation, verify timing, test with known-good commands

**Reference Materials**:
- `../../../resources/SD_CARD_STORAGE_ANALYSIS.md` - Comprehensive storage analysis
- RP2350 documentation (LILYGO T-PICO-2350 or Raspberry Pi Pico 2)
- FatFS documentation (ChaN's FatFS)
- [STM32 SD Card Tutorial](https://01001000.xyz/2020-08-09-Tutorial-STM32CubeIDE-SD-card/) - FatFS integration reference

**Optional Advanced Project**: VIA-Based SPI SD Card Interface
- For students who want deep SPI understanding
- See `SD_CARD_STORAGE_ANALYSIS.md` for VIA-based approach details
- Available as optional Term 3 advanced project

---

## Lab Assessment

### Formative Assessment

- Weekly progress checks
- Code reviews
- Driver demonstrations
- Instructor feedback

### Summative Assessment

**Video Driver** (25%):
- Video initialization (5%)
- Graphics primitives (10%)
- Sprite operations (5%)
- Text output (5%)

**Audio Driver** (25%):
- Audio initialization (5%)
- Tone generation (10%)
- Music playback (5%)
- Sound effects (5%)

**Input Drivers** (25%):
- Keyboard driver (10%)
- Gamepad driver (10%)
- Input API (5%)

**Storage Driver** (25%):
- RP2350 co-processor setup (5%)
- Communication protocol (5%)
- Storage initialization (5%)
- File operations (open, read, write, close) (5%)
- Directory operations (list, create, delete) (5%)

### Assessment Criteria

**Excellent (A)**:
- All drivers implemented correctly
- Clean, well-documented code
- Comprehensive testing
- Complete API documentation

**Good (B)**:
- Most drivers implemented
- Code mostly correct
- Adequate testing
- Good documentation

**Satisfactory (C)**:
- Basic drivers implemented
- Code has some issues
- Basic testing
- Basic documentation

---

## Troubleshooting

### Common Issues

1. **Video Not Displaying**:
   - Check video chip connections
   - Verify register values
   - Check timing
   - Verify video mode
   - Use oscilloscope to check signals

2. **Audio Not Playing**:
   - Check audio chip connections
   - Verify frequency calculations
   - Check volume settings
   - Verify channel enable
   - Test with oscilloscope

3. **Keyboard Not Working**:
   - Check PS/2 connections
   - Verify protocol timing
   - Check interrupt setup
   - Use logic analyzer to debug protocol

4. **SD Card Errors**:
   - Check SPI connections
   - Verify SPI timing
   - Check initialization sequence
   - Try different SD card
   - Use logic analyzer to debug

---

## Resources

- `VIDEO_AUDIO_HARDWARE_REFERENCE.md` - Video and audio chip documentation
- Device datasheets (TMS9918, YM2149F, etc.)
- PS/2 Keyboard Protocol Specification
- SD Card Physical Layer Specification
- 65C816 System Memory Map

---

## Next Steps

After completing device drivers, students move to system services and integration (Lab 21-24), which will use all drivers to create a complete system software stack.

---

*Device drivers provide essential interfaces between applications and hardware*
