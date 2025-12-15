# Week 1-5: Finalizing PCB Schematics and Layout - Theory

## Learning Objectives

By the end of this week-block, students will:
- Finalize PCB schematics for 65C816 system
- Design robust power distribution
- Design reset and clock circuits
- Plan PCB layout and component placement
- Create Gerber files for fabrication

## Prerequisites

- Completed Year 4 (65C816 Prototype)
- Working breadboard prototype
- Complete system design
- Experience with KiCad
- Understanding of PCB design principles

## Key Concepts

### 1. PCB Design Overview

**Why PCBs?**
- More reliable than breadboards
- Professional appearance
- Better signal integrity
- Easier to reproduce
- Foundation for final system

**Design process**:
1. Finalize schematics
2. Plan board layout
3. Place components
4. Route traces
5. Add power planes
6. Generate Gerber files
7. Order fabrication

### 2. Schematic Finalization

**Schematic requirements**:
- All components included
- Power distribution shown
- Decoupling capacitors placed
- Connectors specified
- Test points indicated
- Labels and annotations

**Board organization**:
- Main CPU board (CPU, memory, core I/O)
- Video board (optional, separate)
- Audio board (optional, separate)
- Backplane or connectors

**Component selection**:
- Verify availability
- Check specifications
- Consider alternatives
- Plan for expansion

### 3. Power Distribution Design

**Power supply requirements**:
- 5V regulated supply
- Adequate current capacity
- Stable voltage
- Low noise
- Protection circuits

**Power distribution**:
- Voltage regulator (LM7805 or switching)
- Input from DC jack or USB
- Power switch
- Multiple power connections
- Decoupling capacitors

**Decoupling strategy**:
- 0.1µF ceramic near each IC
- Larger electrolytic for bulk (10-100µF)
- Power planes where possible
- Star grounding
- Filter high-frequency noise

### 4. Reset Circuit Design

**Reset requirements**:
- Power-on reset
- Manual reset button
- Clean reset pulse
- Proper timing
- Reset supervisor IC (recommended)

**Reset circuit**:
- Reset supervisor IC (e.g., MAX809)
- Or RC circuit + Schmitt trigger
- Reset button
- Reset distribution
- Reset vector initialization

**Reset timing**:
- Reset low during power-up
- Reset high after stabilization
- Clean transitions
- No glitches

### 5. Clock Circuit Design

**Clock requirements**:
- Stable frequency
- Clean waveform
- TTL/CMOS compatible
- Single-step capability
- Proper distribution

**Clock circuit**:
- Crystal oscillator or TTL oscillator
- Clock buffer/distribution
- Single-step circuit (optional)
- Clock enable (optional)
- Proper routing

**Clock routing**:
- Short traces
- Avoid noise sources
- Proper termination
- Clock tree design

### 6. Component Placement

**Placement strategy**:
- Group related components
- Minimize trace lengths
- Consider heat dissipation
- Access for testing
- Aesthetic organization

**Critical placements**:
- Clock near CPU
- Decoupling near each IC
- Power regulator accessible
- Connectors on edges
- Test points accessible

**Signal integrity**:
- Short data bus traces
- Avoid long parallel runs
- Proper spacing
- Ground fills
- Power planes

### 7. PCB Layout and Routing

**Layout principles**:
- Logical component grouping
- Minimize trace lengths
- Avoid crossing signals
- Proper layer usage
- Ground planes

**Routing strategy**:
- Route critical signals first
- Power and ground planes
- Data bus routing
- Address bus routing
- Control signals

**Layer usage**:
- Top: Components and signals
- Bottom: Ground plane
- Inner layers (if multi-layer): Power and signals
- Via usage

### 8. Test Points and Connectors

**Test points**:
- Logic analyzer headers
- Critical signals (φ2, R/W, IRQ)
- Power and ground
- Bus signals
- Clock signals

**Connectors**:
- SD card slot
- Expansion header (XBus-style)
- PS/2 or USB ports
- Video output (RCA or HDMI)
- Audio output (jack)
- Serial port

**JTAG header**:
- For programmable logic
- For microcontroller programming
- Debugging interface
- Firmware updates

### 9. Gerber File Generation

**Gerber files**:
- Standard PCB fabrication format
- Multiple layers
- Drill files
- Solder mask
- Silkscreen

**Generation process**:
- Export from KiCad
- Verify all layers
- Check drill holes
- Verify dimensions
- Review with fabrication house

**Fabrication preparation**:
- Choose fabrication house
- Specify requirements
- Order boards
- Plan for lead time (2-4 weeks)

## Mathematical Foundations

### Power Calculations

**Current requirements**:
- Sum of all component currents
- Add 20-30% margin
- Voltage drop: I × R
- Power: V × I

### Trace Width

**Current capacity**:
- Trace width vs current
- Temperature rise
- Copper thickness
- Standard: 10 mils per amp (minimum)

## Common Misconceptions

1. **"PCB design is easy"**
   - Clarify: Requires careful planning
   - Show complexity

2. **"Any layout works"**
   - Clarify: Layout affects performance
   - Show best practices

3. **"Can fix on PCB"**
   - Clarify: Changes are difficult
   - Show importance of design review

## Connections to Year 4

- **Breadboard Prototype**: Foundation for PCB design
- **System Design**: Guides PCB layout
- **Component Selection**: Used in PCB

## Connections to Weeks 6-12

- **Assembly**: Follows PCB design
- **Testing**: Verifies design
- **Integration**: Uses designed boards

## Next Steps

After completing PCB design, students will:
- Order PCBs (Weeks 1-5)
- Assemble boards (Weeks 6-9)
- Integrate system (Weeks 10-12)

---

*PCB design creates the foundation for professional hardware*
