# Week 17-20: Device Drivers - Theory

## Overview

This 4-week block covers device driver development for video, audio, input, and storage devices. Students learn to interface directly with hardware peripherals and provide high-level APIs for applications.

## Learning Objectives

By the end of this block, students will:
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

## Week 17: Video Driver

### 1. Video Hardware Overview

**Video Options** (see `VIDEO_AUDIO_HARDWARE_REFERENCE.md`):
- **TMS9918/V9938/V9958 VDP**: Tile/sprite graphics, text modes
- **Microcontroller**: Software-based video generation

**Note**: VERA FPGA is not used in this curriculum as it is a black box (FPGA-based) that limits educational value, despite being an excellent solution used in other projects.

**Common Features**:
- Video memory (VRAM)
- Register-based control
- Multiple graphics modes
- Sprite/tile support
- Color palettes

### 2. Video Driver Architecture

#### Low-Level Interface
- **Register Access**: Read/write video chip registers
- **Memory Access**: Read/write video memory (VRAM)
- **Initialization**: Initialize video chip and set mode
- **Status**: Read video chip status

#### High-Level API
- **Mode Setting**: Set graphics mode
- **Pixel Drawing**: Draw pixel at (x, y)
- **Line Drawing**: Draw line between points
- **Rectangle Drawing**: Draw filled/outlined rectangle
- **Sprite Control**: Move, show, hide sprites
- **Text Output**: Display text characters

### 3. Video Initialization

#### Hardware Initialization
1. **Power On**: Ensure video chip has power
2. **Clock**: Verify clock signal
3. **Reset**: Reset video chip
4. **Register Setup**: Configure video registers
5. **Mode Selection**: Set graphics mode
6. **Palette Setup**: Configure color palette
7. **Memory Clear**: Clear video memory

#### Mode Configuration
- **Text Mode**: Character-based display
- **Graphics Mode**: Pixel-based display
- **Sprite Mode**: Sprite-based display
- **Mixed Mode**: Combination of modes

### 4. Video Memory Management

#### VRAM Layout
- **Pattern Table**: Character/sprite patterns
- **Name Table**: Screen layout
- **Color Table**: Color attributes
- **Sprite Table**: Sprite attributes

#### Memory Access
- **Direct Access**: Write directly to VRAM
- **Indirect Access**: Use video chip registers
- **Banking**: Handle VRAM banking (if needed)

### 5. Graphics Primitives

#### Pixel Operations
- **Set Pixel**: Set pixel at (x, y) to color
- **Get Pixel**: Read pixel color at (x, y)
- **Clear Screen**: Clear entire screen

#### Drawing Primitives
- **Line**: Draw line using Bresenham algorithm
- **Rectangle**: Draw filled or outlined rectangle
- **Circle**: Draw circle (optional, more complex)

#### Sprite Operations
- **Create Sprite**: Define sprite pattern
- **Move Sprite**: Set sprite position
- **Show/Hide Sprite**: Control sprite visibility
- **Set Sprite Color**: Configure sprite colors

### 6. Text Output

#### Character Rendering
- **Character Set**: Define character patterns
- **Font Data**: Store font in memory
- **Character Drawing**: Draw character at position
- **String Drawing**: Draw string of characters

#### Text Modes
- **Text Mode**: Use video chip text mode
- **Graphics Mode**: Draw text as graphics
- **Mixed Mode**: Combine text and graphics

---

## Week 18: Audio Driver

### 1. Audio Hardware Overview

**Audio Options** (see `VIDEO_AUDIO_HARDWARE_REFERENCE.md`):
- **YM2149F PSG**: 3-channel Programmable Sound Generator
- **SAM2695**: MIDI synthesizer chip

**Common Features**:
- Multiple sound channels
- Frequency control
- Volume control
- Envelope/waveform control
- Noise generation

### 2. Audio Driver Architecture

#### Low-Level Interface
- **Register Access**: Read/write audio chip registers
- **Initialization**: Initialize audio chip
- **Channel Control**: Control individual channels
- **Status**: Read audio chip status

#### High-Level API
- **Tone Generation**: Play tone at frequency
- **Music Playback**: Play music sequences
- **Sound Effects**: Play sound effects
- **Volume Control**: Set volume levels
- **Channel Control**: Enable/disable channels

### 3. YM2149F Driver (Example)

