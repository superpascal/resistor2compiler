# RC2014 Boards and Modules: Comprehensive Curriculum Fit Analysis

## Overview

This document provides a comprehensive analysis of all RC2014 boards and modules from the scraped content, assessing their educational value and fit within the Resistor2Compiler curriculum. For each board/module, we identify:

1. **Educational Value**: How it contributes to learning objectives
2. **Curriculum Fit**: Which years/topics it aligns with
3. **CPU Compatibility**: Changes needed for 65C816 (curriculum) vs Z80 (RC2014)
4. **Design Modifications**: Specific redesign requirements

**Key Architecture Difference**:
- **RC2014**: Z80 (8-bit CPU, 8-bit data bus, 16-bit address bus, 64KB address space)
- **Curriculum**: MOS 65C816 (16-bit CPU, 8/16-bit data bus, 24-bit address bus, 16MB address space)
- **Supporting Chips**: 65C22 VIA (I/O), 65C51 ACIA (serial) vs RC2014's various I/O modules

---

## Analysis Table

### Backplanes

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **Backplane Pro** | **HIGH** - Professional PCB design, bus architecture, power management, modular design | **Years 2-4**: PCB design reference, bus architecture study | ✅ **Compatible** - Bus design is CPU-agnostic | **Minimal**: Bus pinout may need adjustment for 65C816 signals (24-bit address vs 16-bit). Enhanced bus concept directly applicable. |
| **Backplane 5** | **HIGH** - Simpler backplane, good for learning progression | **Years 2-3**: Simpler design for early learning | ✅ **Compatible** - Bus design CPU-agnostic | **Minimal**: Address bus expansion for 65C816 (16-bit → 24-bit). Power management directly applicable. |
| **Backplane 8** | **HIGH** - Intermediate complexity, 8 slots | **Years 3-4**: Intermediate complexity | ✅ **Compatible** - Bus design CPU-agnostic | **Minimal**: Address bus expansion. Isolation techniques directly applicable. |
| **Veroboard Backplane** | **MEDIUM** - DIY approach, educational for understanding | **Year 2**: DIY PCB fabrication | ✅ **Compatible** - Basic bus concept | **Minimal**: Address bus expansion. Good reference for DIY backplane construction. |
| **Front Panel Kit** | **MEDIUM** - I/O interface, LEDs, switches, reset | **Years 4-6**: I/O systems, debugging interface | ⚠️ **Needs Modification** - Uses Z80-specific signals (!IORQ, M1) | **Moderate**: Replace Z80 signal decoding (74HCT138 for !IORQ/M1) with 65C816 equivalent (address decoding for I/O space). Port addressing scheme needs redesign. |
| **Blue Box Enclosure** | **LOW** - Mechanical/enclosure only | **Year 6**: Professional finishing | ✅ **Compatible** - Mechanical only | **None**: Enclosure design is CPU-agnostic. Good reference for professional enclosure design. |

### Memory Modules

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **64k RAM Module** | **HIGH** - Address decoding, memory mapping, jumper configuration | **Years 3-4**: Memory systems, address decoding | ⚠️ **Needs Modification** - Z80-specific address decoding (A15, /MREQ, /WR, /RD) | **Significant**: Replace Z80 control signals (/MREQ, /WR, /RD) with 65C816 equivalents (VPA, R/W, VDA). Address decoding logic needs redesign for 24-bit address space. Memory mapping concepts directly applicable. |
| **512k ROM 512k RAM Module** | **HIGH** - Bank switching, paged memory, advanced memory management | **Years 4-5**: Memory banking, advanced memory systems | ⚠️ **Needs Modification** - Z80-specific paging (32k pages for 64k address space) | **Significant**: Redesign for 65C816 24-bit address space. Bank switching logic needs modification (65C816 has native banking support). Page size and banking scheme need redesign. Memory management concepts directly applicable. |
| **8k ROM Module** | **MEDIUM** - Simple ROM interface, address decoding | **Years 2-3**: Basic memory systems | ⚠️ **Needs Modification** - Z80-specific control signals | **Moderate**: Replace Z80 control signals with 65C816 equivalents. Address decoding needs update for 24-bit address space. ROM interface concepts directly applicable. |

