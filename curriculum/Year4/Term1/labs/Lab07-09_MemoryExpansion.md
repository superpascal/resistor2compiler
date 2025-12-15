# Lab 7-9: Memory Expansion and Harvard Architecture

## Lab Overview

In this lab, students will expand the SAP-1 memory from 4-bit to 8-bit addressing and implement Harvard architecture concepts.

## Learning Objectives

- Expand address space to 8 bits (256 bytes)
- Extend PC and MAR to 8 bits
- Implement address decoding for larger memory
- Implement ROM/RAM separation (Harvard)
- Test memory expansion

## Prerequisites

- Completed Lab 5-8 (Expanded Instruction Set)
- Understanding of memory systems (Year 2-3)
- Understanding of address decoding (Year 2)
- Understanding of PC and MAR (Year 3)

## Materials

### Components
- Enhanced SAP-1 system
- Additional counters for 8-bit PC
- Additional registers for 8-bit MAR
- Larger memory chip (32KB or 64KB SRAM)
- EEPROM for program ROM
- Address decoders
- Logic gates for address formation

### Tools
- EEPROM programmer
- Logic analyzer
- Multimeter

## Safety

- Verify power capacity for larger memory
- Check for shorts
- Test carefully

## Lab Sessions

### Session 1: Extending PC and MAR (Week 9)

**Objective**: Extend PC and MAR to 8 bits

**Steps**:
1. Add second counter for PC (cascade)
2. Connect counters for 8-bit PC
3. Add second register for MAR (cascade)
4. Connect registers for 8-bit MAR
5. Test 8-bit addressing
6. Verify address generation
7. Document expansion

**Expected Result**: 8-bit PC and MAR working

**Troubleshooting**:
- If cascading fails: Check connections, check carry logic
- If addresses wrong: Check bit connections, verify binary
- If timing issues: Check clock, check signal timing

### Session 2: Larger Memory Connection (Week 10)

**Objective**: Connect larger memory chip

**Steps**:
1. Replace small memory with larger SRAM
2. Connect 8-bit address from MAR
3. Connect data bus
4. Implement address decoding
5. Test memory connection
6. Verify address access
7. Test read/write operations

**Expected Result**: Larger memory connected and working

**Troubleshooting**:
- If memory doesn't respond: Check power, check address connections
- If wrong addresses: Check MAR connections, check decoding
- If data wrong: Verify memory, check data connections

### Session 3: Harvard Architecture Implementation (Week 11)

**Objective**: Implement ROM/RAM separation

**Steps**:
1. Design memory map (ROM/RAM split)
2. Implement address decoder for ROM/RAM
3. Connect EEPROM for program ROM
4. Connect SRAM for data RAM
5. Test ROM access (program fetch)
6. Test RAM access (data read/write)
7. Verify separation

**Expected Result**: Harvard architecture implemented

**Troubleshooting**:
- If separation fails: Check address decoding, check chip selects
- If ROM doesn't work: Check EEPROM programming, check connections
- If RAM doesn't work: Check SRAM, check write enable

### Session 4: Complete System Testing (Week 12)

**Objective**: Test complete expanded system

**Steps**:
1. Load program into ROM
2. Load data into RAM
3. Execute program from ROM
4. Access data from RAM
5. Verify complete operation
6. Test with multiple programs
7. Document expanded system

**Expected Result**: Complete expanded system working

**Troubleshooting**:
- If execution fails: Test each component, verify integration
- If data wrong: Check memory map, check addressing
- If issues persist: Review design, check all connections

## Assessment

### Practical Assessment
- Successfully extend PC and MAR
- Connect larger memory
- Implement Harvard architecture
- Test complete system
- Document expansion

### Lab Report
Students should document:
- PC/MAR expansion
- Memory connection
- Harvard implementation
- Memory map design
- Test results
- System verification

## Extension Activities

- Further memory expansion
- Optimize memory map
- Add more memory chips
- Advanced address decoding

## Next Lab

After completing memory expansion, students will move to Term 2: 65C816 introduction.

---

*Memory expansion enables larger programs and prepares for 16-bit systems*
