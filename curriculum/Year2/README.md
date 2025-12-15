# Year 2: Computing Foundations & Physical Logic (Continued) (Age 14)

## Overview

Year 2 consolidates electronics knowledge and introduces memory and control concepts. Students build on Year 1 foundations to understand how computers store and process information.

## Learning Outcomes

By the end of Year 2, students will:
- Understand memory chips and data storage
- Build memory address registers
- Understand control signals and state machines
- Build simple sequencers
- Integrate all concepts into a "manual computer"
- Be ready to build a CPU in Year 3

## Year Structure

- **Term 1**: Advanced Logic and Memory Concepts (Weeks 1-12)
  - Weeks 1-4: Memory Concepts and Simple Storage
  - Weeks 5-8: Control Concepts and State Machines
  - Weeks 9-12: Integration and Review
- **Term 2**: Advanced Control Systems and I/O (Weeks 13-24)
  - Weeks 13-16: Advanced State Machines and Microcode
  - Weeks 17-20: Address Decoding and Memory Mapping
  - Weeks 21-24: Input/Output Systems
- **Term 3**: Advanced Integration and System Optimization (Weeks 25-36)
  - Weeks 25-28: Complex Program Execution
  - Weeks 29-32: System Optimization and Debugging
  - Weeks 33-36: Final Integration and Year 3 Preparation

## Directory Structure

Year 2 follows the standard term-based structure:

```
Year2/
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

### Term 1: Memory Concepts
- Memory chips (EEPROM, RAM)
- Memory Address Register (MAR)
- Reading and writing data
- Address decoding basics

### Term 2: Control Systems
- State machines
- Sequencers
- Control signal generation
- Microcode concepts (introduction)

### Term 3: Integration
- Manual computer construction
- Signal coordination
- Complete system understanding
- Preparation for CPU building

## Prerequisites

- Completed Year 1
- Understanding of:
  - Logic gates
  - Combinational circuits
  - Sequential circuits (flip-flops, counters)
  - Buses and tri-state buffers

## Assessment

- Formative: Weekly practical work
- Summative: Term projects
- Final: Manual computer demonstration

## Materials

- Memory chips (EEPROM, small RAM)
- Registers and latches
- Counters and decoders
- Control logic components
- Output display: **LCD character display (20×4 recommended)** or LEDs/7-segment displays
  - **See**: `../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for LCD integration (covers Year 2-4)
- **⭐ Quick Win Lab Projects** (build once, use throughout curriculum):
  - **TTL Logic Probe** (Term 2, Weeks 16-18): Essential debugging tool
  - **Prototype Module** (Term 3, Weeks 22-24): Experimentation board
  - **See**: `../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for design references

## Delivery

This year continues the hands-on, experimental approach from Year 1. Students should feel confident with hardware before moving to CPU construction.

## PCB Fabrication

**Breadboard → PCB Iterative Approach**: Starting in Term 2 or Term 3, students convert working breadboard circuits to permanent PCBs. This teaches industrialization early and makes student work permanent and reliable.

**See**: `PCB_FABRICATION_GUIDE.md` for detailed breadboard → PCB conversion activities.

**Rationale**: Breadboards are fragile and wires don't stay in place. Converting to PCBs creates permanent, reliable circuits and teaches professional engineering practices.

---

*Year 2 bridges foundational electronics (Year 1) and CPU construction (Year 3)*
