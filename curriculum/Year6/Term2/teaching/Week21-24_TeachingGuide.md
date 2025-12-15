# Week 21-24: System Services and Integration - Teaching Guide

## Overview

This teaching guide supports the delivery of system services API, interrupt handlers, memory management, and complete system integration over 4 weeks. Students create a unified system software stack.

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

## Week 21-22: System Services API

### Week 21: Service Design and File/I/O Services

#### Day 1: System Services Architecture

**Objectives**:
- Design system services architecture
- Plan service categories
- Design service call mechanism

**Activities**:
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

3. **Service Call Design** (60 min):
   - Design service call interface
   - Plan parameter passing
   - Plan return values
   - Plan error handling

**Assessment**:
- Students present service architecture
- Students explain design decisions
- Students create service design document

#### Day 2: File System Services

**Objectives**:
- Implement file system services
- Add file operations
- Add directory operations

**Activities**:
1. **File Operations** (90 min):
   - Implement file open service
   - Implement file read service
   - Implement file write service
   - Implement file close service
   - Test file operations

2. **Directory Operations** (60 min):
   - Implement directory listing service
   - Implement file find service
   - Test directory operations
   - Verify operations work

3. **Service Integration** (30 min):
   - Integrate file services
   - Test integration
   - Fix any issues

**Assessment**:
- Students implement file services
- Students test file operations
- Students verify services work

#### Day 3: I/O Services

**Objectives**:
- Implement console I/O services
- Implement graphics I/O services
- Implement sound I/O services

**Activities**:
1. **Console I/O** (60 min):
   - Implement print service
   - Implement read service
   - Test console I/O
   - Verify console I/O works

2. **Graphics I/O** (90 min):
   - Implement graphics mode service
   - Implement drawing services
   - Implement text output service
   - Test graphics I/O

3. **Sound I/O** (30 min):
   - Implement sound services
   - Test sound I/O
   - Verify sound I/O works

**Assessment**:
- Students implement I/O services
- Students test I/O operations
- Students verify services work

#### Day 4: Memory and System Information Services

**Objectives**:
- Implement memory services
- Implement system information services
- Test all services

**Activities**:
1. **Memory Services** (90 min):
   - Implement memory allocation service
   - Implement memory free service
   - Implement memory info service
   - Test memory services

2. **System Information** (60 min):
   - Implement system info service
   - Implement device status service
   - Test system information services
   - Verify services work

3. **Service Testing** (30 min):
   - Test all services
   - Fix any issues
   - Document services

**Assessment**:
- Students implement memory services
- Students implement system info services
- Students test all services

### Week 22: Service Integration and Testing

#### Day 1: Service API Completion

**Objectives**:
- Complete service API
- Add error handling
- Test service API

**Activities**:
1. **Error Handling** (60 min):
   - Add error codes
   - Add error handling to services
   - Test error handling

2. **API Completion** (90 min):
   - Complete service API
   - Add missing services
   - Test complete API
   - Verify API works

3. **API Documentation** (30 min):
   - Document service API
   - Create API reference
   - Document error codes

**Assessment**:
- Students complete service API
- Students test API
- Students document API

#### Day 2: Service Integration with Monitor

**Objectives**:
- Integrate services with monitor
- Add service commands to monitor
- Test service integration

**Activities**:
1. **Monitor Integration** (90 min):
   - Add service commands to monitor
   - Integrate services with monitor
   - Test integration
   - Fix any issues

2. **Command Testing** (60 min):
   - Test all service commands
   - Verify commands work
   - Test error handling

3. **Service Demo** (30 min):
   - Create service demo
   - Demonstrate services
   - Present demo

**Assessment**:
- Students integrate services
- Students test service commands
- Students demonstrate services

#### Day 3: Service Integration with Boot Loader

**Objectives**:
- Integrate services with boot loader
- Use services in boot loader
- Test integration

**Activities**:
1. **Boot Loader Integration** (90 min):
   - Use services in boot loader
   - Integrate services
   - Test integration
   - Fix any issues

2. **Service Usage** (60 min):
   - Use services for program loading
   - Use services for file operations
   - Test service usage
   - Verify services work

3. **Integration Testing** (30 min):
   - Test complete integration
   - Fix any issues
   - Document integration

**Assessment**:
- Students integrate services with boot loader
- Students test integration
- Students verify services work

#### Day 4: Service Testing and Documentation

**Objectives**:
- Test all services
- Document services
- Create service examples

**Activities**:
1. **Service Testing** (90 min):
   - Test all services
   - Test error handling
   - Test service interactions
   - Fix any issues

2. **Documentation** (60 min):
   - Document service API
   - Document service usage
   - Create service examples
   - Document error codes

3. **Service Review** (30 min):
   - Review service implementation
   - Gather feedback
   - Plan improvements

**Assessment**:
- Students test all services
- Students document services
- Students create examples

---

## Week 23: Interrupt Handlers

### Day 1: Interrupt Vector Table

**Objectives**:
- Set up interrupt vector table
- Initialize interrupt vectors
- Test vector table

**Activities**:
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

3. **Vector Testing** (30 min):
   - Test vector table
   - Verify interrupt routing
   - Fix any issues

**Assessment**:
- Students set up vector table
- Students test vector table
- Students verify vectors work

### Day 2: Timer Interrupts

**Objectives**:
- Implement timer interrupt handler
- Set up timer interrupts
- Test timer interrupts

**Activities**:
1. **Timer Setup** (60 min):
   - Configure timer hardware
   - Set timer frequency
   - Enable timer interrupts
   - Test timer setup

