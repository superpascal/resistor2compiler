# Week 21-24: System Services and Integration - Theory

## Overview

This 4-week block covers system services API, interrupt handlers, memory management, and complete system integration. Students create a unified system software stack that brings together all components developed in Year 6.

## Learning Objectives

By the end of this block, students will:
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

## Week 21-22: System Services API

### 1. What are System Services?

**System Services** provide:
- **Abstraction Layer**: Hide hardware details from applications
- **Unified Interface**: Consistent API for all system functions
- **Resource Management**: Manage system resources
- **Error Handling**: Consistent error reporting

**Analogy**: Think of system services like a library - applications call library functions instead of directly accessing hardware.

### 2. System Services Architecture

#### Service Categories
- **File System Services**: File operations, directory operations
- **I/O Services**: Console I/O, graphics I/O, sound I/O
- **Memory Services**: Memory allocation, memory management
- **System Information**: Get system status, device status
- **Program Management**: Load, execute, terminate programs

#### Service Call Mechanism
- **Software Interrupts**: Use BRK or similar for service calls
- **Function Calls**: Direct function calls (simpler)
- **Parameter Passing**: Pass parameters via registers or stack
- **Return Values**: Return values via registers
- **Error Codes**: Return error codes for failures

### 3. File System Services

#### File Operations
- **Open File**: Open file for reading/writing
- **Read File**: Read data from file
- **Write File**: Write data to file
- **Close File**: Close file
- **Seek File**: Seek to position in file

#### Directory Operations
- **List Directory**: List files in directory
- **Find File**: Find file by name
- **Create File**: Create new file
- **Delete File**: Delete file
- **File Info**: Get file information

#### Implementation
- Use SD card driver for storage
- Use file system interface
- Handle file system errors
- Provide consistent API

### 4. I/O Services

#### Console I/O
- **Print**: Print string to console
- **Read**: Read string from console
- **Character I/O**: Read/write single characters
- **Formatting**: Format output (optional)

#### Graphics I/O
- **Graphics Mode**: Set graphics mode
- **Draw Pixel**: Draw pixel at (x, y)
- **Draw Line**: Draw line
- **Draw Rectangle**: Draw rectangle
- **Text Output**: Display text

#### Sound I/O
- **Play Tone**: Play tone at frequency
- **Play Music**: Play music sequence
- **Play Sound**: Play sound effect
- **Volume Control**: Set volume

#### Implementation
- Use device drivers for hardware access
- Provide high-level API
- Handle device errors
- Abstract hardware details

### 5. Memory Services

#### Memory Allocation
- **Allocate**: Allocate memory block
- **Free**: Free memory block
- **Reallocate**: Reallocate memory block
- **Memory Info**: Get memory information

#### Memory Management
- **Heap Management**: Manage heap memory
- **Memory Map**: Track memory usage
- **Memory Protection**: Protect critical regions
- **Memory Statistics**: Track memory usage

#### Implementation
- Implement heap allocator
- Track allocated blocks
- Handle memory fragmentation
- Provide memory API

### 6. System Information Services

#### System Status
- **Get System Info**: Get system information
- **Get Memory Info**: Get memory information
- **Get Device Status**: Get device status
- **Get Version**: Get system version

#### Device Status
- **Video Status**: Get video chip status
- **Audio Status**: Get audio chip status
- **Input Status**: Get input device status
- **Storage Status**: Get storage device status

#### Implementation
- Query system components
- Aggregate status information
- Provide status API
- Handle status errors

### 7. Program Management Services

#### Program Loading
- **Load Program**: Load program from storage
- **Program Info**: Get program information
- **Program Verification**: Verify program integrity

#### Program Execution
- **Execute Program**: Execute loaded program
- **Program Control**: Control program execution
- **Program Termination**: Handle program termination

#### Implementation
- Use boot loader for program loading
- Manage program execution
- Handle program errors
- Provide program API

---

## Week 23: Interrupt Handlers

### 1. Interrupt Overview

**Interrupts** allow:
- **Real-Time Response**: Respond to events immediately
- **Efficient I/O**: Handle I/O without polling
- **Multitasking**: Support multiple tasks (advanced)

