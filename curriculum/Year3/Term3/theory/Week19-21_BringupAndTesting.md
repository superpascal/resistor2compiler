# Week 19-21: SAP-1 Bring-up and Testing - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand system bring-up procedures
- Learn systematic testing methodologies
- Understand hardware debugging techniques
- Verify signal integrity
- Troubleshoot complex issues

## Prerequisites

- Completed Terms 1-2
- Complete SAP-1 system built
- Understanding of all components
- Understanding of CPU operation

## Key Concepts

### 1. System Bring-up

**What is bring-up?**
- Getting the complete system working
- Testing all components together
- Verifying system operation
- Debugging issues found

**Bring-up process**:
1. **Power-up**: Apply power, check for issues
2. **Basic tests**: Test each subsystem
3. **Integration tests**: Test components together
4. **System tests**: Test complete operation
5. **Debugging**: Fix issues found

**Initial checks**:
- Power connections correct
- No shorts or overheating
- All components powered
- Clock working
- Reset working

### 2. Systematic Testing

**Testing strategy**:
- Start simple: Basic operations
- Build up: More complex operations
- Test systematically: Each component
- Verify results: Compare to expected
- Document tests: Record results

**Test levels**:
- **Unit tests**: Individual components
- **Integration tests**: Components together
- **System tests**: Complete operations
- **Program tests**: Running programs

### 3. Hardware Debugging

**Debugging methodology**:
1. **Observe**: What's happening?
2. **Isolate**: Which component?
3. **Test**: Check component
4. **Fix**: Resolve issue
5. **Verify**: Confirm fix works

**Debugging tools**:
- Logic analyzer: See signals
- Oscilloscope: See timing
- LEDs: Visual status
- Multimeter: Check voltages
- Single-step: Step through execution

### 4. Signal Integrity

**Signal integrity issues**:
- Noise on signals
- Glitches and spikes
- Slow rise/fall times
- Timing violations

**Solutions**:
- Decoupling capacitors (0.1µF per IC)
- Proper grounding
- Short signal paths
- Proper termination
- Stable clock

**Verification**:
- Check signals with scope
- Look for glitches
- Verify timing
- Check power supply

### 5. Common Issues

**Power issues**:
- Insufficient power supply
- Voltage drops
- Noise on power lines
- Missing decoupling

**Signal issues**:
- Wrong control signals
- Timing problems
- Bus conflicts
- Signal integrity

**Component issues**:
- Wrong connections
- Component failures
- ESD damage
- Overheating

### 6. Testing Procedures

**Initial power-up**:
1. Check power supply voltage
2. Check for shorts
3. Apply power slowly
4. Monitor for overheating
5. Check basic signals

**Component testing**:
1. Test each component individually
2. Verify connections
3. Test with known inputs
4. Verify outputs
5. Document results

**Integration testing**:
1. Test components together
2. Verify data flow
3. Check signal coordination
4. Verify timing
5. Test operations

### 7. Debugging Techniques

**Single-step debugging**:
- Execute one step at a time
- Observe signals at each step
- Verify expected behavior
- Find where it goes wrong

**Signal tracing**:
- Follow signals through system
- Check at each point
- Verify signal values
- Find incorrect signals

**Systematic approach**:
- Don't guess
- Test methodically
- Document findings
- Fix one thing at a time

### 8. System Verification

**Verification checklist**:
- All components working
- All connections correct
- All signals correct
- Timing correct
- Programs execute correctly

**Success criteria**:
- CPU fetches instructions
- CPU decodes instructions
- CPU executes instructions
- Programs run correctly
- Results are correct

## Mathematical Foundations

### Signal Timing

**Setup time**: Data must be stable before clock
**Hold time**: Data must remain stable after clock
**Clock period**: Must be longer than longest path
**Propagation delay**: Time for signal to travel

### Power Calculations

**Current requirement**: Sum of all component currents
**Voltage drop**: Current × Resistance
**Power**: Voltage × Current
**Decoupling**: Filters high-frequency noise

## Common Misconceptions

1. **"If it doesn't work, it's broken"**
   - Clarify: Usually wiring or timing issue
   - Show debugging approach

2. **"Debugging is guessing"**
   - Clarify: Systematic approach works
   - Show methodology

3. **"More power is better"**
   - Clarify: Correct voltage is important
   - Show power requirements

## Connections to Terms 1-2

- **All Components**: Testing all we built
- **Integration**: Bringing it all together
- **Control Unit**: Testing automatic operation
- **Complete System**: Final verification

## Connections to Weeks 22-24

- **Programming**: Need working CPU
- **Program Testing**: Will test with programs
- **Debugging**: Skills used for programs too

## Next Steps

After bring-up and testing, students will:
- Program CPU in machine code (Weeks 22-24)
- Run complete programs
- Debug programs
- Complete SAP-1 project

---

*Bring-up and testing ensure reliable CPU operation*
