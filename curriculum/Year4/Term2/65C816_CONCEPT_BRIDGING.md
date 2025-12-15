# 65C816 Concept Bridging Guide

## Overview

This document bridges the gap between **Malvino & Brown's Part 3 (Programming Microprocessors)** and the **65C816 microprocessor** used in the curriculum. The book covers different CPUs (6502, 6800, 8080/8085, 8086/8088), but the **general concepts** apply to all microprocessors, including the 65C816.

**Purpose**: Help students understand how general microprocessor concepts from the book map to 65C816-specific implementation.

---

## Chapter 13: Intro to Microprocessors

### Book Coverage
- General microprocessor concepts
- Register models
- Addressing concepts
- Instruction types
- Examples from: 6502, 6800, 8080/8085, 8086/8088

### 65C816 Mapping

| Book Concept | Book Examples | 65C816 Implementation |
|-------------|---------------|-------------------------|
| **Accumulator** | 6502: A register (8-bit)<br>8080: A register (8-bit)<br>8086: AX register (16-bit) | **A register** (8-bit or 16-bit, selectable) |
| **Index Registers** | 6502: X, Y (8-bit)<br>8086: SI, DI (16-bit) | **X, Y registers** (8-bit or 16-bit, selectable) |
| **Stack Pointer** | 6502: SP (8-bit)<br>8080: SP (16-bit)<br>8086: SP (16-bit) | **SP register** (16-bit, always) |
| **Program Counter** | All CPUs have PC | **PC register** (16-bit) + **K register** (8-bit bank) = 24-bit addressing |
| **Status/Flags Register** | 6502: P (8 flags)<br>8080: Flags (5 flags)<br>8086: FLAGS (16 flags) | **P register** (8 flags: C, Z, I, D, X, M, V, N) |
| **Addressing Modes** | Varies by CPU | **13 addressing modes** (immediate, absolute, indexed, indirect, etc.) |
| **Instruction Types** | Data transfer, arithmetic, logic, branches, etc. | **Same categories**, different mnemonics |

### Key Insight
**All microprocessors have similar concepts** (accumulator, index registers, stack, program counter, flags). The 65C816 has these same concepts, just with different names and capabilities. Students should:
1. Read Chapter 13 to understand **what** these concepts are
2. Reference 65C816 datasheet to see **how** 65C816 implements them
3. Understand that concepts are universal, implementations vary

---

## Chapter 14: Programming & Languages

### Book Coverage
- Assembly language concepts
- Instruction categories
- Program structure
- Addressing modes (general)
- Examples from multiple CPUs

### 65C816 Mapping

| Book Concept | General Pattern | 65C816 Example |
|-------------|----------------|----------------|
| **Data Transfer** | Load, Store, Move | `LDA #$42` (load immediate)<br>`STA $1000` (store absolute)<br>`TAX` (transfer A to X) |
| **Arithmetic** | Add, Subtract, Compare | `ADC $1000` (add with carry)<br>`SBC $2000` (subtract with carry)<br>`CMP #$10` (compare) |
| **Logic** | AND, OR, XOR | `AND #$0F` (mask lower 4 bits)<br>`ORA $1000` (OR with memory)<br>`EOR #$FF` (XOR, invert) |
| **Branches** | Conditional and unconditional jumps | `BEQ label` (branch if equal)<br>`JMP $1000` (unconditional jump)<br>`JSR subroutine` (jump to subroutine) |
| **Stack Operations** | Push, Pull | `PHA` (push accumulator)<br>`PLA` (pull accumulator)<br>`PHP` (push flags) |
| **Program Structure** | Labels, directives, comments | Same concepts, CC65 assembler syntax |

### Key Insight
**Assembly language concepts are universal**. The book teaches general patterns (load data, perform arithmetic, branch conditionally). 65C816 uses the same patterns, just with different mnemonics. Students should:
1. Read Chapter 14 to understand **general assembly patterns**
2. Learn 65C816-specific mnemonics from instruction set reference
3. Practice translating book examples to 65C816 syntax

