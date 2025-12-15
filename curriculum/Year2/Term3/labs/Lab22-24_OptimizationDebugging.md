# Lab 29-32: System Optimization and Debugging

## Lab Overview

In this lab, students will optimize their systems, learn systematic debugging techniques, and improve system reliability and performance. **Students will also build a Prototype Module PCB as a prototyping board that will be used throughout the curriculum.**

## Learning Objectives

- **Build Prototype Module PCB (used throughout curriculum for experimentation)**
- Optimize signal integrity
- Improve timing and performance
- Learn systematic debugging
- Troubleshoot complex issues
- Document optimizations

## Prerequisites

- Completed Lab 25-28 (Complex Programs)
- Working complete system
- Understanding of system operation
- Experience with system issues

## Materials

### Components
- **Prototype Module PCB components (LAB PROJECT - Build in Session 0)**:
  - Perfboard or PCB with standard grid (2.54mm/0.1" spacing)
  - 40-pin header (for bus connection, if applicable)
  - Power connections (5V, GND)
  - Grid of solder pads or holes for component placement
  - Supporting components (resistors, capacitors, sockets)
- Complete system
- Decoupling capacitors (0.1µF)
- Additional components for optimization
- Debugging tools

### Tools
- Multimeter
- **TTL Logic Probe** (built in Year 2 Term 2, used here for debugging)
- Oscilloscope (if available)
- Logic analyzer (if available)
- **Prototype Module** (after Session 0): Students use the prototype board they build for experimentation

## Safety

- Work carefully with optimizations
- Verify changes don't break system
- Test after each change

## Lab Sessions

### Session 0: Prototype Module Construction (Week 22, Day 1-2) ⭐ QUICK WIN LAB PROJECT

**Objective**: Build Prototype Module PCB that will be used throughout the curriculum for experimentation and prototyping

**Learning Value**:
- ✅ **Immediate utility**: Experimentation board for all future labs
- ✅ **PCB skills**: Simple PCB project (grid pattern, no complex routing), good for early success
- ✅ **Practical tool**: Students use throughout curriculum for testing and prototyping
- ✅ **Confidence building**: Early success with PCB fabrication

**Steps**:
1. **Review Prototype Module Design** (30 min):
   - Understand grid-based prototyping board concept
   - Review standard grid spacing (2.54mm/0.1")
   - Plan PCB layout (or use perfboard with grid)
   - Consider bus connector (if connecting to system bus)

2. **Design Prototype Board** (60 min):
   - Design grid of solder pads or holes
   - Add power distribution (5V, GND rails)
   - Add bus connector (40-pin header, if applicable)
   - Add supporting components (decoupling capacitors, power indicator)
   - Create PCB layout (or perfboard layout)

3. **Build Prototype Module** (90 min):
   - Fabricate PCB (or prepare perfboard)
   - Solder power rails and connectors
   - Solder bus connector (if applicable)
   - Add decoupling capacitors
   - Add power indicator LED
   - Test power distribution

4. **Test Prototype Module** (30 min):
   - Verify power distribution (5V, GND)
   - Test bus connector (if applicable)
   - Test component placement on grid
   - Document module specifications

**Expected Result**: Working Prototype Module with power distribution and component grid

**Troubleshooting**:
- If power doesn't work: Check power connections, check rails
- If grid spacing wrong: Verify 2.54mm spacing, check measurements
- If bus connector issues: Check pin assignments, check connections

**Reference**: See `../../../resources/RC2014_BOARDS_CURRICULUM_ANALYSIS.md` for RC2014 Prototype Module design reference

**Ongoing Use**: This prototype module will be used in all subsequent labs (Years 2-6) for experimentation and prototyping

### Session 1: Signal Integrity (Week 23)

**Objective**: Improve signal integrity

**Steps**:
1. Identify signal integrity issues (noise, glitches)
2. Add decoupling capacitors near ICs
3. Improve grounding
4. Shorten signal paths where possible
5. Test system after changes
6. Verify improvements
7. Document changes

**Expected Result**: Improved signal integrity, fewer glitches

**Troubleshooting**:
- If issues persist: Check power distribution, check connections
- If new issues: Revert changes, try different approach
- If no improvement: May need different solution

### Session 2: Timing Optimization (Week 24)

**Objective**: Optimize system timing

**Steps**:
1. Identify timing issues
2. Analyze clock distribution
3. Add delays where needed
4. Optimize signal paths
5. Test timing improvements
6. Verify system still works
7. Document timing changes

**Expected Result**: Better timing, more reliable operation

**Troubleshooting**:
- If timing worse: Revert, try different approach
- If system fails: Check all timing, verify clock
- If no improvement: Timing may already be adequate

### Session 3: Systematic Debugging (Week 31)

**Objective**: Learn and practice systematic debugging

**Steps**:
1. Introduce systematic debugging methodology
2. Practice on known issues
3. Debug real system issues
4. Document debugging process
5. Create troubleshooting guide
6. Share debugging techniques
7. Reflect on debugging skills

**Expected Result**: Improved debugging skills, documented process

**Troubleshooting**:
- If debugging fails: Try different approach, get help
- If issues unclear: Use systematic method, check each component
- If stuck: Break problem into smaller parts

### Session 4: System Validation (Week 32)

**Objective**: Validate optimized system

**Steps**:
1. Test all system functions
2. Run comprehensive test suite
3. Verify optimizations work
4. Check for regressions
5. Document final system state
6. Create optimization report
7. Prepare for final integration

**Expected Result**: Optimized, validated system ready for final integration

**Troubleshooting**:
- If tests fail: Debug, fix, retest
- If optimizations break things: Revert problematic changes
- If validation incomplete: Complete all tests

## Assessment

### Practical Assessment
- Successfully optimize signal integrity
- Improve system timing
- Demonstrate debugging skills
- Validate optimized system
- Document all changes

### Lab Report
Students should document:
- Optimization changes made
- Debugging processes used
- Test results before/after
- Issues encountered and solutions
- Reflection on optimization

## Extension Activities

- Further optimizations
- Advanced debugging techniques
- Performance measurements
- Reliability testing

## Next Lab

After completing this lab, students will move to final integration (Lab 33-36).

---

*Optimization and debugging ensure reliable systems*
