# Week 16-18: Input/Output Systems - Teaching Guide

## Overview

This teaching guide supports the delivery of I/O systems concepts over 4 weeks. Students learn to interface with input and output devices.

## Learning Objectives

By the end of this week-block, students will:
- Build input interfaces
- Build output interfaces
- Implement data direction control
- Interface with displays
- Understand I/O timing

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 13-15
- ✅ Understand memory-mapped I/O
- ✅ Understand address decoding
- ✅ Understand tri-state buffers

## Week-by-Week Breakdown

### Week 16: TTL Logic Probe Construction ⭐ QUICK WIN LAB PROJECT

**Theory Session (45 min)**:
- Digital signal levels (HIGH, LOW, floating)
- Logic probe operation principles
- Comparator-based detection
- Signal analysis techniques

**Lab Session (90 min)**:
- Build TTL Logic Probe circuit
- Test signal detection
- Practice debugging techniques
- Document probe operation

**Key Points**:
- Logic probe detects signal levels
- Essential debugging tool
- Will be used throughout curriculum
- Builds confidence with early success

**Common Questions**:
- Q: What does logic probe do? A: Detects HIGH, LOW, floating, and pulse signals
- Q: Why build it now? A: Tool will be used in all future labs
- Q: How does it work? A: Comparators detect voltage levels, LEDs indicate state

**Reference**: See `../../../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for design reference

### Week 17: Simple Input Interface

**Theory Session (45 min)**:
- Input device basics
- Switch and button interfacing
- Input register design
- Reading input data

**Lab Session (90 min)**:
- Design input register
- Connect switches
- Implement I/O read
- Test input reading

**Key Points**:
- Input devices provide data
- Read like memory location
- Tri-state enables bus drive

**Common Questions**:
- Q: How do we read switches? A: Connect to input register, read address
- Q: What about debouncing? A: Use debouncing circuit if needed
- Q: Can we read multiple switches? A: Yes, use byte-wide register

### Week 18: Simple Output Interface

**Theory Session (45 min)**:
- Output device basics
- LED interfacing
- Output register design
- Writing output data

**Lab Session (90 min)**:
- Design output register
- Connect LEDs
- Implement I/O write
- Test output control

**Key Points**:
- Output devices display data
- Write like memory location
- LEDs need current-limiting resistors

**Common Questions**:
- Q: How do we control LEDs? A: Write to output register address
- Q: Why resistors? A: Limit current to protect LEDs
- Q: Can we control multiple LEDs? A: Yes, use byte-wide register

### Week 19: Data Direction Control

**Theory Session (45 min)**:
- Bidirectional I/O concept
- Data Direction Register (DDR)
- Direction control logic
- Port configuration

**Lab Session (90 min)**:
- Design DDR
- Build bidirectional port
- Test input mode
- Test output mode
- Test direction changes

**Key Points**:
- DDR controls I/O direction
- Same port can be input or output
- Direction can change dynamically

**Common Questions**:
- Q: Why bidirectional? A: Flexibility, fewer pins
- Q: How do we change direction? A: Write to DDR
- Q: Can we mix directions? A: Yes, bit-by-bit control

### Week 20: Display Interfaces

**Theory Session (45 min)**:
- Display device types
- 7-segment display interfacing
- BCD to 7-segment decoding
- Display control

**Lab Session (90 min)**:
- Connect 7-segment display
- Add BCD decoder
- Test number display
- Create display counter
- Optional: Character LCD

**Key Points**:
- Displays show information
- Decoders convert data to display format
- Timing may be needed

**Common Questions**:
- Q: How do displays work? A: Decoder converts data to segments
- Q: Can we show letters? A: 7-segment limited, LCD better for text
- Q: How do we update? A: Write new value to display register

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide pre-built I/O interfaces
- Simplify to single device
- Step-by-step connection guide
- Pair with stronger students

**Extension for advanced students**:
- Build LED matrix displays
- Implement switch matrix scanning
- Add multiple I/O ports
- Create I/O library routines

### Common Misconceptions

1. **"I/O is complex"**
   - Clarify: Simple I/O is straightforward
   - Start with basic switches and LEDs

2. **"Need special I/O instructions"**
   - Clarify: Memory-mapped I/O uses normal read/write
   - Show I/O as memory locations

3. **"All devices are the same"**
   - Clarify: Different devices need different interfaces
   - Show examples of different interfaces

### Assessment Checkpoints

**Week 21**: Can students build input interface?
**Week 22**: Can students build output interface?
**Week 23**: Can students implement data direction control?
**Week 24**: Can students interface with displays?

## Resources

- I/O interface designs
- Display interfacing guides
- Component datasheets
- Example circuits

## Next Term

After completing I/O systems, students move to Term 3: Advanced Integration.

---

*I/O systems connect computers to the real world*