---

## Chapter 15: System Overview

### Book Coverage
- Microprocessor architecture patterns
- Register organization
- Memory models
- System design concepts
- Examples: 6502, 6800, 8080/8085, 8086/8088

### 65C816 Mapping

#### Register Organization Comparison

| CPU Family | Register Model | 65C816 Equivalent |
|-----------|----------------|-------------------|
| **6502** | A (8-bit), X (8-bit), Y (8-bit), SP (8-bit), PC (16-bit), P (8 flags) | **Similar**: A, X, Y, SP, PC, P (65C816 is 6502-compatible in emulation mode) |
| **8080/8085** | A, B, C, D, E, H, L (8-bit), SP (16-bit), PC (16-bit), Flags | **Different**: 65C816 uses A, X, Y model (not B, C, D, E) |
| **8086/8088** | AX, BX, CX, DX, SI, DI, BP, SP (16-bit), IP (16-bit), FLAGS (16-bit) | **Similar concepts**: 16-bit registers, index registers, stack pointer |
| **6800** | A, B (8-bit), IX (16-bit), SP (16-bit), PC (16-bit), CCR (8 flags) | **Similar**: Accumulator, index register, stack pointer concepts |

#### Memory Model Comparison

| CPU | Address Space | 65C816 Equivalent |
|-----|--------------|-------------------|
| **6502** | 16-bit (64KB) | **Emulation mode**: 16-bit addressing (64KB)<br>**Native mode**: 24-bit addressing (16MB) |
| **8080/8085** | 16-bit (64KB) | **Native mode**: 24-bit addressing (16MB) - much larger |
| **8086/8088** | 20-bit (1MB) via segmentation | **Native mode**: 24-bit flat addressing (16MB) - simpler model |
| **6800** | 16-bit (64KB) | **Native mode**: 24-bit addressing (16MB) - much larger |

#### Key Architectural Differences

**65C816 Advantages**:
- **24-bit addressing** (16MB) vs. book's examples (64KB-1MB)
- **8/16-bit register modes** (can switch between modes)
- **Banked memory** (256 banks of 64KB each)
- **Harvard-inspired architecture** (separate program ROM/data RAM)

**65C816 Similarities**:
- **Register-based architecture** (like 6502, 8080)
- **Stack-based subroutines** (like all CPUs in book)
- **Memory-mapped I/O** (like 6502, 6800)
- **Flag-based conditional branches** (like all CPUs)

### Key Insight
**Architecture concepts are universal** (registers, memory, I/O, addressing). 65C816 implements these concepts with modern enhancements (24-bit addressing, banked memory). Students should:
1. Read Chapter 15 to understand **general architecture patterns**
2. Study 65C816 datasheet to see **how 65C816 implements these patterns**
3. Understand that 65C816 is **enhanced** (more address space, more features) but uses **same concepts**

---

## Chapters 16-23: Instruction Sets

### Book Coverage
Instruction categories with examples from different CPUs:
- Chapter 16: Data Transfer (6502: LDA, STA; 8080: MOV, LDA, STA)
- Chapter 17: Arithmetic (6502: ADC, SBC; 8080: ADD, SUB)
- Chapter 18: Logic (6502: AND, ORA, EOR; 8080: ANA, ORA, XRA)
- Chapter 19: Branches (6502: BEQ, BNE; 8080: JMP, JZ, JNZ)
- Chapter 20: Stack (6502: PHA, PLA; 8080: PUSH, POP)
- Chapter 21: Shifts (6502: ASL, LSR; 8080: RAL, RAR)
- Chapter 22: CPU Control (6502: BRK, RTI; 8080: HLT, NOP)
- Chapter 23: Other (various specialized instructions)

### 65C816 Instruction Mapping

