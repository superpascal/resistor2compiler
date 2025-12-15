# Year 3: CPU Construction (Age 15-16)

## Overview

Year 3 is where students build their first complete computer - the SAP-1 (Simple As Possible 1) 8-bit breadboard computer. This is the culmination of Years 1-2 foundations.

## Learning Outcomes

By the end of Year 3, students will:
- Build a complete 8-bit CPU from discrete components
- Understand the fetch-decode-execute cycle
- Program their computer in machine code
- Debug hardware and software issues
- Understand how CPUs work at the lowest level

## Year Structure (Compressed: 36 weeks → 27 weeks)

**Note**: All content preserved, delivery compressed for efficiency.

- **Term 1**: SAP-1 Construction - Data Path (Weeks 1-9, compressed from 1-12)
  - Weeks 1-3: Review and ALU Subsystem (compressed from 4 weeks)
  - Weeks 4-6: Register File and Buses (compressed from 4 weeks)
  - Weeks 7-9: Memory Subsystem (compressed from 4 weeks)
- **Term 2**: SAP-1 Construction - Control Unit (Weeks 10-18, compressed from 13-24)
  - Weeks 10-12: Program Counter and Instruction Register (compressed from 4 weeks)
  - Weeks 13-15: Microcode ROM System (compressed from 4 weeks)
  - Weeks 16-18: Control Unit Integration (compressed from 4 weeks)
- **Term 3**: SAP-1 Completion and Programming (Weeks 19-27, compressed from 25-36)
  - Weeks 19-21: SAP-1 Bring-up and Testing (compressed from 4 weeks)
  - Weeks 22-24: Machine Code Programming (compressed from 4 weeks)
  - Weeks 25-27: System Completion and Documentation (compressed from 4 weeks)

## Directory Structure

Year 3 follows the standard term-based structure:

```
Year3/
├── README.md                    # This file
├── Term1/
│   ├── theory/                 # Theoretical content
│   ├── labs/                   # Practical lab work
│   ├── teaching/              # Teaching guides
│   ├── reading/               # Student reading materials
│   ├── worksheets/             # Practice worksheets
│   ├── assessments/            # Assessment rubrics
│   └── resources/              # Additional resources
├── Term2/
│   └── [same structure]
└── Term3/
    └── [same structure]
```

## Key Topics

### Term 1: Data Path
- Review and integrate Year 1-2 concepts
- Build ALU subsystem
- Build register file
- Build memory subsystem
- Build bus system

### Term 2: Control Unit
- Build program counter
- Build instruction register
- Build microcode ROM
- Build control signal generation
- Integrate control with data path

### Term 3: Complete System
- Bring-up and testing
- Programming in machine code
- Running programs
- Debugging techniques
- System documentation

## Prerequisites

- Completed Years 1-2
- Solid understanding of:
  - All logic gates and circuits
  - Sequential logic
  - Memory concepts
  - Control signals

## Assessment

- Weekly module testing
- Term projects (data path, control unit)
- Final: Working SAP-1 running programs
- Portfolio: Complete documentation

## Materials

- All components from Years 1-2
- Additional: EEPROMs for microcode
- Program memory (EEPROM or RAM)
- **⭐ Quick Win Lab Projects** (from Year 2, used here):
  - **TTL Logic Probe**: Essential debugging tool for SAP-1 troubleshooting
  - **Prototype Module**: Experimentation board for module testing
- **⭐ Quick Win Lab Project** (build in Term 3):
  - **RomWriter** (Term 3, Weeks 22-24): ROM programming tool for SAP-1 development
  - **See**: `../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for design reference
- Output display: **Matrix Orbital LCD2041-GW-V-E (20×4 parallel LCD, REQUIRED)** or 7-segment/LEDs
  - **Part Number**: Matrix Orbital LCD2041-GW-V-E
  - **Interface**: Parallel 8-bit (HD44780-compatible)
  - **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
  - **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)
  - **See**: `../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for LCD integration guide
  - **Ben Eater Alignment**: Ben Eater's SAP-1 uses 2-row or 4-row LCD (we use 4-row for more display area)

## Resources

- Ben Eater's SAP-1 videos (if available offline)
- SAP-1 schematics
- Microcode listings
- Example programs
- `PCB_FABRICATION_GUIDE.md` - Guide for converting SAP-1 modules from breadboard to PCB
- `../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` - Guide for LCD character display output (recommended for SAP-1)
- `../resources/LCD_TECHNOLOGY_EDUCATION.md` - Comprehensive educational material on LCD technology, signaling, ASCII, and programming (Assembly and Pascal examples)
- `../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` - RC2014 boards analysis, including quick-win lab projects (TTL Logic Probe, Prototype Module, RomWriter)

## PCB Fabrication

**Breadboard → PCB Module Conversion**: Starting in Term 1 or Term 2, students convert SAP-1 breadboard modules to permanent PCBs. This makes the SAP-1 system more reliable and teaches system integration with PCBs.

**See**: `PCB_FABRICATION_GUIDE.md` for detailed module conversion activities.

**Rationale**: SAP-1 on breadboard is fragile (many wires, connections fail). Converting key modules to PCBs creates a reliable system and teaches industrialization.

**Ben Eater Integration**: Students watch Ben Eater SAP-1 videos for breadboard construction, then convert those breadboard designs to PCBs.

## Milestones

- **Week 9**: Data path complete and tested
- **Week 18**: Control unit complete
- **Week 27**: Complete SAP-1 running programs (with PCB modules for reliability)

---

*Year 3 produces a working 8-bit computer - a major achievement!*