### I/O Modules

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **LCD Driver Module** | **HIGH** - HD44780 interface, I/O port addressing, data buffering | **Years 3-4**: I/O systems, LCD interfacing | ⚠️ **Needs Modification** - Uses Z80-specific I/O port addressing (!IORQ, M1, port addresses 0xDA/0xDB) | **Moderate**: Replace Z80 I/O port decoding (74HCT688, 74HCT86 for !IORQ/M1) with 65C816 memory-mapped I/O or VIA-based addressing. Port address scheme needs redesign. HD44780 interface logic directly applicable. |
| **Digital I/O Module** | **HIGH** - I/O port programming, LED control, switch reading | **Years 3-4**: I/O systems, parallel I/O | ⚠️ **Needs Modification** - Z80-specific I/O port addressing | **Moderate**: Replace Z80 I/O port addressing with 65C816 VIA (65C22) interface. Port 0 addressing scheme needs redesign. I/O programming concepts directly applicable. |
| **Front Panel I/O Module** | **MEDIUM** - Advanced I/O, LEDs, switches, reset supervisor | **Years 4-6**: Advanced I/O, debugging interface | ⚠️ **Needs Modification** - Z80-specific signals (!IORQ, M1, Port 0) | **Moderate**: Replace Z80 signal decoding with 65C816 VIA interface. Port addressing needs redesign. Reset supervisor (DS1233) directly applicable. |

### Storage Modules

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **RP2350 Storage Co-Processor** | **HIGH** - SD card storage, file systems, co-processor architecture | **Year 6**: Storage systems, file systems, co-processor design | ✅ **Compatible** - Microcontroller-based, communicates via SPI/UART/I2C | **Minimal**: Interface protocol (SPI/UART/I2C) is CPU-agnostic. Storage concepts directly applicable. **RECOMMENDED** approach for Year 6 storage. See `SD_CARD_STORAGE_ANALYSIS.md` for detailed analysis. |
| **VIA-Based SD Card Interface** | **VERY HIGH** - SPI protocol, bit-banging, file systems | **Year 6**: Advanced storage (optional project) | ✅ **Compatible** - Uses 65C22 VIA, bit-bang SPI | **Moderate**: SPI bit-banging implementation required. FatFS porting to 65C816. **OPTIONAL** advanced project for deep SPI understanding. See `SD_CARD_STORAGE_ANALYSIS.md` for detailed analysis. |
| **Compact Flash Module 2.x** | **HIGH** - Storage interface, IDE/ATA protocol, file systems | **Years 5-6**: Storage systems, file systems | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate to Significant**: Interface protocol may need redesign depending on implementation. IDE/ATA protocol concepts directly applicable. May need 65C816-specific interface chip or VIA-based interface. |
| **IDE Hard Drive Module** | **HIGH** - IDE interface, mass storage, system integration | **Years 5-6**: Storage systems, system integration | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate to Significant**: IDE interface may need redesign. Protocol concepts directly applicable. May need 65C816-specific interface or VIA-based design. |
| **CH375 USB Storage** | **MEDIUM** - USB interface, modern storage | **Year 6**: Advanced storage | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate**: USB interface chip may work with 65C816 if interface is generic. Protocol concepts directly applicable. |

### Communication Modules

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **16C550 UART Module** | **HIGH** - Serial communication, UART interface, RS-232 | **Years 4-6**: Serial I/O, communication protocols | ⚠️ **Needs Modification** - I/O port addressing Z80-specific | **Moderate**: Replace Z80 I/O port addressing with 65C816 memory-mapped I/O or VIA interface. UART chip (16C550) directly compatible. Serial communication concepts directly applicable. |
| **SIO/2 Serial Module** | **HIGH** - Dual serial ports, communication | **Years 4-6**: Serial I/O, dual ports | ⚠️ **Needs Modification** - Z80-specific interface | **Moderate**: Interface redesign needed. Serial communication concepts directly applicable. |
| **ESP8266 WiFi Module** | **MEDIUM** - Modern networking, WiFi interface | **Year 6**: Advanced communication | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate**: Interface may work with 65C816 if generic serial. WiFi protocol concepts directly applicable. |

