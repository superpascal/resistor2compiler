# Lab 5-8: Assembler and Toolchain

## Lab Overview

In this lab, students will set up a cross-development toolchain for 65C816 and create assembly language programs. They'll learn to assemble, link, and load programs onto their system.

## Learning Objectives

- Set up CC65 or similar assembler for 65C816
- Configure cross-development environment
- Write assembly language programs
- Assemble and link programs
- Load and execute programs on target system

## Prerequisites

- Monitor program working (Lab 1-4)
- Understanding of 65C816 instruction set
- Basic assembly language knowledge
- Development PC available

## Materials

### Components
- Complete 65C816 system
- Serial interface for program loading
- Development PC

### Tools
- CC65 suite (or similar assembler)
- Text editor
- Serial terminal
- Linker (ld65 or similar)

## Safety

- Verify program addresses don't conflict with monitor
- Test programs carefully before execution
- Use monitor to verify program loading

## Lab Sessions

### Session 1: Toolchain Setup (Week 5)

**Objective**: Install and configure assembler toolchain

**Steps**:
1. Download CC65 suite
2. Install on development PC
3. Configure for 65C816 target
4. Set up build environment
5. Create memory map configuration
6. Test assembler with simple program
7. Verify assembly output

**Expected Result**: Assembler configured and working for 65C816

**Troubleshooting**:
- If assembler not found: Check installation, PATH
- If wrong target: Verify 65C816 configuration
- If assembly fails: Check syntax, configuration

### Session 2: Basic Assembly Programming (Week 6)

**Objective**: Write and assemble simple assembly programs

**Steps**:
1. Write simple program (load value, store, return)
2. Use labels for addresses
3. Use directives (.org, .segment)
4. Add comments
5. Assemble program
6. Verify object file created
7. Examine assembly listing

**Expected Result**: Can write and assemble assembly programs

**Troubleshooting**:
- If assembly errors: Check syntax, labels, directives
- If wrong addresses: Check .org directive, memory map
- If linking fails: Check object file format

### Session 3: Linking and Memory Maps (Week 7)

**Objective**: Link programs and configure memory layout

**Steps**:
1. Create linker configuration file
2. Define memory segments (CODE, DATA, BSS)
3. Set up memory map for target system
4. Link simple program
5. Verify executable image
6. Check memory layout
7. Generate memory map report

**Expected Result**: Can link programs with correct memory layout

**Troubleshooting**:
- If linking fails: Check configuration, object files
- If wrong addresses: Verify memory map
- If segments wrong: Check linker script

### Session 4: Program Loading and Execution (Week 8)

**Objective**: Load and execute programs on target system

**Steps**:
1. Generate hex or binary file from linked program
2. Transfer file to target (via serial or monitor)
3. Load program into memory using monitor
4. Verify program loaded correctly
5. Set program counter to entry point
6. Execute program
7. Debug using monitor if needed
8. Create complete workflow script

**Expected Result**: Complete workflow from source to execution

**Troubleshooting**:
- If loading fails: Check file format, monitor commands
- If execution wrong: Check entry point, program logic
- If debugging needed: Use monitor step and memory commands

## Assessment

### Practical Assessment
- Toolchain set up and working
- Can write assembly programs
- Can assemble and link programs
- Can load and execute programs
- Complete development workflow functional

### Lab Report
Students should document:
- Toolchain setup procedure
- Memory map configuration
- Example assembly programs
- Linking process
- Loading and execution procedure
- Development workflow
- Issues and solutions

## Extension Activities

- Create library of reusable functions
- Optimize assembly code
- Create custom linker scripts
- Build multi-file projects
- Create build automation scripts
- Add debugging symbols

## Next Lab

After completing assembler setup, students move to Pascal runtime preparation (Lab 9-12).

---

*Assemblers enable efficient software development*
