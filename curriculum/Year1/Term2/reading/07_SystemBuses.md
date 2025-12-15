# Chapter 7: System Buses

## Introduction

In this chapter, you'll learn about buses - the "highways" that connect all parts of a computer. Buses allow devices to share data efficiently.

---

## What is a Bus?

### Bus Concept

A **bus** is a shared pathway for data:
- Multiple devices connect to same wires
- Only one device can "talk" at a time
- Like a telephone party line
- Common in all computers

### Why Use a Bus?

**Advantages**:
- **Saves wires**: Shared instead of separate connections
- **Flexible**: Devices can be added easily
- **Standard interface**: Common protocol
- **Cost-effective**: Fewer connections needed

**Without buses**:
- Every device needs separate wires to every other device
- N devices = N×(N-1) connections!
- Very complex and expensive

**With buses**:
- All devices share same wires
- N devices = N connections to bus
- Much simpler!

### Types of Buses

**Data Bus**:
- Carries data (8-bit, 16-bit, 32-bit, etc.)
- Bidirectional (can read or write)
- Shared by all devices

**Address Bus**:
- Carries addresses
- Unidirectional (CPU → Memory/Devices)
- Selects which device/location

**Control Bus**:
- Carries control signals
- Read/Write, Enable, Reset, etc.
- Controls bus operation

### Real-world Analogy

**Highway**:
- Many cars, but only one lane at a time
- Shared road, controlled access

**Bus**:
- Many devices, but only one transmits at a time
- Shared wires, controlled access

---

## The Problem: Multiple Outputs

### Bus Contention

**Challenge**:
- Two registers want to output to same destination
- If both connected directly → conflict!
- Example: Register A outputs 0101, Register B outputs 1010
- If both connected → what value on bus? (undefined!)

**This is Bus Contention**:
- Multiple drivers on same line
- Creates conflicts
- Can damage circuits
- Must be avoided!

### Solution: Tri-State Buffers

**Tri-state buffers**:
- Can output: HIGH, LOW, or **DISCONNECTED** (high-impedance)
- When disabled: Acts like not connected
- When enabled: Drives bus normally
- Only one enabled at a time!

---

## Tri-State Buffers

### What is a Tri-State Buffer?

**Tri-state** = Three states:
1. **HIGH** (1): Outputs high voltage
2. **LOW** (0): Outputs low voltage
3. **HIGH-IMPEDANCE (Z)**: Disconnected (floating)

**Key property**:
- When disabled: Doesn't affect bus
- When enabled: Drives bus normally
- Perfect for bus systems!

### How Tri-State Buffers Work

**Operation**:
- **Enable = 1**: Buffer active, drives output
- **Enable = 0**: Buffer disabled, high-impedance
- Only enabled buffer drives bus
- Others are disconnected

**Truth Table**:
| Enable | Input | Output |
|--------|-------|--------|
| 0 | X | Z (disconnected) |
| 1 | 0 | 0 (LOW) |
| 1 | 1 | 1 (HIGH) |

### 74HC125 Tri-State Buffer

**Features**:
- Quad tri-state buffer (4 buffers)
- Active-low enable (enable = 0 to activate)
- Perfect for bus systems

**74HC244**:
- Octal tri-state buffer (8 buffers)
- Active-low enable
- Good for 8-bit buses

---

## Building a Bus System

### Basic Bus Architecture

**Components**:
- Multiple registers (data sources)
- Tri-state buffers (control access)
- Bus wires (shared pathway)
- Control logic (selects which device)

**Operation**:
1. Only one enable signal active
2. That device drives bus
3. Other devices are disconnected
4. Bus carries data from enabled device

### Register-to-Bus Connection

**How it works**:
- Register outputs → Tri-state buffers → Bus
- Enable signal selects which register
- Only enabled register drives bus
- Others are disconnected

**Example**:
- Register A enable = 1 → Register A drives bus
- Register B enable = 0 → Register B disconnected
- Bus shows Register A value

### Bus Contention Prevention

**Rules**:
- Only one enable active at a time
- Control logic ensures this
- Prevents conflicts
- Safe operation

**How to ensure**:
- Use decoder to select device
- Only one output active
- Each output enables one device
- Guarantees no conflicts

---

## CPU Bus Architecture

### How CPUs Use Buses

**Data Bus**:
- CPU reads/writes data
- Memory provides/stores data
- I/O devices exchange data
- All share same bus

**Address Bus**:
- CPU outputs address
- Selects memory location
- Selects I/O device
- Unidirectional (CPU → others)

**Control Bus**:
- Read/Write signal
- Memory enable
- I/O enable
- Clock signals

### Bus Protocol

**Read Operation**:
1. CPU outputs address on address bus
2. CPU asserts Read signal
3. Selected device outputs data on data bus
4. CPU reads data
5. CPU releases signals

**Write Operation**:
1. CPU outputs address on address bus
2. CPU outputs data on data bus
3. CPU asserts Write signal
4. Selected device stores data
5. CPU releases signals

---

## Key Takeaways

1. **Bus**: Shared pathway for data
2. **Bus contention**: Multiple drivers conflict
3. **Tri-state buffers**: Enable/disable connection
4. **Bus protocol**: How devices communicate
5. **CPU buses**: Data, address, control
6. **SAP-1**: Simple bus architecture

## Practice Questions

1. Why do computers use buses?
   - Answer: Saves wires, flexible, cost-effective

2. What happens if two devices drive bus at once?
   - Answer: Bus contention - conflict, undefined behavior

3. How do tri-state buffers solve bus contention?
   - Answer: Only one enabled at a time, others disconnected

4. How do registers connect to buses?
   - Answer: Through tri-state buffers, enable selects which

5. How does CPU use buses?
   - Answer: Data bus for data, address bus for addresses, control bus for signals

## What's Next?

After reading this chapter:
1. Review the key concepts
2. Understand bus operation
3. Understand tri-state buffers
4. Read the lab material
5. Come to lab ready to build!

---

*Understanding buses helps you understand computer communication!*