### Video/Audio Modules

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **RP2040 VGA Terminal** | **HIGH** - Video output, microcontroller co-processor, HDMI/VGA | **Year 6**: Video systems, co-processor design | ✅ **Compatible** - Microcontroller-based, communicates via serial/SPI | **Minimal**: Interface protocol (serial/SPI) is CPU-agnostic. Video concepts directly applicable. Excellent reference for Year 6 video co-processor approach. |
| **Pi Pico VGA Terminal** | **HIGH** - Video output, microcontroller co-processor | **Year 6**: Video systems | ✅ **Compatible** - Microcontroller-based | **Minimal**: Interface protocol CPU-agnostic. Video concepts directly applicable. |
| **SID-Ulator Sound Module** | **MEDIUM** - Audio output, sound synthesis | **Year 6**: Audio systems | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate**: Interface redesign needed. Audio synthesis concepts directly applicable. |
| **Why Em-Ulator Sound Module** | **MEDIUM** - Audio output, sound synthesis | **Year 6**: Audio systems | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate**: Interface redesign needed. Audio concepts directly applicable. |

### Utility/Development Modules

| Board/Module | Educational Value | Curriculum Fit | CPU Compatibility | Design Changes Required |
|-------------|------------------|----------------|-------------------|------------------------|
| **Prototype Module** | **HIGH** - Breadboard on PCB, experimentation | **Years 2-4**: Prototyping, experimentation | ✅ **Compatible** - Generic prototyping board | **None**: Prototype board is CPU-agnostic. Excellent for curriculum prototyping needs. |
| **TTL Logic Probe** | **MEDIUM** - Debugging tool, signal analysis | **Years 2-4**: Debugging, signal analysis | ✅ **Compatible** - Generic debugging tool | **None**: Logic probe is CPU-agnostic. Useful debugging tool. |
| **RomWriter Modules** | **LOW** - ROM programming, specialized tool | **Years 3-4**: ROM programming | ⚠️ **Needs Modification** - Interface likely Z80-specific | **Moderate**: Interface redesign needed. ROM programming concepts directly applicable. |

**⭐ QUICK WINS - Lab Projects for Throughout Course**: These utility/development modules are ideal as **early lab projects** that students build and use throughout the curriculum. They provide immediate practical value and reinforce learning across multiple years.

---

## Key Design Change Categories

### 1. Control Signal Changes

**Z80 Signals → 65C816 Equivalents**:
- `/MREQ` (Memory Request) → `VPA` (Valid Program Address) / `VDA` (Valid Data Address)
- `/IORQ` (I/O Request) → Memory-mapped I/O or VIA interface
- `/WR` (Write) → `R/W` (Read/Write, inverted)
- `/RD` (Read) → `R/W` (Read/Write)
- `M1` (Machine Cycle 1) → Not directly equivalent (65C816 has different cycle types)

**Impact**: All modules using Z80 control signals need address decoding logic redesign.

### 2. Address Bus Expansion

**Z80**: 16-bit address bus (64KB address space)  
**65C816**: 24-bit address bus (16MB address space)

**Impact**: 
- Address decoding logic needs expansion
- Memory mapping schemes need redesign
- I/O port addressing may move to memory-mapped I/O

### 3. I/O Port Addressing

**Z80**: Dedicated I/O port space (256 ports, accessed via `IN`/`OUT` instructions)  
**65C816**: Memory-mapped I/O (I/O devices appear as memory locations)

**Impact**:
- I/O port decoding logic needs complete redesign
- Port address schemes need conversion to memory addresses
- VIA (65C22) provides parallel I/O, ACIA (65C51) provides serial I/O

### 4. Bus Architecture

**RC2014 Standard Bus**: 40-pin bus (36 signals + power/ground)  
**65C816 System**: Needs 24-bit address + 16-bit data + control signals

