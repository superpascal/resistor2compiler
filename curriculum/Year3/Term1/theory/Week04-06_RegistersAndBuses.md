# Week 5-8: Register File and Buses - Theory

## Learning Objectives

By the end of this week-block, students will:
- Build Register A and Register B for SAP-1
- Implement tri-state bus connections
- Build bus control logic
- Understand bus protocols
- Integrate registers with ALU

## Prerequisites

- Completed Weeks 1-4 (Review and ALU)
- Understanding of registers (Year 1-2)
- Understanding of tri-state buffers (Year 1-2)
- Understanding of buses (Year 1-2)

## Key Concepts

### 1. SAP-1 Register File

**SAP-1 registers**:
- **Register A**: Primary accumulator, stores ALU results
- **Register B**: Secondary register, provides ALU input
- **Both**: 4-bit registers, connect to data bus

**Register characteristics**:
- 4-bit width (matches SAP-1 design)
- Can load from bus
- Can output to bus
- Clocked operation
- Clear/reset capability

### 2. Building Register A

**Register A function**:
- Stores intermediate results
- Receives ALU output
- Provides ALU input
- Can output to bus

**Construction**:
- Use 74HC173 (4-bit register with tri-state)
- Or use 74HC574 (8-bit, use 4 bits)
- Connect to data bus
- Add control signals (AI, AO)

**Control signals**:
- **AI** (A In): Load from bus
- **AO** (A Out): Output to bus
- Clock: Synchronize operations

### 3. Building Register B

**Register B function**:
- Provides second ALU operand
- Can load from bus
- Can output to bus
- Works with Register A

**Construction**:
- Same as Register A
- Separate control signals
- Independent operation

**Control signals**:
- **BI** (B In): Load from bus
- **BO** (B Out): Output to bus
- Clock: Synchronize operations

### 4. Tri-State Bus Connections

**Why tri-state?**
- Multiple components share bus
- Only one can drive bus at a time
- Prevents bus conflicts
- Enables data sharing

**Tri-state implementation**:
- Use 74HC125 (quad tri-state buffer)
- Or use 74HC244 (octal tri-state buffer)
- Enable signal controls output
- When disabled, high-impedance (floating)

**Bus protocol**:
- Only enable one output at a time
- All others must be disabled
- Prevents conflicts and damage
- Essential for proper operation

### 5. Bus Control Logic

**Control signal coordination**:
- AI, AO: Register A control
- BI, BO: Register B control
- EO: ALU output enable
- RO: Memory output enable
- Others: Additional components

**Control logic**:
- Ensure only one output enabled
- Coordinate with clock
- Prevent conflicts
- Enable proper sequencing

**Implementation**:
- Use logic gates
- Or use decoder
- Or use microcode (Term 2)
- Must be reliable

### 6. Register-ALU Integration

**Data flow**:
- Register A → ALU input A
- Register B → ALU input B
- ALU result → Bus → Register A

**Operation sequence**:
1. Load A from memory (AI=1)
2. Load B from memory (BI=1)
3. Enable A and B to ALU (AO=1, BO=1)
4. ALU performs operation
5. Enable ALU output (EO=1)
6. Load result into A (AI=1)

**Control coordination**:
- Signals must be sequenced
- Only one bus driver at a time
- Clock synchronizes operations
- Timing is critical

### 7. SAP-1 Bus Architecture

**SAP-1 bus system**:
- **Data Bus**: 8-bit, connects all components
- **Address Bus**: 4-bit, connects MAR to memory
- **Control Bus**: Multiple signals, coordinates operations

**Components on bus**:
- Register A (input/output)
- Register B (input/output)
- ALU (output only)
- Memory (output for read, input for write)
- Output register (input only)

**Bus protocol**:
- Only one output enabled
- All inputs can be enabled simultaneously
- Clock coordinates timing
- Control signals sequence operations

### 8. Testing Register-Bus System

**Test procedures**:
- Test register loading
- Test register output
- Test bus protocol
- Test register-ALU connection
- Test complete data path

**Verification**:
- Load known values
- Verify storage
- Verify output
- Verify ALU connection
- Verify complete operation

## Mathematical Foundations

### Bus Width

**SAP-1 data bus**: 8 bits
- Allows 8-bit data transfer
- Matches instruction width
- Matches memory data width
- Standard for 8-bit CPU

### Register Capacity

**4-bit registers**: 16 possible values (0-15)
- Sufficient for SAP-1 operations
- Matches ALU width
- Keeps design simple
- Can be extended later

## Common Misconceptions

1. **"Registers are just storage"**
   - Clarify: They're active components with control
   - Show input/output capabilities

2. **"Bus is just wires"**
   - Clarify: Bus has protocol, requires coordination
   - Show tri-state control

3. **"Any component can use bus"**
   - Clarify: Only one output at a time
   - Show bus protocol

## Connections to Weeks 1-4

- **ALU**: Registers provide ALU inputs
- **Data Path**: Registers are part of data path
- **Control**: Register control signals needed
- **Integration**: All components work together

## Connections to Weeks 9-12

- **Memory**: Registers load from memory
- **Complete Data Path**: All components integrated
- **SAP-1 Foundation**: Core data path complete

## Next Steps

After building registers and buses, students will:
- Build memory subsystem (Weeks 9-12)
- Integrate all data path components
- Test complete data path
- Prepare for control unit (Term 2)

---

*Registers and buses form the data path foundation*
