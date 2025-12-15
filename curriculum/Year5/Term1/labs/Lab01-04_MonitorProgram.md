# Lab 1-4: Monitor Program and Machine Code Monitor

## Lab Overview

In this lab, students will develop a monitor program for their 65C816 system. The monitor provides low-level debugging and control capabilities through a serial command interface.

## Learning Objectives

- Design and implement a monitor program
- Create command-line interface via serial
- Implement memory inspection and editing
- Implement register display and modification
- Implement program execution control

## Prerequisites

- Working 65C816 hardware system
- Serial interface functional
- Understanding of 65C816 assembly language
- Basic understanding of command parsing

## Materials

### Components
- Complete 65C816 breadboard system
- Serial interface (ACIA or USB-serial adapter)
- Development PC with serial terminal

### Tools
- Text editor
- Assembler (ca65 or similar)
- Serial terminal software (PuTTY, minicom, etc.)
- Linker (ld65 or similar)

## Safety

- Ensure correct serial connections
- Verify voltage levels (5V vs 3.3V)
- Use proper grounding
- Test serial communication before starting

## Lab Sessions

### Session 1: Basic Command Loop (Week 1)

**Objective**: Create basic monitor structure with command loop

**Steps**:
1. Set up serial communication
2. Create main monitor loop
3. Implement command input (read from serial)
4. Implement command echo
5. Implement simple "help" command
6. Test basic command interface

**Expected Result**: Monitor accepts commands via serial and echoes them

**Troubleshooting**:
- If no serial input: Check connections, baud rate, terminal settings
- If commands not received: Verify serial initialization
- If echo not working: Check serial output routine

### Session 2: Memory Commands (Week 2)

**Objective**: Implement memory inspection and editing commands

**Steps**:
1. Implement memory read command (`M <addr>`)
   - Parse address from command
   - Read memory location
   - Display value in hex
2. Implement memory write command (`M <addr> <data>`)
   - Parse address and data
   - Write to memory location
   - Verify write
3. Implement memory range display (`M <start> <end>`)
   - Display range of memory
   - Format output clearly
4. Test all memory commands

**Expected Result**: Can read and write memory via monitor commands

**Troubleshooting**:
- If read wrong values: Check address parsing, memory access
- If write doesn't work: Check write enable, address validity
- If range display wrong: Check loop logic, formatting

### Session 3: Register Commands (Week 3)

**Objective**: Implement register display and modification

**Steps**:
1. Implement register display command (`R`)
   - Save current registers
   - Display all registers (A, X, Y, S, PC, P)
   - Format output clearly
   - Restore registers
2. Implement register modification (`R <reg> <value>`)
   - Parse register name
   - Parse value
   - Modify register
   - Verify modification
3. Test register commands
4. Test register modification affects execution

**Expected Result**: Can display and modify all CPU registers

**Troubleshooting**:
- If registers wrong: Check register save/restore
- If modification doesn't work: Check register name parsing
- If execution affected incorrectly: Verify register modification

### Session 4: Execution Control (Week 4)

**Objective**: Implement program execution control

**Steps**:
1. Implement go command (`G <addr>`)
   - Parse address
   - Set program counter
   - Start execution
   - Return to monitor on completion
2. Implement step command (`S`)
   - Execute one instruction
   - Return to monitor
   - Display registers after step
3. Implement break/stop command (`B`)
   - Stop execution
   - Return to monitor
   - Display current state
4. Test execution control
5. Load and run simple test program

**Expected Result**: Can control program execution (run, step, stop)

**Troubleshooting**:
- If go doesn't work: Check PC setting, execution start
- If step doesn't work: Check instruction execution, return
- If break doesn't work: Check interrupt handling

## Assessment

### Practical Assessment
- Monitor accepts commands correctly
- Memory commands work (read, write, range)
- Register commands work (display, modify)
- Execution control works (go, step, break)
- Can load and run programs

### Lab Report
Students should document:
- Monitor program structure
- Command interface design
- Implementation details
- Testing procedures
- Example command sessions
- Issues encountered and solutions

## Extension Activities

- Add disassembly command
- Add breakpoint support
- Add memory search
- Add program save/load
- Add help system
- Add command history

## Next Lab

After completing monitor program, students move to assembler and toolchain (Lab 5-8).

---

*Monitor programs provide essential debugging capabilities*
