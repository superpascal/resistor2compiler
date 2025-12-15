# Week 10-12: Introduction to 65C816 CPU - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand the 65C816 CPU architecture
- Compare SAP-1 to 65C816
- Understand 16-bit operations
- Understand 24-bit addressing
- Understand addressing modes
- Map SAP-1 components to 65C816

## Prerequisites

- Completed Term 1 (Enhanced SAP-1)
- Understanding of CPU architecture (from SAP-1)
- Understanding of memory systems
- Understanding of instruction execution

**Required Reading** (Primary Reference): 
- **Malvino & Brown, Chapter 11-5** (SAP-2: Jump and Call Instructions) ⭐ **KEY CONCEPT**
  - JMP (unconditional jump)
  - JM, JZ, JNZ (conditional jumps based on flags)
  - CALL/RET (subroutines with automatic return address saving)
  - **Purpose**: Understand program flow control and subroutines before learning 65C816 branches
- **Malvino & Brown, Chapter 13** (Intro to Microprocessors) - Sections 13-1 to 13-5
  - General microprocessor concepts
  - Register models
  - Addressing concepts
  - Instruction types
  - **Purpose**: Understand universal microprocessor concepts that apply to 65C816
- **Malvino & Brown, Chapter 15** (System Overview) - Sections 15-1 to 15-5
  - Microprocessor architecture patterns
  - Register organization
  - Memory models
  - System design concepts
  - **Purpose**: Understand system architecture patterns for 65C816 system design

**Supplementary Reading**:
- **W65C816 Datasheet** - 65C816-specific hardware reference
- **65C816 Programming Manual** - 65C816-specific instruction set and addressing modes
- **65C816 Concept Bridging Guide** (see `../65C816_CONCEPT_BRIDGING.md`) - Maps book concepts to 65C816 equivalents

**Book Integration**: 
- Read SAP-2 jump and call instructions (11-5) to understand subroutines conceptually
- Compare SAP-2 JMP to 65C816 JMP (same concept, different implementation)
- Compare SAP-2 CALL/RET to 65C816 JSR/RTS (same concept, different mnemonics)
- Study book's microprocessor examples (Chapter 13) to understand universal concepts
- Apply book's system design patterns (Chapter 15) to 65C816 system

**Note**: The book is the **primary conceptual reference** for understanding CPU enhancements. While the book covers different CPUs (6502, 6800, 8080/8085, 8086/8088), the general concepts (registers, addressing modes, instruction types, subroutines) apply to all microprocessors including the 65C816. Use the book for conceptual understanding, then use the bridging guide to see how concepts map to 65C816, then apply to 65C816 specifics.

## Key Concepts

### 1. The 65C816 Microprocessor

**What is the 65C816?**
- 16-bit microprocessor from Western Design Center
- Enhanced version of 6502
- 24-bit addressing (16 MB)
- 16-bit data operations
- Used in Apple IIGS, Super Nintendo

**Key features**:
- 16-bit ALU operations
- 24-bit address space
- Multiple addressing modes
- Stack pointer
- Interrupts
- Emulation and native modes

### 2. Architecture Comparison

**SAP-1 vs 65C816**:

| Component | SAP-1 | 65C816 |
|-----------|-------|--------|
| Data width | 4-bit | 16-bit |
| Address width | 4-bit (expanded to 8) | 24-bit |
| Registers | A, B | A, X, Y, SP, P |
| Program Counter | 4-bit (8-bit expanded) | 16-bit + bank |
| Flags | C, Z | P register (8 flags) |
| Memory | 16 bytes (256 expanded) | Up to 16 MB |
| Instructions | ~6-8 | 256+ |
| Addressing modes | Direct | Many (immediate, direct, indirect, indexed, etc.) |

### 3. 65C816 Registers

**Accumulator (A)**:
- 16-bit (can use as 8-bit)
- Primary working register
- Used for arithmetic

**Index Registers (X, Y)**:
- 16-bit (can use as 8-bit)
- Used for indexing
- Used for counting

**Stack Pointer (SP)**:
- 16-bit
- Points to stack
- Auto-increment/decrement

**Program Counter (PC)**:
- 16-bit
- Extended with bank register (K)
- 24-bit effective address

**Status Register (P)**:
- 8 flags
- C (Carry), Z (Zero), I (Interrupt), D (Decimal), X (Index size), M (Memory size), V (Overflow), N (Negative)

### 4. 24-bit Addressing

**Address space**:
- 24-bit address = 16 MB
- Divided into 256 banks of 64KB each
- Bank register (K) selects bank
- PC + K = 24-bit address

**Banking concept**:
- Each bank is 64KB
- Bank $00 is typically used
- Can switch banks
- Enables large programs

### 5. Addressing Modes

**65C816 addressing modes**:
- **Immediate**: Value in instruction
- **Direct**: Address in instruction
- **Absolute**: Full address
- **Indexed**: Address + index register
- **Indirect**: Address points to address
- **Stack**: Stack-relative
- Many more...

**SAP-1 comparison**:
- SAP-1: Simple direct addressing
- 65C816: Many addressing modes
- More flexible
- More powerful

### 6. Instruction Set Comparison

**SAP-1 instructions**:
- LDA, ADD, SUB, OUT, HLT
- ~6-8 instructions
- Simple operations

**65C816 instructions**:
- 256+ instructions
- Arithmetic: ADD, SUB, ADC, SBC, etc.
- Logic: AND, OR, EOR, etc.
- Shifts: ASL, LSR, ROL, ROR
- Branches: BCC, BCS, BEQ, BNE, etc.
- Stack: PHA, PLA, PHX, PLX, etc.
- Many more...

### 7. Internal Architecture

**65C816 internals**:
- Microcoded control unit (like SAP-1, but complex)
- 16-bit ALU
- Register file
- Address generation unit
- Bus interface unit

**Similarities to SAP-1**:
- Both use microcode
- Both have ALU
- Both have registers
- Both have program counter
- Both fetch-decode-execute

**Differences**:
- 65C816 much more complex
- More registers
- More addressing modes
- More instructions
- Hardware stack

### 8. System Design Implications

**Designing with 65C816**:
- Need to support 24-bit addressing
- Need to handle 16-bit data
- Need to support addressing modes
- Need interrupt handling
- Need stack support

**Compared to SAP-1**:
- More complex system
- More memory needed
- More I/O needed
- More support circuits
- But more powerful

## Mathematical Foundations

### Address Space

**24-bit address**: 2^24 = 16,777,216 bytes = 16 MB
- Vastly larger than SAP-1
- Enables large programs
- Requires more memory hardware

### Data Width

**16-bit data**: 65,536 possible values
- Much larger than 4-bit (16 values)
- Enables larger numbers
- More useful for calculations

## Common Misconceptions

1. **"65C816 is completely different"**
   - Clarify: Same concepts, more complex
   - Show similarities

2. **"Too complex to understand"**
   - Clarify: Built on same foundations
   - Show progression from SAP-1

3. **"Can't build systems with it"**
   - Clarify: Many have built systems
   - Show examples

## Connections to Term 1

- **Enhanced SAP-1**: Understanding expansion
- **Memory Expansion**: Understanding larger memory
- **Instruction Expansion**: Understanding ISA evolution

## Connections to Weeks 17-24

- **System Design**: Will design 65C816 system
- **Prototype**: Will build 65C816 system
- **Year 5**: Will complete 65C816 system

## Next Steps

After understanding 65C816, students will:
- Design 65C816 system (Weeks 17-20)
- Build breadboard prototype (Weeks 21-24)
- Prepare for Year 5 completion

---

*65C816 introduces modern CPU architecture*
