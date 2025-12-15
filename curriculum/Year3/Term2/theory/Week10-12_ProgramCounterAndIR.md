# Week 10-12: Program Counter and Instruction Register - Theory

## Learning Objectives

By the end of this week-block, students will:
- Understand the Program Counter's role
- Build the Program Counter (PC)
- Understand the Instruction Register's role
- Build the Instruction Register (IR)
- Understand instruction format
- Understand instruction fetching

## Prerequisites

- Completed Term 1 (Data Path)
- Understanding of counters (Year 1-2)
- Understanding of registers (Year 1-2)
- Understanding of control signals

## Key Concepts

### 1. The Program Counter (PC)

**PC function**:
- Holds address of next instruction to execute
- Increments after each instruction
- Can be loaded (for jumps)
- Connects to address bus (via MAR)

**PC characteristics**:
- 4-bit for SAP-1 (addresses 0-15)
- Increments automatically
- Can be loaded from bus
- Outputs to MAR

**Why we need PC**:
- CPU needs to know which instruction to fetch
- PC tracks program execution
- Enables sequential execution
- Enables jumps (load new address)

### 2. Building the Program Counter

**PC construction**:
- Use 74HC161 or 74HC163 (4-bit counter)
- Connect to address bus (via MAR)
- Add increment control
- Add load control (for jumps)
- Add reset (start at 0)

**Control signals**:
- **CO** (Counter Out): Enable PC to bus/MAR
- **CE** (Counter Enable): Enable increment
- **CL** (Counter Load): Load from bus (for jumps)
- Clock: Increment on clock edge

**PC operation**:
- Normal: Increment on each clock
- Jump: Load new address from bus
- Reset: Set to 0

### 3. The Instruction Register (IR)

**IR function**:
- Holds current instruction being executed
- Loaded during instruction fetch
- Provides opcode for microcode address
- Provides operand for instruction execution

**IR characteristics**:
- 8-bit for SAP-1 (4-bit opcode + 4-bit operand)
- Loaded from memory
- Opcode used for microcode
- Operand used during execution

**Why we need IR**:
- CPU needs to know what instruction to execute
- IR holds instruction until execution complete
- Opcode selects microcode sequence
- Operand provides instruction data

### 4. Building the Instruction Register

**IR construction**:
- Use 74HC173 (4-bit register) × 2 for 8 bits
- Or use 74HC574 (8-bit register)
- Connect to data bus
- Add control signal (II - Instruction In)

**Control signals**:
- **II** (Instruction In): Load from bus
- Clock: Synchronize loading
- Output: Always available (for decoding)

**IR operation**:
- Load instruction from memory
- Hold instruction during execution
- Provide opcode and operand

### 5. Instruction Format

**SAP-1 instruction format**:
- **Upper 4 bits**: Opcode (operation code)
- **Lower 4 bits**: Operand (data/address)

**Example instructions**:
- LDA 14h: Opcode = 0000, Operand = 1110 (14)
- ADD 15h: Opcode = 0001, Operand = 1111 (15)
- OUT: Opcode = 1110, Operand = 0000
- HLT: Opcode = 1111, Operand = 0000

**Instruction encoding**:
- Each instruction has unique opcode
- Operand provides data or address
- Some instructions don't need operand

### 6. Instruction Fetching

**Fetch sequence**:
1. PC outputs address to MAR (CO, MI)
2. Memory outputs instruction (RO)
3. Instruction loaded into IR (II)
4. PC increments (CE)
5. Ready for decode/execute

**Control signals for fetch**:
- **CO** (Counter Out): PC to MAR
- **MI** (MAR In): Load address
- **RO** (RAM Out): Memory output
- **II** (Instruction In): Load instruction
- **CE** (Counter Enable): Increment PC

**Timing**:
- All signals coordinated
- Clock synchronizes
- Sequence must be correct
- Foundation for automatic execution

### 7. PC and IR Integration

**Complete fetch cycle**:
- PC provides address
- MAR holds address
- Memory provides instruction
- IR holds instruction
- PC increments for next instruction

**Integration with data path**:
- PC connects to MAR
- IR connects to microcode ROM (Term 2, Week 17-20)
- IR operand used during execution
- All components work together

### 8. Testing PC and IR

**Test procedures**:
- Test PC increment
- Test PC load (for jumps)
- Test PC reset
- Test IR loading
- Test instruction fetch
- Verify complete fetch cycle

**Verification**:
- PC increments correctly
- IR loads correctly
- Fetch cycle works
- Ready for microcode (Term 2, Week 17-20)

## Mathematical Foundations

### Address Space

**4-bit PC**: 2^4 = 16 addresses
- Sufficient for learning
- Keeps design simple
- Can demonstrate concepts
- Can be expanded later

### Instruction Encoding

**4-bit opcode**: 2^4 = 16 possible instructions
- Sufficient for basic CPU
- Can implement essential operations
- Room for expansion

## Common Misconceptions

1. **"PC is just a counter"**
   - Clarify: PC tracks program execution
   - Show its role in fetch cycle

2. **"IR is just a register"**
   - Clarify: IR holds instruction being executed
   - Show opcode/operand separation

3. **"Fetch is simple"**
   - Clarify: Requires coordination of multiple components
   - Show signal sequence

## Connections to Term 1

- **Data Path**: PC and IR use data path components
- **Memory**: Fetch reads from memory
- **Buses**: PC and IR use buses
- **Control**: Fetch needs control signals

## Connections to Weeks 17-20

- **Microcode**: IR opcode addresses microcode
- **Control Unit**: PC and IR are part of control unit
- **Execution**: IR operand used during execution
- **Complete CPU**: PC and IR essential for CPU

## Next Steps

After building PC and IR, students will:
- Build microcode ROM system (Weeks 17-20)
- Program microcode for instructions
- Generate control signals automatically
- Complete control unit

---

*PC and IR enable automatic instruction fetching*
