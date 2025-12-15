# Chapter 2: PCB Assembly and Testing

## Introduction

PCB assembly transforms designed boards into working hardware. This chapter explains assembly and testing procedures.

## PCB Assembly Overview

**Assembly process**:
1. Inspect PCBs
2. Prepare components
3. Solder components
4. Perform continuity tests
5. Perform smoke tests
6. Test subsystems
7. Document results

**Assembly order**:
- Power supply components first
- Passive components
- ICs last
- Connectors
- Final inspection

## ESD Protection

**ESD risks**:
- Static electricity can damage CMOS chips
- CPU and memory are sensitive
- One zap can destroy a chip
- Chips are limited in supply

**Protection measures**:
- ESD wrist straps
- ESD mats
- Grounded workstations
- Anti-static bags
- Handle chips carefully

## Soldering Techniques

**Through-hole soldering**:
- Most components are through-hole
- DIP ICs in sockets
- Resistors, capacitors
- Connectors
- Standard technique

**Soldering quality**:
- Good fillets
- No cold joints
- No bridges
- Clean appearance
- Proper temperature

## Continuity and Smoke Tests

**Continuity tests**:
- Check power and ground
- Verify no shorts
- Check connections
- Use multimeter
- Before power-up

**Smoke test**:
- Power up without chips
- Check regulator output
- Verify voltage levels
- Check for shorts
- No smoke or heat

## Subsystem Testing

**Testing strategy**:
- Test each subsystem separately
- Unit testing approach
- Verify before integration
- Document all tests
- Fix issues immediately

**CPU board tests**:
- Reset circuit
- Clock generator
- Address decoding
- Basic CPU operation
- Memory access

## Assembly Documentation

**Assembly log**:
- Components installed
- Test results
- Issues encountered
- Fixes applied
- Verification status

## Practice Questions

1. Why ESD protection?
2. How do we solder?
3. What are continuity tests?
4. How do we test subsystems?
5. Why document?

## Key Takeaways

- ESD protection essential
- Good soldering critical
- Test before chips
- Test each subsystem
- Document everything

---

*Assembly and testing ensure reliable hardware before integration*
