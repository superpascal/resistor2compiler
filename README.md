# Resistor → Compiler  
## A 6-Year, From-First-Principles Computer Science & Engineering Curriculum

**Resistor2Compiler** is an open educational initiative that takes students from **zero electronics knowledge** to building a **working 16-bit computer and game console**, capable of running **SuperPascal programs**, over a structured **6-year (High school fresher → GCSE → A-Level)** journey.

The project is intentionally **offline-first**, **hardware-centric**, and **transparent**, designed to teach *how computers actually work* — not just how to use them.

> From resistors and logic gates  
> → to CPUs and memory  
> → to assembly language  
> → to Pascal runtimes  
> → to compiler internals

---

## 🎯 Project Goals

- Teach **computer science from first principles**
- Eliminate black-box abstractions unsuitable for school-age learners, even at the detriment of performance.
  - This means **NO FPGA's**
  - Everything they use, will be build by them.
  - Students will build initial versions of IC's.
  - The only black box will be:
    - MOS 65C816
    - Complex IC's (Sound, Midi,  Video)
- Integrate **electronics, systems programming, and algorithms**
- Produce students who understand:
  - how software maps to hardware
  - how compilers translate languages
  - how real systems are architected under constraints

This is **not** a “learn to code” course.

It is a **learn how computers are built and programmed** curriculum.

---

## 🧱 What Students Build

By the end of the 6-year program, students will have built:

### Final System (Year 6)
- A **16-bit computer / game console** based on the **MOS 65C816**
- **Hardware** (fabricated on professional PCBs):
  - 65C816 CPU with 24-bit addressing (up to 16 MB)
  - RAM, ROM, address decoding
  - Video output (TMS9918/V9938/V9958 VDP or microcontroller solution)
  - Sound (YM2149F PSG or SAM2695 MIDI synthesizer)
  - Input devices (PS/2 keyboard, gamepad controllers)
  - Mass storage (SD card interface)
- **Software Stack**:
  - Enhanced ROM monitor with advanced debugging (breakpoints, disassembly)
  - Boot loader for SD card program loading
  - Device drivers (video, audio, input, storage)
  - System services API
  - Interrupt handlers
  - Memory management
  - Assembler and toolchain
  - SuperPascal runtime (from Year 5)
  - Complete system integration

**Note**: SuperPascal compiler development runs in parallel as a separate project. Year 6 focuses on system-level programming that makes the hardware functional.

Students **run their own programs** on a machine they physically built, from resistors to a complete computer system.

---

## 🧠 What Is Actually Taught on the Advanced Side

This curriculum teaches **foundational and advanced algorithms**, including:

- Graph algorithms (A* pathfinding)
- Finite State Machines (FSMs)
- Behavior Trees
- Rule engines & decision tables
- Deterministic simulation systems
- Fixed-point numerical methods
- Small neural networks as *numerical systems*, not black boxes

These are taught as **algorithms and decision systems**.

---

## 🧩 Hardware Architecture (Final System)

The final system (Year 6) uses a **Harvard-inspired architecture** with the **MOS 65C816** as the main CPU:

### Core Components
- **65C816** — main CPU (16-bit, 24-bit addressing, up to 16 MB)
- **Memory**: Separate program ROM and data RAM (Harvard architecture)
- **Video**: TMS9918/V9938/V9958 VDP or microcontroller solution
- **Audio**: YM2149F PSG or SAM2695 MIDI synthesizer
- **Input**: PS/2 keyboard, gamepad controllers
- **Storage**: SD card interface (SPI)

### Architecture Decisions
- **Harvard-inspired**: Separate program ROM and data RAM for security and clarity
- **65C816 CPU**: Modern availability, educational value, 16-bit capabilities
- **Pascal as Primary Language**: Structured, readable, educational
- **Assembly for System Programming**: Monitor, drivers, system services

All components are programmable using **assembly and Pascal**, preserving transparency and educational value.

---

## 📚 Curriculum Structure

The curriculum is structured as a **6-year progression** (Ages 13-18: Pre-GCSE → GCSE → A-Level):

### Year 1 (Age 13) — Foundations
- Electronics safety & lab discipline
- Resistors, capacitors, 555 timers
- Logic gates & Boolean algebra
- Adders, registers, buses
- Sequential logic (flip-flops, counters)
- Optional: Practical Electronics workshops

### Year 2 (Age 14) — Computing Foundations
- Memory concepts and storage
- Control concepts and state machines
- Address decoding and memory mapping
- I/O systems
- **PCB Fabrication Introduction**: Convert working breadboard circuits to permanent PCBs (breadboard → PCB iterative approach)

### Year 3 (Age 15) — CPU Construction
- Build SAP-1-inspired 8-bit breadboard computer
- Instruction cycle (fetch/decode/execute)
- Microcode & control logic
- Machine code programming
- **PCB Module Conversion**: Convert SAP-1 breadboard modules to PCBs for reliability (register, counter, ALU, memory interface modules)

### Year 4 (Age 16) — System Enhancement
- Enhance and improve SAP-1
- Expand instruction set
- Memory expansion and Harvard architecture concepts
- Transition to 16-bit architecture (65C816 introduction)
- 16-bit system design and breadboard prototype
- **Advanced PCB Conversion**: Convert system enhancement modules to production-quality DIY PCBs (memory expansion, I/O interface, optional video/audio)

### Year 5 (Age 17) — 16-bit System Development
- Complete 16-bit 65C816 system on breadboard
- Memory banking and addressing
- I/O subsystems integration
- **Software Development**:
  - Basic monitor program
  - Assembler and toolchain
  - Pascal runtime
  - Compiler implementation (SuperPascal)

