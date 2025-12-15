# Year 3, Term 2: SAP-1 Construction - Control Unit

## Overview

Term 2 of Year 3 focuses on building the control unit for the SAP-1 CPU. Students construct the program counter, instruction register, microcode ROM, and control signal generation to automate CPU operations.

## Learning Outcomes

By the end of Term 2, students will:
- Build the Program Counter (PC)
- Build the Instruction Register (IR)
- Build the microcode ROM system
- Generate control signals automatically
- Integrate control unit with data path
- Understand the fetch-decode-execute cycle

## Week Structure (Compressed: 12 weeks → 9 weeks)

**Note**: All content preserved, delivery compressed for efficiency.

### Weeks 10-12: Program Counter and Instruction Register (Compressed from 4 weeks)
- Build Program Counter (PC)
- Build Instruction Register (IR)
- Connect PC and IR to system
- Test instruction fetching
- Understand instruction format

### Weeks 13-15: Microcode ROM System (Compressed from 4 weeks)
- Design microcode format
- Build microcode ROM (using EEPROM)
- Program microcode for instructions
- Test microcode execution
- Verify control signal generation

### Weeks 16-18: Control Unit Integration (Compressed from 4 weeks)
- Integrate control unit with data path
- Implement fetch-decode-execute cycle
- Test instruction execution
- Debug control unit
- Verify complete CPU operation

## Materials

### Components
- Counters (74HC161/163) for PC
- Registers (74HC173) for IR
- EEPROMs (28C16 or similar) for microcode ROM
- Decoders for instruction decoding
- Logic gates for address formation
- Clock circuit (555 timer or oscillator)

### Tools
- EEPROM programmer (Arduino-based)
- Logic analyzer (highly recommended)
- Oscilloscope (optional)
- Multimeter

## Assessment

- **Formative**: Weekly module testing
- **Summative**: PC/IR subsystem project (Weeks 10-12)
- **Summative**: Microcode ROM project (Weeks 13-15)
- **Summative**: Control unit integration project (Weeks 16-18)
- **Final**: Complete control unit demonstration

## Prerequisites

Students must have completed Term 1 and understand:
- Complete data path (registers, ALU, memory, buses)
- Control signals and their functions
- State machines and sequencers (Year 2)
- Microcode concepts (Year 2)
- Instruction concepts

## Key Concepts

- **Program Counter**: Tracks current instruction address
- **Instruction Register**: Holds current instruction
- **Microcode ROM**: Stores control sequences
- **Fetch-Decode-Execute**: The CPU instruction cycle
- **Control Unit**: Automates CPU operations

## Milestones

- **Week 12**: PC and IR complete
- **Week 15**: Microcode ROM working
- **Week 18**: Complete control unit integrated

---

*Term 2 adds automatic control to create a working CPU*
