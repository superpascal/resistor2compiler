# Chapter 3: Integration and Review

## Introduction

Integration brings all components together into a working system. This chapter reviews Years 1-2 concepts and shows how they integrate into a complete "manual computer."

## System Integration

**Integration** means connecting all components into a working whole.

**Components we've built**:
- **Registers**: Store data (A, B, MAR)
- **ALU**: Performs arithmetic (add, subtract)
- **Memory**: Stores instructions and data
- **Buses**: Connect components together
- **Control**: Coordinates operations

**The challenge**: Making them all work together!

## The "Manual Computer"

A **manual computer** is a system where humans control all the signals manually (no automatic control unit yet).

**Why build one**:
- Understand how all pieces fit together
- See the complete data flow
- Practice coordinating signals
- Prepare for automatic control (Year 3)

**What it demonstrates**:
- How data moves through the system
- How operations are sequenced
- How control signals coordinate everything
- The foundation for CPU operation

## Complete System Architecture

**Data Path**:
- Registers (A, B)
- ALU (adder/subtractor)
- Memory (RAM/EEPROM)
- Buses (data, address, control)

**Control Path**:
- Control signals (MI, RO, AI, AO, etc.)
- Manual switches or simple sequencer
- Signal coordination logic

**Memory Subsystem**:
- Memory chip
- MAR (Memory Address Register)
- Address decoding
- Read/Write control

## Manual Program Execution

**Example program**: Add two numbers
1. Load first number from memory address 0x05 into Register A
2. Load second number from memory address 0x06 into Register B
3. Add A and B, store result in A
4. Store result to memory address 0x07
5. Output result

**Manual execution steps**:
- **Step 1**: Set MAR to 0x05, enable memory read, load into A
- **Step 2**: Set MAR to 0x06, enable memory read, load into B
- **Step 3**: Enable A and B to ALU, set ADD, load result into A
- **Step 4**: Set MAR to 0x07, put A on bus, enable memory write
- **Step 5**: Enable A output, display result

**Key insight**: This is exactly what a CPU does automatically!

## Signal Coordination

**The coordination challenge**:
- Only one component can use the bus at a time
- Operations must happen in the right order
- Signals must be active at the right time
- No conflicts or races

**Coordination rules**:
- **Bus protocol**: Only enable one output at a time
- **Timing**: Wait for operations to complete
- **Sequence**: Follow the correct order
- **Synchronization**: Use clock edges when needed

## Data Flow Through System

**Read operation flow**:
1. Address → MAR → Memory address pins
2. Control signal → Memory read enable
3. Memory data → Bus → Destination register
4. Control signal → Register load

**Write operation flow**:
1. Source register → Bus
2. Address → MAR → Memory address pins
3. Data → Bus → Memory data pins
4. Control signal → Memory write enable

**ALU operation flow**:
1. Register A → ALU input A
2. Register B → ALU input B
3. Control signal → ALU operation select
4. ALU result → Bus → Destination register

## Review: Year 1 Concepts

**Electronics Foundations**:
- Voltage, current, resistance (Ohm's law)
- Components (resistors, capacitors, LEDs)
- Breadboarding and measurement
- Safety practices

**Digital Logic**:
- Boolean algebra and truth tables
- Logic gates (AND, OR, NOT, NAND, NOR, XOR)
- Combinational circuits (adders, multiplexers, decoders)

**Sequential Logic**:
- Flip-flops and latches
- Registers (storage)
- Counters (program counter concept)
- Clocked operations

**System Concepts**:
- Buses (data, address, control)
- Tri-state buffers
- ALU (arithmetic operations)
- Flags (carry, zero)

## Review: Year 2 Concepts

**Memory**:
- Memory chips (EEPROM, RAM)
- Memory Address Register (MAR)
- Reading and writing data
- Address decoding

**Control**:
- Control signals
- State machines
- Sequencers
- Microcode concepts

**Integration**:
- Connecting all components
- Signal coordination
- Manual computer operation
- Complete system understanding

## Preparing for Year 3

**What Year 3 will add**:
- **Automatic control**: Control unit replaces manual switches
- **Instruction set**: Defined operations the CPU can perform
- **Program storage**: Instructions stored in memory
- **Fetch-decode-execute**: Automatic instruction cycle
- **Complete CPU**: Working 8-bit computer (SAP-1)

**What you already know**:
- All the components (registers, ALU, memory, buses)
- How they work individually
- How they connect together
- How operations are sequenced

**What you'll learn**:
- How to automate the control
- How instructions are encoded
- How the CPU fetches and executes instructions
- How to program the computer

## Practice Questions

1. How do all components work together?
2. What is a manual computer?
3. How do you execute a program manually?
4. What would make this automatic?
5. How does this prepare for CPU construction?

## Key Takeaways

- Integration brings all components together
- Manual computer shows how automatic computers work
- Signal coordination is critical
- Complete system understanding prepares for CPU
- Year 3 will add automatic control

---

*Integration brings all the pieces together into a working system*
