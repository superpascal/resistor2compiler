# Week 6-9: PCB Assembly and Unit Testing - Theory

## Learning Objectives

By the end of this week-block, students will:
- Assemble components on PCBs
- Perform continuity and smoke tests
- Test each subsystem individually
- Document assembly and testing
- Verify each board before integration

## Prerequisites

- Completed Weeks 1-5 (PCB Design)
- Received fabricated PCBs
- Understanding of soldering techniques
- Understanding of ESD protection
- Understanding of testing procedures

## Key Concepts

### 1. PCB Assembly Overview

**Assembly process**:
1. Inspect PCBs
2. Prepare components
3. Solder components
4. Perform continuity tests
5. Perform smoke tests
6. Test subsystems
7. Document results

**Assembly order**:
- Power supply components first
- Passive components
- ICs last
- Connectors
- Final inspection

### 2. ESD Protection

**ESD risks**:
- Static electricity can damage CMOS chips
- CPU and memory are sensitive
- One zap can destroy a chip
- Chips are limited in supply

**Protection measures**:
- ESD wrist straps
- ESD mats
- Grounded workstations
- Anti-static bags
- Handle chips carefully

**Best practices**:
- Always wear wrist strap
- Work on ESD mat
- Keep chips in bags until needed
- Touch ground before handling
- Avoid static-generating materials

### 3. Soldering Techniques

**Through-hole soldering**:
- Most components are through-hole
- DIP ICs in sockets
- Resistors, capacitors
- Connectors
- Standard technique

**SMD soldering** (if needed):
- Some memory chips may be SMD
- Requires careful technique
- Hot air or fine-tip iron
- Solder paste
- More challenging

**Soldering quality**:
- Good fillets
- No cold joints
- No bridges
- Clean appearance
- Proper temperature

### 4. Continuity and Smoke Tests

**Continuity tests**:
- Check power and ground
- Verify no shorts
- Check connections
- Use multimeter
- Before power-up

**Smoke test**:
- Power up without chips
- Check regulator output
- Verify voltage levels
- Check for shorts
- No smoke or heat

**Power verification**:
- 5.0V ± 0.1V
- Stable voltage
- No ripple
- Proper current capacity
- Check at multiple points

### 5. Subsystem Testing

**Testing strategy**:
- Test each subsystem separately
- Unit testing approach
- Verify before integration
- Document all tests
- Fix issues immediately

**CPU board tests**:
- Reset circuit
- Clock generator
- Address decoding
- Basic CPU operation
- Memory access

**Peripheral board tests**:
- Video board (if separate)
- Audio board (if separate)
- I/O boards
- Each tested independently

### 6. Reset Circuit Testing

**Reset test procedures**:
- Power on/off test
- Manual reset button
- Reset pulse timing
- Reset vector access
- Oscilloscope verification

**Expected results**:
- Reset low on power-up
- Reset high after stabilization
- Clean transitions
- Proper timing
- CPU responds correctly

### 7. Clock Circuit Testing

**Clock test procedures**:
- Frequency measurement
- Waveform verification
- Stability check
- Distribution test
- Oscilloscope analysis

**Expected results**:
- Stable frequency
- Clean square wave
- Proper amplitude
- No jitter
- Correct distribution

### 8. Memory Testing

**Memory test procedures**:
- Write test patterns
- Read back and verify
- Test all addresses
- Test read/write timing
- Verify address decoding

**Test patterns**:
- All zeros
- All ones
- Alternating pattern
- Walking ones
- Random data

### 9. I/O Testing

**I/O test procedures**:
- Test VIA ports
- Test ACIA serial
- Test LCD display
- Test timers
- Verify address decoding

**Test methods**:
- Write to registers
- Read back values
- Test input/output
- Verify functionality
- Check timing

### 10. Assembly Documentation

**Assembly log**:
- Components installed
- Test results
- Issues encountered
- Fixes applied
- Verification status

**Test documentation**:
- Test procedures
- Expected results
- Actual results
- Pass/fail status
- Notes and observations

## Mathematical Foundations

### Voltage Measurements

**Tolerance**:
- 5.0V ± 0.1V acceptable
- Check at multiple points
- Under load conditions
- Stable over time

### Timing Measurements

**Clock frequency**:
- Measure with oscilloscope
- Verify stability
- Check jitter
- Confirm distribution

## Common Misconceptions

1. **"Assembly is easy"**
   - Clarify: Requires care and skill
   - Show importance

2. **"Can skip testing"**
   - Clarify: Essential for success
   - Show consequences

3. **"ESD not important"**
   - Clarify: Can destroy chips
   - Show protection needed

## Connections to Weeks 1-5

- **PCB Design**: Assembly follows design
- **Component Selection**: Used in assembly
- **Layout**: Affects assembly ease

## Connections to Weeks 10-12

- **Integration**: Uses tested boards
- **System Testing**: Builds on unit tests
- **Final System**: All boards verified

## Next Steps

After completing assembly and testing, students will:
- Integrate all boards (Weeks 10-12)
- Test complete system
- Verify all functionality

---

*Assembly and testing ensure reliable hardware before integration*
