# Week 13-15: Address Decoding and Memory Mapping - Teaching Guide

## Overview

This teaching guide supports the delivery of address decoding and memory mapping concepts over 4 weeks. Students learn to design memory maps and interface multiple devices.

## Learning Objectives

By the end of this week-block, students will:
- Design and implement address decoding
- Create memory maps
- Build systems with multiple memory chips
- Implement memory-mapped I/O
- Understand device selection

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 10-12
- ✅ Understand memory concepts
- ✅ Understand address spaces
- ✅ Understand decoders

## Week-by-Week Breakdown

### Week 17: Simple Address Decoding

**Theory Session (45 min)**:
- Address decoding basics
- Chip select generation
- Simple decoding logic
- Memory map concepts

**Lab Session (90 min)**:
- Design memory map for 2 devices
- Build address decoder
- Connect to chip selects
- Test device selection

**Key Points**:
- Address decoding selects devices
- Higher address bits select device
- Lower address bits select location

**Common Questions**:
- Q: How do we select device? A: Use address decoder
- Q: What if addresses overlap? A: Design map to avoid conflicts
- Q: Can devices share addresses? A: No, each address must be unique

### Week 18: Multiple Memory Chips

**Theory Session (45 min)**:
- Expanding memory with multiple chips
- Address decoding for memory
- Bus sharing with tri-state
- Memory system design

**Lab Session (90 min)**:
- Connect multiple memory chips
- Implement address decoding
- Test read/write to each chip
- Verify correct chip selection

**Key Points**:
- Multiple chips expand memory
- Address decoding selects chip
- Tri-state prevents conflicts

**Common Questions**:
- Q: How many chips can we have? A: Depends on address bits
- Q: Do chips conflict? A: No, if decoding is correct
- Q: How do we expand? A: Add more chips and decoding

### Week 19: Memory Map Design

**Theory Session (45 min)**:
- Memory map principles
- Address space allocation
- Device placement
- Map documentation

**Lab Session (90 min)**:
- Design complete memory map
- Implement decoding for all devices
- Test each address range
- Document memory map

**Key Points**:
- Memory map organizes address space
- Each device has address range
- Documentation is essential

**Common Questions**:
- Q: How do we design map? A: Allocate ranges for each device
- Q: What about gaps? A: Gaps are fine, even beneficial
- Q: Can we change map? A: Yes, but requires hardware changes

### Week 20: Memory-Mapped I/O

**Theory Session (45 min)**:
- Memory-mapped I/O concept
- I/O as memory locations
- I/O address space
- I/O device interfacing

**Lab Session (90 min)**:
- Design I/O address space
- Build I/O device interfaces
- Test I/O read/write
- Verify I/O operations

**Key Points**:
- I/O devices are like memory
- Read = input, Write = output
- Simple and flexible

**Common Questions**:
- Q: Why memory-mapped? A: Simple, unified addressing
- Q: How do we interface I/O? A: Like memory, with address decoding
- Q: Can I/O be anywhere? A: Yes, in I/O address space

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide pre-designed memory map
- Simplify to 2 devices initially
- Step-by-step decoding guide
- Pair with stronger students

**Extension for advanced students**:
- Design complex memory maps
- Implement partial address decoding
- Add more I/O devices
- Optimize address space usage

### Common Misconceptions

1. **"All addresses must be used"**
   - Clarify: Gaps are fine, even beneficial
   - Show examples with gaps

2. **"Decoding is complex"**
   - Start simple: 2 devices
   - Build up gradually
   - Show decoder ICs simplify

3. **"I/O needs special instructions"**
   - Clarify: Memory-mapped I/O is simpler
   - Show I/O as memory locations

### Assessment Checkpoints

**Week 17**: Can students implement address decoding?
**Week 18**: Can students connect multiple memory chips?
**Week 19**: Can students design memory maps?
**Week 20**: Can students implement memory-mapped I/O?

## Resources

- Memory map templates
- Address decoding examples
- I/O interface designs
- Documentation templates

## Next Week

After completing address decoding, students move to I/O systems (Week 16-18).

---

*Address decoding enables complex memory and I/O systems*
