# Chapter 6: Control Unit Integration

## Introduction

Control unit integration brings all components together into a working CPU. This chapter explains the fetch-decode-execute cycle and complete CPU operation.

## Complete CPU Architecture

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

## Fetch-Decode-Execute Cycle

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

## Instruction Execution Examples

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

## CPU Testing

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

## Practice Questions

1. What is the fetch-decode-execute cycle?
2. How do all components work together?
3. How do we test the CPU?
4. What if the CPU doesn't work?
5. How does this compare to real CPUs?

## Key Takeaways

- CPU has three-phase cycle
- All components work together
- Microcode automates control
- Testing verifies operation
- This is how real CPUs work

---

*Control unit integration creates a working CPU*
