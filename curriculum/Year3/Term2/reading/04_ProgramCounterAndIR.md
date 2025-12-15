# Chapter 4: Program Counter and Instruction Register

## Introduction

The Program Counter (PC) tracks which instruction to execute. The Instruction Register (IR) holds the current instruction. This chapter explains how to build these essential CPU components.

## The Program Counter (PC)

**PC function**:
- Holds address of next instruction to execute
- Increments after each instruction
- Can be loaded (for jumps)
- Connects to address bus (via MAR)

**PC characteristics**:
- 4-bit for SAP-1 (addresses 0-15)
- Increments automatically
- Can be loaded from bus
- Outputs to MAR

**Why we need PC**:
- CPU needs to know which instruction to fetch
- PC tracks program execution
- Enables sequential execution
- Enables jumps (load new address)

## Building the Program Counter

**PC construction**:
- Use 74HC161 or 74HC163 (4-bit counter)
- Connect to address bus (via MAR)
- Add increment control
- Add load control (for jumps)
- Add reset (start at 0)

**Control signals**:
- **CO** (Counter Out): Enable PC to bus/MAR
- **CE** (Counter Enable): Enable increment
- **CL** (Counter Load): Load from bus (for jumps)
- Clock: Increment on clock edge

## The Instruction Register (IR)

**IR function**:
- Holds current instruction being executed
- Loaded during instruction fetch
- Provides opcode for microcode address
- Provides operand for instruction execution

**IR characteristics**:
- 8-bit for SAP-1 (4-bit opcode + 4-bit operand)
- Loaded from memory
- Opcode used for microcode
- Operand used during execution

## Instruction Format

**SAP-1 instruction format**:
- **Upper 4 bits**: Opcode (operation code)
- **Lower 4 bits**: Operand (data/address)

**Example instructions**:
- LDA 14h: Opcode = 0000, Operand = 1110 (14)
- ADD 15h: Opcode = 0001, Operand = 1111 (15)
- OUT: Opcode = 1110, Operand = 0000
- HLT: Opcode = 1111, Operand = 0000

## Instruction Fetching

**Fetch sequence**:
1. PC outputs address to MAR (CO, MI)
2. Memory outputs instruction (RO)
3. Instruction loaded into IR (II)
4. PC increments (CE)
5. Ready for decode/execute

**Control signals for fetch**:
- **CO** (Counter Out): PC to MAR
- **MI** (MAR In): Load address
- **RO** (RAM Out): Memory output
- **II** (Instruction In): Load instruction
- **CE** (Counter Enable): Increment PC

## Practice Questions

1. What is the Program Counter's function?
2. How does the Instruction Register work?
3. What is instruction format?
4. How does instruction fetching work?
5. How do PC and IR work together?

## Key Takeaways

- PC tracks instruction address
- IR holds current instruction
- Instruction format: opcode + operand
- Fetch cycle: PC→MAR→Memory→IR
- Foundation for automatic execution

---

*PC and IR enable automatic instruction fetching*