### Year 6 (Age 18, A-Level) — Final System & System Programming
- **Term 1**: Professional PCB fabrication (PCBWay/JLCPCB), assembly, and hardware integration
- **Term 2**: System-level programming:
  - Enhanced monitor with advanced debugging
  - Boot loader for SD card program loading
  - Device drivers (video, audio, input, storage)
  - System services API
  - Interrupt handlers
  - Memory management
  - Complete system integration
- **Capstone**: Complete, functional 16-bit computer system with full software stack


---

## 🛠️ Repository Purpose

This repository exists to:

- Define the **technical and curricular backbone**
- Document hardware and software architectures
- Provide reference designs, specifications, and teaching materials
- Coordinate development of:
  - hardware schematics
  - firmware
  - toolchains
  - SuperPascal integration
  - educational documentation

It is **not** a single codebase, but a **systems-level project**.

---

## 🔒 Offline-First Philosophy

The project is designed for environments where:

- students do **not** have unrestricted Internet access
- learning happens through **direct interaction**, not AI tooling
- documentation is printable and inspectable
- progress depends on understanding, not copy-paste

This aligns with:
- parental expectations
- school policies
- long-term educational sustainability

---

## 🎓 Intended Audience

- Secondary school students (13–18 year olds) in advanced tracks
- Teachers of:
  - computer science
  - electronics
  - physics
- University faculty evaluating incoming students
- Developers interested in educational systems & retro-modern computing

---

## 🤝 How This Relates to SuperPascal

**Resistor2Compiler** is the **hardware and systems foundation** for:

- **SuperPascal**, a modernized Pascal dialect for education
- Its runtime, compiler, and system libraries

SuperPascal is used because:
- it is structured
- readable
- statically typed
- historically linked to computer science education
- suitable for compiler study

---

## 🚧 Project Status

- **Curriculum Structure**: ✅ Complete (6-year roadmap defined)
- **Year 1-4 Content**: ✅ Complete (theory, labs, teaching guides)
- **Year 5 Content**: ✅ Complete (monitor, assembler, runtime, compiler)
- **Year 6 Content**: ✅ Complete (PCB fabrication, system programming)
- **PCB Fabrication Integration**: ✅ Complete (breadboard → PCB approach for Years 2-4)
- **Malvino Book Alignment**: ✅ Complete (Years 4-5 excellent alignment)
- **Hardware Designs**: 🔄 In progress
- **Toolchains & Runtime**: 🔄 In development
- **Teaching Materials**: ✅ Comprehensive (theory, teaching guides, labs for all years)

**Current Focus**: Corrections, optimizations for readability and understanding. Major structural updates complete.

---

## 📜 License & Ethos

This project is developed for **educational use**, openness, and long-term maintainability.

The goal is not commercial lock-in, but:
- understanding
- reproducibility
- knowledge transfer

---

## 📎 Key Resources

### Curriculum Documents
- **Main Roadmap**: `background/BuildYourOwn_16-bitSuperPascalComputer_4-YearCurriculumRoadmap.md` (6-year curriculum)
- **PCB Fabrication**: 
  - `curriculum/PCB_FABRICATION_INTEGRATION_PLAN.md` (integration plan)
  - `curriculum/Year6/PCB_FABRICATION_APPROACHES.md` (methods and approaches)
  - `curriculum/Year2/PCB_FABRICATION_GUIDE.md` (Year 2 guide)
  - `curriculum/Year3/PCB_FABRICATION_GUIDE.md` (Year 3 guide)
  - `curriculum/Year4/PCB_FABRICATION_GUIDE.md` (Year 4 guide)

### Year-Specific Resources
- **Year 1**: `curriculum/Year1/` (foundations, optional workshops)
- **Year 2**: `curriculum/Year2/` (computing foundations, PCB introduction)
- **Year 3**: `curriculum/Year3/` (SAP-1 construction, module PCBs)
- **Year 4**: `curriculum/Year4/` (system enhancement, advanced PCBs)
- **Year 5**: `curriculum/Year5/` (16-bit system, software development)
- **Year 6**: `curriculum/Year6/` (PCB fabrication, system programming)

### Reference Materials
- **Malvino Book Alignment**: `docs/MALVINO_BOOK_CURRICULUM_ALIGNMENT.md`
- **Video/Audio Hardware**: `curriculum/Year6/VIDEO_AUDIO_HARDWARE_REFERENCE.md`
- **SuperPascal Language**: https://github.com/superpascal/superpascal (parallel project)

---

## 🎓 Key Pedagogical Features

### Breadboard → PCB Iterative Approach
Starting in Year 2, students convert working breadboard circuits to permanent PCBs:
- **Year 2**: Simple circuits (logic gates, LED flashers, counters)
- **Year 3**: SAP-1 modules (register, counter, ALU, memory interface)
- **Year 4**: System enhancements (memory expansion, I/O interface)
- **Year 6**: Professional PCB manufacturing (complete 16-bit system)

**Why**: Breadboards are fragile and wires don't stay in place. Converting to PCBs teaches industrialization early and makes student work permanent and reliable.

### Progressive Complexity
- **Years 1-2**: Foundations (electronics, logic, memory concepts)
- **Year 3**: Complete 8-bit computer (SAP-1)
- **Year 4**: System enhancements and 16-bit preparation
- **Year 5**: 16-bit system development and software
- **Year 6**: Professional manufacturing and system programming

### Integration with Educational Resources
- **Malvino & Brown "Digital Computer Electronics"**: Primary textbook for Years 1-4, conceptual reference for Years 5-6
- **Ben Eater SAP-1 Videos**: Reference for Year 3 breadboard construction (then converted to PCBs)
- **Practical Electronics for Inventors**: Optional workshops for Year 1

---

## ✨ Final Note

Resistor2Compiler is based on a simple belief:

> **Students should understand the machines they program.**

If you share that belief, you’re in the right place.
