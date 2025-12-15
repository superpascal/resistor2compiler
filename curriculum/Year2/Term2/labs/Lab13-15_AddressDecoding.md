# Lab 17-20: Address Decoding and Memory Mapping

## Lab Overview

In this lab, students will implement address decoding for multiple devices, design memory maps, and build systems with multiple memory chips.

## Learning Objectives

- Design and implement address decoding logic
- Create memory maps for systems
- Build systems with multiple memory chips
- Implement memory-mapped I/O concepts
- Test address decoding and device selection

## Prerequisites

- Completed Lab 13-16 (Advanced State Machines)
- Understanding of address decoding concepts
- Understanding of memory systems
- Understanding of decoders

## Materials

### Components
- Multiple memory chips (2-3 RAM or EEPROM chips)
- Decoders (74HC138, 74HC139)
- Logic gates for address decoding
- LEDs for address and chip select display
- Resistors and breadboards

### Tools
- Multimeter
- Logic analyzer (if available)

## Safety

- Verify power connections for multiple chips
- Ensure proper current capacity
- Check for shorts

## Lab Sessions

### Session 1: Simple Address Decoding (Week 17)

**Objective**: Build basic address decoder for 2 devices

**Steps**:
1. Design memory map (Device 0: 0x00-0x7F, Device 1: 0x80-0xFF)
2. Build address decoder using logic gates or decoder IC
3. Connect higher address bit to decoder
4. Connect decoder outputs to chip select signals
5. Test: Set address, verify correct chip selected
6. Verify only one chip active at a time

**Expected Result**: Address decoder selects correct device based on address

**Troubleshooting**:
- If wrong device selected: Check address bit connections
- If both devices active: Check decoder logic
- If no device selected: Check decoder enable

### Session 2: Multiple Memory Chips (Week 18)

**Objective**: Connect and test multiple memory chips

**Steps**:
1. Place 2-3 memory chips on breadboard
2. Connect address decoder to chip selects
3. Connect lower address bits to all chips
4. Connect data bus to all chips (via tri-state)
5. Connect MAR to address bus
6. Test: Read/write to different address ranges
7. Verify data stored in correct chip

**Expected Result**: Can read/write to multiple memory chips correctly

**Troubleshooting**:
- If data conflicts: Check tri-state enables, ensure only one chip active
- If wrong chip accessed: Check address decoding
- If data wrong: Verify address connections to chips

### Session 3: Memory Map Design (Week 19)

**Objective**: Design and implement custom memory map

**Steps**:
1. Design memory map with RAM, ROM, and I/O space
2. Plan address ranges for each device type
3. Build address decoding for all devices
4. Implement chip select generation
5. Test: Access each address range
6. Verify correct device responds
7. Document memory map

**Expected Result**: Complete memory map with all devices accessible

**Troubleshooting**:
- If address conflicts: Review memory map design
- If device not accessible: Check address decoding
- If wrong device: Verify chip select connections

### Session 4: Memory-Mapped I/O (Week 20)

**Objective**: Implement simple memory-mapped I/O

**Steps**:
1. Design I/O address space (e.g., 0x9000-0x9FFF)
2. Build address decoder for I/O space
3. Create simple I/O device (LED output register)
4. Connect I/O device to address decoder
5. Test: Write to I/O address, verify LED changes
6. Create input device (switch register)
7. Test: Read from I/O address, verify switch state

**Expected Result**: Can read/write I/O devices as memory locations

**Troubleshooting**:
- If I/O not accessible: Check address decoding
- If no response: Check I/O device connections
- If wrong data: Verify I/O register connections

## Assessment

### Practical Assessment
- Successfully implement address decoding
- Connect multiple memory chips
- Design and implement memory map
- Implement memory-mapped I/O
- Document complete system

### Lab Report
Students should document:
- Memory map design
- Address decoding logic
- Device connections
- Test results for each address range
- Reflection on memory mapping concepts

## Extension Activities

- Expand to more devices
- Implement partial address decoding
- Add I/O devices with multiple registers
- Design optimized memory map

## Next Lab

After completing this lab, students will move to I/O systems (Lab 21-24).

---

*Address decoding enables complex memory and I/O systems*