#### Data Transfer (Chapter 16)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `LDA #$42` | 6502 | `LDA #$42` | **Same mnemonic!** 65C816 is 6502-compatible |
| `STA $1000` | 6502 | `STA $1000` | **Same mnemonic!** |
| `MOV A,B` | 8080 | `TAX` then `TXA` | 65C816 uses transfer instructions (TAX, TAY, etc.) |
| `LDA $1000` | 8080 | `LDA $1000` | **Same concept**, different addressing modes available |

**Key Insight**: 65C816 is **6502-compatible**, so many instructions are **identical**. For 8080/8085 examples, students learn the **concept** (data transfer), then use 65C816's equivalent.

#### Arithmetic (Chapter 17)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `ADC $1000` | 6502 | `ADC $1000` | **Same mnemonic!** |
| `ADD B` | 8080 | `ADC` (add with carry) | 65C816 uses ADC (with carry), not separate ADD |
| `SUB C` | 8080 | `SBC` (subtract with carry) | 65C816 uses SBC (with borrow), not separate SUB |
| `CMP #$10` | 6502 | `CMP #$10` | **Same mnemonic!** |

**Key Insight**: 65C816 arithmetic is **6502-compatible**. For 8080 examples, students learn the **concept** (addition, subtraction, comparison), then use 65C816's ADC/SBC/CMP.

#### Logic (Chapter 18)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `AND #$0F` | 6502 | `AND #$0F` | **Same mnemonic!** |
| `ORA $1000` | 6502 | `ORA $1000` | **Same mnemonic!** |
| `EOR #$FF` | 6502 | `EOR #$FF` | **Same mnemonic!** |
| `ANA B` | 8080 | `AND` (with register) | 65C816 uses `AND` with addressing modes |
| `XRA C` | 8080 | `EOR` (XOR) | 65C816 uses `EOR` (same as 6502) |

**Key Insight**: 65C816 logic instructions are **6502-compatible**. For 8080 examples, students learn the **concept** (AND, OR, XOR), then use 65C816's AND/ORA/EOR.

#### Branches (Chapter 19)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `BEQ label` | 6502 | `BEQ label` | **Same mnemonic!** |
| `BNE loop` | 6502 | `BNE loop` | **Same mnemonic!** |
| `JMP $1000` | 6502/8080 | `JMP $1000` | **Same mnemonic!** |
| `JZ label` | 8080 | `BEQ label` | 65C816 uses BEQ (branch if equal/zero) |
| `JNZ loop` | 8080 | `BNE loop` | 65C816 uses BNE (branch if not equal/not zero) |
| `CALL $5000` | 8080 | `JSR $5000` | 65C816 uses JSR (Jump to Subroutine) |
| `RET` | 8080 | `RTS` | 65C816 uses RTS (Return from Subroutine) |

**Key Insight**: 65C816 branches are **6502-compatible**. For 8080 examples, students learn the **concept** (conditional branches, subroutines), then use 65C816's equivalents (BEQ/BNE for JZ/JNZ, JSR/RTS for CALL/RET).

#### Stack (Chapter 20)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `PHA` | 6502 | `PHA` | **Same mnemonic!** |
| `PLA` | 6502 | `PLA` | **Same mnemonic!** |
| `PUSH B` | 8080 | `PHX` or `PHY` | 65C816 has PHX, PHY (push X, push Y) |
| `POP C` | 8080 | `PLX` or `PLY` | 65C816 has PLX, PLY (pull X, pull Y) |
| `PHP` | 6502 | `PHP` | **Same mnemonic!** |
| `PLP` | 6502 | `PLP` | **Same mnemonic!** |

**Key Insight**: 65C816 stack operations are **6502-compatible**. For 8080 examples, students learn the **concept** (push/pull registers), then use 65C816's PHA/PLA/PHX/PLX/PHY/PLY.

