# Year 3: PCB Fabrication Guide - SAP-1 Module Conversion

## Overview

This guide supports the integration of DIY PCB fabrication into Year 3, converting SAP-1 breadboard modules to permanent PCBs. Students build SAP-1 modules on breadboards first, then convert key modules to PCBs for reliability.

**Core Learning**: SAP-1 on breadboard is fragile (many wires, connections fail) → PCB modules make it reliable and permanent.

**Reference**: Ben Eater's SAP-1 videos provide excellent guidance for breadboard construction, which students then convert to PCBs.

---

## When to Introduce

**Recommended Timing**: 
- **Term 1, Weeks 7-9** (after Memory Subsystem breadboard build)
- **Term 2, Weeks 13-15** (after Microcode ROM System breadboard build)

**Rationale**:
- Students have built SAP-1 modules on breadboards
- They've experienced breadboard limitations in complex system
- Natural progression: make modules permanent with PCBs
- Reinforces system integration concepts

---

## Modules to Convert

### Module 1: Register Module (Term 1, after Weeks 4-6)

**Breadboard Circuit**: SAP-1 register (A register or B register)

**Learning Objectives**:
- Build register module on breadboard
- Test register operations in SAP-1 system
- Convert register module to PCB
- Migrate components from breadboard to PCB
- Integrate PCB register into SAP-1 system
- Compare: breadboard SAP-1 vs PCB-enhanced SAP-1

**Time Required**: 3-4 weeks
- Week 1: Breadboard module build and test in SAP-1
- Week 2: PCB design and fabrication
- Week 3: Migration and integration
- Week 4: System testing and comparison

**Materials**:
- Register ICs (74LS173 or similar)
- Supporting logic (as per SAP-1 design)
- Breadboard and jumper wires
- Copper-clad board
- PCB fabrication materials
- Silk screen materials (for component labels)

**Ben Eater Reference**: 
- [Placeholder: Ben Eater SAP-1 Register Module video]
- Students watch Ben Eater video for breadboard construction
- Then convert breadboard design to PCB

---

### Module 2: Counter Module (Term 2, after Weeks 10-12)

**Breadboard Circuit**: SAP-1 program counter

**Learning Objectives**:
- Build program counter on breadboard
- Test counting functionality in SAP-1
- Convert counter module to PCB
- Integrate PCB counter into SAP-1 system

**Time Required**: 3-4 weeks

**Materials**:
- Counter ICs (74LS161 or similar)
- Supporting logic
- Breadboard and jumper wires
- PCB materials

**Ben Eater Reference**:
- [Placeholder: Ben Eater SAP-1 Program Counter video]

---

### Module 3: ALU Module (Term 2, after Weeks 13-15)

**Breadboard Circuit**: SAP-1 ALU (from Year 1/2 work)

**Learning Objectives**:
- Build ALU on breadboard (or review existing)
- Test arithmetic operations in SAP-1
- Convert ALU to PCB
- Replace breadboard ALU with PCB

**Time Required**: 3-4 weeks

**Materials**:
- ALU ICs (74LS181 or discrete logic)
- Supporting components
- Breadboard and jumper wires
- PCB materials

**Ben Eater Reference**:
- [Placeholder: Ben Eater SAP-1 ALU video]

---

### Module 4: Memory Interface Module (Term 2, after Weeks 16-18)

**Breadboard Circuit**: SAP-1 memory interface

**Learning Objectives**:
- Build memory interface on breadboard
- Test memory operations in SAP-1
- Convert memory interface to PCB
- Final SAP-1 uses PCB modules

**Time Required**: 3-4 weeks

**Materials**:
- Memory chips (EEPROM or RAM)
- Address decoding logic
- Breadboard and jumper wires
- PCB materials

**Ben Eater Reference**:
- [Placeholder: Ben Eater SAP-1 Memory video]

---

## Detailed Workflow: Register Module Example

### Week 1: Breadboard Module Build and Test

**Day 1-2: Build Register Module on Breadboard**

**Activities**:
1. **Review SAP-1 Register Design**:
   - Watch Ben Eater SAP-1 register video
   - [Placeholder: Ben Eater SAP-1 Register Module video]
   - Understand register circuit
   - Review component requirements

2. **Build on Breadboard**:
   - Build register module following Ben Eater design
   - Connect to SAP-1 system (if other modules ready)
   - Test register operations
   - Document connections

**Learning Outcomes**:
- Students understand register module
- Students can build on breadboard
- Students experience breadboard limitations (wires, connections)

