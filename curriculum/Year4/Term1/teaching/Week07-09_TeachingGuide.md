# Week 7-9: Memory Expansion and Harvard Architecture - Teaching Guide

## Overview

This teaching guide supports memory expansion and Harvard architecture implementation over 4 weeks. Students expand SAP-1 memory and implement code/data separation.

## Learning Objectives

By the end of this week-block, students will:
- Expand address space to 8 bits
- Extend PC and MAR to 8 bits
- Implement address decoding for larger memory
- Implement Harvard architecture
- Test memory expansion

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 4-6 (Instruction Expansion)
- ✅ Understand memory systems (Year 2-3)
- ✅ Understand address decoding (Year 2)
- ✅ Understand PC and MAR (Year 3)

## Week-by-Week Breakdown

### Week 9: Extending PC and MAR

**Theory Session (45 min)**:
- Address space expansion
- Counter cascading
- Register cascading
- 8-bit addressing

**Lab Session (90 min)**:
- Add second counter for PC
- Cascade counters
- Add second register for MAR
- Cascade registers
- Test 8-bit addressing

**Key Points**:
- Cascading extends range
- Both components need extension
- Test carefully
- Verify addresses

**Common Questions**:
- Q: How do we cascade? A: Lower wraps, upper increments
- Q: Why both PC and MAR? A: Both need 8-bit addresses
- Q: How do we test? A: Generate addresses, verify range

### Week 10: Larger Memory Connection

**Theory Session (45 min)**:
- Larger memory chips
- Memory connection
- Address decoding
- Testing procedures

**Lab Session (90 min)**:
- Replace small memory
- Connect larger SRAM
- Implement address decoding
- Test memory access
- Verify operation

**Key Points**:
- Larger memory enables expansion
- Address decoding needed
- Test thoroughly
- Verify all addresses

**Common Questions**:
- Q: Which memory chip? A: 32KB or 64KB SRAM
- Q: How to connect? A: 8-bit address, 8-bit data, control
- Q: What if doesn't work? A: Check connections, check decoding

### Week 11: Harvard Architecture

**Theory Session (45 min)**:
- Harvard architecture concept
- ROM/RAM separation
- Memory map design
- Implementation

**Lab Session (90 min)**:
- Design memory map
- Implement address decoder
- Connect ROM for programs
- Connect RAM for data
- Test separation

**Key Points**:
- Harvard separates code and data
- Address decoder selects ROM/RAM
- Programs in ROM, data in RAM
- Test both memories

**Common Questions**:
- Q: Why Harvard? A: Prevents overwriting programs, clear separation
- Q: How to implement? A: Address decoder, separate memories
- Q: What if conflicts? A: Check decoding, verify chip selects

### Week 12: Complete System Testing

**Theory Session (45 min)**:
- Complete system testing
- Program execution from ROM
- Data access to RAM
- System verification

**Lab Session (90 min)**:
- Load program into ROM
- Load data into RAM
- Execute program
- Verify operation
- Test multiple programs
- Document system

**Key Points**:
- Test complete system
- Verify ROM/RAM work
- Document expansion
- Ready for Term 2

**Common Questions**:
- Q: How do we test? A: Load program in ROM, data in RAM, execute
- Q: What if fails? A: Test each memory, verify decoding
- Q: Ready for 16-bit? A: Yes, understanding expansion prepares

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide expansion checklist
- Step-by-step connection guide
- Extra time for work
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Further memory expansion
- Advanced address decoding
- Optimize memory map
- Help other students

### Common Misconceptions

1. **"More memory is always better"**
   - Clarify: Balance with complexity
   - Show practical limits

2. **"Harvard is complex"**
   - Clarify: Simple address decoding
   - Show basic implementation

3. **"Expansion is just adding bits"**
   - Clarify: Requires system changes
   - Show all components affected

### Assessment Checkpoints

**Week 9**: Can students extend PC and MAR?
**Week 10**: Can students connect larger memory?
**Week 11**: Can students implement Harvard architecture?
**Week 12**: Is expanded system working?

## Resources

- Memory expansion guides
- Address decoding examples
- Harvard architecture diagrams
- Memory map templates

## Next Term

After completing memory expansion, students move to Term 2: 65C816 introduction.

---

*Memory expansion enables larger programs and prepares for 16-bit systems*
