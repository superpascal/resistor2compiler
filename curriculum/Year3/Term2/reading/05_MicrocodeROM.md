# Chapter 5: Microcode ROM System

## Introduction

Microcode stores control sequences in ROM. This chapter explains how to build the microcode ROM system that automates control signal generation for the SAP-1 CPU.

## Microcode for SAP-1

**What is microcode?**
- Low-level control sequences
- Stored in ROM
- Each instruction has microcode sequence
- Generates control signals automatically

**SAP-1 microcode**:
- Stored in EEPROM
- Address = instruction opcode + microstep
- Data = control signals for that step
- Multiple EEPROMs for more signals

**Why microcode?**
- Flexible: Easy to change instructions
- Organized: All sequences in one place
- Scalable: Easy to add instructions
- Professional: How real CPUs work

## Microcode Format Design

**Address formation**:
- Upper bits: Instruction opcode (from IR)
- Lower bits: Microstep counter
- Example: 4-bit opcode + 2-bit step = 6-bit address

**Data format**:
- Each bit = one control signal
- 8-bit EEPROM = 8 control signals
- Multiple EEPROMs = more signals

**Control signal mapping**:
- Bit 0: MI (MAR In)
- Bit 1: RO (RAM Out)
- Bit 2: RI (RAM In / Write Enable)
- Bit 3: IO (Instruction Out)
- Bit 4: II (Instruction In)
- Bit 5: AI (A In)
- Bit 6: AO (A Out)
- Bit 7: EO (Enable Out / ALU output)

## Building Microcode ROM

**EEPROM selection**:
- 28C16 (2KB) or similar
- Enough for microcode
- Programmable
- Non-volatile

**Address formation circuit**:
- IR opcode (4 bits) → EEPROM address upper bits
- Microstep counter (2-3 bits) → EEPROM address lower bits
- Logic gates combine them
- Form 6-7 bit address

## Microcode Programming

**Microcode for LDA (Load A)**:
- Step 0: CO, MI (fetch instruction address)
- Step 1: RO, II (load instruction)
- Step 2: (decode - automatic)
- Step 3: CO, MI (fetch data address)
- Step 4: RO, AI (load data into A)
- Step 5: (complete)

**Programming process**:
1. Design microcode for each instruction
2. Create microcode table
3. Program EEPROM with microcode
4. Test instruction execution
5. Verify control signals

## Microcode Execution

**Execution flow**:
1. Instruction in IR
2. Opcode addresses microcode
3. Microstep counter starts at 0
4. EEPROM outputs control signals
5. CPU components respond
6. Counter increments
7. Next microstep executes
8. Repeat until instruction complete

## Practice Questions

1. What is microcode?
2. How is microcode address formed?
3. How does microcode generate signals?
4. How do we program microcode?
5. How does microcode execute?

## Key Takeaways

- Microcode stores control sequences
- Address = opcode + microstep
- Data = control signals
- Microcode automates control
- This is how real CPUs work

---

*Microcode automates control signal generation*
