# Week 13-15: Microcode ROM System - Theory

## Learning Objectives

By the end of this week-block, students will:
- Design microcode format for SAP-1
- Build microcode ROM using EEPROM
- Program microcode for instructions
- Understand microcode execution
- Generate control signals automatically

## Prerequisites

- Completed Weeks 10-12 (PC and IR)
- Understanding of microcode concepts (Year 2)
- Understanding of EEPROM programming
- Understanding of instruction format

## Key Concepts

### 1. Microcode for SAP-1

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

### 2. Microcode Format Design

**Address formation**:
- Upper bits: Instruction opcode (from IR)
- Lower bits: Microstep counter
- Example: 4-bit opcode + 2-bit step = 6-bit address

**Data format**:
- Each bit = one control signal
- 8-bit EEPROM = 8 control signals
- Multiple EEPROMs = more signals
- Example: 2 EEPROMs = 16 control signals

**Control signal mapping**:
- Bit 0: MI (MAR In)
- Bit 1: RO (RAM Out)
- Bit 2: RI (RAM In / Write Enable)
- Bit 3: IO (Instruction Out / IR to bus)
- Bit 4: II (Instruction In)
- Bit 5: AI (A In)
- Bit 6: AO (A Out)
- Bit 7: EO (Enable Out / ALU output)
- (Additional signals in second EEPROM)

### 3. Building Microcode ROM

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

**Data output**:
- EEPROM data pins → control signals
- Each bit drives one signal
- May need buffers/drivers
- Signals control CPU components

### 4. Microstep Counter

**Microstep counter function**:
- Tracks progress through microcode sequence
- Increments each clock cycle
- Resets when instruction complete
- Provides step bits for microcode address

**Counter construction**:
- Use 74HC161 or 74HC163
- 2-3 bits (4-8 microsteps per instruction)
- Reset when instruction done
- Clock advances steps

**Counter control**:
- Clock: Advances to next step
- Reset: Returns to step 0
- Enable: Controls counting
- Output: Step number to microcode address

### 5. Microcode Programming

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

**Microcode table example**:
```
Address  Control Signals
000000   CO MI (LDA step 0)
000001   RO II (LDA step 1)
000010   (decode)
000011   CO MI (LDA step 3)
000100   RO AI (LDA step 4)
...
```

### 6. Instruction Decoding

**Decoding process**:
1. IR holds instruction
2. Extract opcode (upper 4 bits)
3. Opcode → microcode address upper bits
4. Microstep counter → address lower bits
5. Complete address → EEPROM
6. EEPROM outputs control signals

**Decoding logic**:
- IR opcode directly to EEPROM address
- No complex decoding needed
- Simple and effective
- Easy to understand

### 7. Microcode Execution

**Execution flow**:
1. Instruction in IR
2. Opcode addresses microcode
3. Microstep counter starts at 0
4. EEPROM outputs control signals
5. CPU components respond
6. Counter increments
7. Next microstep executes
8. Repeat until instruction complete

**Control signal generation**:
- Automatic from microcode
- No manual switches needed
- Coordinated by clock
- Reliable and fast

### 8. Testing Microcode

**Test procedures**:
- Program microcode for one instruction
- Load instruction into IR
- Run microcode sequence
- Verify control signals
- Verify instruction execution
- Test with multiple instructions

**Verification**:
- Control signals match microcode
- Instruction executes correctly
- All steps complete
- Ready for integration

## Mathematical Foundations

### Address Space

**6-bit address**: 2^6 = 64 locations
- 4-bit opcode (16 instructions) × 4 microsteps = 64
- Sufficient for SAP-1
- Can expand if needed

### Control Signal Count

**SAP-1 control signals**: ~12-16 signals
- Need 2 EEPROMs (16 signals)
- Or optimize to fit in 1 EEPROM (8 signals)
- Depends on design choices

## Common Misconceptions

1. **"Microcode is programming"**
   - Clarify: It's a lookup table
   - Show address → data mapping

2. **"Microcode is complex"**
   - Clarify: Simple format, straightforward
   - Show basic example

3. **"Need many EEPROMs"**
   - Clarify: 1-2 EEPROMs sufficient
   - Show signal count calculation

## Connections to Weeks 10-12

- **IR**: Provides opcode for microcode
- **PC**: Used during fetch (in microcode)
- **Instruction Format**: Determines microcode structure

## Connections to Weeks 21-24

- **Control Unit**: Microcode is core of control unit
- **CPU Integration**: Microcode controls entire CPU
- **Instruction Execution**: Microcode executes instructions

## Next Steps

After building microcode ROM, students will:
- Integrate control unit with data path (Weeks 21-24)
- Test complete CPU
- Execute first programs
- Debug CPU operation

---

*Microcode automates control signal generation*
