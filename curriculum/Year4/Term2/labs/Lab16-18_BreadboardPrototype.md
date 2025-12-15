# Lab 16-18: Breadboard Prototype Construction

## Lab Overview

In this lab, students will build a minimal 65C816 system on breadboard, test essential functions, and verify CPU operation.

## Learning Objectives

- Build minimal 65C816 system
- Connect CPU, memory, and basic I/O
- Test reset and clock circuits
- Test basic memory access
- Verify CPU operation

## Prerequisites

- Completed Lab 17-20 (System Design)
- Complete system design
- Understanding of 65C816 architecture
- Understanding of system components

## Materials

### Components
- 65C816 CPU (DIP or PLCC with adapter)
- SRAM (32KB or 64KB)
- EEPROM/ROM for monitor
- 65C22 VIA (one for prototype)
- Clock oscillator (1 MHz)
- Reset circuit components
- Address decoders
- Decoupling capacitors

### Tools
- Breadboards (multiple)
- Logic analyzer (essential)
- Oscilloscope (highly recommended)
- Multimeter
- EEPROM programmer

## Safety

- Handle CPU carefully (ESD protection)
- Verify power before applying
- Check for shorts
- Monitor for overheating

## Lab Sessions

### Session 1: Power, Clock, and Reset (Week 21)

**Objective**: Get CPU powered, clocked, and resetting

**Steps**:
1. Place 65C816 on breadboard
2. Connect power and ground
3. Add decoupling capacitors
4. Connect clock oscillator
5. Build reset circuit
6. Test power supply
7. Test clock signal
8. Test reset circuit

**Expected Result**: CPU powered, clocked, and resetting

**Troubleshooting**:
- If power issues: Check connections, check supply
- If clock wrong: Check oscillator, check connections
- If reset fails: Check reset circuit, check CPU

### Session 2: Memory Connection (Week 22)

**Objective**: Connect and test memory

**Steps**:
1. Place SRAM on breadboard
2. Connect address bus
3. Connect data bus
4. Connect control signals
5. Implement address decoding
6. Test RAM access
7. Program ROM with test code
8. Test ROM access

**Expected Result**: Memory connected and accessible

**Troubleshooting**:
- If memory doesn't work: Check connections, check decoding
- If addresses wrong: Check address bus, check MAR
- If data wrong: Check data bus, verify memory

### Session 3: Basic I/O and Integration (Week 23)

**Objective**: Connect basic I/O and integrate system

**Steps**:
1. Place VIA on breadboard
2. Connect to address/data buses
3. Implement I/O address decoding
4. Connect basic I/O (LEDs)
5. Test I/O access
6. Integrate all components
7. Test complete system
8. Verify integration

**Expected Result**: Complete system integrated

**Troubleshooting**:
- If I/O doesn't work: Check connections, check decoding
- If integration fails: Test each component, verify connections
- If system issues: Debug systematically

### Session 4: CPU Verification (Week 24)

**Objective**: Verify CPU operation

**Steps**:
1. Program simple test in ROM
2. Reset CPU
3. Monitor address lines
4. Verify reset vector access
5. Verify instruction execution
6. Test memory access
7. Test I/O access
8. Document prototype

**Expected Result**: CPU showing signs of life and executing instructions

**Troubleshooting**:
- If CPU doesn't respond: Check reset, check clock, check power
- If execution fails: Check ROM programming, check connections
- If issues persist: Review design, get help

## Assessment

### Practical Assessment
- Successfully build prototype
- Connect all components
- Test essential functions
- Verify CPU operation
- Document prototype

### Lab Report
Students should document:
- Prototype construction
- Test results
- Issues encountered
- Solutions implemented
- CPU verification
- Reflection on prototype

## Extension Activities

- Add more I/O
- Test at higher speeds
- Add debugging features
- Optimize prototype

## Next Lab

After completing prototype, students will continue with 65C816 system in Year 5.

---

*Prototype development tests design and enables learning*