**Teaching Moment**: "Notice how many wires this module needs? Imagine if we had a PCB - all connections would be permanent!"

---

**Day 3-4: Test in SAP-1 System**

**Activities**:
1. **Integrate with SAP-1**:
   - Connect register module to SAP-1 system
   - Test register operations in context
   - Verify register works in fetch-execute cycle

2. **Document Module**:
   - Document all connections
   - Create connection list
   - Take photos
   - Note any issues (loose wires, intermittent connections)

**Deliverables**:
- Working register module on breadboard
- Module integrated into SAP-1
- Connection documentation
- Photos of breadboard module

---

### Week 2: PCB Design and Fabrication

**Day 1: PCB Design**

**Activities**:
1. **Create PCB Layout**:
   - Use Fritzing or KiCad
   - Place all components from breadboard design
   - Route all connections (replace jumper wires with traces)
   - Add power and ground planes
   - Check design rules

2. **Optimize Layout**:
   - Minimize trace lengths
   - Avoid crossing traces (if single-sided, use jumpers)
   - Group related components
   - Plan component placement for easy assembly

3. **Add Silk Screen**:
   - Add component labels
   - Add pin numbers
   - Add module name
   - Export silk screen layer

**Resources**:
- [Placeholder: YouTube video - Module PCB design]
- [Placeholder: YouTube video - SAP-1 module PCB layout]
- Fritzing/KiCad tutorials

**Deliverables**:
- PCB layout design
- Silk screen design
- Printed designs (mirror image for toner transfer)

---

**Day 2-3: PCB Fabrication**

**Activities**:
1. **Toner Transfer** (as per Year 2 process):
   - Prepare copper board
   - Transfer main PCB layer
   - Transfer silk screen layer (separate transfer)

2. **Etching**:
   - **Select Etchant**: Ferric chloride (recommended) or ammonium persulfate (alternative)
   - **Ferric Chloride Process**:
     - Prepare 30-40% solution (300-400g per liter)
     - Warm to 40-50°C for faster etching (optional, but recommended)
     - Continuous agitation required
     - Etching time: 10-30 minutes (warm) or 30-60 minutes (room temp)
   - **Ammonium Persulfate Process** (Alternative):
     - Prepare 15-20% solution (150-200g per liter)
     - Warm to 40-50°C (essential)
     - Continuous agitation required
     - Etching time: 5-15 minutes (warm)
   - **See**: `../resources/PRESENSITIZED_PCB_TEACHER_GUIDE.md` for comprehensive etchant guide
   - Etch PCB
   - Clean board
   - Remove toner/photoresist

3. **Drilling**:
   - Drill all component holes
   - Verify hole alignment

**Resources**:
- [Placeholder: YouTube video - Toner transfer for modules]
- [Placeholder: YouTube video - PCB etching]
- Year 2 PCB fabrication guide (reference)

**Deliverables**:
- Etched and drilled PCB
- Silk screen applied (if using toner transfer method)

---

### Week 3: Migration and Integration

**Day 1: Component Migration**

**Activities**:
1. **Remove Components from Breadboard**:
   - Carefully remove all components
   - Keep track of component values and orientations
   - Clean components

2. **Solder to PCB**:
   - Place components on PCB
   - Verify orientations match design
   - Solder all components
   - Trim leads
   - Inspect solder joints

3. **Test PCB Module**:
   - Test PCB module standalone
   - Verify all connections
   - Test register operations

**Deliverables**:
- Completed PCB module
- Test results

---

**Day 2-3: System Integration**

**Activities**:
1. **Integrate PCB Module into SAP-1**:
   - Remove breadboard module from SAP-1
   - Connect PCB module to SAP-1 system
   - Use appropriate connectors (headers, wires for connections to other modules)

2. **Test in SAP-1 System**:
   - Test register operations in SAP-1
   - Verify fetch-execute cycle works
   - Test with sample programs
   - Compare with breadboard version

3. **Troubleshooting**:
   - Fix any connection issues
   - Verify power connections
   - Check signal integrity

**Deliverables**:
- PCB module integrated into SAP-1
- SAP-1 working with PCB module
- Test results

---

### Week 4: System Testing and Comparison

**Day 1-2: Comprehensive Testing**

**Activities**:
1. **Test SAP-1 with PCB Module**:
   - Run comprehensive test suite
   - Test all register operations
   - Test with various programs
   - Stress test (run for extended period)

