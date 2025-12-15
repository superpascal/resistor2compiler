# Week 10-12: Advanced State Machines and Microcode - Theory

## Learning Objectives

By the end of this week-block, students will:
- Design and build complex state machines
- Understand microcode ROM concepts
- Implement instruction decoding
- Store control sequences in ROM
- Optimize control signal generation

## Prerequisites

- Completed Year 2 Term 1
- Understanding of basic state machines
- Understanding of memory (EEPROM)
- Understanding of control signals

## Key Concepts

### 1. Complex State Machines

**Beyond simple sequencers**:
- Multiple operation types
- Conditional state transitions
- Nested state machines
- State machine optimization

**Design principles**:
- Minimize number of states
- Clear state transitions
- Efficient control signal generation
- Easy to debug and modify

### 2. Microcode ROM Concepts

**What is microcode?**
- Low-level instructions that control CPU operations
- Stored in ROM (Read-Only Memory)
- Each instruction has a microcode sequence
- Microcode generates control signals

**Why use microcode?**
- Flexible: Easy to change instruction behavior
- Organized: All control sequences in one place
- Scalable: Can add new instructions easily
- Professional: How real CPUs work

### 3. Building a Microcode ROM

**Using EEPROM for microcode**:
- EEPROM stores control signal patterns
- Address = instruction + microstep
- Data = control signals for that step
- Multiple EEPROMs for more control signals

**Address formation**:
- Upper bits: Instruction opcode
- Lower bits: Microstep counter
- Example: 4-bit opcode + 2-bit step = 6-bit address

**Data output**:
- Each bit = one control signal
- 8-bit EEPROM = 8 control signals
- Multiple EEPROMs = more signals

### 4. Instruction Decoding

**Instruction format**:
- Opcode: What operation to perform
- Operand: Data for the operation
- Example: LDA 14h (Load A from address 14)

**Decoding process**:
1. Load instruction into Instruction Register (IR)
2. Extract opcode (upper bits)
3. Use opcode to address microcode ROM
4. Execute microcode sequence

**Instruction Register (IR)**:
- Holds current instruction
- Opcode used for microcode address
- Operand used during execution

### 5. Microcode Sequence Example

**LDA (Load A) instruction**:
- Microstep 0: CO (Counter Out), MI (MAR In) - fetch instruction
- Microstep 1: RO (RAM Out), II (IR In) - load instruction
- Microstep 2: (decode - determine it's LDA)
- Microstep 3: CO, MI - fetch data address
- Microstep 4: RO, AI (A In) - load data into A

**Each microstep**:
- Generates specific control signals
- Advances to next microstep
- Completes when instruction done

### 6. Control Signal Optimization

**Reducing signal count**:
- Combine related signals
- Use decoders where appropriate
- Share signals between operations
- Minimize bus conflicts

**Timing optimization**:
- Overlap operations where possible
- Minimize clock cycles
- Reduce setup/hold requirements
- Improve system speed

### 7. Advanced Sequencer Design

**Multi-level sequencers**:
- Main sequencer for instruction cycle
- Sub-sequencers for complex operations
- Nested state machines
- Hierarchical control

**Conditional sequencing**:
- Branch based on flags
- Skip steps conditionally
- Loop operations
- Conditional execution

## Mathematical Foundations

### Address Space Calculation

For microcode ROM:
- **Address bits** = Opcode bits + Microstep bits
- **Example**: 4-bit opcode + 2-bit step = 6-bit address = 64 locations
- **Data bits** = Number of control signals needed

### Control Signal Count

- **Minimum**: One signal per component operation
- **Typical**: 10-20 signals for simple CPU
- **Optimized**: Can reduce with clever design
- **Maximum**: Limited by EEPROM data width

## Common Misconceptions

1. **"Microcode is programming"**: It's more like a lookup table
2. **"More states is better"**: Fewer, well-designed states are better
3. **"Microcode is complex"**: Simple microcode teaches concepts well
4. **"Need many EEPROMs"**: Can start with one or two

## Connections to Term 1

- **State Machines**: Building on basic sequencers
- **Memory**: Using EEPROM for microcode storage
- **Control Signals**: Same signals, now from ROM
- **Sequencers**: More sophisticated versions

## Connections to Year 3

- **SAP-1 Control Unit**: Uses microcode ROM exactly like this
- **Instruction Set**: Microcode defines instruction behavior
- **CPU Design**: This is how real CPUs work
- **Program Execution**: Microcode executes instructions

## Next Steps

After understanding microcode, students will:
- Build microcode ROM system
- Program EEPROM with microcode
- Test instruction execution
- Move to address decoding (Weeks 13-15)

---

*Microcode is the bridge between instructions and control signals*
