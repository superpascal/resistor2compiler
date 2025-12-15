# Chapter 2: Register File and Buses

## Introduction

Registers store data temporarily. Buses connect all components. This chapter explains how to build the register file and bus system for the SAP-1 CPU.

## SAP-1 Register File

**SAP-1 registers**:
- **Register A**: Primary accumulator, stores ALU results
- **Register B**: Secondary register, provides ALU input
- **Both**: 4-bit registers, connect to data bus

**Register characteristics**:
- 4-bit width (matches SAP-1 design)
- Can load from bus
- Can output to bus
- Clocked operation

## Building Registers

**Register A function**:
- Stores intermediate results
- Receives ALU output
- Provides ALU input
- Can output to bus

**Register B function**:
- Provides second ALU operand
- Can load from bus
- Can output to bus
- Works with Register A

**Control signals**:
- **AI** (A In): Load from bus
- **AO** (A Out): Output to bus
- **BI** (B In): Load from bus
- **BO** (B Out): Output to bus

## Tri-State Bus Connections

**Why tri-state?**
- Multiple components share bus
- Only one can drive bus at a time
- Prevents bus conflicts
- Enables data sharing

**Tri-state implementation**:
- Use 74HC125 (quad tri-state buffer)
- Enable signal controls output
- When disabled, high-impedance (floating)

**Bus protocol**:
- Only enable one output at a time
- All others must be disabled
- Prevents conflicts and damage

## Bus Control Logic

**Control signal coordination**:
- AI, AO: Register A control
- BI, BO: Register B control
- EO: ALU output enable
- RO: Memory output enable

**Control logic**:
- Ensure only one output enabled
- Coordinate with clock
- Prevent conflicts
- Enable proper sequencing

## Register-ALU Integration

**Data flow**:
- Register A → ALU input A
- Register B → ALU input B
- ALU result → Bus → Register A

**Operation sequence**:
1. Load A from memory (AI=1)
2. Load B from memory (BI=1)
3. Enable A and B to ALU (AO=1, BO=1)
4. ALU performs operation
5. Enable ALU output (EO=1)
6. Load result into A (AI=1)

## Practice Questions

1. Why do we need registers?
2. How do tri-state buffers work?
3. Why is bus protocol important?
4. How do registers connect to ALU?
5. What is the data flow?

## Key Takeaways

- Registers store data temporarily
- Buses connect all components
- Tri-state prevents conflicts
- Bus protocol is essential
- Registers integrate with ALU

---

*Registers and buses form the data path foundation*
