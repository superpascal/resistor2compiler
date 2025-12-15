# Chapter 5: 65C816 System Design

## Introduction

System design creates the blueprint for construction. This chapter explains how to design a 65C816-based computer system.

## System Architecture Design

**Design process**:
1. **Requirements**: What should system do?
2. **Components**: What components needed?
3. **Memory map**: How to organize memory?
4. **I/O map**: How to organize I/O?
5. **Address decoding**: How to select devices?
6. **Schematic**: Draw complete design

**Key components**:
- 65C816 CPU
- Memory (RAM and ROM)
- I/O chips (VIA, ACIA)
- Address decoders
- Clock and reset circuits
- Power supply

## Memory Map Design

**Memory organization**:
```
Bank $00:
  0x0000 - 0x7FFF: RAM (32KB)
  0x8000 - 0xFFFD: ROM (32KB)
  0xFFFE - 0xFFFF: Reserved

I/O Space:
  0x9F00 - 0x9FFF: VIA and ACIA
```

**Design considerations**:
- RAM size (32KB, 64KB, or more)
- ROM size (for monitor program)
- I/O space allocation
- Room for expansion
- Standard locations (reset vectors)

## Address Decoding

**Decoding requirements**:
- Select RAM vs ROM
- Select I/O devices
- Handle 24-bit addressing
- Support banking (if implemented)

**Implementation**:
- Use decoders (74HC138, etc.)
- Higher address bits select device
- Lower address bits select location
- Chip select generation

## I/O Interface Design

**VIA (Versatile Interface Adapter) 65C22**:
- Parallel I/O ports (A and B)
- Timers
- Shift register
- Interrupt capability

**ACIA (Asynchronous Communications Interface Adapter) 65C51**:
- Serial communication
- UART functionality
- RS-232 compatible
- For terminal interface

## Schematic Capture

**Using KiCad**:
- Professional schematic tool
- Offline available
- Standard format
- Can generate PCB layouts

**Best practices**:
- Clear organization
- Proper labeling
- Power distribution shown
- Decoupling shown
- Test points indicated

## Practice Questions

1. How do we design a system?
2. What is a memory map?
3. How does address decoding work?
4. What I/O devices do we need?
5. Why use schematic capture?

## Key Takeaways

- Design before building
- Memory map organizes system
- Address decoding selects devices
- I/O enables interaction
- Schematics are essential

---

*System design is the blueprint for construction*