#### Shifts (Chapter 21)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `ASL A` | 6502 | `ASL A` | **Same mnemonic!** |
| `LSR $1000` | 6502 | `LSR $1000` | **Same mnemonic!** |
| `ROL A` | 6502 | `ROL A` | **Same mnemonic!** |
| `ROR $1000` | 6502 | `ROR $1000` | **Same mnemonic!** |
| `RAL` | 8080 | `ROL` | 65C816 uses ROL (rotate left through carry) |
| `RAR` | 8080 | `ROR` | 65C816 uses ROR (rotate right through carry) |

**Key Insight**: 65C816 shift/rotate instructions are **6502-compatible**. For 8080 examples, students learn the **concept** (shift, rotate), then use 65C816's ASL/LSR/ROL/ROR.

#### CPU Control (Chapter 22)

| Book Example | CPU | 65C816 Equivalent | Notes |
|-------------|-----|------------------|-------|
| `BRK` | 6502 | `BRK` | **Same mnemonic!** |
| `RTI` | 6502 | `RTI` | **Same mnemonic!** |
| `NOP` | All | `NOP` | **Same mnemonic!** |
| `HLT` | 8080 | `STP` or `WAI` | 65C816 uses STP (stop) or WAI (wait for interrupt) |
| `CLC` | 6502 | `CLC` | **Same mnemonic!** |
| `SEC` | 6502 | `SEC` | **Same mnemonic!** |

**Key Insight**: 65C816 control instructions are **6502-compatible**. For 8080 examples, students learn the **concept** (interrupts, halting, flag control), then use 65C816's equivalents.

---

## Addressing Modes Comparison

### Book Coverage
Different CPUs have different addressing modes. The book shows examples from:
- 6502: Immediate, absolute, zero-page, indexed, indirect
- 8080/8085: Immediate, direct, register, indirect
- 8086/8088: Immediate, direct, register, indexed, based-indexed, etc.

### 65C816 Addressing Modes

**65C816 has 13 addressing modes**, combining the best of multiple CPU families:

| Addressing Mode | 65C816 Syntax | Similar To | Notes |
|----------------|---------------|------------|-------|
| **Immediate** | `LDA #$42` | 6502, 8080 | Value in instruction |
| **Absolute** | `LDA $1000` | 6502, 8080 | Direct address |
| **Absolute Indexed** | `LDA $1000,X` | 6502 | Address + index register |
| **Zero-Page** | `LDA $10` | 6502 | Fast access to first 256 bytes |
| **Zero-Page Indexed** | `LDA $10,X` | 6502 | Zero-page + index |
| **Indirect** | `LDA ($10)` | 6502 | Pointer at zero-page |
| **Indirect Indexed** | `LDA ($10),Y` | 6502 | Pointer + Y register |
| **Indexed Indirect** | `LDA ($10,X)` | 6502 | Pointer + X (pre-indexed) |
| **Stack Relative** | `LDA $10,S` | 6800 | Stack pointer + offset |
| **Absolute Long** | `LDA $001000` | 8086 | 24-bit address |
| **Absolute Long Indexed** | `LDA $001000,X` | 8086 | 24-bit address + index |
| **Absolute Indirect Long** | `LDA [$1000]` | 8086 | 24-bit pointer |
| **Program Counter Relative** | `BEQ label` | 6502, 6800 | 8-bit signed offset |

**Key Insight**: 65C816 combines addressing modes from **multiple CPU families**:
- **6502-style**: Zero-page, indexed, indirect (fast, efficient)
- **6800-style**: Stack relative (useful for local variables)
- **8086-style**: Long addressing (24-bit addresses)

Students should:
1. Read book chapters to understand **what addressing modes are** and **why they're useful**
2. Learn 65C816's specific addressing modes (which include all the useful ones from the book's examples)
3. Understand that 65C816 has **more addressing modes** than any single CPU in the book (best of all worlds)

---

## Translation Exercises

### Exercise 1: Translate 6502 Code to 65C816

**Book Example (6502)**:
```assembly
LDA #$10
STA $2000
ADC $2000
STA $2001
```

