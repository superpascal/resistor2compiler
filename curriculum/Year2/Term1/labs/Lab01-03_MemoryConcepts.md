# Lab 1-3: Memory Concepts and Simple Storage

## Lab Overview

In this lab, students will build a memory subsystem with a Memory Address Register (MAR) and learn to read and write data to memory chips.

## Learning Objectives

- Build a Memory Address Register (MAR) from registers
- Connect memory chips to the system bus
- Read data from memory
- Write data to memory
- Understand address decoding basics

## Prerequisites

- Completed Year 1 labs
- Understanding of registers and buses
- Understanding of tri-state buffers

## Materials

### Components
- 2× 74HC173 (4-bit registers) for MAR
- 1× 74LS189 (64-bit RAM) or 28C16 EEPROM
- 1× 74HC125 or 74HC244 (tri-state buffers)
- DIP switches (for address input)
- LEDs (for address and data display)
- Resistors (220Ω for LEDs, 10kΩ pull-ups)
- Breadboards and jumper wires

### Tools
- Multimeter
- Logic probe (optional)
- Arduino-based EEPROM programmer (if using EEPROM)

## Safety

- Always double-check power connections before applying power
- Ensure correct polarity for all components
- Use current-limiting resistors for LEDs
- Work on ESD-safe surface when handling memory chips

## Lab Sessions

### Session 1: Building the MAR (Week 1)

**Objective**: Construct an 8-bit Memory Address Register

**Steps**:
1. Place two 74HC173 registers on breadboard
2. Connect power (VCC to 5V, GND to ground)
3. Connect register outputs together to form 8-bit output
4. Connect DIP switches to register inputs (for manual address entry)
5. Connect register clock inputs together
6. Add LEDs to display 8-bit address value
7. Test: Set switches, clock register, verify LEDs show address

**Expected Result**: 8-bit address value displayed on LEDs, can be loaded from switches

**Troubleshooting**:
- If LEDs don't light: Check power, check resistor values
- If address doesn't load: Check clock connection, check enable pins
- If values wrong: Check switch connections, verify binary input

### Session 2: Connecting Memory and Reading (Week 2 - Combined)

**Objective**: Connect memory chip, verify operation, and read data from memory

**Steps**:
1. Place memory chip (74LS189 or 28C16) on breadboard
2. Connect power and ground
3. Connect MAR outputs to memory address pins
4. Connect memory data pins to bus (via tri-state buffer)
5. Connect tri-state buffer enable to control signal
6. Add LEDs to bus to display data
7. Test: Set address in MAR, enable memory output, verify data appears
8. Program memory with known data (use EEPROM programmer or pre-programmed chip)
9. Set MAR to address 0x00
10. Enable memory output (RO signal)
11. Observe data on bus LEDs
12. Change MAR to different addresses
13. Read and record data from multiple addresses
14. Verify data matches what was programmed

**Expected Result**: Memory connected and can read different data values from different addresses

**Troubleshooting**:
- If no data appears: Check address connections, check enable signal
- If wrong data: Check address value, verify memory contents, check memory programming
- If bus conflicts: Ensure only one output enabled at a time
- If same data at all addresses: Check address connections

### Session 3: Writing to Memory (Week 3)

**Objective**: Write data to memory locations

**Steps**:
1. Set MAR to target address
2. Put data value on bus (from switches or register)
3. Assert write enable signal (WE)
4. Verify write operation completes
5. Read back written data to verify
6. Write to multiple addresses
7. Read back all addresses to verify writes

**Expected Result**: Can write data to memory and read it back correctly

**Troubleshooting**:
- If write doesn't work: Check write enable signal, check timing
- If data doesn't persist: Check if using RAM (volatile) vs EEPROM
- If wrong address written: Check MAR value, check address connections

## Assessment

### Practical Assessment
- Successfully build MAR and display address
- Connect memory and read data correctly
- Write data to memory and verify
- Document read/write operations with timing

### Lab Report
Students should document:
- Circuit diagrams
- Address and data values observed
- Timing diagrams (if using logic analyzer)
- Any issues encountered and solutions
- Reflection on how memory operations work

## Extension Activities

- Build address decoder to select between multiple memory chips
- Implement memory-mapped I/O concept
- Create a simple memory test routine
- Explore different memory types (RAM vs EEPROM vs ROM)

## Next Lab

After completing this lab, students will move to control concepts and state machines (Lab 4-6).

---

*Memory is the foundation of computer storage*
