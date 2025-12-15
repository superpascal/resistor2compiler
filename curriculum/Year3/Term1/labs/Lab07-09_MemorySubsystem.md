# Lab 7-9: Memory Subsystem

## Lab Overview

In this lab, students will build the Memory Address Register (MAR), connect memory chip, implement address decoding, and integrate memory with the complete data path.

## Learning Objectives

- Build Memory Address Register (MAR)
- Connect memory chip to system
- Implement address decoding
- Test read/write operations
- Integrate memory with data path

## Prerequisites

- Completed Lab 5-8 (Registers and Buses)
- Understanding of memory concepts (Year 2)
- Understanding of MAR (Year 2)
- Understanding of address decoding

## Materials

### Components
- 74HC173 (4-bit register) for MAR
- Memory chip (74LS189 or 28C16 EEPROM)
- 74HC125 or 74HC244 (tri-state buffer)
- Address decoder (if needed)
- LEDs for address and data display
- Resistors (220Ω for LEDs)
- Arduino-based EEPROM programmer (if using EEPROM)

### Tools
- EEPROM programmer (if using EEPROM)
- Multimeter
- Logic probe (optional)

## Safety

- Handle memory chips carefully (ESD protection)
- Verify power connections
- Check for shorts

## Lab Sessions

### Session 1: Building the MAR (Week 9)

**Objective**: Construct Memory Address Register

**Steps**:
1. Place 74HC173 on breadboard
2. Connect power and ground
3. Connect data inputs (from bus or switches)
4. Connect clock and enable
5. Connect outputs to LEDs (address display)
6. Connect outputs to memory address pins (prepare)
7. Test: Load addresses, verify display
8. Verify address output

**Expected Result**: MAR loads and displays addresses correctly

**Troubleshooting**:
- If doesn't load: Check enable, check clock
- If address wrong: Check connections, verify binary
- If output wrong: Check connections to memory

### Session 2: Connecting Memory (Week 10)

**Objective**: Connect memory chip to system

**Steps**:
1. Place memory chip on breadboard
2. Connect power and ground
3. Connect MAR outputs to memory address pins
4. Connect memory data pins to bus (via tri-state)
5. Connect chip select (if needed)
6. Connect read/write enable
7. Test: Basic memory connection
8. Verify memory responds

**Expected Result**: Memory chip connected and responding

**Troubleshooting**:
- If memory doesn't respond: Check power, check connections
- If wrong data: Check address connections, verify memory contents
- If bus conflicts: Check tri-state enable, verify only one output

### Session 3: Memory Operations (Week 11)

**Objective**: Test read and write operations

**Steps**:
1. Program memory with test data (or use pre-programmed)
2. Test read: Set MAR, enable RO, read data
3. Verify data matches memory contents
4. Test write: Set MAR, put data on bus, enable WE
5. Read back to verify write
6. Test multiple addresses
7. Document read/write operations

**Expected Result**: Can read and write memory correctly

**Troubleshooting**:
- If read doesn't work: Check RO signal, check address
- If write doesn't work: Check WE signal, check data on bus
- If data wrong: Verify memory programming, check connections

### Session 4: Complete Data Path Integration (Week 12)

**Objective**: Integrate memory with complete data path

**Steps**:
1. Connect all components (registers, ALU, memory)
2. Test: Load from memory into Register A
3. Test: Load from memory into Register B
4. Test: Add A and B, store result
5. Test: Store result to memory
6. Test: Complete operation sequence
7. Verify complete data path
8. Document complete system

**Expected Result**: Complete data path integrated and working

**Troubleshooting**:
- If integration fails: Test each component, verify connections
- If data flow wrong: Trace data path, check each step
- If timing issues: Check clock, check signal coordination

## Assessment

### Practical Assessment
- Successfully build MAR
- Connect memory correctly
- Test read/write operations
- Integrate with data path
- Document complete system

### Lab Report
Students should document:
- MAR circuit diagram
- Memory connection diagram
- Read/write test results
- Complete data path diagram
- System verification

## Extension Activities

- Expand memory size
- Add address decoding for multiple chips
- Implement memory test routines
- Optimize memory access

## Next Lab

After completing this lab, students will move to Term 2: Control Unit construction.

---

*Memory completes the data path and enables program storage*