**65C816 Translation**:
```assembly
LDA #$10      ; Same! 65C816 is 6502-compatible
STA $2000     ; Same!
ADC $2000     ; Same!
STA $2001     ; Same!
```

**Result**: **No translation needed!** 65C816 is 6502-compatible, so 6502 code works directly (in emulation mode) or with minor syntax adjustments (in native mode).

---

### Exercise 2: Translate 8080/8085 Concepts to 65C816

**Book Example (8080)**:
```assembly
MVI A,10H     ; Move immediate 10H to accumulator
MOV B,A       ; Move A to B register
ADD B         ; Add B to A
STA 2000H     ; Store A at address 2000H
```

**65C816 Translation**:
```assembly
LDA #$10      ; Load immediate (65C816 uses LDA, not MVI)
TAX           ; Transfer A to X (65C816 doesn't have B register, use X or Y)
ADC $2000     ; Add (65C816 uses ADC with addressing mode, not separate ADD B)
STA $2000     ; Store (same concept, different syntax)
```

**Key Differences**:
- 8080: `MVI A,10H` → 65C816: `LDA #$10` (immediate addressing)
- 8080: `MOV B,A` → 65C816: `TAX` (transfer A to X, since no B register)
- 8080: `ADD B` → 65C816: `ADC $2000` (add with addressing mode, not register-to-register)
- 8080: `STA 2000H` → 65C816: `STA $2000` (same concept, $ prefix for hex)

**Learning Approach**:
1. Understand the **concept** from 8080 example (load, move, add, store)
2. Learn 65C816's **equivalent instructions** (LDA, TAX, ADC, STA)
3. Practice translating concepts, not exact syntax

---

### Exercise 3: Translate 8086 Concepts to 65C816

**Book Example (8086)**:
```assembly
MOV AX,0010H  ; Move immediate to AX register
ADD AX,BX     ; Add BX to AX
MOV [2000H],AX ; Store AX to memory
```

**65C816 Translation**:
```assembly
LDA #$10      ; Load immediate (65C816 A register = 8086 AX)
ADC $2000     ; Add (65C816 uses addressing modes, not register-to-register ADD)
STA $2000     ; Store (65C816 uses STA with addressing mode)
```

**Key Differences**:
- 8086: 16-bit registers (AX, BX) → 65C816: 16-bit A register (can be 8 or 16-bit mode)
- 8086: `ADD AX,BX` → 65C816: `ADC $2000` (use addressing mode, not register-to-register)
- 8086: `MOV [2000H],AX` → 65C816: `STA $2000` (store accumulator)

**Learning Approach**:
1. Understand the **concept** from 8086 example (16-bit operations, register-to-register, memory access)
2. Learn 65C816's **addressing modes** (which provide similar flexibility)
3. Understand that 65C816 uses **addressing modes** instead of separate register-to-register instructions

---

## Concept Mapping Strategy

### Step 1: Read Book for Concepts
**Goal**: Understand general microprocessor concepts

**Example**: Read Chapter 16 (Data Transfer)
- Learn: What are data transfer instructions?
- Learn: Why do we need them?
- Learn: How do they work in general?

**Don't worry about**: Specific CPU mnemonics (yet)

---

### Step 2: Map Concepts to 65C816
**Goal**: See how 65C816 implements these concepts

**Example**: After reading Chapter 16
- Reference: 65C816 Instruction Set Reference (Data Transfer section)
- Learn: 65C816 has LDA, STA, LDX, STX, LDY, STY
- Learn: 65C816 addressing modes for these instructions
- Practice: Write 65C816 data transfer code

---

### Step 3: Compare and Contrast
**Goal**: Understand similarities and differences

**Example**: Compare 6502 vs 65C816
- **Similarity**: Both use LDA, STA (same mnemonics!)
- **Difference**: 65C816 has more addressing modes (absolute long, stack relative)
- **Insight**: 65C816 is 6502-compatible but enhanced

