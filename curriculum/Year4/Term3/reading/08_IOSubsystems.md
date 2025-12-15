# Chapter 8: Input/Output Subsystems

## Introduction

I/O subsystems enable the computer to interact with the outside world. This chapter explains how to integrate serial, parallel, LCD, and timer functions.

## Serial Communication with ACIA

**ACIA (65C51)**:
- Asynchronous Communications Interface Adapter
- UART functionality
- RS-232 compatible
- Serial communication

**ACIA features**:
- Transmit and receive
- Baud rate selection
- Status registers
- Interrupt capability

## Parallel I/O with VIA

**VIA (65C22)**:
- Versatile Interface Adapter
- Parallel I/O ports (A and B)
- Timers
- Shift register
- Interrupt capability

**VIA features**:
- Two 8-bit ports
- Programmable direction
- Timer/counter functions
- Shift register mode

## LCD Display Interface

**LCD display**:
- Character LCD (2×16 or 4×20)
- Parallel interface
- Simple control
- Text output

**LCD operation**:
- Send commands
- Send data
- Control cursor
- Display text

## Timer Functions

**VIA timers**:
- Two timers (Timer 1 and Timer 2)
- Programmable intervals
- Interrupt generation
- One-shot or continuous

**Timer uses**:
- Delays
- Periodic interrupts
- Time measurement
- Event timing

## I/O Address Mapping

**Memory-mapped I/O**:
- I/O devices in address space
- Access like memory
- Register-based interface
- Standard addressing

## Practice Questions

1. What is ACIA used for?
2. What is VIA used for?
3. How do we interface LCD?
4. How do timers work?
5. How is I/O mapped?

## Key Takeaways

- ACIA enables serial communication
- VIA enables parallel I/O
- LCD provides text display
- Timers provide timing functions
- I/O is memory-mapped

---

*I/O subsystems enable interaction and prepare for complete systems*