**Impact**:
- Backplane bus design needs expansion for 24-bit address
- Enhanced bus concept directly applicable
- Power distribution and isolation techniques directly applicable

---

## Curriculum Integration Recommendations

### High Priority (Direct Educational Value)

1. **⭐ Quick Wins - Utility/Development Modules** - ✅ **Use as-is, implement as early lab projects**
   - **TTL Logic Probe**: Build in Year 2, use throughout curriculum
   - **Prototype Module**: Build in Year 2, use for experimentation
   - **RomWriter**: Build in Year 3, use for ROM programming
   - **Benefits**: CPU-agnostic, immediate utility, reinforce learning, build confidence
   - **See**: "Quick Wins: Utility/Development Modules as Lab Projects" section above

2. **Backplane Pro** - ✅ **Use as-is for design reference**
   - Years 2-4: PCB design patterns, bus architecture
   - Minimal changes needed (address bus expansion)

3. **Prototype Module** - ✅ **Use as-is**
   - Years 2-4: Prototyping and experimentation
   - No changes needed

4. **RP2040/Pi Pico VGA Terminal** - ✅ **Use as reference**
   - Year 6: Video co-processor approach
   - Interface protocol directly applicable

### Medium Priority (Good Educational Value, Needs Redesign)

1. **LCD Driver Module** - ⚠️ **Redesign for 65C816**
   - Years 3-4: I/O systems, LCD interfacing
   - Replace I/O port addressing with memory-mapped or VIA interface
   - HD44780 interface logic directly applicable

2. **64k RAM Module** - ⚠️ **Redesign for 65C816**
   - Years 3-4: Memory systems, address decoding
   - Replace Z80 control signals with 65C816 equivalents
   - Address decoding concepts directly applicable

3. **Digital I/O Module** - ⚠️ **Redesign for 65C816**
   - Years 3-4: I/O systems, parallel I/O
   - Replace with 65C22 VIA interface
   - I/O programming concepts directly applicable

### Low Priority (Specialized or Limited Value)

1. **Z80-Specific Modules** (CPU, Z80 Tester) - ❌ **Not applicable**
   - Z80 CPU modules have no direct curriculum value
   - Use only for understanding Z80 architecture (comparison)

2. **RomWriter Modules** - ⚠️ **Limited value**
   - Specialized tooling, may need interface redesign
   - ROM programming concepts applicable

---

## Design Modification Guidelines

### For Memory Modules

**Required Changes**:
1. Replace Z80 control signals (`/MREQ`, `/WR`, `/RD`) with 65C816 equivalents (`VPA`/`VDA`, `R/W`)
2. Expand address decoding for 24-bit address space
3. Update memory mapping for 65C816 memory map
4. Modify bank switching logic (if applicable) for 65C816 native banking

**Directly Applicable**:
- Address decoding principles
- Memory mapping concepts
- Bank switching concepts
- Jumper configuration patterns

### For I/O Modules

**Required Changes**:
1. Replace Z80 I/O port addressing (`!IORQ`, `M1`, port addresses) with 65C816 memory-mapped I/O
2. Use 65C22 VIA for parallel I/O (replaces dedicated I/O port modules)
3. Use 65C51 ACIA for serial I/O (replaces UART modules with I/O port addressing)
4. Redesign address decoding for memory-mapped I/O space

**Directly Applicable**:
- I/O programming concepts
- Device interface protocols (HD44780, etc.)
- Data buffering techniques
- Control signal generation

### For Backplanes

**Required Changes**:
1. Expand address bus from 16-bit to 24-bit
2. Update bus pinout for 65C816 signals
3. Maintain power distribution and isolation techniques

**Directly Applicable**:
- Bus architecture concepts
- Power management design
- Isolation techniques
- Modular design patterns
- Professional PCB design

---

## Quick Wins: Utility/Development Modules as Lab Projects

### Overview

The **Utility/Development Modules** (Prototype Module, TTL Logic Probe, RomWriter) are **quick wins** that can be implemented as early lab projects and used throughout the curriculum. These modules:

