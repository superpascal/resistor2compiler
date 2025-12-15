# Chapter 6: Input/Output Systems

## Introduction

I/O systems connect computers to the real world. Input devices provide data, output devices display results. This chapter explains how to interface with I/O devices.

## I/O Device Basics

**What are I/O devices?**
- **Input**: Devices that provide data to the system (switches, buttons, sensors)
- **Output**: Devices that display or act on data (LEDs, displays, motors)
- **Bidirectional**: Devices that can do both (some displays, communication ports)

**Why I/O matters**:
- Computers need to interact with the world
- Input provides data and control
- Output shows results and status
- I/O makes computers useful

## Simple Input Devices

**Switches and buttons**:
- Provide binary input (on/off)
- Need debouncing (learned in Year 1)
- Can be read as memory location
- Simple but essential

**Reading input**:
- Address decoder selects input device
- Device drives data bus (via tri-state)
- CPU reads data from bus
- Data represents input state

## Simple Output Devices

**LEDs**:
- Binary output (on/off)
- Can be individual or arrays
- Need current-limiting resistors
- Simple status indication

**7-segment displays**:
- Display digits 0-9 (and some letters)
- Need decoder/driver IC
- Can show numbers and simple text
- Common in embedded systems

## Data Direction Control

**The problem**:
- Some devices are input only
- Some devices are output only
- Some devices are bidirectional
- Need to control data flow direction

**The solution**:
- **Data Direction Register (DDR)**: Controls I/O direction
- Bit = 0: Input (read from device)
- Bit = 1: Output (write to device)
- Can be changed dynamically

## Memory-Mapped I/O

**I/O as memory**:
- I/O devices at specific addresses
- Read = input operation
- Write = output operation
- Same bus protocol as memory

**Example I/O map**:
```
0x9000: LED output register
0x9001: Switch input register
0x9002: Display data register
0x9003: Display control register
```

## I/O Timing

**Synchronization**:
- I/O operations take time
- Need to wait for completion
- Polling: Check status until ready
- Interrupts: Device signals when ready (advanced)

**Read timing**:
- Assert address and chip select
- Wait for device to respond
- Read data from bus
- Deassert signals

**Write timing**:
- Put data on bus
- Assert address and chip select
- Assert write enable
- Wait for device to latch
- Deassert signals

## Practice Questions

1. What are I/O devices?
2. How do we read input?
3. How do we write output?
4. What is data direction control?
5. Why is I/O timing important?

## Key Takeaways

- I/O devices connect computers to the world
- Input devices provide data
- Output devices display results
- Memory-mapped I/O is simple
- Data direction control enables flexibility

---

*I/O systems connect computers to the real world*