#### Chip Overview
- **3 Channels**: A, B, C
- **Frequency**: 16-bit frequency control
- **Volume**: 4-bit volume control
- **Envelope**: Envelope generator
- **Noise**: Noise generator

#### Register Map
- **R0-R5**: Channel A frequency (low/high)
- **R6-R7**: Channel B frequency
- **R8-R9**: Channel C frequency
- **R10-R12**: Channel volumes
- **R13**: Envelope frequency (low)
- **R14**: Envelope frequency (high)
- **R15**: Envelope shape

#### Initialization
1. **Reset**: Reset audio chip
2. **Register Setup**: Configure initial values
3. **Volume**: Set initial volumes
4. **Envelope**: Configure envelope generator

### 4. Tone Generation

#### Frequency Calculation
- **Formula**: `frequency = clock / (16 * period)`
- **Period**: 12-bit period value
- **Calculation**: Convert frequency to period value

#### Tone Playing
- **Set Frequency**: Write period to channel registers
- **Set Volume**: Write volume to channel register
- **Enable Channel**: Enable channel output
- **Stop Tone**: Disable channel or set volume to 0

### 5. Music Playback

#### Music Data Format
- **Notes**: Frequency values for notes
- **Durations**: Note durations
- **Tempo**: Playback speed
- **Channels**: Channel assignments

#### Playback Engine
- **Sequencer**: Play notes in sequence
- **Timing**: Handle note durations
- **Tempo Control**: Control playback speed
- **Looping**: Support music loops

### 6. Sound Effects

#### Sound Effect Types
- **Beep**: Simple tone
- **Click**: Short click sound
- **Explosion**: Noise-based sound
- **Swoosh**: Frequency sweep

#### Sound Effect Playback
- **Trigger**: Start sound effect
- **Duration**: Play for specified duration
- **Channel**: Use available channel
- **Cleanup**: Stop and free channel

---

## Week 19: Input Drivers

### 1. Input Hardware Overview

**Input Options**:
- **PS/2 Keyboard**: Standard keyboard interface ✅ **REQUIRED**
- **Gamepad**: Controller input (optional)
- **Serial Input**: Serial port input (fallback)

**Common Features**:
- Serial communication protocol
- Key/button codes
- Status reporting
- Interrupt support

**Input Device Progression**:
- **Year 3**: Simple buttons (SAP-1 control)
- **Year 4**: Matrix keypad (optional enhancement)
- **Year 6**: PS/2 keyboard (full keyboard interface) ✅

**Reference**: See `../../../resources/KEYBOARD_INPUT_INTERFACE_ANALYSIS.md` for complete input device analysis

### 2. PS/2 Keyboard Driver

**Status**: ✅ **REQUIRED** - Essential for complete system functionality

**Reference**: See `../../../resources/PS2_KEYBOARD_INTERFACE_GUIDE.md` for comprehensive PS/2 keyboard guide

#### PS/2 Protocol

**Physical Interface**:
- **PS/2 Connector**: 6-pin mini-DIN connector
- **Signals**: Clock (CLK), Data (DATA), Ground, +5V
- **Open-collector**: Both clock and data are open-collector
- **Pull-up resistors**: 10kΩ required on clock and data lines

**Protocol Details**:
- **Serial**: 2-wire serial protocol (clock + data)
- **Bidirectional**: Host can send commands to keyboard
- **11-bit frames**: Start bit (0), 8 data bits (LSB first), odd parity, stop bit (1)
- **Clock-driven**: Keyboard generates clock signal (10-16.7 kHz)
- **Asynchronous**: No fixed clock rate (keyboard controls timing)

**Communication Modes**:
- **Keyboard → Host**: Default mode, keyboard initiates, used for key events
- **Host → Keyboard**: Command mode, host initiates, used for commands

**Timing**:
- **Clock period**: ~60-100µs (keyboard controlled)
- **Data setup**: 5µs before clock falling edge
- **Data hold**: 5µs after clock falling edge

#### Scan Codes

**Scan Code Sets**:
- **Set 1**: Original IBM PC/XT
- **Set 2**: IBM PC/AT (default, recommended)
- **Set 3**: IBM PS/2 (less common)

**Recommendation**: Use **Scan Code Set 2** (most common, default)

**Make and Break Codes**:
- **Make Code**: Key pressed (single-byte: 0x01-0x83, or two-byte with 0xE0 prefix)
- **Break Code**: Key released (0xF0 prefix + make code)