2. **Timer Handler** (90 min):
   - Implement timer interrupt handler
   - Update system clock
   - Test timer handler
   - Verify timer interrupts work

3. **Timer Testing** (30 min):
   - Test timer interrupts
   - Test timer timing
   - Verify timer accuracy

**Assessment**:
- Students implement timer interrupts
- Students test timer interrupts
- Students verify timer works

### Day 3: I/O Interrupts

**Objectives**:
- Implement keyboard interrupts
- Implement serial interrupts
- Test I/O interrupts

**Activities**:
1. **Keyboard Interrupts** (90 min):
   - Set up keyboard interrupts
   - Implement keyboard handler
   - Process keys in handler
   - Test keyboard interrupts

2. **Serial Interrupts** (60 min):
   - Set up serial interrupts
   - Implement serial handler
   - Process data in handler
   - Test serial interrupts

3. **I/O Interrupt Testing** (30 min):
   - Test I/O interrupts
   - Test interrupt timing
   - Verify interrupts work

**Assessment**:
- Students implement I/O interrupts
- Students test I/O interrupts
- Students verify interrupts work

### Day 4: Interrupt Management

**Objectives**:
- Implement interrupt management
- Test interrupt system
- Document interrupt system

**Activities**:
1. **Interrupt Management** (90 min):
   - Implement interrupt enable/disable
   - Implement interrupt priority
   - Implement interrupt status
   - Test interrupt management

2. **Interrupt Testing** (60 min):
   - Test all interrupt types
   - Test interrupt timing
   - Test error handling
   - Fix any issues

3. **Interrupt Documentation** (30 min):
   - Document interrupt system
   - Document interrupt vectors
   - Document interrupt handlers
   - Create interrupt reference

**Assessment**:
- Students implement interrupt management
- Students test interrupt system
- Students document interrupts

---

## Week 24: System Integration

### Day 1: Memory Management

**Objectives**:
- Implement heap allocator
- Implement memory map
- Test memory management

**Activities**:
1. **Heap Allocator** (90 min):
   - Implement heap allocator
   - Implement allocation algorithm
   - Test heap allocator
   - Verify allocator works

2. **Memory Map** (60 min):
   - Implement memory map
   - Track memory regions
   - Test memory map
   - Verify memory tracking

3. **Memory Testing** (30 min):
   - Test memory management
   - Test memory allocation
   - Test memory deallocation
   - Fix any issues

**Assessment**:
- Students implement memory management
- Students test memory management
- Students verify memory works

### Day 2: Boot Sequence Integration

**Objectives**:
- Integrate boot sequence
- Test system initialization
- Fix initialization issues

**Activities**:
1. **Boot Sequence Design** (60 min):
   - Design boot sequence
   - Plan initialization order
   - Plan error handling
   - Review design

2. **Boot Sequence Implementation** (90 min):
   - Implement boot sequence
   - Initialize all components
   - Test boot sequence
   - Fix any issues

3. **Boot Testing** (30 min):
   - Test system boot
   - Test initialization
   - Verify boot works

**Assessment**:
- Students implement boot sequence
- Students test boot sequence
- Students verify boot works

### Day 3: System Testing

**Objectives**:
- Test complete system
- Fix system issues
- Optimize system

**Activities**:
1. **System Testing** (120 min):
   - Test all system functions
   - Test component interactions
   - Test error handling
   - Fix any issues

2. **Performance Testing** (60 min):
   - Measure system performance
   - Identify bottlenecks
   - Optimize if needed
   - Test optimizations

**Assessment**:
- Students test complete system
- Students fix issues
- Students optimize system

### Day 4: Documentation and Demonstration

**Objectives**:
- Document complete system
- Create system demonstration
- Present system

**Activities**:
1. **System Documentation** (90 min):
   - Document system architecture
   - Document all components
   - Create user manual
   - Create technical manual

2. **System Demonstration** (60 min):
   - Create system demo
   - Demonstrate all features
   - Show system capabilities
   - Answer questions

3. **Final Review** (30 min):
   - Review complete system
   - Gather feedback
   - Plan future improvements

**Assessment**:
- Students document system
- Students demonstrate system
- Students present system

---

## Teaching Tips

### Common Challenges

1. **Service Integration**:
   - Problem: Services don't integrate well
   - Solution: Design consistent API, plan integration early
   - Tip: Use service stubs for testing

2. **Interrupt Timing**:
   - Problem: Interrupt timing issues
   - Solution: Check interrupt setup, verify timing
   - Tip: Use oscilloscope to verify timing

3. **Memory Management**:
   - Problem: Memory fragmentation
   - Solution: Implement coalescing, use appropriate algorithm
   - Tip: Test with various allocation patterns

4. **System Integration**:
   - Problem: Components don't work together
   - Solution: Test integration early, fix issues as they arise
   - Tip: Use integration tests

### Assessment Strategies

1. **System Demonstration**:
   - Students demonstrate complete system
   - Students show all features
   - Students answer questions

2. **Documentation Review**:
   - Review system documentation
   - Check completeness
   - Provide feedback

3. **Code Review**:
   - Review system code
   - Check for best practices
   - Provide feedback

---

## Resources

- System Architecture Document
- Component Design Documents
- Memory Map
- Interrupt Vector Map
- Service API Reference

---

## Next Steps

After completing system services and integration, students have a complete, functional 16-bit computer system with full software stack. This represents the culmination of the 6-year curriculum journey.

---

*System services and integration bring together all components into a complete, functional system*