**Example**: Compare 8080 vs 65C816
- **Similarity**: Both have load, store, transfer concepts
- **Difference**: Different mnemonics (MVI vs LDA, MOV vs TAX)
- **Insight**: Concepts are universal, implementations vary

---

### Step 4: Practice Translation
**Goal**: Become comfortable with 65C816 syntax

**Example**: Translate book examples
- Take 8080 example from book
- Identify the **concept** (load immediate, add, store)
- Write 65C816 equivalent using 65C816 syntax
- Test on 65C816 system

---

## Teaching Strategy

### For Instructors

**When Teaching Chapter 13 (Intro to Microprocessors)**:
1. Present general concepts (registers, addressing, instruction types)
2. Show examples from book (6502, 8080, etc.)
3. **Then** show 65C816 equivalents using this bridging guide
4. Emphasize: Concepts are universal, implementations vary

**When Teaching Chapter 14 (Programming & Languages)**:
1. Present general assembly patterns
2. Show book examples (different CPUs)
3. **Then** show 65C816 equivalents
4. Practice: Translate book examples to 65C816

**When Teaching Chapter 15 (System Overview)**:
1. Present general architecture patterns
2. Compare different CPUs from book
3. **Then** show 65C816 architecture
4. Emphasize: 65C816 combines best features from multiple CPU families

**When Teaching Chapters 16-23 (Instruction Sets)**:
1. Present instruction category (e.g., Data Transfer)
2. Show examples from book (6502, 8080, etc.)
3. **Then** show 65C816 instructions in same category
4. Practice: Write 65C816 code for same operations

---

### For Students

**Reading Strategy**:
1. **Read book chapter** for conceptual understanding
2. **Reference this bridging guide** to see 65C816 equivalents
3. **Reference 65C816 instruction set** for specific syntax
4. **Practice** writing 65C816 code

**Translation Practice**:
1. Take book example (any CPU)
2. Identify the **concept** (what is it trying to do?)
3. Find 65C816 **equivalent instruction**
4. Write 65C816 code
5. Test on 65C816 system

**Key Insight**: Don't memorize every CPU's syntax. Instead:
- Understand **concepts** (what are we trying to do?)
- Learn **65C816 syntax** (how do we do it on our CPU?)
- Practice **translation** (how do concepts map to 65C816?)

---

## Common Translation Patterns

### Pattern 1: 6502 → 65C816
**Result**: **Usually identical!** 65C816 is 6502-compatible.

**Example**:
- 6502: `LDA #$42` → 65C816: `LDA #$42` ✅ **Same!**
- 6502: `BEQ label` → 65C816: `BEQ label` ✅ **Same!**
- 6502: `PHA` → 65C816: `PHA` ✅ **Same!**

**When Different**:
- 6502: 16-bit addressing only
- 65C816: Can use 24-bit addressing (absolute long mode)
- Example: `LDA $001000` (24-bit address, not available on 6502)

---

### Pattern 2: 8080/8085 → 65C816
**Result**: **Different syntax, same concepts**

**Translation Rules**:
- `MVI A,value` → `LDA #value` (load immediate)
- `MOV B,A` → `TAX` (transfer A to X, since no B register)
- `ADD B` → `ADC $address` (add with addressing mode)
- `SUB C` → `SBC $address` (subtract with addressing mode)
- `JMP address` → `JMP $address` (jump, same concept)
- `CALL address` → `JSR $address` (subroutine call)
- `RET` → `RTS` (return from subroutine)
- `PUSH B` → `PHX` or `PHY` (push X or Y register)
- `POP C` → `PLX` or `PLY` (pull X or Y register)

**Key Insight**: 8080 uses **register-to-register** operations (MOV B,A, ADD B). 65C816 uses **addressing modes** instead (TAX, ADC $address). Both achieve the same goal, different approach.

---

### Pattern 3: 8086/8088 → 65C816
**Result**: **Different syntax, similar concepts**

