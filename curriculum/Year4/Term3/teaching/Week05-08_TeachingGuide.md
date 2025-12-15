# Week 5-8: Input/Output Subsystems - Teaching Guide

## Overview

This teaching guide supports I/O subsystem integration over 4 weeks. Students integrate serial, parallel, LCD, and timer functions.

## Learning Objectives

By the end of this week-block, students will:
- Integrate ACIA for serial communication
- Integrate VIA for parallel I/O
- Interface LCD display
- Implement timer functions
- Test I/O subsystems

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 1-4 (Memory Banking)
- ✅ Have expanded system
- ✅ Understand I/O concepts
- ✅ Understand memory-mapped I/O

## Week-by-Week Breakdown

### Week 5: ACIA Integration

**Theory Session (45 min)**:
- Serial communication concepts
- ACIA architecture
- UART functionality
- Baud rate configuration

**Lab Session (90 min)**:
- Place ACIA on breadboard
- Connect to buses
- Implement decoding
- Connect serial interface
- Initialize and test

**Key Points**:
- ACIA handles serial
- Memory-mapped I/O
- Initialize before use
- Test transmission/reception

**Common Questions**:
- Q: How to connect? A: Address/data buses, serial interface
- Q: How to initialize? A: Set baud rate, configure registers
- Q: What if doesn't work? A: Check connections, check baud rate

### Week 6: VIA Integration

**Theory Session (45 min)**:
- Parallel I/O concepts
- VIA architecture
- Port configuration
- Timer functions

**Lab Session (90 min)**:
- Place VIA on breadboard
- Connect to buses
- Configure ports
- Test ports
- Test timers

**Key Points**:
- VIA provides parallel I/O
- Configure direction
- Test ports
- Use timers

**Common Questions**:
- Q: How to configure? A: Set direction registers, configure ports
- Q: How to use timers? A: Set value, configure mode, enable
- Q: What if doesn't work? A: Check configuration, check connections

### Week 7: LCD Display Interface

**Theory Session (45 min)**:
- LCD display concepts
- LCD interface
- Initialization sequence
- Character display

**Lab Session (90 min)**:
- Connect LCD
- Implement control
- Initialize LCD
- Display text
- Test display

**Key Points**:
- LCD needs initialization
- Send commands then data
- Test display
- Format output

**Common Questions**:
- Q: How to connect? A: Via VIA or direct, check datasheet
- Q: How to initialize? A: Send initialization sequence
- Q: What if doesn't work? A: Check connections, check initialization

### Week 8: Complete I/O Integration

**Theory Session (45 min)**:
- I/O system integration
- Testing procedures
- I/O map documentation
- System verification

**Lab Session (90 min)**:
- Integrate all I/O
- Test serial
- Test parallel
- Test LCD
- Test timers
- Verify system

**Key Points**:
- Test all I/O
- Verify integration
- Document I/O map
- Prepare for graphics/sound

**Common Questions**:
- Q: How to test? A: Test each subsystem, verify integration
- Q: What if conflicts? A: Check address decoding, verify I/O map
- Q: Ready for research? A: Yes, if I/O working

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide I/O integration checklist
- Step-by-step connection guide
- Extra time for work
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Additional I/O devices
- Advanced I/O features
- Optimize I/O code
- Help other students

### Common Misconceptions

1. **"I/O is complex"**
   - Clarify: Register-based, straightforward
   - Show simple examples

2. **"Need many chips"**
   - Clarify: Start with few, expand
   - Show minimal setup

3. **"Serial is difficult"**
   - Clarify: ACIA handles details
   - Show basic usage

### Assessment Checkpoints

**Week 5**: Can students integrate ACIA?
**Week 6**: Can students integrate VIA?
**Week 7**: Can students interface LCD?
**Week 8**: Is I/O system complete?

## Resources

- I/O integration guides
- ACIA/VIA datasheets
- LCD interface guides
- I/O map templates

## Next Week

After completing I/O integration, students move to graphics/sound research (Week 9-12).

---

*I/O subsystems enable interaction and prepare for complete systems*
