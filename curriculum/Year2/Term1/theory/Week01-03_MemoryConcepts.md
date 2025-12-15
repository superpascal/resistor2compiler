# Week 1-3: Memory Concepts and Simple Storage - Theory

## Learning Objectives

By the end of this 3-week block, students will:
- Understand how memory chips store and retrieve data
- Understand the concept of memory addresses
- Know how to build a Memory Address Register (MAR)
- Understand address decoding basics
- Know how to read and write data to memory

## Prerequisites

- Understanding of registers and flip-flops (Year 1)
- Understanding of buses and tri-state buffers (Year 1)
- Basic binary number concepts

## Key Concepts

### 1. What is Memory?

**Memory** is where computers store information (data and instructions). Unlike registers which hold single values, memory can hold many values, each at a specific **address**.

**Key Analogy**: Think of memory like a post office with numbered boxes. Each box (address) can hold a letter (data). To get a letter, you need to know which box number (address) it's in.

### 2. Types of Memory

#### EEPROM (Electrically Erasable Programmable Read-Only Memory)
- **Non-volatile**: Keeps data when power is off
- **Programmable**: Can be written to (with special equipment)
- **Read-only in normal operation**: Once programmed, acts like ROM
- **Example**: 28C16 (2KB EEPROM)

#### RAM (Random Access Memory)
- **Volatile**: Loses data when power is off
- **Read/Write**: Can be read from and written to during operation
- **Fast**: Quick access to any location
- **Example**: 74LS189 (64-bit RAM), larger SRAM chips

### 3. Memory Address Register (MAR)

The **Memory Address Register (MAR)** holds the address of the memory location we want to access.

**Why we need it**: 
- Memory chips have address pins that need to be set
- We need a way to store and hold the address value
- The MAR acts as a buffer between the bus and memory address pins

**Construction**:
- Use two 4-bit registers (like 74HC173) to create an 8-bit MAR
- Connect register outputs to memory address pins
- Load MAR from the bus when needed

### 4. Address Decoding

**Address decoding** selects which memory chip (or memory region) to use based on the address.

**Basic concept**:
- Higher address bits select which chip
- Lower address bits select location within chip
- Use decoders (like 74HC139) to generate chip select signals

**Example**: 
- If we have 16 bytes of memory (4-bit address)
- Addresses 0-15 select locations within the memory chip
- If we had multiple chips, higher bits would select which chip

### 5. Reading from Memory

**Read operation sequence**:
1. Load address into MAR
2. Enable memory chip (chip select)
3. Enable memory output (read enable)
4. Data appears on bus
5. Read data from bus

**Control signals needed**:
- **MI** (MAR In): Load address into MAR
- **RO** (RAM Out): Enable memory output to bus

### 6. Writing to Memory

**Write operation sequence**:
1. Load address into MAR
2. Put data on bus
3. Enable memory chip (chip select)
4. Assert write enable signal
5. Data is stored in memory

**Control signals needed**:
- **MI** (MAR In): Load address into MAR
- **WE** (Write Enable): Enable memory write operation

### 7. Memory Timing

**Important considerations**:
- **Setup time**: Address must be stable before read/write
- **Hold time**: Address must remain stable after operation
- **Access time**: How long memory takes to respond
- **Clock synchronization**: Operations must be coordinated with clock

### 8. Memory Mapping

**Memory mapping** defines which addresses correspond to which physical memory.

**Simple example**:
- Addresses 0x00-0x0F: 16 bytes of RAM
- Addresses 0x10-0x1F: Reserved for future expansion
- Addresses 0xF0-0xFF: I/O devices (memory-mapped I/O)

## Mathematical Foundations

### Address Space Calculation

For an n-bit address:
- **Number of locations** = 2^n
- **Example**: 4-bit address = 2^4 = 16 locations
- **Example**: 8-bit address = 2^8 = 256 locations

### Memory Size

- **1 byte** = 8 bits
- **1 KB** = 1024 bytes (not 1000!)
- **Memory size** = Number of locations × Bits per location

## Common Misconceptions

1. **"Memory is just like a register"**: Memory can hold many values, registers hold one
2. **"All memory is the same"**: Different types (ROM, RAM, EEPROM) have different properties
3. **"Addresses are the same as data"**: Addresses select locations, data is what's stored
4. **"Memory is instant"**: Memory operations take time (access time)

## Connections to Year 1

- **Registers**: MAR is built from registers we learned about
- **Buses**: Memory connects to the system bus
- **Tri-state buffers**: Memory output uses tri-state to avoid bus conflicts
- **Binary numbers**: Addresses are binary numbers

## Connections to Year 3

- **CPU construction**: Memory is a key component of the SAP-1 CPU
- **Instruction storage**: Programs are stored in memory
- **Data storage**: Variables are stored in memory
- **Fetch cycle**: CPU reads instructions from memory

## Next Steps

After understanding memory concepts, students will:
- Build a MAR from registers
- Connect memory chips to the bus
- Practice reading and writing data
- Understand how this fits into a complete computer system

---

*Memory is the foundation of all computer operations*