**Translation Rules**:
- `MOV AX,value` → `LDA #value` (16-bit load immediate)
- `ADD AX,BX` → `ADC $address` (add with addressing mode)
- `MOV [address],AX` → `STA $address` (store to memory)
- `CMP AX,BX` → `CMP $address` (compare with addressing mode)
- `JZ label` → `BEQ label` (jump if zero/equal)
- `JNZ loop` → `BNE loop` (jump if not zero/not equal)

**Key Insight**: 8086 uses **register-to-register** operations extensively. 65C816 uses **addressing modes** to achieve similar results. Both support 16-bit operations.

---

### Pattern 4: 6800 → 65C816
**Result**: **Different syntax, similar concepts**

**Translation Rules**:
- `LDA #value` → `LDA #value` (load immediate, same!)
- `STA address` → `STA $address` (store, same concept)
- `ADD A` → `ADC $address` (add with addressing mode)
- `BEQ label` → `BEQ label` (branch if equal, same!)
- `JSR address` → `JSR $address` (jump to subroutine, same!)

**Key Insight**: 6800 and 65C816 have similar instruction sets (both inspired by 6502 family). Many concepts translate directly.

---

## Addressing Mode Translation

### Book Examples → 65C816 Equivalents

| Book Example | CPU | Concept | 65C816 Equivalent |
|-------------|-----|---------|-------------------|
| `LDA #$42` | 6502 | Immediate | `LDA #$42` ✅ **Same!** |
| `LDA $1000` | 6502 | Absolute | `LDA $1000` ✅ **Same!** |
| `LDA $1000,X` | 6502 | Indexed | `LDA $1000,X` ✅ **Same!** |
| `LDA ($10),Y` | 6502 | Indirect indexed | `LDA ($10),Y` ✅ **Same!** |
| `LDA $10` | 6502 | Zero-page | `LDA $10` ✅ **Same!** |
| `LDA [BX]` | 8086 | Register indirect | `LDA ($10),Y` (use zero-page indirect) |
| `LDA [BX+SI]` | 8086 | Based-indexed | `LDA ($10,X),Y` (indexed indirect) |
| `LDA $10,SP` | 6800 | Stack relative | `LDA $10,S` ✅ **Same concept!** |

**Key Insight**: 65C816 has addressing modes that cover **all the useful patterns** from the book's examples, plus more (24-bit addressing, absolute long, etc.).

---

## Practical Translation Examples

### Example 1: Simple Addition Program

**8080 Code (from book)**:
```assembly
MVI A,05H      ; Load 5 into A
MVI B,03H      ; Load 3 into B
ADD B          ; Add B to A (result in A)
STA 2000H      ; Store result at 2000H
HLT            ; Halt
```

**65C816 Translation**:
```assembly
LDA #$05       ; Load 5 into A (immediate)
LDX #$03       ; Load 3 into X (we'll use X instead of B)
STX $1000      ; Store X to temp location
ADC $1000      ; Add temp location to A (result in A)
STA $2000      ; Store result at $2000
STP            ; Stop (65C816 uses STP, not HLT)
```

**Or, simpler 65C816 version**:
```assembly
LDA #$05       ; Load 5
CLC            ; Clear carry
ADC #$03       ; Add 3 (immediate mode, no need for B register)
STA $2000      ; Store result
STP            ; Stop
```

**Key Learning**: 65C816 can use **immediate addressing** for the second operand, eliminating the need for a separate B register.

---

### Example 2: Loop with Counter

**8080 Code (from book)**:
```assembly
MVI C,10H      ; Load counter with 16
LOOP: DCR C    ; Decrement counter
      JNZ LOOP ; Jump if not zero
      HLT      ; Halt
```

**65C816 Translation**:
```assembly
LDX #$10       ; Load counter with 16 (use X register)
LOOP: DEX      ; Decrement X (65C816 uses DEX, not DCR C)
      BNE LOOP ; Branch if not equal (65C816 uses BNE, not JNZ)
      STP      ; Stop
```

