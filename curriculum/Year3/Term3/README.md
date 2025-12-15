# Year 3, Term 3: SAP-1 Completion and Programming

## Overview

Term 3 of Year 3 focuses on completing the SAP-1 CPU, testing and debugging, programming in machine code, and running complete programs. Students bring up their 8-bit computer and use it.

## Learning Outcomes

By the end of Term 3, students will:
- Complete SAP-1 bring-up and testing
- Debug hardware and software issues systematically
- Program the CPU in machine code
- Run complete programs successfully
- Understand CPU operation at the lowest level
- Document complete SAP-1 system

## Week Structure (Compressed: 12 weeks → 9 weeks)

**Note**: All content preserved, delivery compressed for efficiency.

### Weeks 19-21: SAP-1 Bring-up and Testing (Compressed from 4 weeks)
- Complete system integration
- Initial bring-up procedures
- Systematic testing
- Hardware debugging
- Signal integrity verification

### Weeks 22-24: Machine Code Programming (Compressed from 4 weeks)
- **LCD Integration**: Connect 20×4 parallel LCD to SAP-1 output port
- SAP-1 instruction set
- Machine code programming
- Program development
- Program testing and debugging
- Running complete programs with LCD output

### Weeks 25-27: System Completion and Documentation (Compressed from 4 weeks)
- Final system testing
- Performance optimization
- Complete system documentation
- System presentation
- Year 3 portfolio completion

## Materials

### Components
- Complete SAP-1 system
- All components from Terms 1-2
- **Output display: Matrix Orbital LCD2041-GW-V-E (20×4 parallel LCD, REQUIRED)** or 7-segment/LEDs
  - **Part Number**: Matrix Orbital LCD2041-GW-V-E
  - **Interface**: Parallel 8-bit (HD44780-compatible)
  - **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
  - **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)
  - **See**: `../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for LCD integration guide
  - **Ben Eater Alignment**: Ben Eater's SAP-1 uses 2-row or 4-row LCD (we use 4-row for more display area)
- **LCD interface components** (if using LCD):
  - Tri-state buffers (74HC245)
  - Address decoder
  - Pull-up resistors (10kΩ)
  - Potentiometer (10kΩ) for contrast
- Debugging tools

### Tools
- Logic analyzer (highly recommended)
- Oscilloscope (optional)
- Multimeter
- Documentation materials

## Assessment

- **Formative**: Weekly testing and debugging
- **Summative**: Bring-up project (Weeks 19-21)
- **Summative**: Programming project (Weeks 22-24)
- **Final**: Complete SAP-1 demonstration and documentation
- **Final**: Year 3 portfolio

## Prerequisites

Students must have completed Terms 1-2 and have:
- Complete data path (Term 1)
- Complete control unit (Term 2)
- Understanding of CPU operation
- Understanding of instruction execution

## Key Concepts

- **System Bring-up**: Getting CPU working
- **Debugging**: Systematic problem-solving
- **Machine Code**: Programming at lowest level
- **Program Execution**: Running programs on CPU
- **System Documentation**: Professional documentation

## Milestones

- **Week 21**: SAP-1 bring-up complete
- **Week 24**: Programs running successfully
- **Week 27**: Complete SAP-1 system documented and presented

---

*Term 3 completes the SAP-1 and enables programming*
