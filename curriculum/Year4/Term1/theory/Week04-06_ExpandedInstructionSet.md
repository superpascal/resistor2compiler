# Week 4-6: Expanded Instruction Set - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand how to expand CPU instruction set
- Design new instructions
- Expand microcode ROM capacity
- Program new microcode sequences
- Test new instructions

## Prerequisites

- Completed Weeks 1-3 (SAP-1 Improvements)
- Understanding of microcode (Year 3)
- Understanding of instruction execution
- Experience with EEPROM programming
- Access to Malvino & Brown textbook

**Required Reading** (Primary Reference):
- **Malvino & Brown, Chapter 11-3**: SAP-2 Memory-Reference Instructions (LDA, STA, MVI)
- **Malvino & Brown, Chapter 11-4**: SAP-2 Register Instructions (MOV, ADD/SUB with registers, INR/DCR)
- **Malvino & Brown, Chapter 11-6**: SAP-2 Logic Instructions (CMA, ANA, ORA, XRA)

**Book Integration**:
- Study SAP-2 instruction set expansion: SAP-1 (5 instructions) → SAP-2 (42 instructions)
- Understand why more instructions are useful (efficiency, capability)
- Compare SAP-2 register instructions (11-4) to SAP-1 limitations
- Study SAP-2 logic instructions (11-6) - understand bitwise operations
- Plan which SAP-2-style instructions to add to enhanced SAP-1

**Book-Based Exercise**:
- Exercise: Study SAP-2 register instructions (Chapter 11-4), design similar for enhanced SAP-1
- Exercise: Translate SAP-2 logic instruction example (from book) to enhanced SAP-1 microcode
- Exercise: Compare SAP-2 addressing modes to SAP-1 addressing (what's possible vs what's not)

## Key Concepts

### 1. Instruction Set Expansion

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

**SAP-1 limitations**:
- Limited opcode space (4 bits = 16 opcodes)
- Limited microcode space
- Limited control signals
- Simple instruction format

### 2. New Instruction Examples

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

**SUB (Subtract)**:
- May not have been in original SAP-1
- Adds subtraction capability
- Uses two's complement
- Expands ALU usage

### 3. Microcode ROM Expansion

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

### 4. Instruction Register Expansion

**IR width expansion**:
- Original: 4-bit opcode + 4-bit operand
- Expanded: 8-bit opcode space (conceptual)
- More opcodes possible
- Still use 4-bit for now (compatibility)

**Future expansion**:
- Full 8-bit opcode space
- 256 possible instructions
- More addressing modes
- More operand formats

### 5. Microcode Design for New Instructions

**Design process**:
1. Define instruction behavior
2. Break into microsteps
3. Assign control signals to each step
4. Program microcode ROM
5. Test instruction
6. Verify operation

**Example: LDB instruction**:
- Step 0: Fetch instruction (standard)
- Step 1: Load instruction into IR
- Step 2: Decode (determine LDB)
- Step 3: Fetch operand address
- Step 4: Load data into Register B
- Complete

### 6. Testing New Instructions

**Test procedures**:
- Write test program using new instruction
- Execute program
- Verify correct operation
- Compare to old method
- Document results

**Verification**:
- Instruction executes correctly
- Results match expectations
- More efficient than old method
- No side effects

### 7. Instruction Set Architecture (ISA) Evolution

**ISA development**:
- Start simple (SAP-1)
- Add useful instructions
- Optimize common operations
- Balance complexity vs. usefulness

**Real-world examples**:
- 6502 → 65C816 evolution
- x86 evolution
- RISC vs. CISC
- Modern CPU features

### 8. Programming with New Instructions

**Benefits**:
- Shorter programs
- More readable code
- More efficient execution
- Easier programming

**Example**:
- Old: LDA addr, (MOV via ALU), use B
- New: LDB addr, use B
- Saves instructions
- Clearer intent

## Mathematical Foundations

### Opcode Space

**4-bit opcode**: 2^4 = 16 possible instructions
- SAP-1 uses subset
- Room for expansion
- Can add new instructions

**8-bit opcode**: 2^8 = 256 possible instructions
- Conceptual expansion
- Much more room
- Future possibility

### Microcode Space

**Address space**: Opcode bits + Microstep bits
- More opcodes need more space
- More microsteps need more space
- Balance needed

## Common Misconceptions

1. **"More instructions is always better"**
   - Clarify: Balance needed
   - Show complexity trade-offs

2. **"All instructions are equal"**
   - Clarify: Some more useful
   - Show usage patterns

3. **"Expansion is easy"**
   - Clarify: Requires careful design
   - Show microcode complexity

## Connections to Weeks 1-3

- **Improved System**: Reliable base for expansion
- **Microcode**: Foundation for new instructions
- **Testing**: Skills from improvements used

## Connections to Weeks 7-9

- **Memory Expansion**: New instructions may use it
- **System Enhancement**: Part of overall expansion
- **16-bit Preparation**: Understanding ISA evolution

## Next Steps

After expanding instruction set, students will:
- Expand memory (Weeks 9-12)
- Implement Harvard architecture
- Prepare for 16-bit systems

---

*Instruction set expansion enhances CPU capabilities*
