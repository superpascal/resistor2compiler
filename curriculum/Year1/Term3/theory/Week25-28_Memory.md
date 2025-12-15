# Week 25-28: Memory and MAR - Theory

## Learning Objectives

After reading this material, you will understand:
- How memory chips work
- What the Memory Address Register (MAR) is
- How to read and write data to memory
- How address decoding works
- How memory connects to bus systems
- How memory timing works
- How this prepares for CPU memory subsystem

## What is Memory?

### Memory Concept

**Memory** stores data at addresses:
- Like a post office: Each box (address) holds mail (data)
- Can read (retrieve) or write (store)
- Organized by address

### Types of Memory

**ROM (Read-Only Memory)**:
- Written once, read many times
- Non-volatile (keeps data when power off)
- Used for programs, constants

**RAM (Random Access Memory)**:
- Read and write
- Volatile (loses data when power off)
- Used for variables, temporary data

**EEPROM**:
- Can be erased and rewritten
- Non-volatile
- Used for configuration, small programs

### Memory Organization

**Address**: Which location (like box number)
- 16 bytes = addresses 0-15
- 256 bytes = addresses 0-255
- 2KB = addresses 0-2047

**Data**: What's stored (like mail in box)
- Each address holds data
- Usually 8 bits (1 byte) per address
- Can be read or written

**Operations**:
- **Read**: Get data from address
- **Write**: Put data at address

## Memory Chips

### 28C16 EEPROM (Example)

**Features**:
- 2KB memory (2048 bytes)
- 11 address lines (2¹¹ = 2048)
- 8 data lines (8 bits per byte)
- Can read and write
- Non-volatile

**Pinout**:
- A0-A10: Address inputs
- D0-D7: Data inputs/outputs
- CE: Chip Enable
- OE: Output Enable (for reading)
- WE: Write Enable (for writing)
- VCC, GND: Power

### Simple RAM Alternative

**74LS189**: 16x4 RAM
- 4 address lines (16 locations)
- 4 data lines
- Simpler for learning
- Good for understanding

## Memory Address Register (MAR)

### What is MAR?

**Memory Address Register (MAR)**:
- Holds address to access
- Connects to memory address inputs
- CPU loads address into MAR
- Then reads/writes that memory location

### Why MAR?

**Advantages**:
- Separates address from data
- Allows sequential access
- Standard CPU component
- Simplifies control

**Operation**:
1. Load address into MAR
2. MAR outputs address to memory
3. Memory accesses that location
4. Data flows on data bus

### Building MAR

**Components**:
- 4-bit register (74HC173)
- Connects to memory address inputs
- Control: MI (MAR In) - load address
- Output: Address to memory

**SAP-1 Example**:
- 4-bit MAR (addresses 0-15)
- Points to 16-byte memory
- CPU loads address, then accesses

## Reading from Memory

### Read Operation

**Steps**:
1. Load address into MAR
2. Assert Read signal (OE)
3. Memory outputs data
4. Data appears on data bus
5. CPU reads data

**Timing**:
- Address must be stable
- Read signal asserted
- Data appears after delay
- Data valid until read released

### Read Circuit

**Components**:
- MAR (holds address)
- Memory chip
- Tri-state buffer (for data bus)
- Control: RO (RAM Out)

**Operation**:
- MAR → Memory address
- Memory → Tri-state → Bus
- RO enables tri-state
- Data on bus

## Writing to Memory

### Write Operation

**Steps**:
1. Load address into MAR
2. Put data on data bus
3. Assert Write signal (WE)
4. Memory stores data
5. Release signals

**Timing**:
- Address must be stable
- Data must be stable
- Write signal asserted
- Data stored
- Signals released

### Write Circuit

**Components**:
- MAR (holds address)
- Data bus (carries data)
- Memory chip
- Control: WE (Write Enable)

**Operation**:
- MAR → Memory address
- Bus → Memory data
- WE enables write
- Data stored

## Address Decoding

### What is Address Decoding?

**Address decoding** selects which memory chip:
- Multiple memory chips
- Address bits select chip
- Decoder generates chip selects
- Only one chip active at a time

### How It Works

**Example**: 4 memory chips
- 2 address bits select chip
- Decoder: 2-to-4 decoder
- Each output enables one chip
- Address range per chip

**Benefits**:
- Expand memory
- Select correct chip
- Prevent conflicts
- Standard technique

## Memory Timing

### Timing Requirements

**Setup Time**:
- Address must be stable before read/write
- Data must be stable before write
- Critical for reliable operation

**Hold Time**:
- Address must stay stable after operation
- Data must stay stable after write
- Ensures data stored correctly

**Access Time**:
- Time from address to data (read)
- Time from write to stored (write)
- Varies by memory type

### Why Timing Matters

**Reliable Operation**:
- Must meet timing requirements
- Too fast = errors
- Too slow = works but inefficient
- Proper timing = reliable

## Bus Connection

### Memory on Bus

**Connection**:
- MAR → Memory address
- Memory data → Tri-state → Bus
- Bus → Memory data (for write)
- Control signals coordinate

**Operation**:
- Read: Memory → Bus
- Write: Bus → Memory
- Only one operation at a time
- Control signals coordinate

## Key Concepts Summary

1. **Memory**: Stores data at addresses
2. **MAR**: Holds address to access
3. **Read**: Get data from address
4. **Write**: Put data at address
5. **Address decoding**: Selects memory chip
6. **Timing**: Critical for reliable operation
7. **Bus connection**: Memory on shared bus

## Questions to Think About

Before the lab, think about:
1. How does memory store data?
2. Why do we need MAR?
3. How does read operation work?
4. How does write operation work?
5. Why is timing important?

## Next Steps

After reading this theory:
1. Review the key concepts
2. Understand memory operation
3. Understand MAR function
4. Read the lab material
5. Come to lab ready to build!

---

*Theory helps you understand - labs help you build!*