**Interrupt Types**:
- **IRQ**: Interrupt Request (maskable)
- **NMI**: Non-Maskable Interrupt
- **Software Interrupts**: BRK instruction

### 2. Interrupt Vector Table

#### Vector Table Setup
- **Vector Locations**: Interrupt vectors at specific addresses
- **Vector Table**: Table of interrupt handler addresses
- **Initialization**: Set up vector table at boot
- **Vector Updates**: Update vectors as needed

#### Vector Organization
- **Reset Vector**: System reset handler
- **IRQ Vector**: IRQ interrupt handler
- **NMI Vector**: NMI interrupt handler
- **BRK Vector**: BRK instruction handler

### 3. Timer Interrupts

#### Timer Hardware
- **VIA Timer**: VIA chip timer (if available)
- **Timer Modes**: One-shot, continuous
- **Timer Frequency**: Configurable frequency
- **Timer Interrupt**: Generate interrupt on timer expiry

#### Timer Interrupt Handler
- **Handler Function**: Timer interrupt handler
- **System Clock**: Update system clock
- **Task Scheduling**: Support task scheduling (if implemented)
- **Event Timing**: Support timed events

#### Implementation
- Configure timer hardware
- Set up timer interrupt
- Implement timer handler
- Test timer interrupts

### 4. I/O Interrupts

#### Keyboard Interrupts
- **Interrupt on Key Press**: Generate interrupt when key pressed
- **Key Processing**: Process key in interrupt handler
- **Key Buffer**: Add key to buffer
- **Wake Application**: Wake waiting application

#### Serial Interrupts
- **Receive Interrupt**: Interrupt on data received
- **Transmit Interrupt**: Interrupt on transmit ready
- **Data Processing**: Process data in interrupt handler
- **Buffer Management**: Manage receive/transmit buffers

#### Implementation
- Configure I/O interrupts
- Set up interrupt handlers
- Process interrupts
- Test I/O interrupts

### 5. Interrupt Management

#### Interrupt Enable/Disable
- **Enable Interrupts**: Enable specific interrupts
- **Disable Interrupts**: Disable interrupts
- **Interrupt Mask**: Control interrupt mask
- **Critical Sections**: Disable interrupts in critical sections

#### Interrupt Priority
- **Priority Levels**: Assign priority to interrupts
- **Priority Handling**: Handle interrupts by priority
- **Nested Interrupts**: Support nested interrupts (if needed)

#### Interrupt Status
- **Interrupt Status**: Check interrupt status
- **Pending Interrupts**: Check pending interrupts
- **Interrupt Logging**: Log interrupt events (for debugging)

### 6. Interrupt Best Practices

#### Handler Design
- **Keep Handlers Short**: Minimize handler execution time
- **Save Registers**: Save all registers in handler
- **Restore Registers**: Restore registers before return
- **Avoid Blocking**: Don't block in interrupt handler

#### Error Handling
- **Handle Errors**: Handle errors in interrupt handler
- **Error Reporting**: Report errors appropriately
- **Recovery**: Attempt error recovery

#### Testing
- **Test Interrupts**: Test all interrupt types
- **Test Timing**: Test interrupt timing
- **Test Error Cases**: Test error handling

---

## Week 24: System Integration

### 1. Integration Overview

**System Integration** brings together:
- Enhanced Monitor
- Boot Loader
- Device Drivers (Video, Audio, Input, Storage)
- System Services
- Interrupt Handlers
- Memory Management

**Goal**: Create a complete, functional system software stack.

### 2. Boot Sequence

#### System Initialization
1. **Hardware Reset**: System resets
2. **Vector Table**: Set up interrupt vectors
3. **Hardware Init**: Initialize all hardware
4. **Driver Init**: Initialize all drivers
5. **Service Init**: Initialize system services
6. **Monitor Start**: Start monitor program
7. **Ready**: System ready for use

#### Initialization Order
- **Critical First**: Initialize critical components first
- **Dependencies**: Initialize components in dependency order
- **Error Handling**: Handle initialization errors
- **Status Reporting**: Report initialization status

### 3. Component Integration

#### Monitor Integration
- **Monitor Commands**: Add commands for all services
- **Driver Access**: Monitor can access drivers
- **Service Access**: Monitor can use services
- **Debugging**: Monitor supports debugging all components

