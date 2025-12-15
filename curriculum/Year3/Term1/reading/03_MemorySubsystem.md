# Chapter 3: Memory Subsystem

## Introduction

Memory stores instructions and data. The Memory Address Register (MAR) holds addresses. This chapter explains how to build the memory subsystem for the SAP-1 CPU.

## SAP-1 Memory System

**SAP-1 memory characteristics**:
- **Size**: 16 bytes (4-bit address)
- **Width**: 8 bits per location
- **Type**: RAM or EEPROM
- **Purpose**: Store instructions and data

**Memory organization**:
- Addresses 0x0 to 0xF (16 locations)
- Each location holds 8-bit value
- Instructions stored in memory
- Data stored in memory

## Memory Address Register (MAR)

**MAR function**:
- Holds address of memory location to access
- Connects to memory address pins
- Loaded from bus
- 4-bit for SAP-1 (16 locations)

**MAR construction**:
- Use 74HC173 (4-bit register)
- Connect to address bus
- Connect to memory address pins
- Add control signal (MI - MAR In)

## Memory Chip Connection

**Memory chip options**:
- **74LS189**: 64-bit RAM (use 16 bytes)
- **28C16**: 2KB EEPROM (use 16 bytes)

**Connections**:
- Address pins: From MAR
- Data pins: To/from data bus (via tri-state)
- Chip select: From address decoder
- Read/Write enable: Control signals

## Memory Operations

**Read operation**:
1. Load address into MAR (MI=1)
2. Enable memory output (RO=1)
3. Data appears on bus
4. Load data into destination

**Write operation**:
1. Load address into MAR (MI=1)
2. Put data on bus
3. Enable memory write (WE=1)
4. Data stored in memory

**Control signals**:
- **MI**: Load address into MAR
- **RO**: Enable memory output
- **WE**: Enable memory write

## Memory-Data Path Integration

**Complete data path**:
- Registers (A, B)
- ALU
- Memory (via MAR)
- All connected via bus

**Data flow examples**:
- **Load A from memory**: MAR←address, RO→bus, AI→A
- **Store A to memory**: MAR←address, AO→bus, WE→write
- **Load, add, store**: Multiple operations in sequence

## Practice Questions

1. Why do we need memory?
2. What is the MAR's function?
3. How do we read from memory?
4. How do we write to memory?
5. How does memory integrate with data path?

## Key Takeaways

- Memory stores instructions and data
- MAR holds memory addresses
- Read/write operations need control
- Memory completes the data path
- Foundation for program storage

---

*Memory completes the data path and enables program storage*