2. **Compare with Breadboard**:
   - If possible, compare with breadboard SAP-1
   - Test wire stability (wiggle test)
   - Test reliability (run same program multiple times)
   - Note any differences

**Comparison Points**:
- **Reliability**: Which is more reliable?
- **Wire Stability**: Do connections stay in place?
- **System Stability**: Does system run without issues?
- **Professionalism**: Which looks more professional?
- **Maintainability**: Which is easier to maintain?

---

**Day 3-4: Documentation**

**Activities**:
1. **Document Process**:
   - Document breadboard → PCB workflow
   - Note design decisions
   - Document any issues and solutions

2. **Create Comparison Report**:
   - Compare breadboard vs PCB module
   - Document advantages of PCB
   - Note any disadvantages
   - Reflect on learning

3. **Update SAP-1 Documentation**:
   - Update SAP-1 documentation with PCB module
   - Note which modules are PCB vs breadboard
   - Plan for future module conversions

**Deliverables**:
- Process documentation
- Comparison report
- Updated SAP-1 documentation
- Reflection on learning

---

## Assessment

### Formative Assessment

**Breadboard Module** (25%):
- Module works correctly on breadboard
- Integrated into SAP-1 successfully
- Proper documentation

**PCB Fabrication** (35%):
- PCB design quality
- Etching and drilling quality
- Silk screening quality (if applicable)
- Safety compliance

**Migration and Integration** (30%):
- Successful component migration
- PCB module works in SAP-1
- System integration successful
- Troubleshooting ability

**Documentation and Comparison** (10%):
- Process documentation
- Comparison report quality
- Reflection on learning

### Assessment Criteria

**Excellent (A)**:
- Breadboard module works perfectly in SAP-1
- PCB design is clean, well-routed, optimized
- Etching is perfect, no issues
- Migration successful, PCB module works in SAP-1
- Comprehensive comparison showing clear advantages
- Excellent safety compliance

**Good (B)**:
- Breadboard module works with minor issues
- PCB design is adequate
- Etching has minor issues (fixed)
- Migration mostly successful
- Good comparison report
- Good safety compliance

**Satisfactory (C)**:
- Breadboard module works but has issues
- PCB design has problems
- Etching has issues (some fixed)
- Migration partially successful
- Basic comparison report
- Adequate safety compliance

---

## Safety Protocols

### Chemical Safety

**Ferric Chloride**:
- **MANDATORY**: Gloves and safety goggles
- Well-ventilated area
- No skin contact
- Neutralize before disposal
- Store properly

**Acetone**:
- Flammable - no open flames
- Well-ventilated area
- Avoid inhalation

### Equipment Safety

**Iron (Toner Transfer)**:
- Temperature-controlled
- Heat-resistant surface
- Avoid burns

**Drilling**:
- Eye protection mandatory
- Secure board
- Supervised use

---

## Resources

### Professional PCB Design Reference