**Example**:
- Key 'A' pressed: `0x1C`
- Key 'A' released: `0xF0 0x1C`

**Special Codes**:
- **0xE0**: Extended key prefix
- **0xF0**: Break code prefix
- **0xFA**: Acknowledge (ACK)
- **0xFE**: Resend request
- **0xFF**: Error/Reset

#### Keyboard Initialization

**Initialization Sequence**:
1. **Set up interrupt**: Configure IRQ for PS/2 clock falling edge
2. **Reset keyboard**: Send reset command (0xFF), wait for ACK (0xFA) and reset complete (0xAA)
3. **Set scan code set**: Send 0xF0 0x02 (Set 2), wait for ACK
4. **Enable keyboard**: Send enable command (0xF4), wait for ACK
5. **Clear key buffer**: Initialize circular buffer

**Hardware Setup**:
- Connect PS/2 clock to interrupt input (IRQ)
- Connect PS/2 data to I/O port
- Add pull-up resistors (10kΩ) to clock and data
- Provide +5V power to keyboard (if needed)

#### Key Processing

**Interrupt Handler**:
- **Trigger**: Clock falling edge (keyboard sending data)
- **Action**: Read data bit, shift into frame register
- **Frame complete**: When 11 bits received, process scan code

**Scan Code Reception**:
- **Receive bits**: On each clock falling edge, read data bit
- **Build frame**: Shift bits into 11-bit frame register
- **Validate**: Check start bit (0), parity, stop bit (1)
- **Extract data**: Extract 8-bit data byte from frame

**Scan Code Translation**:
- **Lookup table**: Translate scan code to key code/ASCII
- **Handle break codes**: Detect 0xF0 prefix, mark key as released
- **Handle extended keys**: Detect 0xE0 prefix, use extended table
- **Key state tracking**: Track which keys are pressed/released

**Key Buffer**:
- **Circular buffer**: Store key codes for application access
- **Buffer size**: 32 keys (adjustable)
- **Operations**: Add key (from interrupt), get key (from application)
- **Overflow handling**: Discard keys if buffer full

#### Device Driver API

**High-Level Interface**:
- **GetKey()**: Get next key from buffer (blocking)
- **KeyAvailable()**: Check if key available (non-blocking)
- **GetKeyState()**: Check if specific key is pressed
- **FlushBuffer()**: Clear key buffer

**Event System** (optional):
- **Key press events**: Notify application of key press
- **Key release events**: Notify application of key release
- **Event queue**: Queue key events for application processing

### 3. Gamepad Driver

#### Gamepad Interface
- **Buttons**: Digital button inputs
- **Directional Pad**: Direction inputs
- **Interface**: Parallel or serial interface
- **Polling**: Poll gamepad state

#### Gamepad Initialization
1. **Interface Setup**: Configure interface
2. **Button Mapping**: Map buttons to codes
3. **Polling Setup**: Set up polling routine
- **State Reading**: Read gamepad state

#### Input Processing
- **Button States**: Track button press/release
- **Direction States**: Track direction inputs
- **Input Buffer**: Buffer input events
- **Input Events**: Generate input events

### 4. Input API

#### High-Level Interface
- **Key Read**: Read key from buffer
- **Key Available**: Check if key available
- **Key State**: Check if key pressed
- **Input Poll**: Poll input devices

#### Event System
- **Key Press Event**: Key pressed
- **Key Release Event**: Key released
- **Button Press Event**: Button pressed
- **Direction Event**: Direction changed

### 5. Input Buffering

#### Buffer Design
- **Circular Buffer**: Circular key buffer
- **Buffer Size**: Appropriate buffer size
- **Buffer Operations**: Add, remove, check
- **Buffer Overflow**: Handle buffer overflow

#### Input Handling
- **Interrupt Handler**: Handle input interrupts
- **Polling**: Poll input devices
- **Event Generation**: Generate input events
- **Application Interface**: Provide API to applications

---

## Week 20: Storage Driver (SD Card)

**Reference**: See `../../../resources/SD_CARD_STORAGE_ANALYSIS.md` for comprehensive SD card storage options analysis.

### Storage Architecture Overview

**Two Approaches Available**:

1. **RP2350 Storage Co-Processor** (Recommended - Primary Approach)
   - RP2350 handles SD card interface and FatFS file system
   - 65C816 communicates via SPI/UART/I2C
   - Similar architecture to video co-processor (Year 6)
   - **Performance**: High (1-2 MB/s read, 500KB-1MB/s write)
   - **Complexity**: Moderate (4-6 weeks)

