# Lab 21-24: System Services and Integration

## Lab Overview

In this lab, students will design and implement system services API, implement interrupt handlers, implement memory management, and integrate all system components into a complete, functional system software stack.

## Learning Objectives

- Design and implement system services API
- Implement interrupt handlers
- Implement memory management
- Integrate all system components
- Test complete system
- Document complete system

## Prerequisites

- ✅ Completed Weeks 17-20 (Device Drivers)
- ✅ Enhanced monitor working
- ✅ Boot loader working
- ✅ All device drivers working
- ✅ Understanding of system architecture
- ✅ Understanding of interrupts
- ✅ Complete 65C816 system on PCB

## Materials

### Components
- Complete 65C816 system on PCB
- All hardware peripherals (video, audio, input, storage)
- Development PC with serial terminal

### Tools
- Text editor
- Assembler (ca65 or similar)
- Serial terminal software
- Linker (ld65 or similar)
- Oscilloscope (for timing verification)
- Logic analyzer (for debugging)

## Safety

- Verify all connections
- Check power requirements
- Test components individually
- Use proper grounding

## Lab Sessions

### Session 1: System Services Architecture (Week 21, Day 1-2)

**Objective**: Design system services architecture and implement service call mechanism

**Steps**:
1. **Architecture Design** (60 min):
   - Design system services architecture
   - Plan service categories
   - Design service call mechanism
   - Review design

2. **Service Categories** (60 min):
   - Define file system services
   - Define I/O services
   - Define memory services
   - Define system information services
   - Define program management services

3. **Service Call Implementation** (120 min):
   - Design service call interface
   - Implement parameter passing
   - Implement return values
   - Implement error handling
   - Test service call mechanism

**Deliverables**:
- System services architecture design
- Service call mechanism code
- Service category definitions

**Assessment**:
- Students present service architecture
- Students explain design decisions
- Students implement service call mechanism

---

### Session 2: File System and I/O Services (Week 21, Day 3-4)

**Objective**: Implement file system services and I/O services

**Steps**:
1. **File System Services** (120 min):
   - Implement file open service
   - Implement file read service
   - Implement file write service
   - Implement file close service
   - Implement directory listing service
   - Test file system services

2. **I/O Services** (120 min):
   - Implement console I/O services (print, read)
   - Implement graphics I/O services (mode, drawing)
   - Implement sound I/O services (tone, music)
   - Test I/O services
   - Verify services work

**Deliverables**:
- File system services code
- I/O services code
- Test programs

**Assessment**:
- Students implement file services
- Students implement I/O services
- Students test services
- Students verify services work

---

### Session 3: Memory and System Information Services (Week 22, Day 1-2)

**Objective**: Implement memory services and system information services

**Steps**:
1. **Memory Services** (120 min):
   - Implement memory allocation service
   - Implement memory free service
   - Implement memory info service
   - Test memory services
   - Verify memory management

2. **System Information Services** (90 min):
   - Implement system info service
   - Implement device status service
   - Test system information services
   - Verify services work

3. **Service API Completion** (30 min):
   - Complete service API
   - Add error handling
   - Document API

**Deliverables**:
- Memory services code
- System information services code
- Complete service API
- API documentation

**Assessment**:
- Students implement memory services
- Students implement system info services
- Students complete service API
- Students document API

---

### Session 4: Service Integration (Week 22, Day 3-4)

**Objective**: Integrate services with monitor and boot loader

**Steps**:
1. **Monitor Integration** (90 min):
   - Add service commands to monitor
   - Integrate services with monitor
   - Test integration
   - Fix any issues

2. **Boot Loader Integration** (90 min):
   - Use services in boot loader
   - Integrate services
   - Test integration
   - Fix any issues

3. **Service Testing** (60 min):
   - Test all services
   - Test error handling
   - Test service interactions
   - Fix any issues

**Deliverables**:
- Integrated services
- Service commands in monitor
- Service usage in boot loader
- Test suite

**Assessment**:
- Students integrate services with monitor
- Students integrate services with boot loader
- Students test all services
- Students verify integration

---

### Session 5: Interrupt Vector Table (Week 23, Day 1-2)

**Objective**: Set up interrupt vector table and implement interrupt handlers

**Steps**:
1. **Vector Table Design** (60 min):
   - Design interrupt vector table
   - Plan vector locations
   - Plan vector organization
   - Review design

2. **Vector Table Setup** (90 min):
   - Implement vector table setup
   - Initialize all vectors
   - Test vector table
   - Verify vectors set correctly

3. **Basic Interrupt Handler** (90 min):
   - Implement basic interrupt handler
   - Save registers
   - Handle interrupt
   - Restore registers
   - Return from interrupt
   - Test interrupt handler

**Deliverables**:
- Interrupt vector table code
- Basic interrupt handler code
- Test program

**Assessment**:
- Students set up vector table
- Students implement interrupt handler
- Students test interrupts
- Students verify interrupts work

---

### Session 6: Timer and I/O Interrupts (Week 23, Day 3-4)