**RC2014 Backplane Pro GERBER Files** (Reference):
- **Source**: [RC2014 Backplane Pro](https://rc2014.co.uk/backplanes/backplane-pro/)
- **Value**: Professional PCB design files (GERBER) for study and reference
- **Use**: Analyze professional PCB design patterns, bus architecture, component placement
- **When**: When designing SAP-1 module PCBs, use as reference for professional design standards
- **Reference**: See `../resources/RC2014_BACKPLANE_PRO_ANALYSIS.md` for detailed analysis

**GERBER File Analysis for SAP-1 Modules**:
1. Download RC2014 Backplane Pro GERBER files
2. Study bus architecture design (40-pin bus)
3. Analyze component placement patterns
4. Study power distribution design
5. Analyze decoupling capacitor placement
6. Compare with SAP-1 module PCB designs
7. Apply professional patterns to SAP-1 modules

**Educational Value**:
- ✅ Professional bus architecture example (relevant for SAP-1 data/address buses)
- ✅ Component placement patterns
- ✅ Power distribution design
- ✅ Decoupling capacitor placement
- ✅ Professional PCB design standards

**Note**: RC2014 uses different CPU (Z80) and architecture, so use as **design reference only**, not as hardware to build. Focus on PCB design patterns, not system architecture.

### Ben Eater SAP-1 Videos (Placeholders - to be added)

- [Placeholder: Ben Eater SAP-1 Complete Series]
- [Placeholder: Ben Eater SAP-1 Register Module]
- [Placeholder: Ben Eater SAP-1 Program Counter]
- [Placeholder: Ben Eater SAP-1 ALU]
- [Placeholder: Ben Eater SAP-1 Memory]
- [Placeholder: Ben Eater SAP-1 Control Unit]

### PCB Fabrication Videos (Placeholders - to be added)

- [Placeholder: Module PCB design tutorial]
- [Placeholder: SAP-1 module PCB conversion]
- [Placeholder: Module silk screening]
- [Placeholder: System integration with PCB modules]

### Books

**Circuit Theory and Design**:
- **"Fundamentals of Electric Circuits"** (ISE Edition) - ISBN-13: 978-1260570793
  - [Amazon: Fundamentals of Electric Circuits](https://www.amazon.com/ISE-Fundamentals-of-Electric-Circuits/dp/1260570797)
  - **Useful for**: Home PCB workshops, understanding circuit fundamentals, circuit design principles
  - **Value**: Comprehensive circuit theory and analysis, essential for designing SAP-1 module circuits before PCB fabrication

**PCB Fabrication**:
- "Build Your Own Printed Circuit Board" by Al Williams
- PCB fabrication tutorials (online)

### Software
- **Fritzing**: Free, beginner-friendly
- **KiCad**: Free, professional (recommended for modules)

### Materials

#### Presensitized PCB Boards (Recommended for Year 3)

**Higher Quality Results**: Presensitized boards provide better resolution and more reliable results for SAP-1 module PCBs.

**Presensitized PCB Board Suppliers**:
- **[Amazon: Presensitized PCB Board](https://www.amazon.com/dp/B08257VSVX)** - Single-sided presensitized board
- **[Parts Express: Presensitized Board](https://www.amazon.com/Parts-Express-Presensitized-Board-Single/dp/B0002BGBM8/)** - Single-sided presensitized board
- **[Fortex Engineering: Presensitized FR4 Board](https://www.fortex.co.uk/product/pcb-laminate-presensitized-board-single-sided/)** - High-quality FR4 presensitized board (UK supplier)

**Additional Materials for Presensitized Method**:
- **UV Exposure Unit**: UV light source (DIY UV box or commercial unit)
- **Developer Solution**: Chemical developer (sodium carbonate solution)
- **Positive Artwork**: Transparent film with circuit pattern
- **Etchant**: Ferric chloride or similar
- **Stripper**: To remove photoresist after etching

**⚠️ CRITICAL**: Presensitized PCB fabrication involves hazardous chemicals and requires **strict supervision**. See `../resources/PRESENSITIZED_PCB_TEACHER_GUIDE.md` for comprehensive teacher guide covering:
- Complete step-by-step process (UV exposure, development, etching, stripping)
- Chemical handling and safety procedures
- Student supervision guidelines
- Emergency procedures
- Troubleshooting guide

#### Alternative: Toner Transfer Method
- Copper-clad board (plain FR4, single-sided)
- Ferric chloride etchant
- Acetone
- Glossy paper (for toner transfer)
- Silk screen materials
- PCB drill and bits
- Safety equipment

---

## Troubleshooting

### Common Issues

**Module Doesn't Work in SAP-1**:
- **Issue**: PCB module not working when integrated
- **Solution**: Check connections to SAP-1, verify power, check signal integrity

**Connection Problems**:
- **Issue**: Connections to other modules not working
- **Solution**: Use proper connectors, verify pin assignments, check continuity

**Design Issues**:
- **Issue**: PCB layout has problems
- **Solution**: Review design, check connections, verify component placement

---

## Extension Activities

### For Advanced Students

1. **Convert Multiple Modules**:
   - Convert 2-4 modules to PCBs
   - Create mostly-PCB SAP-1 system

2. **Professional Finishing**:
   - Advanced silk screening
   - Multiple layer approach (if skills allow)

3. **System Optimization**:
   - Optimize module layouts
   - Reduce board sizes
   - Improve routing

---

## Integration with Curriculum

### Links to Year 3 Topics

- **SAP-1 Construction**: PCB modules are part of SAP-1 build
- **System Integration**: PCB modules teach system integration
- **Reliability**: PCBs make system more reliable

### Preparation for Year 4

- Students understand module PCBs
- Ready for system enhancement PCBs
- Appreciate value of permanent modules

---

## Next Steps

After completing Year 3 module PCBs, students are ready for:
- **Year 4**: Advanced DIY PCBs for system enhancements (professional finishing)
- **Year 6**: Professional manufacturing (appreciate value after DIY experience)

---

**Document Created**: 2025-12-15  
**Purpose**: Guide for Year 3 SAP-1 module breadboard → PCB conversion
