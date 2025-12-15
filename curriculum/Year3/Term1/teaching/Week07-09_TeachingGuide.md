# Week 7-9: Memory Subsystem - Teaching Guide

## Overview

This teaching guide supports the delivery of memory subsystem construction over 4 weeks. Students complete the data path by adding memory to the SAP-1 CPU.

## Learning Objectives

By the end of this week-block, students will:
- Build Memory Address Register (MAR)
- Connect memory chip to system
- Implement address decoding
- Test read/write operations
- Integrate memory with data path

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 4-6 (Registers and Buses)
- ✅ Understand memory concepts (Year 2)
- ✅ Understand MAR (Year 2)
- ✅ Can program EEPROM (if using)

## Week-by-Week Breakdown

### Week 9: Building the MAR

**Theory Session (45 min)**:
- MAR function
- MAR construction
- Address bus connection
- Control signal (MI)
- Testing procedures

**Lab Session (90 min)**:
- Build MAR from register
- Connect to address bus
- Add address display
- Test address loading
- Verify address output

**Key Points**:
- MAR holds memory address
- Connects to memory address pins
- Loaded from bus
- 4-bit for SAP-1

**Common Questions**:
- Q: Why MAR? A: Holds address, connects to memory
- Q: How many bits? A: 4 bits for 16 locations
- Q: How does it work? A: Loads address, outputs to memory

### Week 10: Connecting Memory

**Theory Session (45 min)**:
- Memory chip options
- Memory connections
- Address pins
- Data pins
- Control pins

**Lab Session (90 min)**:
- Place memory chip
- Connect MAR to address
- Connect data to bus
- Connect control signals
- Test basic connection

**Key Points**:
- Memory needs address
- Memory connects to bus
- Control signals needed
- Tri-state for output

**Common Questions**:
- Q: Which memory chip? A: 74LS189 or 28C16 EEPROM
- Q: How to connect? A: Address from MAR, data to bus
- Q: What about control? A: RO for read, WE for write

### Week 11: Memory Operations

**Theory Session (45 min)**:
- Read operation sequence
- Write operation sequence
- Control signal timing
- Testing procedures
- Verification methods

**Lab Session (90 min)**:
- Program memory (or use pre-programmed)
- Test read operations
- Test write operations
- Verify data correctness
- Document operations

**Key Points**:
- Read: Set address, enable output, read data
- Write: Set address, put data, enable write
- Timing is critical
- Verify operations

**Common Questions**:
- Q: How do we read? A: Set MAR, enable RO, read bus
- Q: How do we write? A: Set MAR, put data, enable WE
- Q: What if wrong? A: Check signals, check timing, verify

### Week 12: Complete Data Path Integration

**Theory Session (45 min)**:
- Complete data path review
- All components together
- Data flow examples
- Integration testing
- System verification

**Lab Session (90 min)**:
- Connect all components
- Test complete operations
- Load from memory
- Operate with ALU
- Store to memory
- Verify complete system

**Key Points**:
- All components integrated
- Data path complete
- Ready for control unit
- Foundation for CPU

**Common Questions**:
- Q: Is data path complete? A: Yes, all components connected
- Q: What's next? A: Control unit (Term 2)
- Q: How do we test? A: Complete operations, verify results

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide memory connection reference
- Step-by-step integration guide
- Extra time for testing
- Pair with stronger students
- Review memory concepts

**Extension for advanced students**:
- Expand memory size
- Add multiple memory chips
- Implement memory test routines
- Optimize memory access

### Common Misconceptions

1. **"Memory is just storage"**
   - Clarify: Active component, needs control
   - Show read/write operations

2. **"MAR is optional"**
   - Clarify: Essential for addressing
   - Show why needed

3. **"All memory is the same"**
   - Clarify: Different types, different characteristics
   - Show RAM vs EEPROM

### Assessment Checkpoints

**Week 9**: Can students build MAR?
**Week 10**: Can students connect memory?
**Week 11**: Can students read/write memory?
**Week 12**: Can students integrate complete data path?

## Resources

- MAR circuit diagrams
- Memory connection diagrams
- Read/write sequence guides
- Integration checklists

## Next Term

After completing data path, students move to Term 2: Control Unit construction.

---

*Memory completes the data path and enables program storage*
