# Year 4: From SAP-1 to a More Powerful 8-bit System (Age 16)

## Overview

Year 4 enhances the SAP-1 computer and prepares for the transition to 16-bit architecture. Students learn to modify and improve existing designs.

## Learning Outcomes

By the end of Year 4, students will:
- Improve and debug the SAP-1
- Expand instruction set
- Expand memory capacity
- Understand Harvard architecture concepts
- Prepare for 16-bit systems

## Year Structure (Realigned for GCSE Exam Period)

**Critical**: Hardware must complete by Term 2 Week 27 (before GCSE exams)

- **Term 1**: SAP-1 Enhancements (Weeks 1-9, compressed from 1-12)
  - Weeks 1-3: Review and SAP-1 Improvements (compressed from 4 weeks)
  - Weeks 4-6: Expanded Instruction Set (compressed from 4 weeks)
  - Weeks 7-9: Memory Expansion and Harvard Architecture (compressed from 4 weeks)
- **Term 2**: Complete 16-bit Hardware (Weeks 10-27, expanded to include Term 3 hardware)
  - Weeks 10-12: Introduction to 65C816 CPU (compressed from 4 weeks)
  - Weeks 13-15: 65C816 System Design (compressed from 4 weeks)
  - Weeks 16-18: Breadboard Prototype Construction (compressed from 4 weeks)
  - Weeks 19-21: Memory Banking (moved from Term 3, compressed from 4 weeks)
  - Weeks 22-24: I/O Subsystems (moved from Term 3, compressed from 4 weeks)
  - Weeks 25-27: Graphics/Sound Selection (moved from Term 3, compressed from 4 weeks)
  - **Hardware Completion**: Week 27 ✅ (BEFORE GCSEs)
- **Term 3**: GCSE Exam Period (Weeks 28-36)
  - **NO CURRICULUM CONTENT** - Students focus on GCSE exams
  - Project on hold, resume Year 5 Term 1

## Directory Structure

Year 4 follows the standard term-based structure:

```
Year4/
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

### Term 1: Enhancements
- SAP-1 reliability improvements
- Expanded instruction set
- Memory expansion (4-bit to 8-bit addressing)
- Harvard architecture introduction

### Term 2: 16-bit Preparation
- Introduction to 65C816 CPU
- Architecture comparison (SAP-1 vs 65C816)
- System design planning
- Schematic capture

## Prerequisites

- Completed Year 3 (working SAP-1)
- Understanding of CPU architecture
- Experience with debugging

## Assessment

- Enhanced SAP-1 demonstration
- New instruction implementation
- System design documentation
- Architecture comparison essay

## PCB Fabrication

**Breadboard → PCB System Enhancement Conversion**: Starting in Term 1 or Term 2, students convert 8-bit system enhancement modules to production-quality DIY PCBs. This prepares students for professional manufacturing in Year 6.

**See**: `PCB_FABRICATION_GUIDE.md` for detailed enhancement module conversion activities.

**Rationale**: Enhanced system works but needs better reliability. Professional-quality DIY PCBs provide production-grade results and prepare students to appreciate professional manufacturing in Year 6.

**Methods**: Toner transfer (familiar) or UV photoresist (advanced, optional) with professional silk screening.

## Required Video Hardware Module

**Ben Eater VGA Project ("Worst Video Card Ever")**: **REQUIRED** foundational video hardware module. This project teaches video signal generation from first principles using discrete components, providing essential foundational knowledge before implementing TMS9918/V9938/V9958 VDP chips or Raspberry Pi Pico (RP2040/RP2350) video co-processor solutions in Year 6.

**See**: `BEN_EATER_VGA_ANALYSIS.md` for comprehensive analysis of how this project fits into the curriculum.

**Timing**: Term 2, Weeks 22-24 (I/O Subsystems) - **REQUIRED**, integrated into I/O Subsystems module.

**Rationale**: **Educational value is paramount**. Students must build a video card from discrete components, understanding video fundamentals from first principles before using IC video chips or microcontroller video solutions in Year 6. This foundational experience is essential for effective implementation and understanding of TMS9918/VDP or Raspberry Pi Pico video co-processors. This aligns with the curriculum's philosophy of building from first principles and eliminating black-box abstractions.

**Progression**: Year 4 Ben Eater VGA → Year 6 TMS9918/VDP or Raspberry Pi Pico video integration

## Output Display Progression

**Weeks 1-21**: Students continue using LCD character display from Year 3 for system output and debugging.

**Weeks 22-24**: Students build Ben Eater VGA project, which replaces LCD as primary video output.

**LCD Reference**: See `../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for LCD integration details.

## Input Device Progression

**Year 3**: Simple buttons for control (SAP-1) - ✅ **IMPLEMENTED**

**Year 4 (Optional)**: Matrix keypad for text/numeric input - ⚠️ **OPTIONAL ENHANCEMENT**
- **4×4 Matrix Keypad**: ~$3-5, connects to VIA I/O port
- **Educational Value**: Teaches matrix scanning, debouncing, I/O programming
- **When**: Term 2, Weeks 22-24 (I/O Subsystems) - **OPTIONAL**, if time permits
- **Reference**: See `../resources/MATRIX_KEYPAD_INTERFACE_GUIDE.md` for comprehensive guide
- **Note**: System works fine with buttons only. Keypad is valuable progression but not essential.

**Year 6**: PS/2 keyboard interface - ✅ **PLANNED**

**Input Reference**: See `../resources/KEYBOARD_INPUT_INTERFACE_ANALYSIS.md` for complete input device analysis.

---

*Year 4 bridges 8-bit (Year 3) and 16-bit (Year 5) systems*
