# Week 22-24: Machine Code Programming - Theory

## Learning Objectives

By the end of this week-block, students will:
- Integrate 20×4 parallel LCD display with SAP-1
- Understand LCD interface and initialization
- Understand the SAP-1 instruction set
- Program in machine code
- Develop and test programs
- Debug programs systematically
- Run complete programs on the CPU with LCD output

## Prerequisites

- Completed Weeks 19-21 (Bring-up and Testing)
- Working SAP-1 CPU
- Understanding of CPU operation
- Understanding of instruction execution

## Key Concepts

### 1. LCD Display Integration

**Why LCD for SAP-1?**
- Ben Eater's SAP-1 uses 2-row or 4-row LCD for output
- Provides text output for program results
- More informative than 7-segment displays
- Foundation for understanding character displays

**20×4 HD44780 LCD**:
- **20 characters × 4 rows**: More display area than 2-row LCD
- **HD44780 controller**: Standard character LCD controller
- **Parallel interface**: Direct connection to data bus (educational value)
- **Memory-mapped I/O**: LCD appears as memory locations

**LCD Interface to SAP-1**:
- **Data Bus**: LCD D0-D7 connected to SAP-1 data bus via tri-state buffers
- **Address Decoding**: Address decoder selects LCD registers
- **Control Signals**: RS (Register Select), E (Enable), R/W (Read/Write)
- **Memory Map** (example):
  - `$0E`: LCD Data Register (write characters)
  - `$0F`: LCD Command Register (send commands)

**LCD Initialization Sequence**:
1. Power-on delay (wait 50ms)
2. Function set: 8-bit mode, 2-line, 5×8 font
3. Display control: Display on, cursor off
4. Clear display
5. Entry mode: Increment cursor

**Displaying Program Results**:
- OUT instruction writes accumulator value to LCD
- Convert binary to ASCII for display
- Display numbers, text, or program status
- Use multiple rows for complex output

**Educational Value**:
- Students see direct bus connection
- Understand memory-mapped I/O
- Learn character display programming
- Foundation for Year 4 VGA project

**Reference**: 
- See `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for integration guide
- See `../../../resources/LCD_TECHNOLOGY_EDUCATION.md` for comprehensive LCD technology education (how LCDs work, signaling, ASCII, programming examples)

### 2. SAP-1 Instruction Set

**SAP-1 instructions**:
- **LDA addr**: Load A from memory address
- **ADD addr**: Add memory value to A, store in A
- **SUB addr**: Subtract memory value from A, store in A
- **OUT**: Output A register to display
- **HLT**: Halt CPU execution
- **JMP addr**: Jump to address (if implemented)
- **JZ addr**: Jump if zero (if implemented)

**Instruction encoding**:
- 4-bit opcode + 4-bit operand
- Opcode determines operation
- Operand provides data/address

### 3. Machine Code Programming

**What is machine code?**
- Binary representation of instructions
- Direct CPU language
- Lowest level programming
- What CPU actually executes

**Programming process**:
1. Design program algorithm
2. Write instructions in assembly (conceptual)
3. Convert to machine code
4. Load into memory
5. Execute on CPU
6. Verify results

### 4. Program Development

**Program design**:
- Define goal
- Plan algorithm
- Break into steps
- Map to instructions
- Plan memory usage

**Example program**: Add two numbers
```
Address  Instruction  Machine Code  Meaning
0x0      LDA 0xE     0000 1110     Load A from address 14
0x1      ADD 0xF     0001 1111     Add value from address 15
0x2      OUT         1110 0000     Output result
0x3      HLT         1111 0000     Halt
...
0xE      [data]      0001 1100     Data: 28
0xF      [data]      0000 1110     Data: 14
```

**Expected result**: LCD displays "42" (28 + 14) on the 20×4 LCD screen

### 5. Program Testing

**Test strategy**:
- Start with simple programs
- Test each instruction
- Test instruction sequences
- Test complete programs
- Verify results

**Debugging programs**:
- Single-step through program
- Check register values
- Check memory contents
- Verify instruction execution
- Fix errors

### 6. Program Loading

**Loading methods**:
- Manual: Set memory with switches
- EEPROM programmer: Program EEPROM
- Serial loader: Load via serial (if available)
- Monitor program: Use monitor to load (if available)

**For SAP-1**:
- Typically manual or EEPROM programmer
- Load program into memory addresses
- Verify program loaded correctly
- Reset CPU and run

### 7. Program Execution

**Execution process**:
1. Load program into memory
2. Reset CPU (PC = 0)
3. Start clock
4. CPU fetches first instruction
5. CPU executes instruction
6. CPU fetches next instruction
7. Repeat until HLT

**Monitoring execution**:
- Single-step mode: Step through manually
- LEDs: Show addresses, data, signals
- **LCD Display**: Show program output and results (20×4 LCD)
- Logic analyzer: Capture signals

### 8. Program Debugging

**Debugging techniques**:
- Single-step execution
- Check register values
- Check memory contents
- Verify control signals
- Trace data flow
- Compare to expected

**Common program errors**:
- Wrong instruction encoding
- Wrong memory addresses
- Wrong data values
- Logic errors
- Missing instructions

### 9. Advanced Programming

**Program types**:
- Arithmetic: Calculations
- Control flow: Jumps and conditionals
- Loops: Repeated operations
- Data manipulation: Moving data

**Programming challenges**:
- Limited memory (16 bytes)
- Simple instruction set
- Manual programming
- Debugging difficulty

## Mathematical Foundations

### Instruction Encoding

**4-bit opcode**: 16 possible instructions
- SAP-1 uses subset
- Each instruction unique opcode
- Operand provides data

### Program Size

**16-byte memory**: Limits program size
- Must be efficient
- Reuse memory locations
- Plan carefully
- Can expand later

## Common Misconceptions

1. **"Machine code is hard"**
   - Clarify: Simple format, just binary
   - Show encoding examples

2. **"Programs are complex"**
   - Clarify: Start simple, build up
   - Show simple examples

3. **"Debugging is impossible"**
   - Clarify: Systematic approach works
   - Show debugging techniques

## Connections to Weeks 19-21

- **Working CPU**: Need working CPU to program
- **Debugging Skills**: Used for programs too
- **Testing**: Programs test CPU

## Connections to Weeks 33-36

- **Documentation**: Will document programs
- **Portfolio**: Programs in portfolio
- **Presentation**: Will demonstrate programs

## Next Steps

After programming, students will:
- Complete system documentation (Weeks 25-27)
- Present SAP-1 system
- Complete Year 3 portfolio
- Prepare for Year 4

---

*Machine code programming enables CPU use*