#### Boot Loader Integration
- **Driver Loading**: Load drivers from SD card
- **Service Loading**: Load services from SD card
- **Program Loading**: Load programs using services
- **Error Handling**: Handle loading errors

#### Driver Integration
- **Service Access**: Drivers accessible via services
- **Monitor Access**: Drivers accessible via monitor
- **Application Access**: Drivers accessible via API
- **Error Handling**: Consistent error handling

### 4. System Testing

#### Unit Testing
- **Component Tests**: Test each component individually
- **Function Tests**: Test each function
- **Error Tests**: Test error handling
- **Integration Tests**: Test component interactions

#### System Testing
- **Boot Test**: Test system boot sequence
- **Functionality Test**: Test all system functions
- **Stress Test**: Test under load
- **Error Test**: Test error handling

#### Performance Testing
- **Response Time**: Measure response times
- **Throughput**: Measure throughput
- **Resource Usage**: Measure resource usage
- **Optimization**: Optimize if needed

### 5. System Documentation

#### User Documentation
- **User Manual**: How to use the system
- **Command Reference**: Monitor command reference
- **API Reference**: System services API reference
- **Examples**: Usage examples

#### Technical Documentation
- **Architecture**: System architecture
- **Component Design**: Component designs
- **Memory Map**: System memory map
- **Interrupt Map**: Interrupt vector map

#### Developer Documentation
- **Development Guide**: How to develop for system
- **Driver Development**: How to write drivers
- **Service Development**: How to add services
- **Debugging Guide**: How to debug system

### 6. System Demonstration

#### Demonstration Requirements
- **Complete System**: All components working
- **Program Loading**: Load program from SD card
- **Program Execution**: Execute program successfully
- **Graphics/Sound**: Demonstrate graphics and sound
- **Input Handling**: Demonstrate input handling

#### Demonstration Scenarios
- **Basic Demo**: Basic system functionality
- **Graphics Demo**: Graphics capabilities
- **Sound Demo**: Sound capabilities
- **Game Demo**: Simple game (if time permits)

---

## Memory Management

### 1. Heap Allocator

#### Allocation Algorithm
- **First Fit**: Allocate first suitable block
- **Best Fit**: Allocate best suitable block
- **Free List**: Maintain free block list
- **Coalescing**: Coalesce adjacent free blocks

#### Implementation
- **Block Header**: Store block metadata
- **Free List**: Maintain free block list
- **Allocation**: Find and allocate block
- **Deallocation**: Free and coalesce blocks

### 2. Memory Map

#### Memory Regions
- **Monitor**: Monitor program region
- **OS**: Operating system region
- **Drivers**: Driver code region
- **Services**: Service code region
- **Heap**: Heap memory region
- **Stack**: Stack memory region
- **User Programs**: User program region

#### Memory Tracking
- **Region Tracking**: Track memory regions
- **Usage Tracking**: Track memory usage
- **Protection**: Protect critical regions
- **Statistics**: Track memory statistics

### 3. Memory Protection

#### Protection Mechanisms
- **Region Protection**: Protect critical regions
- **Access Control**: Control memory access
- **Bounds Checking**: Check memory bounds
- **Error Detection**: Detect memory errors

#### Implementation
- **Protection Flags**: Set protection flags
- **Access Checks**: Check access permissions
- **Error Handling**: Handle protection violations

---

## Learning Outcomes

After completing this block, students will:

1. **System Services**:
   - Design system services API
   - Implement file system services
   - Implement I/O services
   - Implement memory services
   - Implement system information services

2. **Interrupt Handlers**:
   - Set up interrupt vector table
   - Implement timer interrupts
   - Implement I/O interrupts
   - Manage interrupts

3. **Memory Management**:
   - Implement heap allocator
   - Manage memory map
   - Protect critical memory regions

4. **System Integration**:
   - Integrate all system components
   - Test complete system
   - Document complete system
   - Demonstrate complete system

---

## Next Steps

After completing system services and integration, students have a complete, functional 16-bit computer system with full software stack. This represents the culmination of the 6-year curriculum journey.

---

*System services and integration bring together all components into a complete, functional system*