2. **VIA-Based SPI Interface** (Optional - Advanced Project)
   - 65C816 bit-bangs SPI protocol via 65C22 VIA
   - FatFS implemented on 65C816
   - Maximum educational value (SPI implementation)
   - **Performance**: Moderate (50-200 KB/s)
   - **Complexity**: High (6-8 weeks, optional Term 3 project)

**Recommendation**: Use **RP2350 co-processor** as primary approach (consistent with video co-processor). VIA-based approach available as optional advanced project.

### 1. RP2350 Storage Co-Processor (Primary Approach)

#### Architecture
```
65C816 → SPI/UART/I2C → RP2350 → SD Card → FAT32 File System
```

**RP2350 Responsibilities**:
- SD card SPI interface
- FatFS file system implementation
- Command protocol with 65C816
- File operations (read, write, open, close, etc.)

#### Hardware Interface

**RP2350 Board Options**:
- **LILYGO T-PICO-2350**: Built-in microSD card slot
- **Raspberry Pi Pico 2 (RP2350)**: Standard board + SD card breakout

**SD Card Breakout**:
- [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682) - Standard SPI interface
- Connection: RP2350 SPI pins → SD card breakout

#### Communication Protocol

**Command Protocol** (65C816 → RP2350):
- `OPEN <filename> <mode>` - Open file (read/write/append)
- `READ <handle> <length>` - Read data from file
- `WRITE <handle> <data>` - Write data to file
- `CLOSE <handle>` - Close file
- `LIST` - List directory contents
- `MKDIR <dirname>` - Create directory
- `DELETE <filename>` - Delete file
- `SEEK <handle> <position>` - Seek to position in file

**Response Format**:
- Success: `OK <data>` or `OK`
- Error: `ERROR <code> <message>`

#### File System API (65C816 Side)

**High-Level API**:
```assembly
; File operations
FileOpen(filename, mode) → handle
FileRead(handle, buffer, length) → bytes_read
FileWrite(handle, buffer, length) → bytes_written
FileClose(handle) → status
FileSeek(handle, position) → status

; Directory operations
DirList(path) → file_list
DirCreate(path) → status
DirDelete(path) → status

; File management
FileDelete(filename) → status
FileExists(filename) → boolean
FileSize(filename) → size
```

#### Storage Partition Strategy

**Single SD Card Approach** (Recommended):
- **System Partition** (~1-2MB, FAT32): Bootloader + kernel/userland (updatable)
- **User Partition** (remainder, FAT32): User files + extensions (removable)

**Bootloader Update**:
- Bootloader stored in SD card system partition
- Update process: 65C816 sends update command to RP2350
- RP2350 writes new bootloader to system partition
- System reboots with new bootloader

### 2. VIA-Based SPI Interface (Optional Advanced Project)

**Note**: This approach is available as an optional advanced project for students who want deep SPI understanding. See `SD_CARD_STORAGE_ANALYSIS.md` for details.

#### SPI Protocol (Bit-Banging via VIA)
- **Signals**: MOSI, MISO, SCK, CS (via VIA Port A)
- **Mode**: SPI Mode 0
- **Speed**: Limited by 65C816 bit-banging speed
- **Timing**: Critical timing requirements

#### SD Card Types
- **SDSC**: Standard Capacity (up to 2GB)
- **SDHC**: High Capacity (2GB-32GB)
- **SDXC**: Extended Capacity (32GB+)

### 3. RP2350 Co-Processor Initialization

#### Initialization Sequence
1. **RP2350 Communication Setup**: Initialize SPI/UART/I2C interface
2. **RP2350 Firmware Check**: Verify RP2350 is running storage firmware
3. **SD Card Mount**: Send mount command to RP2350
4. **File System Check**: Verify FAT32 file system
5. **Partition Check**: Verify system and user partitions exist

#### Error Handling
- **Communication Errors**: Handle RP2350 communication failures
- **SD Card Errors**: RP2350 reports SD card errors
- **File System Errors**: Handle file system errors
- **Retry Logic**: Retry failed operations
- **Status Reporting**: Report initialization status

### 4. File Operations (RP2350 Co-Processor)

