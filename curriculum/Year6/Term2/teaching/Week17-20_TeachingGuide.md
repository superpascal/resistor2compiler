# Week 17-20: Device Drivers - Teaching Guide

## Overview

This teaching guide supports the delivery of device driver development over 4 weeks. Students write drivers for video, audio, input, and storage devices, learning to interface directly with hardware and provide high-level APIs.

## Learning Objectives

- Write device drivers for video hardware
- Write device drivers for audio hardware
- Write device drivers for input devices
- Write device drivers for storage
- Provide high-level APIs for applications
- Handle device initialization and errors

## Prerequisites

- ✅ Completed Weeks 13-16 (Enhanced Monitor + Boot Loader)
- ✅ Working 65C816 system on PCB
- ✅ Video hardware integrated
- ✅ Audio hardware integrated
- ✅ Input hardware available
- ✅ SD card interface available

## Week 17: Video Driver

### Day 1: Video Hardware and Initialization

**Objectives**:
- Understand video hardware
- Initialize video chip
- Set graphics mode

**Activities**:
1. **Video Hardware Review** (30 min):
   - Review video chip options
   - Understand video chip features
   - Review datasheet

2. **Video Initialization** (90 min):
   - Implement video chip reset
   - Configure video registers
   - Set graphics mode
   - Test initialization

3. **Mode Testing** (60 min):
   - Test different graphics modes
   - Verify mode changes
   - Test mode switching

**Assessment**:
- Students initialize video chip
- Students set graphics mode
- Students verify mode works

### Day 2: Basic Graphics Primitives

**Objectives**:
- Implement pixel operations
- Draw basic shapes
- Clear screen

**Activities**:
1. **Pixel Operations** (60 min):
   - Implement SetPixel function
   - Implement GetPixel function
   - Test pixel operations
   - Verify pixel drawing

2. **Screen Clearing** (30 min):
   - Implement ClearScreen function
   - Test screen clearing
   - Optimize clearing

3. **Basic Shapes** (90 min):
   - Implement line drawing (Bresenham)
   - Implement rectangle drawing
   - Test shape drawing
   - Verify shapes display correctly

**Assessment**:
- Students draw pixels
- Students draw lines and rectangles
- Students clear screen

### Day 3: Advanced Graphics

**Objectives**:
- Implement sprite operations
- Add text output
- Create graphics library

**Activities**:
1. **Sprite Operations** (90 min):
   - Implement sprite creation
   - Implement sprite movement
   - Implement sprite show/hide
   - Test sprite operations

2. **Text Output** (60 min):
   - Implement character rendering
   - Implement string drawing
   - Test text output
   - Verify text displays correctly

3. **Graphics Library** (30 min):
   - Organize graphics functions
   - Create graphics API
   - Document API

**Assessment**:
- Students create and move sprites
- Students display text
- Students use graphics library

### Day 4: Video Driver Integration

**Objectives**:
- Integrate video driver with system
- Test video driver
- Create demo program

**Activities**:
1. **System Integration** (60 min):
   - Integrate video driver
   - Add video initialization to boot
   - Test integration

2. **Driver Testing** (60 min):
   - Test all video functions
   - Test error handling
   - Fix any issues

3. **Demo Program** (60 min):
   - Create graphics demo
   - Display demo on screen
   - Present demo

**Assessment**:
- Students integrate video driver
- Students test video driver
- Students demonstrate video driver

---

## Week 18: Audio Driver

### Day 1: Audio Hardware and Initialization

**Objectives**:
- Understand audio hardware
- Initialize audio chip
- Test audio output

**Activities**:
1. **Audio Hardware Review** (30 min):
   - Review audio chip options
   - Understand audio chip features
   - Review datasheet

2. **Audio Initialization** (90 min):
   - Implement audio chip reset
   - Configure audio registers
   - Set initial volumes
   - Test initialization

3. **Basic Tone** (60 min):
   - Generate simple tone
   - Test audio output
   - Verify tone plays

**Assessment**:
- Students initialize audio chip
- Students generate tone
- Students verify audio works

### Day 2: Tone Generation

**Objectives**:
- Implement frequency calculation
- Generate tones at different frequencies
- Control volume

