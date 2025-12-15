# Week 22-24: Machine Code Programming - Teaching Guide

## Overview

This teaching guide supports machine code programming over 4 weeks. Students learn to program the SAP-1 CPU and run complete programs.

## Learning Objectives

By the end of this week-block, students will:
- Integrate 20×4 parallel LCD display with SAP-1
- Initialize LCD and display test messages
- Understand SAP-1 instruction set
- Program in machine code
- Develop and test programs
- Debug programs
- Run complete programs with LCD output

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 19-21 (Bring-up and Testing)
- ✅ Working SAP-1 CPU
- ✅ Have 20×4 HD44780 LCD and interface components
- ✅ Understand instruction set
- ✅ Understand CPU operation
- ✅ Have read LCD Display Output Guide

## Week-by-Week Breakdown

### Week 22, Day 1: RomWriter Construction (Session 0A) ⭐ QUICK WIN LAB PROJECT

**Theory Session (30 min)**:
- ROM programming concepts
- Programming protocols (parallel, serial, adapter-based)
- Interface design principles
- Status indication (LEDs, feedback)

**Lab Session (90 min)**:
- Design RomWriter interface
- Build RomWriter module
- Test ROM socket connection
- Test programming interface (if applicable)
- Document RomWriter specifications

**Key Points**:
- RomWriter enables ROM programming
- Interface may need adaptation for SAP-1/65C816
- Essential tool for system development
- Will be used throughout curriculum

**Common Questions**:
- Q: What is RomWriter? A: Tool for programming ROM chips with machine code
- Q: Why build it now? A: Needed for programming SAP-1 ROMs
- Q: How does it work? A: Interface connects to ROM socket, programs chip via protocol

**Reference**: See `../../../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for design reference (may need interface adaptation)

**Note**: RomWriter interface may need adaptation for SAP-1/65C816 system. Students may use existing EEPROM programmer with adapter, or build custom interface.

### Week 22, Day 2-3: LCD Integration (Session 0B)

**Theory Session (30 min)**:
- LCD display basics (HD44780 controller)
- Parallel interface to SAP-1
- Memory-mapped I/O for LCD
- LCD initialization sequence
- Reference to LCD guide

**Lab Session (180 min)**:
- Connect 20×4 LCD to SAP-1 data bus
- Implement address decoding for LCD
- Initialize LCD display
- Test LCD with test messages
- Verify LCD displays correctly

**Key Points**:
- LCD connects to SAP-1 output port
- Parallel interface shows direct bus connection
- Initialization sequence is critical
- LCD will display program results

**Common Questions**:
- Q: Why parallel not I2C? A: Educational value - see direct bus connection
- Q: How to connect? A: See LCD guide for detailed wiring
- Q: What if LCD doesn't work? A: Check power, contrast, initialization sequence

**Troubleshooting**:
- LCD not displaying: Check power, adjust contrast, verify initialization
- Garbled text: Check data bus connections, add delays
- No response: Check address decoding, check control signals

**Reference**: `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md`

### Week 22, Day 3-4: Instruction Set and Programming (Session 1)

**Theory Session (45 min)**:
- SAP-1 instruction set review
- Instruction encoding
- Machine code format
- Program design

**Lab Session (90 min)**:
- Review instruction set
- Learn machine code
- Design simple program (with LCD output)
- Convert to machine code
- Plan memory layout
- Plan LCD output format
- Document program

**Key Points**:
- Instruction set is simple
- Machine code is binary
- Program design is important
- Memory layout matters

**Common Questions**:
- Q: How many instructions? A: ~6-8 basic instructions
- Q: How do we encode? A: 4-bit opcode + 4-bit operand
- Q: How do we design? A: Plan algorithm, map to instructions

### Week 23: Program Loading and Execution (Session 2)

**Theory Session (45 min)**:
- Program loading methods
- Memory programming
- Execution process
- Debugging programs

**Lab Session (90 min)**:
- Load program into memory
- Verify program loaded
- Reset CPU
- Run program
- Verify execution
- **Check LCD output**: Verify result displays on LCD
- Debug if needed
- Document execution

**Key Points**:
- Load program correctly
- Verify before running
- Single-step for debugging
- Check results

**Common Questions**:
- Q: How do we load? A: Manual or EEPROM programmer
- Q: How do we verify? A: Check memory contents
- Q: What if wrong? A: Debug step-by-step

### Week 24: Arithmetic Program (Session 3)

**Theory Session (45 min)**:
- Arithmetic operations
- Program design for arithmetic
- Testing arithmetic programs
- Debugging arithmetic

**Lab Session (90 min)**:
- Design add program
- Convert to machine code
- Load program and data
- Execute program
- **Verify result on LCD**: Check LCD displays sum correctly
- Test with different numbers
- Verify LCD shows all test results
- Debug if needed

**Key Points**:
- Arithmetic uses ALU
- Load operands first
- Store result
- Verify calculation

**Common Questions**:
- Q: How do we add? A: Load numbers, ADD, output
- Q: What if wrong? A: Check ALU, check registers, check data
- Q: How do we test? A: Try different numbers, verify results

### Week 24 (continued): Complex Program (Session 4)

**Theory Session (45 min)**:
- Complex program design
- Multi-step operations
- Program optimization
- Advanced debugging

**Lab Session (90 min)**:
- Design complex program
- Convert to machine code
- Load and execute
- **Verify results on LCD**: All results display on LCD
- Test edge cases
- Verify LCD shows intermediate and final results
- Debug if needed
- Document program

**Key Points**:
- Plan carefully
- Test thoroughly
- Debug systematically
- Document completely

**Common Questions**:
- Q: How complex? A: Multiple operations, 5-10 instructions
- Q: How do we debug? A: Single-step, check each step
- Q: What if stuck? A: Simplify, test parts, get help

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide program templates
- Step-by-step programming guide
- Simple program examples
- Pair with stronger students
- Extra time for programming

**Extension for advanced students**:
- More complex programs
- Program optimization
- Create program library
- Help other students

### Common Misconceptions

1. **"Machine code is hard"**
   - Clarify: Simple format, just binary
   - Show encoding examples

2. **"Programs are complex"**
   - Clarify: Start simple, build up
   - Show simple examples

3. **"Debugging is impossible"**
   - Clarify: Systematic approach works
   - Show debugging techniques

### Assessment Checkpoints

**Week 22, Day 1-2**: Can students integrate and initialize LCD?
**Week 22, Day 3-4**: Can students understand instruction set?
**Week 23**: Can students load and run programs with LCD output?
**Week 24**: Can students write arithmetic and complex programs with LCD output?

## Resources

- **LCD Display Output Guide**: `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md`
- Instruction set reference
- Machine code examples
- Program templates
- Debugging guides
- LCD initialization code examples

## Next Week

After completing programming, students move to system completion (Week 33-36).

---

*Machine code programming enables CPU use*