#### File Reading
- **Open File**: Send OPEN command to RP2350
- **Read Data**: Send READ command, receive data
- **Seek**: Send SEEK command to change position
- **Close File**: Send CLOSE command

#### File Writing
- **Open File**: Send OPEN command with write mode
- **Write Data**: Send WRITE command with data
- **Flush**: Ensure data written to SD card
- **Close File**: Send CLOSE command

#### Directory Operations
- **List Directory**: Send LIST command, receive file list
- **Create Directory**: Send MKDIR command
- **Delete File/Directory**: Send DELETE command

### 5. Driver API (RP2350 Co-Processor)

#### Low-Level API (Communication)
- **Init**: Initialize RP2350 communication
- **SendCommand**: Send command to RP2350
- **ReceiveResponse**: Receive response from RP2350
- **CheckStatus**: Check RP2350 status

#### High-Level API (File System)
- **StorageInit**: Initialize storage system
- **FileOpen**: Open file (returns handle)
- **FileRead**: Read from file
- **FileWrite**: Write to file
- **FileClose**: Close file
- **FileSeek**: Seek to position
- **DirList**: List directory
- **DirCreate**: Create directory
- **FileDelete**: Delete file

---

## Driver Design Principles

### 1. Layered Architecture

#### Hardware Layer
- Direct register access
- Hardware-specific code
- Low-level operations

#### Driver Layer
- Device initialization
- Device control
- Error handling

#### API Layer
- High-level interface
- Application-friendly functions
- Abstraction of hardware details

### 2. Error Handling

#### Error Types
- **Hardware Errors**: Device not responding
- **Communication Errors**: Protocol errors
- **Data Errors**: Corrupted data
- **Resource Errors**: Out of resources

#### Error Reporting
- **Error Codes**: Return error codes
- **Error Messages**: Provide error messages
- **Error Recovery**: Attempt error recovery
- **Status Reporting**: Report device status

### 3. Initialization and Cleanup

#### Initialization
- **Hardware Setup**: Configure hardware
- **Register Setup**: Set initial register values
- **Interrupt Setup**: Configure interrupts (if needed)
- **Status Verification**: Verify initialization success

#### Cleanup
- **Resource Release**: Release resources
- **Device Reset**: Reset device to safe state
- **Interrupt Disable**: Disable interrupts
- **Status Reporting**: Report cleanup status

### 4. Interrupt Handling

#### Interrupt Support
- **Interrupt Enable**: Enable device interrupts
- **Interrupt Handler**: Handle interrupt events
- **Interrupt Disable**: Disable interrupts
- **Interrupt Status**: Check interrupt status

#### Polling Alternative
- **Polling Mode**: Poll device status
- **Timing**: Appropriate polling frequency
- **Efficiency**: Balance responsiveness and CPU usage

---

## Integration with System

### Monitor Integration
- **Driver Testing**: Use monitor to test drivers
- **Register Inspection**: Inspect device registers
- **Debugging**: Debug driver issues

### Boot Loader Integration
- **Driver Loading**: Load drivers from SD card
- **Driver Initialization**: Initialize drivers at boot
- **Driver Access**: Access drivers from boot loader

### Application Integration
- **API Usage**: Applications use driver APIs
- **Abstraction**: Applications don't need hardware details
- **Error Handling**: Applications handle driver errors

---

## Learning Outcomes

After completing this block, students will:

1. **Video Driver**:
   - Initialize video hardware
   - Set graphics modes
   - Draw graphics primitives
   - Control sprites
   - Display text

2. **Audio Driver**:
   - Initialize audio hardware
   - Generate tones
   - Play music
   - Create sound effects
   - Control volume

3. **Input Drivers**:
   - Interface with PS/2 keyboard
   - Interface with gamepad
   - Process input events
   - Provide input API

4. **Storage Driver** (SD Card):
   - **RP2350 Co-Processor Approach** (Primary):
     - Initialize RP2350 storage co-processor
     - Implement communication protocol
     - Provide file system API
     - Handle file operations (open, read, write, close)
     - Manage storage partitions (system + user)
   - **VIA-Based SPI Approach** (Optional Advanced):
     - Initialize SD card via VIA bit-banging
     - Implement SPI protocol
     - Port FatFS to 65C816
     - Provide file operations

---

## Next Steps

After completing device drivers, students move to system services and integration (Weeks 21-24), which will use all drivers to create a complete system software stack.

---

*Device drivers provide essential interfaces between applications and hardware*