- ✅ **CPU-agnostic**: Work with any CPU architecture
- ✅ **Immediate value**: Provide practical tools students use regularly
- ✅ **Reinforce learning**: Used across multiple years, reinforcing concepts
- ✅ **Build confidence**: Early success builds student confidence
- ✅ **Practical skills**: Teach PCB design, soldering, debugging

### Prototype Module - Lab Project Integration

**When to Build**: **Year 2, Term 2** (Weeks 17-20, I/O Systems) or **Year 2, Term 3** (Weeks 25-28, Complex Program Execution)

**Learning Objectives**:
- Convert breadboard prototyping to PCB
- Design simple PCB with standard grid
- Solder components to PCB
- Use prototype board for experimentation

**Curriculum Integration**:
- **Year 2**: Build prototype module, use for logic circuit experiments
- **Year 3**: Use for SAP-1 module testing and debugging
- **Year 4**: Use for enhanced system module prototyping
- **Years 5-6**: Use for 65C816 system experimentation

**Educational Value**:
- ✅ **PCB Design**: Simple PCB layout (grid pattern, no complex routing)
- ✅ **Soldering Practice**: Through-hole components, good for skill building
- ✅ **Practical Tool**: Students use throughout curriculum for experiments
- ✅ **Confidence Building**: Early success with PCB fabrication

**Implementation**:
- Use RC2014 Prototype Module design as reference
- Adapt to curriculum needs (may need different grid size or connector)
- Can be built as first PCB project (simple design, high success rate)

### TTL Logic Probe - Lab Project Integration

**When to Build**: **Year 2, Term 2** (Weeks 17-20, I/O Systems) or **Year 3, Term 1** (Weeks 1-3, Review and SAP-1 Improvements)

**Learning Objectives**:
- Build debugging tool
- Understand digital signal levels (HIGH, LOW, floating)
- Use tool for circuit debugging
- Practice soldering and PCB assembly

**Curriculum Integration**:
- **Year 2**: Build logic probe, use for digital circuit debugging
- **Year 3**: Essential tool for SAP-1 debugging and troubleshooting
- **Year 4**: Use for enhanced system debugging
- **Years 5-6**: Use for 65C816 system debugging

**Educational Value**:
- ✅ **Debugging Tool**: Essential for hardware troubleshooting
- ✅ **Signal Understanding**: Teaches digital signal levels and states
- ✅ **Practical Skills**: Soldering, component identification, testing
- ✅ **Reinforcement**: Used throughout curriculum, reinforces debugging concepts

**Implementation**:
- Use RC2014 TTL Logic Probe design as reference
- Simple circuit (LEDs, resistors, comparators)
- Can be built as early project (high success rate, immediate utility)

### RomWriter Modules - Lab Project Integration

**When to Build**: **Year 3, Term 3** (Weeks 22-24, Machine Code Programming) or **Year 4, Term 1** (Weeks 1-3, Review and SAP-1 Improvements)

**Learning Objectives**:
- Build ROM programming tool
- Understand ROM programming process
- Program ROM chips with machine code
- Use for system development

**Curriculum Integration**:
- **Year 3**: Build RomWriter, program SAP-1 ROMs
- **Year 4**: Program enhanced system ROMs
- **Years 5-6**: Program 65C816 system ROMs

**Educational Value**:
- ✅ **ROM Programming**: Essential for system development
- ✅ **Tool Building**: Build practical development tool
- ✅ **System Integration**: Connects software development to hardware
- ✅ **Practical Skills**: Interface design, programming protocols

**Implementation**:
- Use RC2014 RomWriter design as reference
- May need interface redesign for 65C816 system (if using parallel interface)
- Can be built as intermediate project (moderate complexity, high utility)

### Lab Project Progression

**Year 2**:
1. **TTL Logic Probe** (Term 2) - First PCB project, debugging tool
2. **Prototype Module** (Term 2 or 3) - Second PCB project, experimentation board

**Year 3**:
3. **RomWriter** (Term 3) - ROM programming tool for SAP-1 development

