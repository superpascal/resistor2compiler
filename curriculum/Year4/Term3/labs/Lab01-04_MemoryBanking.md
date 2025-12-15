# Lab 1-4: Memory and Banking on 65C816

## Lab Overview

In this lab, students will expand the 65C816 system memory beyond 64KB and implement memory banking to access larger address spaces.

## Learning Objectives

- Expand RAM to 128KB or 512KB
- Implement bank switching
- Test memory banking
- Document memory map
- Verify bank isolation

## Prerequisites

- Completed Term 2 (65C816 Prototype)
- Working 65C816 breadboard prototype
- Understanding of 65C816 architecture
- Understanding of address decoding

## Materials

### Components
- Additional SRAM chips (for expansion)
- Bank register latch
- Address decoders
- Logic gates for bank selection
- Decoupling capacitors

### Tools
- Logic analyzer
- Oscilloscope
- Multimeter
- Documentation materials

## Safety

- Verify power capacity for larger memory
- Check for shorts
- Test carefully

## Lab Sessions

### Session 1: Memory Expansion Planning (Week 1)

**Objective**: Plan memory expansion

**Steps**:
1. Review current memory setup
2. Determine expansion size (128KB or 512KB)
3. Plan bank organization
4. Design memory map
5. Plan address decoding
6. List required components
7. Document plan

**Expected Result**: Complete expansion plan

**Troubleshooting**:
- If plan unclear: Simplify, focus on essentials
- If components missing: Research, adjust plan
- If map wrong: Review, revise

### Session 2: Bank Register Implementation (Week 2)

**Objective**: Implement bank switching

**Steps**:
1. Build bank register circuit
2. Connect to address decoding
3. Implement bank selection logic
4. Test bank register
5. Verify bank selection
6. Document implementation
7. Test basic switching

**Expected Result**: Bank switching working

**Troubleshooting**:
- If register doesn't work: Check connections, check logic
- If selection wrong: Check decoding, verify logic
- If timing issues: Check signals, verify timing

### Session 3: Memory Connection and Testing (Week 3)

**Objective**: Connect expanded memory and test

**Steps**:
1. Connect additional SRAM chips
2. Implement address decoding for banks
3. Test each bank individually
4. Write test patterns to different banks
5. Read back and verify
6. Test bank switching
7. Verify bank isolation

**Expected Result**: Expanded memory working with banking

**Troubleshooting**:
- If memory doesn't work: Check connections, check decoding
- If banks conflict: Check isolation, verify decoding
- If data wrong: Check connections, verify memory

### Session 4: Complete Banking System (Week 4)

**Objective**: Complete and verify banking system

**Steps**:
1. Complete memory expansion
2. Test all banks
3. Verify bank switching
4. Test cross-bank access
5. Document memory map
6. Create test programs
7. Verify complete system

**Expected Result**: Complete banking system working

**Troubleshooting**:
- If system fails: Test each component, verify integration
- If banking issues: Review design, check logic
- If issues persist: Debug systematically

## Assessment

### Practical Assessment
- Successfully expand memory
- Implement bank switching
- Test all banks
- Document memory map
- Verify complete system

### Lab Report
Students should document:
- Expansion plan
- Bank register implementation
- Memory connection
- Test results
- Memory map
- System verification

## Extension Activities

- Further memory expansion
- Optimize bank organization
- Advanced banking features
- Help other students

## Next Lab

After completing memory banking, students will move to I/O subsystems (Lab 5-8).

---

*Memory banking enables larger programs and prepares for complete systems*