**Key Learning**: 65C816 uses **index registers** (X, Y) for counting, similar to 8080's C register, but with different mnemonics.

---

### Example 3: Subroutine Call

**8080 Code (from book)**:
```assembly
CALL SUBROUTINE ; Call subroutine
HLT             ; Halt
SUBROUTINE:     ; Subroutine start
  MVI A,42H     ; Load 42H
  RET           ; Return
```

**65C816 Translation**:
```assembly
JSR SUBROUTINE ; Jump to subroutine (65C816 uses JSR, not CALL)
STP            ; Stop
SUBROUTINE:    ; Subroutine start
  LDA #$42     ; Load 42H (65C816 uses LDA, not MVI A)
  RTS          ; Return from subroutine (65C816 uses RTS, not RET)
```

**Key Learning**: 65C816 uses **JSR/RTS** for subroutines (same as 6502), not CALL/RET (8080). Concept is identical, syntax differs.

---

## Summary: Bridging Strategy

### The Gap
- **Book covers**: 6502, 6800, 8080/8085, 8086/8088
- **Curriculum uses**: 65C816
- **Problem**: Different CPUs, different syntax

### The Solution

**Three-Layer Approach**:

1. **Conceptual Layer** (Book):
   - Read book for **general concepts** (what are registers, addressing modes, instruction types?)
   - Understand **why** these concepts exist
   - See examples from **multiple CPUs** (broader understanding)

2. **Mapping Layer** (This Document):
   - Map book concepts to **65C816 equivalents**
   - Show **translation patterns** (how to convert book examples to 65C816)
   - Provide **comparison tables** (book CPU vs 65C816)

3. **Implementation Layer** (65C816 Reference):
   - Use **65C816 Instruction Set Reference** (`docs/65C816_INSTRUCTION_SET_REFERENCE.md`) for specific syntax
   - Practice **writing 65C816 code**
   - Test on **actual 65C816 system**

### Key Principles

1. **Concepts are Universal**: All microprocessors have similar concepts (registers, addressing, instructions). Learn the concepts, then apply to 65C816.

2. **65C816 is 6502-Compatible**: Many book examples from 6502 work directly on 65C816 (same mnemonics). This is a huge advantage!

3. **Translation is Concept-Based**: When translating from other CPUs (8080, 8086), focus on the **concept** (what are we trying to do?), not exact syntax.

4. **65C816 is Enhanced**: 65C816 has more features than any single CPU in the book (24-bit addressing, more addressing modes, 8/16-bit modes). Students get the best of all worlds.

5. **Practice Makes Perfect**: Regular translation exercises help students become comfortable with 65C816 syntax while understanding general concepts.

---

## Additional Resources

### For Students
- **65C816 Instruction Set Reference** (`docs/65C816_INSTRUCTION_SET_REFERENCE.md`) - Complete instruction set
- **W65C816 Datasheet** - Hardware reference
- **65C816 Programming Manual** - Detailed instruction descriptions
- **CC65 Documentation** - Assembler syntax and directives

### For Instructors
- **Translation Exercise Bank** - Practice problems converting book examples to 65C816
- **Comparison Worksheets** - Side-by-side comparisons of book CPUs vs 65C816
- **Concept Mapping Charts** - Visual guides showing concept relationships

---

## Conclusion

**The gap is bridgeable!** While the book covers different CPUs, the **concepts are universal**. By:
1. Using the book for **conceptual understanding**
2. Using this bridging guide for **concept mapping**
3. Using 65C816 references for **implementation details**

Students get the **best of both worlds**:
- **Broad understanding** from seeing multiple CPU examples
- **Deep expertise** in 65C816 (the CPU they'll actually use)
- **Translation skills** (understanding how concepts map across CPUs)

**Result**: Students understand general microprocessor concepts AND can program the 65C816 effectively.

---

**Document Created**: 2025-12-15  
**Purpose**: Bridge the gap between Malvino & Brown's Part 3 (different CPUs) and 65C816-specific curriculum implementation