**Ongoing Use**:
- All three tools used throughout remaining years
- Reinforces learning through practical application
- Builds student confidence and practical skills

### Benefits of Early Lab Projects

1. **Immediate Utility**: Students use tools they build, seeing immediate value
2. **Skill Building**: Early PCB projects build confidence for later complex projects
3. **Reinforcement**: Tools used across multiple years reinforce learning
4. **Practical Experience**: Hands-on experience with PCB design and assembly
5. **Debugging Skills**: Logic probe teaches essential debugging techniques
6. **System Development**: RomWriter enables practical system development

## Summary by Curriculum Year

### Year 2: PCB Fabrication Introduction
- ✅ **Backplane Pro** - Design reference, GERBER file analysis
- ✅ **TTL Logic Probe** - **LAB PROJECT**: Build debugging tool (Term 2, Weeks 17-20)
- ✅ **Prototype Module** - **LAB PROJECT**: Build prototyping board (Term 2 or 3)
- ✅ **Veroboard Backplane** - DIY approach reference

### Year 3: SAP-1 and Basic Systems
- ✅ **TTL Logic Probe** - **USE**: Essential debugging tool for SAP-1
- ✅ **Prototype Module** - **USE**: Module testing and experimentation
- ✅ **RomWriter** - **LAB PROJECT**: Build ROM programming tool (Term 3, Weeks 22-24)
- ⚠️ **64k RAM Module** - Memory systems (needs redesign)
- ⚠️ **LCD Driver Module** - I/O systems (needs redesign)
- ⚠️ **8k ROM Module** - Memory systems (needs redesign)
- ✅ **Backplane designs** - Bus architecture reference

### Year 4: Enhanced Systems
- ✅ **TTL Logic Probe** - **USE**: Enhanced system debugging
- ✅ **Prototype Module** - **USE**: Enhanced module prototyping
- ✅ **RomWriter** - **USE**: Program enhanced system ROMs
- ⚠️ **512k ROM/RAM Module** - Memory banking (needs redesign)
- ⚠️ **Digital I/O Module** - I/O systems (replace with VIA)
- ⚠️ **Front Panel Kit** - Advanced I/O (needs redesign)
- ✅ **Backplane Pro** - Multi-module system reference

### Year 5: 16-bit System Design
- ⚠️ **Memory modules** - Advanced memory systems (needs redesign)
- ⚠️ **Communication modules** - Serial I/O (needs redesign)
- ✅ **Backplane designs** - System architecture reference

### Year 6: Final System Integration
- ✅ **RP2040/Pi Pico VGA** - Video co-processor reference
- ⚠️ **Storage modules** - Mass storage (needs redesign)
- ⚠️ **Audio modules** - Audio systems (needs redesign)
- ✅ **Backplane Pro** - Professional PCB design reference

---

## Conclusion

**Primary Value**: RC2014 boards provide excellent **design pattern references** and **PCB design examples** for the curriculum, even when CPU-specific changes are needed.

**Key Takeaways**:
1. **Backplanes**: Highly valuable as-is for bus architecture and PCB design reference
2. **Memory Modules**: Concepts directly applicable, but need signal/address redesign
3. **I/O Modules**: Concepts applicable, but need interface redesign (VIA/ACIA)
4. **Video Modules**: Microcontroller-based modules directly applicable
5. **⭐ Quick Wins - Utility/Development Modules**: **Directly usable as-is** - Ideal as early lab projects (Year 2-3) that students build and use throughout the curriculum:
   - **TTL Logic Probe**: Essential debugging tool, build in Year 2
   - **Prototype Module**: Experimentation board, build in Year 2
   - **RomWriter**: ROM programming tool, build in Year 3
   - All three provide immediate utility and reinforce learning across multiple years

**Recommendation**: Use RC2014 designs as **educational references** and **design pattern sources**, adapting the concepts to 65C816 architecture rather than using boards directly.

---

**Document Created**: 2025-12-16  
**Source**: RC2014 scraped content analysis  
**Purpose**: Comprehensive curriculum fit analysis for all RC2014 boards/modules

