# Chapter 8: Machine Code Programming

## Introduction

Machine code is the lowest level programming language. This chapter explains how to program the SAP-1 CPU in machine code.

## SAP-1 Instruction Set

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

## Machine Code Programming

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

## Program Development

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

**Note**: SAP-1 uses a 20×4 parallel LCD display for output (per Ben Eater approach). See `../../../resources/LCD_DISPLAY_OUTPUT_GUIDE.md` for LCD integration details.

## Program Testing

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

## Practice Questions

1. What is machine code?
2. How do we encode instructions?
3. How do we develop programs?
4. How do we test programs?
5. How do we debug programs?

## Key Takeaways

- Machine code is binary instructions
- Instruction set is simple but functional
- Program design is important
- Testing verifies correctness
- Debugging solves problems

---

*Machine code programming enables CPU use*
