# Chapter 1: Memory Concepts

## Introduction

Memory is where computers store information. Unlike registers which hold a single value, memory can hold many values, each at a specific address. Understanding memory is essential for understanding how computers work.

## What is Memory?

Think of memory like a post office with numbered boxes. Each box has a number (the **address**), and each box can hold a letter (the **data**). To get a specific letter, you need to know which box number it's in.

In computers:
- **Address**: The location number (like box 5)
- **Data**: What's stored at that location (like the letter in box 5)
- **Read**: Getting data from an address
- **Write**: Putting data into an address

## Types of Memory

### RAM (Random Access Memory)
- **Volatile**: Loses data when power is turned off
- **Read/Write**: Can be read from and written to during operation
- **Fast**: Quick access to any location
- **Use**: Storing data that changes (variables, temporary data)

### ROM (Read-Only Memory)
- **Non-volatile**: Keeps data when power is off
- **Read-only**: Cannot be written to during normal operation
- **Use**: Storing programs or data that doesn't change

### EEPROM (Electrically Erasable Programmable ROM)
- **Non-volatile**: Keeps data when power is off
- **Programmable**: Can be written to (with special equipment)
- **Read-only in normal operation**: Once programmed, acts like ROM
- **Use**: Storing programs or data that rarely changes

## Memory Address Register (MAR)

The **Memory Address Register (MAR)** holds the address of the memory location we want to access.

**Why we need it**:
- Memory chips have address pins that need to be set
- We need a way to store and hold the address value
- The MAR acts as a buffer between the bus and memory address pins

**How it works**:
1. Load address into MAR from the bus
2. MAR outputs address to memory chip address pins
3. Memory chip uses address to select location
4. Data from that location can be read or written

## Reading from Memory

**Read operation**:
1. Load address into MAR
2. Enable memory chip (chip select)
3. Enable memory output (read enable signal)
4. Data appears on the bus
5. Read data from bus into register

**Control signals**:
- **MI** (MAR In): Load address into MAR
- **RO** (RAM Out): Enable memory output to bus

## Writing to Memory

**Write operation**:
1. Load address into MAR
2. Put data on the bus
3. Enable memory chip (chip select)
4. Assert write enable signal
5. Data is stored in memory

**Control signals**:
- **MI** (MAR In): Load address into MAR
- **WE** (Write Enable): Enable memory write operation

## Address Decoding

**Address decoding** selects which memory chip (or memory region) to use based on the address.

**Basic concept**:
- Higher address bits select which chip
- Lower address bits select location within chip
- Use decoders to generate chip select signals

**Example**:
- If we have 16 bytes of memory (4-bit address)
- Addresses 0-15 select locations within the memory chip
- If we had multiple chips, higher bits would select which chip

## Memory Size

**Calculating memory size**:
- For n address bits: 2^n locations
- **Example**: 4-bit address = 2^4 = 16 locations
- **Example**: 8-bit address = 2^8 = 256 locations

**Memory capacity**:
- 1 byte = 8 bits
- 1 KB = 1024 bytes (not 1000!)
- Memory size = Number of locations × Bits per location

## Practice Questions

1. How many locations can a 6-bit address access?
2. What's the difference between RAM and ROM?
3. Why do we need a MAR?
4. What happens if we try to read from address that doesn't exist?
5. How do we write data to memory?

## Key Takeaways

- Memory stores data at specific addresses
- MAR holds the address we want to access
- Reading: Set address → Enable read → Data appears
- Writing: Set address → Put data → Enable write → Data stored
- Address decoding selects which memory chip to use

---

*Memory is the foundation of computer storage*
