# Week 16-18: Control Unit Integration - Theory

## Learning Objectives

By the end of this week-block, students will:
- Integrate control unit with data path
- Implement fetch-decode-execute cycle
- Test instruction execution
- Debug CPU operation
- Verify complete CPU functionality

## Prerequisites

- Completed Weeks 13-15 (Microcode ROM)
- Complete data path (Term 1)
- Complete control unit components (Weeks 10-15)
- Understanding of CPU operation

## Key Concepts

### 1. Complete CPU Architecture

**SAP-1 CPU components**:
- **Data Path**: Registers, ALU, Memory, Buses
- **Control Unit**: PC, IR, Microcode ROM, Control Logic
- **Clock**: Synchronizes all operations
- **Output**: Display results

**Component integration**:
- All components connected
- Control signals coordinate operations
- Clock synchronizes timing
- Complete system works together

### 2. Fetch-Decode-Execute Cycle

**The CPU cycle**:
1. **Fetch**: Get instruction from memory
2. **Decode**: Determine what instruction is
3. **Execute**: Perform instruction operation
4. **Repeat**: Fetch next instruction

**Fetch phase**:
- PC outputs address to MAR
- Memory outputs instruction
- Instruction loaded into IR
- PC increments

**Decode phase**:
- IR opcode addresses microcode
- Microcode sequence selected
- Ready for execution

**Execute phase**:
- Microcode generates control signals
- CPU components perform operation
- Result stored or output
- Instruction complete

### 3. Control Unit Integration

**Connecting control to data path**:
- Microcode outputs → control signals
- Control signals → component enables
- Components respond to signals
- Data flows through path

**Signal coordination**:
- Only appropriate signals active
- Signals sequenced correctly
- Timing coordinated by clock
- No conflicts or races

### 4. Instruction Execution Examples

**LDA (Load A) execution**:
1. Fetch: PC→MAR, Memory→IR, PC++
2. Decode: IR opcode → microcode
3. Execute:
   - Step 0: PC→MAR (fetch operand address)
   - Step 1: Memory→IR (get address)
   - Step 2: (decode operand)
   - Step 3: PC→MAR (fetch data)
   - Step 4: Memory→A (load data)
   - Complete

**ADD (Add) execution**:
1. Fetch: PC→MAR, Memory→IR, PC++
2. Decode: IR opcode → microcode
3. Execute:
   - Step 0: PC→MAR (fetch operand address)
   - Step 1: Memory→B (load operand)
   - Step 2: A, B→ALU (add)
   - Step 3: ALU→A (store result)
   - Complete

### 5. Clock and Timing

**Clock function**:
- Synchronizes all operations
- Advances microstep counter
- Coordinates signal changes
- Controls execution speed

**Clock considerations**:
- Must be stable
- Speed appropriate for system
- Single-step capability for debugging
- Run/halt control

**Timing requirements**:
- Signals must be stable
- Setup/hold times met
- Propagation delays accounted for
- Clock period sufficient

### 6. CPU Testing

**Test strategy**:
- Start with simple instructions
- Test each instruction type
- Test instruction sequences
- Test complete programs
- Verify all operations

**Test programs**:
- Simple: Load and output
- Arithmetic: Add two numbers
- Control: Conditional operations
- Complex: Multi-step programs

### 7. Debugging the CPU

**Debugging tools**:
- Single-step mode
- Logic analyzer
- LEDs on control signals
- LEDs on data/address buses
- Oscilloscope

**Debugging process**:
- Observe behavior
- Check control signals
- Check data flow
- Verify timing
- Fix issues
- Retest

**Common issues**:
- Wrong control signals
- Timing problems
- Bus conflicts
- Component failures
- Microcode errors

### 8. Complete CPU Operation

**Running a program**:
1. Load program into memory
2. Reset CPU (PC = 0)
3. Start clock
4. CPU fetches first instruction
5. CPU executes instruction
6. CPU fetches next instruction
7. Repeat until HLT

**Program example**:
```
Address  Instruction  Meaning
0x0      LDA 0xE     Load A from address 14
0x1      ADD 0xF     Add value from address 15
0x2      OUT         Output result
0x3      HLT         Halt
...
0xE      [data]      Data value 28
0xF      [data]      Data value 14
```

**Expected result**: Output displays 42 (28 + 14)

## Mathematical Foundations

### Instruction Cycle Time

**Cycle time** = Fetch time + Execute time
- Fetch: ~3-4 clock cycles
- Execute: Depends on instruction (3-6 cycles)
- Total: ~6-10 cycles per instruction

### Program Execution

**Program length**: Limited by memory (16 bytes for SAP-1)
- Can store multiple instructions
- Can store data
- Enough for learning
- Can be expanded

## Common Misconceptions

1. **"CPU is complex"**
   - Clarify: Built from simple components
   - Show how pieces fit together

2. **"Microcode is magic"**
   - Clarify: Simple lookup table
   - Show how it works

3. **"CPU is fast"**
   - Clarify: Our CPU is slow (for learning)
   - Show clock speed vs. real CPUs

## Connections to Term 1

- **Data Path**: Control unit uses data path
- **All Components**: Control coordinates all
- **Integration**: Complete system together

## Connections to Term 3

- **Programming**: Will write programs for CPU
- **Debugging**: Will debug programs
- **System Use**: Will use CPU for projects

## Next Steps

After integrating control unit, students will:
- Test complete CPU (Term 3)
- Write and run programs
- Debug programs
- Complete SAP-1 project

---

*Control unit integration creates a working CPU*