**Activities**:
1. **Frequency Calculation** (60 min):
   - Implement frequency to period conversion
   - Test frequency calculations
   - Verify calculations

2. **Tone Generation** (90 min):
   - Implement tone playing function
   - Test different frequencies
   - Test volume control
   - Verify tones play correctly

3. **Channel Control** (30 min):
   - Control multiple channels
   - Test channel independence
   - Verify channels work

**Assessment**:
- Students generate tones
- Students control volume
- Students use multiple channels

### Day 3: Music Playback

**Objectives**:
- Design music data format
- Implement music sequencer
- Play music sequences

**Activities**:
1. **Music Format** (60 min):
   - Design music data format
   - Create music data structure
   - Test format

2. **Music Sequencer** (90 min):
   - Implement music playback engine
   - Handle note durations
   - Control tempo
   - Test sequencer

3. **Music Playback** (30 min):
   - Play music sequence
   - Test music playback
   - Verify music plays correctly

**Assessment**:
- Students design music format
- Students implement sequencer
- Students play music

### Day 4: Sound Effects

**Objectives**:
- Create sound effects
- Implement sound effect system
- Test sound effects

**Activities**:
1. **Sound Effect Design** (60 min):
   - Design sound effects
   - Create sound effect data
   - Test sound effects

2. **Sound Effect System** (90 min):
   - Implement sound effect playback
   - Handle sound effect timing
   - Test sound effects
   - Verify sound effects work

3. **Audio Driver Integration** (30 min):
   - Integrate audio driver
   - Test integration
   - Create audio demo

**Assessment**:
- Students create sound effects
- Students implement sound system
- Students demonstrate audio driver

---

## Week 19: Input Drivers

**Reference**: See `../../../resources/PS2_KEYBOARD_INTERFACE_GUIDE.md` for comprehensive PS/2 keyboard guide

### Day 1: PS/2 Keyboard Driver

**Objectives**:
- Understand PS/2 protocol fundamentals
- Connect PS/2 keyboard hardware
- Set up interrupts for keyboard
- Initialize keyboard
- Receive scan codes

**Activities**:
1. **PS/2 Protocol Theory** (30 min):
   - Review PS/2 protocol fundamentals
   - Understand physical interface (6-pin mini-DIN)
   - Study protocol timing (clock, data, 11-bit frames)
   - Review scan code sets (Set 2 recommended)
   - Plan implementation approach
   - **Reference**: PS/2 keyboard guide

2. **Hardware Connection** (30 min):
   - Connect PS/2 keyboard to system
   - Connect clock line to interrupt input (IRQ)
   - Connect data line to I/O port
   - Add pull-up resistors (10kΩ) to clock and data
   - Verify connections with multimeter
   - Test power supply to keyboard

3. **Interrupt Setup** (30 min):
   - Configure interrupt for PS/2 clock falling edge
   - Set up interrupt vector
   - Write interrupt handler stub
   - Test interrupt triggering
   - Verify interrupt fires on clock edge
   - Debug interrupt issues

4. **Keyboard Initialization** (60 min):
   - Implement keyboard reset command (0xFF)
   - Wait for ACK (0xFA) and reset complete (0xAA)
   - Set scan code set 2 (0xF0 0x02)
   - Enable keyboard scanning (0xF4)
   - Test initialization sequence
   - Verify keyboard responds correctly
   - Handle initialization errors

5. **Scan Code Reception** (90 min):
   - Implement interrupt handler for data reception
   - Read data bit on clock falling edge
   - Shift bits into 11-bit frame register
   - Detect frame complete (11 bits received)
   - Validate frame (start bit, parity, stop bit)
   - Extract 8-bit data byte
   - Test scan code reception
   - Verify scan codes received correctly
   - Debug reception issues

**Assessment**:
- Students successfully connect PS/2 keyboard hardware
- Students configure interrupts correctly
- Students initialize keyboard and receive ACK
- Students receive scan codes via interrupt
- Students verify keyboard works end-to-end

**Common Questions**:
- Q: How to connect keyboard? A: Clock to IRQ, data to I/O port, add pull-ups
- Q: Why interrupts? A: Keyboard generates clock, interrupt on falling edge
- Q: What scan code set? A: Set 2 (most common, default)
- Q: How to test? A: Press keys, verify scan codes received

### Day 2: Key Processing and Driver API

