# SD Card Storage Options Analysis for 65C816 System

## Overview

This document analyzes storage options for the Resistor2Compiler 65C816 system, considering both **RP2350 co-processor** and **VIA-based SPI interface** approaches. The recommended architecture uses:

- **FRAM (8KB)**: Bootloader storage - Fast, reliable, non-volatile, perfect for bootloader
- **SD Card**: System storage (kernel, OS, userland) + User files - Large capacity, removable, file system support

**Recommended Hardware**:
- **Bootloader Storage**: [Adafruit SPI Non-Volatile FRAM Breakout - 64Kbit/8KB](https://www.adafruit.com/product/1897) - $5.95
- **System/User Storage**: [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682) - Standard SD card breakout

**Reference Tutorial**: [STM32 SD Card over SPI with FatFS](https://01001000.xyz/2020-08-09-Tutorial-STM32CubeIDE-SD-card/) - Demonstrates FatFS integration with SPI interface

---

## Storage Architecture Requirements

### 1. Bootloader Storage (FRAM - Recommended)

**Purpose**:
- **Bootloader**: System initialization, firmware update capability
- **Critical System Code**: Must be available immediately on power-on

**Requirements**:
- **Updatable**: Bootloader must support firmware updates
- **Persistent**: Must survive power cycles
- **Reliable**: System-critical, must be robust
- **Fast Writes**: Bootloader updates should be fast
- **High Endurance**: Many update cycles expected
- **Size**: ~4KB-8KB (bootloader code)

**Recommended Solution**: **Adafruit SPI FRAM Breakout - 64Kbit/8KB**
- **Product**: [Adafruit SPI Non-Volatile FRAM Breakout - 64Kbit/8KB](https://www.adafruit.com/product/1897)
- **Price**: $5.95
- **Interface**: SPI (compatible with VIA bit-banging or direct SPI)
- **Voltage**: 5V compatible (works with 65C816 system)
- **Features**:
  - ✅ **Non-volatile**: Data persists without power (95 years at room temperature)
  - ✅ **Fast writes**: No page erase needed (unlike Flash/EEPROM)
  - ✅ **High endurance**: 10^13 write cycles (essentially unlimited)
  - ✅ **Byte-level access**: Each byte can be read/written instantly
  - ✅ **SPI interface**: Up to 20MHz SPI clock rate
  - ✅ **Perfect size**: 8KB is ideal for bootloader

**Why FRAM for Bootloader**:
- **Fast Updates**: No page erase cycles (unlike Flash/EEPROM)
- **Reliable**: High endurance means bootloader can be updated frequently
- **Simple**: Byte-level access, no complex erase/write sequences
- **Persistent**: Non-volatile, survives power loss
- **5V Compatible**: Works directly with 65C816 system

**Bootloader Update Mechanism**:
1. Bootloader stored in FRAM (8KB)
2. Update process:
   - 65C816 reads new bootloader from SD card (via RP2350 or VIA)
   - 65C816 writes new bootloader to FRAM via SPI
   - System reboots with new bootloader
3. **Advantage**: Fast, reliable updates without complex erase sequences

### 2. System Storage (SD Card - Kernel, OS, Userland)

**Purpose**:
- **Kernel**: Core operating system kernel
- **Base OS**: Essential system services
- **Base Userland**: Essential system utilities
- **User Files**: User data, documents, programs
- **User Extensions**: User-built utilities, applications, libraries

**Requirements**:
- **Removable**: Must be physically removable (for user files)
- **File System**: FAT32 (compatible with modern systems)
- **Capacity**: Support standard SD card sizes (up to 32GB recommended)
- **Accessible**: Can be read/written by 65C816 system
- **Size**: ~512KB-2MB (kernel + base OS) + ~128KB-512KB (base userland) + user space

### 2. Removable SD Card Storage (User Files + Extensions)

**Purpose**:
- **User Files**: User data, documents, programs
- **User Extensions**: User-built utilities, applications, libraries
- **Portability**: Users can transfer files between systems

**Requirements**:
- **Removable**: Must be physically removable
- **File System**: FAT32 (compatible with modern systems)
- **Capacity**: Support standard SD card sizes (up to 32GB recommended)
- **Accessible**: Can be read/written by 65C816 system

---

## Option 1: RP2350 Storage Co-Processor (Recommended)

### Architecture

**Similar to Video Co-Processor Approach**:
```
65C816 → SPI/UART/I2C → RP2350 → SD Card → FAT32 File System
```

**RP2350 Responsibilities**:
- SD card interface (SPI to SD card)
- FatFS file system implementation
- Command protocol with 65C816
- File operations (read, write, open, close, etc.)

### Hardware Setup

**RP2350 Board Options**:
1. **LILYGO T-PICO-2350**: Includes built-in microSD card slot
   - **Advantage**: Integrated SD card slot, no additional hardware
   - **Reference**: [LILYGO T-PICO-2350 Wiki](https://wiki.lilygo.cc/get_started/en/Display/T-Pico-2350/T-Pico-2350.html)
2. **Raspberry Pi Pico 2 (RP2350)**: Standard Pico board + SD card breakout
   - **Advantage**: Lower cost, more flexible
   - **Requires**: Adafruit SD card breakout board

**SD Card Breakout**:
- [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682) - Standard SPI interface
- [Adafruit MicroSD SPI or SDIO Card Breakout](https://www.adafruit.com/product/4899) - Alternative option

**Connection**:
```
RP2350 SPI Pins → SD Card Breakout:
  - MOSI → DI (Data In)
  - MISO → DO (Data Out)
  - SCK → CLK (Clock)
  - CS → CS (Chip Select)
  - 3.3V → VCC
  - GND → GND
```

### Software Stack

**RP2350 Firmware**:
- **FatFS Library**: File system implementation (ChaN's FatFS)
- **SD Card SPI Driver**: Low-level SD card communication
- **Command Protocol**: Simple protocol for 65C816 communication

**Command Protocol Example**:
```
65C816 → RP2350 Commands:
  - OPEN <filename> <mode>     // Open file
  - READ <handle> <length>      // Read data
  - WRITE <handle> <data>       // Write data
  - CLOSE <handle>              // Close file
  - LIST                        // List directory
  - MKDIR <dirname>             // Create directory
  - DELETE <filename>            // Delete file
```

**65C816 Driver**:
- **Serial/SPI Interface**: Communicate with RP2350
- **File System API**: High-level file operations
- **Error Handling**: Handle communication errors

### Educational Value

**Advantages**:
- ✅ **Co-Processor Architecture**: Students learn co-processor design (similar to video co-processor)
- ✅ **File System Concepts**: Students understand file systems, directories, files
- ✅ **Protocol Design**: Students design and implement communication protocol
- ✅ **Firmware Study**: Students can study RP2350 firmware source code
- ✅ **Modern Approach**: Uses modern microcontroller capabilities
- ✅ **Foundation**: Builds on Year 4 Ben Eater VGA experience (co-processor concepts)

**Learning Objectives**:
- Understand co-processor architecture
- Learn file system concepts (FAT32, directories, files)
- Design communication protocols
- Implement file operations
- Understand storage abstraction

### Implementation Complexity

**Moderate Complexity**:
- RP2350 firmware development (FatFS integration)
- Command protocol design
- 65C816 driver implementation
- Error handling and recovery

**Time Estimate**: 4-6 weeks (Year 6, Term 2)

### Performance

**Speed**: **HIGH**
- RP2350 handles SD card SPI at high speeds
- FatFS optimized for performance
- Minimal overhead for 65C816

**Typical Performance**:
- Read: ~1-2 MB/s (depends on SD card)
- Write: ~500KB-1MB/s (depends on SD card)
- File operations: Fast (handled by RP2350)

---

## Option 2: VIA-Based SPI Interface (Alternative)

### Architecture

**Direct 65C816 Connection**:
```
65C816 → 65C22 VIA → Bit-Bang SPI → SD Card → FAT32 File System (on 65C816)
```

**65C816 Responsibilities**:
- SPI protocol implementation (bit-banging via VIA)
- SD card low-level communication
- FatFS file system implementation (on 65C816)
- File operations

### Hardware Setup

**VIA Configuration**:
- **Port A**: SPI signals (MOSI, MISO, SCK, CS)
- **Port B**: Status/control (optional)
- **Timers**: For SPI timing (if needed)

**SPI Bit-Banging**:
- **MOSI**: VIA Port A bit 0 (output)
- **MISO**: VIA Port A bit 1 (input, with pull-up)
- **SCK**: VIA Port A bit 2 (output)
- **CS**: VIA Port A bit 3 (output)

**SD Card Breakout**:
- [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682)
- Connect directly to VIA Port A pins

**Connection**:
```
VIA Port A → SD Card Breakout:
  - PA0 (MOSI) → DI
  - PA1 (MISO) → DO
  - PA2 (SCK) → CLK
  - PA3 (CS) → CS
  - 3.3V → VCC (via level shifter if needed)
  - GND → GND
```

### Software Stack

**65C816 Implementation**:
- **SPI Bit-Bang Driver**: Implement SPI protocol using VIA
- **SD Card Driver**: Low-level SD card communication
- **FatFS Port**: Port FatFS to 65C816 (requires disk I/O functions)
- **File System API**: High-level file operations

**FatFS Disk I/O Functions** (required):
```assembly
; disk_initialize - Initialize SD card
; disk_read - Read sector(s)
; disk_write - Write sector(s)
; disk_ioctl - Control functions
```

### Educational Value

**Advantages**:
- ✅ **SPI Protocol**: Students implement SPI protocol from scratch
- ✅ **Bit-Banging**: Students learn bit-level I/O programming
- ✅ **File System**: Students understand file system internals (FatFS source)
- ✅ **Low-Level**: Maximum educational value (all code on 65C816)
- ✅ **First Principles**: Builds from first principles (no co-processor abstraction)

**Learning Objectives**:
- Implement SPI protocol (bit-banging)
- Understand SD card communication protocol
- Port FatFS to 65C816
- Understand file system internals
- Learn low-level storage programming

### Implementation Complexity

**High Complexity**:
- SPI bit-banging implementation
- SD card initialization and communication
- FatFS porting to 65C816
- Timing-critical code
- Error handling

**Time Estimate**: 6-8 weeks (Year 6, Term 2-3)

### Performance

**Speed**: **MODERATE to SLOW**
- Bit-banging SPI is slower than hardware SPI
- 65C816 handles all file system operations
- Limited by 65C816 processing speed

**Typical Performance**:
- Read: ~50-200 KB/s (depends on implementation)
- Write: ~20-100 KB/s (depends on implementation)
- File operations: Moderate (handled by 65C816)

**Note**: Similar to RC2014 SC611 module performance (comparable to 1980s floppy disk speeds)

---

## Comparison: RP2350 vs VIA-Based

| Aspect | RP2350 Co-Processor | VIA-Based SPI |
|--------|---------------------|--------------|
| **Educational Value** | High (co-processor architecture) | Very High (SPI implementation) |
| **Complexity** | Moderate | High |
| **Performance** | High (1-2 MB/s) | Moderate (50-200 KB/s) |
| **Implementation Time** | 4-6 weeks | 6-8 weeks |
| **Code Location** | RP2350 firmware + 65C816 driver | All on 65C816 |
| **Protocol Learning** | Communication protocol | SPI protocol |
| **File System** | FatFS on RP2350 | FatFS on 65C816 |
| **Hardware Cost** | ~$5-10 (RP2350 + breakout) | ~$5 (VIA + breakout) |
| **Foundation** | Builds on video co-processor | Builds on I/O programming |

---

## Recommended Approach: Hybrid Architecture

### Primary Storage: RP2350 Co-Processor

**Rationale**:
- **Consistency**: Matches video co-processor approach (Year 6)
- **Performance**: Adequate for user files and extensions
- **Educational Value**: Co-processor architecture is valuable learning
- **Time Efficiency**: Faster implementation than VIA-based
- **Foundation**: Builds on Year 4 Ben Eater VGA experience

**Implementation**:
- **Year 6, Term 2**: RP2350 storage co-processor implementation
- **Lab Project**: Build storage co-processor system
- **Integration**: Similar to video co-processor integration

### Optional: VIA-Based SPI (Advanced Project)

**Rationale**:
- **Advanced Learning**: For students who want deeper understanding
- **SPI Protocol**: Maximum educational value for SPI implementation
- **Alternative**: Can be offered as optional advanced project

**Implementation**:
- **Year 6, Term 3**: Optional advanced project
- **Lab Project**: VIA-based SPI SD card interface
- **Integration**: Alternative to RP2350 approach

---

## Storage Partition Strategy

### Recommended Architecture: FRAM + SD Card

**Optimal Storage Layout**:
```
1. FRAM (8KB): Bootloader
   - System initialization code
   - Firmware update capability
   - Fast, reliable, updatable

2. SD Card (32GB recommended): System + User Storage
   - Partition 1: System (FAT32, ~2-4MB)
     * Kernel (core OS)
     * Base OS (system services)
     * Base Userland (essential utilities)
   - Partition 2: User (FAT32, remainder)
     * User files (data, documents, programs)
     * User extensions (user-built utilities, applications)
```

**Why This Architecture**:
- ✅ **FRAM for Bootloader**: Fast updates, high endurance, perfect size
- ✅ **SD Card for System**: Large capacity, removable, file system support
- ✅ **Separation of Concerns**: Bootloader separate from system files
- ✅ **Update Flexibility**: Bootloader updates via FRAM, system updates via SD card
- ✅ **Educational Value**: Students understand different storage technologies

### Bootloader Update Mechanism (FRAM)

**FRAM-Based Bootloader Update**:
1. **Bootloader Location**: FRAM (8KB, SPI interface)
2. **Update Process**:
   - 65C816 reads new bootloader from SD card (via RP2350 or VIA)
   - 65C816 writes new bootloader to FRAM via SPI (byte-by-byte, no erase needed)
   - System reboots with new bootloader
3. **Advantages**:
   - **Fast**: No page erase cycles (unlike Flash/EEPROM)
   - **Reliable**: High endurance (10^13 write cycles)
   - **Simple**: Byte-level access, straightforward implementation
   - **Safe**: Can verify bootloader before committing

**System Update Mechanism (SD Card)**:
1. **System Location**: SD card system partition
2. **Update Process**:
   - 65C816 reads new kernel/OS from SD card user partition (or external source)
   - 65C816 writes new system files to SD card system partition (via RP2350)
   - System reboots, loads new kernel/OS from SD card
3. **Advantages**:
   - **Large Capacity**: Can store multiple kernel versions
   - **Removable**: Can update system files on another computer
   - **File System**: Standard FAT32, compatible with modern systems

---

## Curriculum Integration

### Year 6, Term 2: Storage Systems

**Week 17-20: Device Drivers** (existing)
- **Add**: Storage driver development
- **RP2350 Storage Co-Processor**: Implement storage co-processor
- **File System API**: Design and implement file system API

**Learning Objectives**:
- Understand co-processor architecture (storage)
- Learn file system concepts (FAT32)
- Implement file operations (open, read, write, close)
- Design communication protocols

**Lab Project**: Build RP2350 storage co-processor system

### Year 6, Term 3: Advanced Topics (Optional)

**Optional Advanced Project**: VIA-Based SPI SD Card Interface
- **For Advanced Students**: Want deeper SPI understanding
- **Implementation**: Bit-bang SPI, SD card driver, FatFS port
- **Time**: 6-8 weeks

---

## Hardware Requirements

### RP2350 Co-Processor Approach

**Required**:
- **FRAM for Bootloader**: [Adafruit SPI Non-Volatile FRAM Breakout - 64Kbit/8KB](https://www.adafruit.com/product/1897) - $5.95
- **RP2350 Board**: LILYGO T-PICO-2350 or Raspberry Pi Pico 2 + SD card breakout
- **SD Card Breakout**: [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682)
- **SD Card**: MicroSD card (FAT32 formatted, 32GB recommended)
- **Interface**: SPI/UART/I2C connection to 65C816

**Cost**: ~$16-21 per student (FRAM + RP2350 + SD card breakout)

### VIA-Based Approach

**Required**:
- **FRAM for Bootloader**: [Adafruit SPI Non-Volatile FRAM Breakout - 64Kbit/8KB](https://www.adafruit.com/product/1897) - $5.95
- **65C22 VIA**: Already in system (for SPI bit-banging)
- **SD Card Breakout**: [Adafruit MicroSD Card Breakout Board](https://www.adafruit.com/product/4682)
- **SD Card**: MicroSD card (FAT32 formatted)
- **Level Shifter** (optional): If 5V to 3.3V conversion needed

**Cost**: ~$11-13 per student (FRAM + SD card breakout)

---

## References

### Tutorials and Resources

1. **FRAM for Bootloader**: [Adafruit SPI Non-Volatile FRAM Breakout - 64Kbit/8KB](https://www.adafruit.com/product/1897)
   - Perfect for bootloader storage
   - Fast writes, high endurance, non-volatile
   - 5V compatible, SPI interface
   - $5.95 per board

2. **STM32 SD Card Tutorial**: [STM32CubeIDE SD Card over SPI with FatFS](https://01001000.xyz/2020-08-09-Tutorial-STM32CubeIDE-SD-card/)
   - Excellent tutorial on FatFS integration
   - SPI interface implementation
   - File system concepts

3. **Adafruit SD Card Breakout**: [MicroSD Card Breakout Board](https://www.adafruit.com/product/4682)
   - Standard SPI interface
   - Level shifting included
   - Well-documented

4. **FatFS Library**: [ChaN's FatFS](http://elm-chan.org/fsw/ff/00index_e.html)
   - Open-source FAT file system
   - Well-documented
   - Portable to different platforms

5. **RP2350 Documentation**: [LILYGO T-PICO-2350 Wiki](https://wiki.lilygo.cc/get_started/en/Display/T-Pico-2350/T-Pico-2350.html)
   - RP2350 specifications
   - SD card integration examples

6. **RC2014 SC611 Module**: Reference for VIA-based approach
   - Bit-bang SPI implementation
   - Performance characteristics
   - Integration patterns

---

## Conclusion

### Recommended: RP2350 Storage Co-Processor

**Primary Choice**: RP2350 co-processor approach provides the best balance of:
- **Educational Value**: Co-processor architecture learning
- **Performance**: Adequate for user files and extensions
- **Implementation Time**: Reasonable (4-6 weeks)
- **Consistency**: Matches video co-processor approach
- **Foundation**: Builds on Year 4 Ben Eater VGA experience

### Optional: VIA-Based SPI (Advanced)

**Alternative**: VIA-based approach for students who want:
- **Deep SPI Understanding**: Implement SPI protocol from scratch
- **Maximum Educational Value**: All code on 65C816
- **First Principles Learning**: Bit-level I/O programming

### Storage Strategy

**FRAM + SD Card Approach** (Recommended):
- **FRAM (8KB)**: Bootloader (fast, reliable, updatable)
- **SD Card System Partition**: Kernel + OS + base userland (updatable, removable)
- **SD Card User Partition**: User files + extensions (removable)

**Why This is Optimal**:
- ✅ **FRAM for Bootloader**: Perfect technology for bootloader (fast writes, high endurance, non-volatile)
- ✅ **SD Card for System**: Large capacity, file system support, removable
- ✅ **Separation**: Bootloader separate from system files (better architecture)
- ✅ **Educational Value**: Students learn about different storage technologies (FRAM vs SD card)
- ✅ **Update Flexibility**: Different update mechanisms for bootloader vs system

This provides the best balance of performance, reliability, and educational value.

---

**Document Created**: 2025-12-16  
**Status**: Analysis complete, ready for curriculum integration

