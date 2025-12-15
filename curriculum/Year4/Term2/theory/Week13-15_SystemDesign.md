# Week 13-15: 65C816 System Design - Theory

## Learning Objectives

By the end of this week-block, students will:
- Design a 65C816-based computer system
- Plan memory map and address decoding
- Design I/O interfaces
- Create schematics using CAD tools
- Understand professional design practices

## Prerequisites

- Completed Weeks 13-16 (65C816 Introduction)
- Understanding of 65C816 architecture
- Understanding of system design (from SAP-1)
- Understanding of address decoding (Year 2-4)

## Key Concepts

### 1. System Architecture Design

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

### 2. Memory Map Design

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

### 3. Address Decoding

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

**Example**:
- A15=0: Select RAM (0x0000-0x7FFF)
- A15=1, A14-A12=1111: Select ROM (0xF000-0xFFFF)
- A15=1, A14-A8=10011111: Select I/O (0x9F00-0x9FFF)

### 4. I/O Interface Design

**VIA (Versatile Interface Adapter) 65C22**:
- Parallel I/O ports (A and B)
- Timers
- Shift register
- Interrupt capability
- Two VIAs for more I/O

**ACIA (Asynchronous Communications Interface Adapter) 65C51**:
- Serial communication
- UART functionality
- RS-232 compatible
- For terminal interface

**I/O mapping**:
- Memory-mapped I/O
- Specific address ranges
- Register access
- Control and data registers

### 5. Clock and Reset Design

**Clock circuit**:
- Stable oscillator (1-10 MHz)
- Not 555 timer (too unstable)
- Crystal oscillator or TTL oscillator
- Single-step capability
- Clock buffering

**Reset circuit**:
- Power-on reset
- Manual reset button
- Reset supervisor IC (recommended)
- Clean reset pulse
- Reset vector initialization

### 6. Power Supply Design

**Power requirements**:
- 5V for logic (65C816, memory, I/O)
- Adequate current capacity
- Stable voltage
- Low noise

**Power distribution**:
- Voltage regulator
- Multiple power connections
- Decoupling capacitors
- Power switch
- Fuse protection

### 7. Schematic Capture

**Using KiCad**:
- Professional schematic tool
- Offline available
- Standard format
- Can generate PCB layouts

**Schematic elements**:
- Components and symbols
- Connections (wires)
- Power and ground
- Labels and annotations
- Title block

**Best practices**:
- Clear organization
- Proper labeling
- Power distribution shown
- Decoupling shown
- Test points indicated

### 8. Design Review

**Review checklist**:
- All components included?
- Address decoding correct?
- Power distribution adequate?
- Decoupling capacitors?
- Clock circuit stable?
- Reset circuit proper?
- I/O interfaces planned?
- Room for expansion?

**Peer review**:
- Present design to class
- Explain design decisions
- Answer questions
- Incorporate feedback
- Refine design

## Mathematical Foundations

### Address Decoding

**For 64KB address space**:
- A15-A0: 16 address bits
- A15 selects RAM (0) vs ROM/I/O (1)
- A14-A12 further decode
- A11-A0 select location within device

### Memory Sizing

**32KB RAM**: 2^15 = 32,768 bytes
**32KB ROM**: 2^15 = 32,768 bytes
**Total**: 64KB in bank $00

## Common Misconceptions

1. **"Design is just drawing"**
   - Clarify: Requires understanding and planning
   - Show design process

2. **"More is always better"**
   - Clarify: Appropriate for needs
   - Show balance

3. **"Schematic is optional"**
   - Clarify: Essential for complex systems
   - Show professional practice

## Connections to Weeks 13-16

- **65C816 Knowledge**: Used in design
- **Architecture Understanding**: Guides design
- **Component Mapping**: Applied in design

## Connections to Weeks 21-24

- **Prototype**: Design becomes prototype
- **Construction**: Follows design
- **Testing**: Verifies design

## Next Steps

After designing system, students will:
- Build breadboard prototype (Weeks 21-24)
- Test design
- Verify operation
- Prepare for Year 5

---

*System design is the blueprint for construction*
