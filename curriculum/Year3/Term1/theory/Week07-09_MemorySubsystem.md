# Week 9-12: Memory Subsystem - Theory

## Learning Objectives

By the end of this week-block, students will:
- Build Memory Address Register (MAR) for SAP-1
- Connect memory chip to system
- Implement address decoding
- Test read/write operations
- Integrate memory with complete data path

## Prerequisites

- Completed Weeks 5-8 (Registers and Buses)
- Understanding of memory concepts (Year 2)
- Understanding of MAR (Year 2)
- Understanding of address decoding (Year 2)

## Key Concepts

### 1. SAP-1 Memory System

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

### 2. Memory Address Register (MAR)

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

**Control signal**:
- **MI** (MAR In): Load address from bus
- Clock: Synchronize loading
- Output: Always connected to memory

### 3. Memory Chip Connection

**Memory chip options**:
- **74LS189**: 64-bit RAM (use 16 bytes)
- **28C16**: 2KB EEPROM (use 16 bytes)
- **Other**: Any suitable memory chip

**Connections**:
- Address pins: From MAR
- Data pins: To/from data bus (via tri-state)
- Chip select: From address decoder
- Read/Write enable: Control signals

**Tri-state connection**:
- Memory output via tri-state buffer
- Enable signal: RO (RAM Out)
- Prevents bus conflicts
- Allows memory read

### 4. Address Decoding for SAP-1

**SAP-1 address space**:
- 4-bit address = 16 locations
- All addresses map to one memory chip
- Simple decoding (chip always enabled)
- Can add decoder for future expansion

**Decoding logic**:
- For single chip: Always enable
- For multiple chips: Use decoder
- Higher bits select chip
- Lower bits select location

### 5. Memory Read Operation

**Read sequence**:
1. Load address into MAR (MI=1)
2. Enable memory output (RO=1)
3. Data appears on bus
4. Load data into destination (AI, BI, etc.)
5. Disable memory output

**Control signals**:
- **MI**: Load address
- **RO**: Enable memory output
- **AI/BI/etc.**: Load data into register

**Timing**:
- Address must be stable
- Memory needs access time
- Data must be latched
- Signals must be coordinated

### 6. Memory Write Operation

**Write sequence**:
1. Load address into MAR (MI=1)
2. Put data on bus (from source register)
3. Enable memory write (WE=1)
4. Data stored in memory
5. Disable write enable

**Control signals**:
- **MI**: Load address
- **AO/BO/etc.**: Put data on bus
- **WE**: Enable memory write

**Timing**:
- Address must be stable
- Data must be stable
- Write pulse must be adequate
- Signals must be coordinated

### 7. Memory-Data Path Integration

**Complete data path**:
- Registers (A, B)
- ALU
- Memory (via MAR)
- All connected via bus

**Data flow examples**:
- **Load A from memory**: MAR←address, RO→bus, AI→A
- **Store A to memory**: MAR←address, AO→bus, WE→write
- **Load, add, store**: Multiple operations in sequence

**Integration requirements**:
- All components on bus
- Proper control signals
- Correct timing
- No conflicts

### 8. SAP-1 Memory Map

**SAP-1 memory organization**:
- Addresses 0x0-0xF: Program and data
- Typically: Lower addresses for program
- Higher addresses for data
- Can be organized as needed

**Example organization**:
- 0x0-0x7: Program instructions
- 0x8-0xF: Data storage
- Flexible arrangement

## Mathematical Foundations

### Address Space

**4-bit address**: 2^4 = 16 locations
- Sufficient for learning
- Keeps design simple
- Can demonstrate concepts
- Can be expanded later

### Memory Capacity

**16 bytes × 8 bits = 128 bits total**
- Small but functional
- Enough for simple programs
- Demonstrates concepts
- Foundation for larger systems

## Common Misconceptions

1. **"Memory is just storage"**
   - Clarify: Memory is active, needs control
   - Show read/write operations

2. **"MAR is optional"**
   - Clarify: MAR is essential for addressing
   - Show why it's needed

3. **"All memory is the same"**
   - Clarify: Different types, different characteristics
   - Show RAM vs EEPROM

## Connections to Weeks 1-8

- **ALU**: Memory provides data for ALU
- **Registers**: Memory loads/stores register values
- **Buses**: Memory uses data bus
- **Complete System**: Memory completes data path

## Connections to Term 2

- **Control Unit**: Will control memory operations
- **Instruction Fetch**: CPU will fetch from memory
- **Program Storage**: Instructions in memory
- **Complete CPU**: Memory is essential component

## Next Steps

After building memory subsystem, students will:
- Complete data path integration
- Test complete data path
- Prepare for control unit (Term 2)
- Understand SAP-1 data path

---

*Memory completes the data path and enables program storage*
