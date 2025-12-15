# Chapter 2: Expanded Instruction Set

## Introduction

Expanding the instruction set adds new capabilities to the CPU. This chapter explains how to design and implement new instructions for the SAP-1.

## Instruction Set Expansion

**Why expand?**
- Add useful operations
- Improve programming efficiency
- Learn CPU design evolution
- Understand ISA development

**Expansion methods**:
- Add more opcodes
- Use more microcode space
- Add more control signals
- Extend instruction format

## New Instruction Examples

**LDB (Load B directly)**:
- Loads Register B from memory
- Previously: LDA + MOV A→B via ALU
- Now: Single instruction
- More efficient

**ADI (Add Immediate)**:
- Adds immediate value to A
- Previously: Load value, then ADD
- Now: Value in instruction
- More convenient

## Microcode ROM Expansion

**Expanding capacity**:
- Add third EEPROM for more control signals
- Use larger EEPROMs
- Optimize microcode usage
- Reuse microcode sequences

**Control signal expansion**:
- Original: 16 signals (2 EEPROMs)
- Expanded: 24 signals (3 EEPROMs)
- Enables more complex operations
- More flexibility

## Microcode Design

**Design process**:
1. Define instruction behavior
2. Break into microsteps
3. Assign control signals to each step
4. Program microcode ROM
5. Test instruction
6. Verify operation

**Example: LDB instruction**:
- Step 0: Fetch instruction
- Step 1: Load instruction into IR
- Step 2: Decode (determine LDB)
- Step 3: Fetch operand address
- Step 4: Load data into Register B
- Complete

## Instruction Set Architecture Evolution

**ISA development**:
- Start simple (SAP-1)
- Add useful instructions
- Optimize common operations
- Balance complexity vs. usefulness

## Practice Questions

1. Why expand the instruction set?
2. How do we design new instructions?
3. How do we expand microcode?
4. How do we program new instructions?
5. What are the benefits?

## Key Takeaways

- Expansion adds capabilities
- Design carefully
- Microcode enables expansion
- Testing verifies correctness
- Evolution improves systems

---

*Instruction set expansion enhances CPU capabilities*