**Objective**: Implement timer interrupts and I/O interrupts

**Steps**:
1. **Timer Interrupts** (120 min):
   - Configure timer hardware
   - Set timer frequency
   - Enable timer interrupts
   - Implement timer interrupt handler
   - Update system clock
   - Test timer interrupts

2. **I/O Interrupts** (120 min):
   - Set up keyboard interrupts
   - Implement keyboard interrupt handler
   - Set up serial interrupts
   - Implement serial interrupt handler
   - Test I/O interrupts
   - Verify interrupts work

**Deliverables**:
- Timer interrupt code
- I/O interrupt code
- Test programs

**Assessment**:
- Students implement timer interrupts
- Students implement I/O interrupts
- Students test interrupts
- Students verify interrupts work

---

### Session 7: Memory Management (Week 24, Day 1-2)

**Objective**: Implement heap allocator and memory map

**Steps**:
1. **Heap Allocator** (120 min):
   - Implement heap allocator
   - Implement allocation algorithm (first-fit or best-fit)
   - Implement free list management
   - Implement block coalescing
   - Test heap allocator
   - Verify allocator works

2. **Memory Map** (90 min):
   - Implement memory map
   - Track memory regions
   - Track memory usage
   - Test memory map
   - Verify memory tracking

3. **Memory Protection** (30 min):
   - Implement memory protection
   - Protect critical regions
   - Test memory protection

**Deliverables**:
- Heap allocator code
- Memory map code
- Memory protection code
- Test programs

**Assessment**:
- Students implement heap allocator
- Students implement memory map
- Students test memory management
- Students verify memory works

---

### Session 8: System Integration and Testing (Week 24, Day 3-4)

**Objective**: Integrate all components and test complete system

**Steps**:
1. **Boot Sequence** (90 min):
   - Design boot sequence
   - Implement boot sequence
   - Initialize all components
   - Test boot sequence
   - Fix any issues

2. **System Testing** (120 min):
   - Test all system functions
   - Test component interactions
   - Test error handling
   - Test performance
   - Fix any issues

3. **Documentation** (90 min):
   - Document system architecture
   - Document all components
   - Create user manual
   - Create technical manual
   - Create API reference

**Deliverables**:
- Integrated system
- Test suite
- System documentation
- User manual
- Technical manual

**Assessment**:
- Students integrate all components
- Students test complete system
- Students document system
- Students demonstrate system

---

## Lab Assessment

### Formative Assessment

- Weekly progress checks
- Code reviews
- Integration demonstrations
- Instructor feedback

### Summative Assessment

**System Services** (30%):
- Service architecture (5%)
- File system services (10%)
- I/O services (10%)
- Memory services (5%)

**Interrupt Handlers** (25%):
- Interrupt vector table (10%)
- Timer interrupts (5%)
- I/O interrupts (10%)

**Memory Management** (15%):
- Heap allocator (10%)
- Memory map (5%)

**System Integration** (20%):
- Boot sequence (10%)
- Component integration (10%)

**Documentation** (10%):
- System documentation (5%)
- User manual (5%)

### Assessment Criteria

**Excellent (A)**:
- All components implemented correctly
- Clean, well-documented code
- Comprehensive testing
- Complete documentation
- System fully functional

**Good (B)**:
- Most components implemented
- Code mostly correct
- Adequate testing
- Good documentation
- System mostly functional

**Satisfactory (C)**:
- Basic components implemented
- Code has some issues
- Basic testing
- Basic documentation
- System partially functional

---

## Troubleshooting

### Common Issues

1. **Service Calls Not Working**:
   - Check service call mechanism
   - Verify parameter passing
   - Check return values
   - Verify error handling

2. **Interrupts Not Firing**:
   - Check interrupt vector table
   - Verify interrupt enable
   - Check interrupt hardware
   - Use oscilloscope to verify

3. **Memory Allocation Fails**:
   - Check heap allocator
   - Verify free list
   - Check memory fragmentation
   - Test with various patterns

4. **System Integration Issues**:
   - Test components individually
   - Check component interactions
   - Verify initialization order
   - Check resource conflicts

---

## Resources

- System Architecture Document
- Component Design Documents
- Memory Map
- Interrupt Vector Map
- Service API Reference
- Device Driver Documentation

---

## Final Demonstration

### "Curriculum Complete" Condition

Students must demonstrate:
1. **System Boot**: System boots successfully
2. **Monitor Interaction**: Can interact with enhanced monitor
3. **Program Loading**: Can load program from SD card via boot loader
4. **Program Execution**: Can execute loaded program
5. **Hardware Functionality**: Graphics, sound, and input all working
6. **System Services**: Can use system services from programs
7. **Complete Documentation**: User manual and technical manual complete

### Demonstration Requirements

- Complete system working
- All components integrated
- All features demonstrated
- Documentation complete
- System ready for use

---

## Next Steps

After completing system services and integration, students have a complete, functional 16-bit computer system with full software stack. This represents the culmination of the 6-year curriculum journey.

---

*System services and integration bring together all components into a complete, functional system*
