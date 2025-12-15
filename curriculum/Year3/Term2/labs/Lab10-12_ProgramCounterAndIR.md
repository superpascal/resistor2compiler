# Lab 10-12: Program Counter and Instruction Register

## Lab Overview

In this lab, students will build the Program Counter (PC) and Instruction Register (IR), enabling automatic instruction fetching for the SAP-1 CPU.

## Learning Objectives

- Build the Program Counter (PC)
- Build the Instruction Register (IR)
- Connect PC and IR to system
- Test instruction fetching
- Understand instruction format

## Prerequisites

- Completed Term 1 (Data Path)
- Understanding of counters (Year 1-2)
- Understanding of registers (Year 1-2)
- Understanding of control signals

## Materials

### Components
- 74HC161 or 74HC163 (4-bit counter) for PC
- 74HC173 (4-bit register) × 2 for IR (8-bit)
- Or 74HC574 (8-bit register) for IR
- Logic gates for connections
- LEDs for status display
- Resistors (220Ω for LEDs)

### Tools
- Breadboards
- Multimeter
- Logic probe (optional)

## Safety

- Verify power connections
- Check for shorts
- Use current-limiting resistors

## Lab Sessions

### Session 1: Building the Program Counter (Week 13)

**Objective**: Construct 4-bit Program Counter

**Steps**:
1. Place 74HC161 counter on breadboard
2. Connect power and ground
3. Connect clock input
4. Connect enable for increment
5. Connect load control (for jumps)
6. Connect reset (start at 0)
7. Connect outputs to LEDs
8. Test: Increment, load, reset

**Expected Result**: PC increments correctly, can load and reset

**Troubleshooting**:
- If doesn't increment: Check enable, check clock
- If doesn't load: Check load signal, check data inputs
- If doesn't reset: Check reset circuit

### Session 2: Connecting PC to System (Week 14)

**Objective**: Integrate PC with address bus/MAR

**Steps**:
1. Connect PC outputs to MAR inputs (via tri-state or direct)
2. Add control signal (CO - Counter Out)
3. Test: PC outputs address to MAR
4. Test: MAR loads address from PC
5. Verify address flow
6. Test with memory connection

**Expected Result**: PC can provide addresses to memory via MAR

**Troubleshooting**:
- If address wrong: Check connections, check PC value
- If MAR doesn't load: Check control signal, check timing
- If memory access fails: Check address connections

### Session 3: Building the Instruction Register (Week 15)

**Objective**: Construct 8-bit Instruction Register

**Steps**:
1. Place registers for IR (2× 74HC173 or 1× 74HC574)
2. Connect power and ground
3. Connect data inputs (from bus)
4. Connect clock and enable
5. Connect outputs (for opcode/operand)
6. Add control signal (II - Instruction In)
7. Test: Load instruction, verify storage
8. Test: Extract opcode and operand

**Expected Result**: IR loads and stores instructions correctly

**Troubleshooting**:
- If doesn't load: Check enable, check clock, check bus
- If data wrong: Check connections, verify instruction format
- If opcode wrong: Check bit extraction

### Session 4: Instruction Fetch Testing (Week 16)

**Objective**: Test complete instruction fetch cycle

**Steps**:
1. Connect all components (PC, MAR, Memory, IR)
2. Load test program into memory
3. Reset PC to 0
4. Execute fetch: PC→MAR, Memory→IR, PC++
5. Verify instruction in IR
6. Verify PC incremented
7. Test multiple fetches
8. Document fetch cycle

**Expected Result**: Complete fetch cycle works correctly

**Troubleshooting**:
- If fetch fails: Check each step, verify signals
- If instruction wrong: Check memory contents, check connections
- If PC wrong: Check increment, check reset

## Assessment

### Practical Assessment
- Successfully build PC
- Successfully build IR
- Connect to system correctly
- Test fetch cycle
- Document system

### Lab Report
Students should document:
- PC circuit diagram
- IR circuit diagram
- Fetch cycle procedure
- Test results
- Instruction format understanding

## Extension Activities

- Add jump capability to PC
- Expand PC to 8 bits
- Add instruction decoding logic
- Optimize fetch cycle

## Next Lab

After completing this lab, students will move to microcode ROM system (Lab 17-20).

---

*PC and IR enable automatic instruction fetching*