**Objectives**:
- Translate scan codes to key codes/ASCII
- Handle make/break codes and extended keys
- Track key states
- Implement circular key buffer
- Create driver API

**Activities**:
1. **Scan Code Translation** (60 min):
   - Create scan code lookup table (Set 2)
   - Implement scan code to key code translation
   - Handle make codes (key pressed)
   - Handle break codes (0xF0 prefix, key released)
   - Handle extended keys (0xE0 prefix)
   - Test translation with various keys
   - Verify correct key codes

2. **Key State Tracking** (60 min):
   - Track key press/release states
   - Implement key state table (256 keys)
   - Update state on make/break codes
   - Test key state tracking
   - Verify state changes correctly
   - Handle modifier keys (Shift, Ctrl, Alt)

3. **Key Buffer Implementation** (60 min):
   - Design circular key buffer (32 keys)
   - Implement buffer add operation (from interrupt)
   - Implement buffer get operation (from application)
   - Handle buffer overflow
   - Test buffer operations
   - Verify buffer works correctly

4. **Driver API** (60 min):
   - Design high-level API
   - Implement GetKey() function (blocking)
   - Implement KeyAvailable() function (non-blocking)
   - Implement GetKeyState() function (check specific key)
   - Implement FlushBuffer() function
   - Test API functions
   - Create test program using API

**Assessment**:
- Students translate scan codes to key codes correctly
- Students handle make/break codes properly
- Students track key states accurately
- Students implement and use key buffer
- Students create working keyboard driver API
- Students demonstrate keyboard input in test program

**Common Questions**:
- Q: How to translate scan codes? A: Use lookup table, handle prefixes
- Q: What about break codes? A: 0xF0 prefix indicates key release
- Q: Buffer size? A: 32 keys typical, adjust as needed
- Q: How to test? A: Press keys, verify correct translation and buffering

### Day 3: Gamepad Driver

**Objectives**:
- Interface with gamepad
- Read gamepad state
- Process gamepad input

**Activities**:
1. **Gamepad Interface** (60 min):
   - Understand gamepad interface
   - Implement interface setup
   - Test interface

2. **Gamepad Reading** (90 min):
   - Implement gamepad state reading
   - Read button states
   - Read direction states
   - Test gamepad reading

3. **Input Processing** (30 min):
   - Process gamepad input
   - Generate input events
   - Test input processing

**Assessment**:
- Students interface with gamepad
- Students read gamepad state
- Students process gamepad input

### Day 4: Input API

**Objectives**:
- Create input API
- Integrate input drivers
- Test input system

**Activities**:
1. **Input API Design** (60 min):
   - Design input API
   - Plan API functions
   - Document API

2. **Input API Implementation** (90 min):
   - Implement input API
   - Integrate keyboard and gamepad
   - Test API
   - Verify API works

3. **Input System Integration** (30 min):
   - Integrate input system
   - Test integration
   - Create input demo

**Assessment**:
- Students create input API
- Students integrate input drivers
- Students demonstrate input system

---

## Week 20: Storage Driver (RP2350 Co-Processor)

**Reference**: See `../../../resources/SD_CARD_STORAGE_ANALYSIS.md` for comprehensive storage options analysis.

### Day 1: RP2350 Storage Co-Processor Setup

**Objectives**:
- Understand RP2350 storage co-processor architecture
- Set up RP2350 hardware connection
- Implement communication protocol

**Activities**:
1. **RP2350 Architecture Review** (30 min):
   - Review co-processor architecture (similar to video co-processor)
   - Understand RP2350 responsibilities (SD card, FatFS)
   - Review command protocol design
   - **Reference**: `SD_CARD_STORAGE_ANALYSIS.md`

2. **Hardware Setup** (60 min):
   - Connect RP2350 to 65C816 (SPI/UART/I2C)
   - Connect SD card breakout to RP2350
   - Verify RP2350 firmware (storage firmware)
   - Test hardware connections

3. **Communication Protocol** (90 min):
   - Design command protocol (OPEN, READ, WRITE, CLOSE, LIST)
   - Implement SendCommand function
   - Implement ReceiveResponse function
   - Test communication protocol
   - Verify command/response format

**Assessment**:
- Students successfully connect RP2350 storage co-processor
- Students implement communication protocol
- Students test communication with RP2350

### Day 2: Storage Initialization and File Operations

**Objectives**:
- Initialize storage system
- Implement file operations (open, read, write, close)
- Test file operations

**Activities**:
1. **Storage Initialization** (60 min):
   - Implement StorageInit function
   - Send mount command to RP2350
   - Verify SD card is mounted
   - Check file system (FAT32)
   - Verify partitions (system + user)

2. **File Operations** (120 min):
   - Implement FileOpen function (send OPEN command)
   - Implement FileRead function (send READ command)
   - Implement FileWrite function (send WRITE command)
   - Implement FileClose function (send CLOSE command)
   - Test file operations (open, read, write, close)

**Assessment**:
- Students initialize storage system
- Students implement file operations
- Students test file operations successfully

### Day 3: Directory Operations and API

**Objectives**:
- Implement directory operations
- Create storage driver API
- Test complete API

**Activities**:
1. **Directory Operations** (90 min):
   - Implement DirList function (send LIST command)
   - Implement DirCreate function (send MKDIR command)
   - Implement FileDelete function (send DELETE command)
   - Test directory operations
   - Create test files and directories

2. **Storage Driver API** (90 min):
   - Organize file system functions
   - Create storage driver API
   - Document API functions
   - Test complete API
   - Create file system demo program

**Assessment**:
- Students implement directory operations
- Students create storage driver API
- Students demonstrate file system operations

### Day 4: Storage Driver Integration and Testing

**Objectives**:
- Integrate storage driver
- Test complete driver
- Create file system demo

**Activities**:
1. **Driver Integration** (60 min):
   - Integrate storage driver with system
   - Test integration
   - Fix any issues

2. **Driver Testing** (60 min):
   - Test all driver functions
   - Test error handling
   - Verify driver works correctly
   - Test with different file sizes

3. **File System Demo** (60 min):
   - Create file system demo
   - Demonstrate file operations
   - Demonstrate directory operations
   - Present demo

**Assessment**:
- Students integrate storage driver
- Students test driver thoroughly
- Students demonstrate complete file system

---

## Teaching Tips

### Common Challenges

1. **Video Initialization**:
   - Problem: Video doesn't initialize
   - Solution: Check register values, verify timing, check hardware connections
   - Tip: Use oscilloscope to verify signals

2. **Audio Timing**:
   - Problem: Audio timing issues
   - Solution: Check clock frequency, verify register timing
   - Tip: Use timer interrupts for music playback

3. **PS/2 Protocol**:
   - Problem: Scan codes not received
   - Solution: Check timing, verify signal levels, check interrupt setup
   - Tip: Use logic analyzer to debug protocol

4. **RP2350 Storage Co-Processor**:
   - Problem: RP2350 not responding
   - Solution: Check connections, verify firmware, test communication protocol
   - Problem: SD card not mounting
   - Solution: Check SD card format (FAT32), verify connections, check power
   - Problem: File operations failing
   - Solution: Verify command format, check file permissions, verify file system
   - Tip: Use serial terminal to debug RP2350 communication

### Assessment Strategies

1. **Practical Demonstrations**:
   - Students demonstrate drivers working
   - Students show driver features
   - Students test error handling

2. **Code Reviews**:
   - Review student driver code
   - Check for best practices
   - Provide feedback

3. **Integration Testing**:
   - Test drivers with system
   - Test driver interactions
   - Verify system stability

---

## Resources

- `VIDEO_AUDIO_HARDWARE_REFERENCE.md` - Video and audio chip documentation
- `../../../resources/PS2_KEYBOARD_INTERFACE_GUIDE.md` - Comprehensive PS/2 keyboard guide
- `../../../resources/KEYBOARD_INPUT_INTERFACE_ANALYSIS.md` - Input device analysis
- PS/2 Protocol Specification (scan code set 2 reference)
- Device datasheets (TMS9918, YM2149F, etc.)
- PS/2 Keyboard Protocol Specification
- SD Card Physical Layer Specification
- 65C816 System Memory Map

---

## Next Steps

After completing device drivers, students move to system services and integration (Weeks 21-24), which will use all drivers to create a complete system software stack.

---

*Device drivers provide essential interfaces between applications and hardware*
