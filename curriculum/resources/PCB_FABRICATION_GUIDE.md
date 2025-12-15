# Year 2: PCB Fabrication Guide - Breadboard to PCB Conversion

## Overview

This guide supports the integration of DIY PCB fabrication into Year 2, following the iterative breadboard → PCB approach. Students build circuits on breadboards first, then convert them to permanent PCBs.

**Core Learning**: Breadboards are fragile and wires don't stay in place → PCBs create permanent, reliable circuits.

---

## When to Introduce

**Recommended Timing**: Term 2, Weeks 17-20 (I/O Systems) or Term 3, Weeks 25-28 (Complex Program Execution)

**Rationale**:
- Students have built several breadboard circuits by this point
- They've experienced breadboard limitations (wires falling out, fragile connections)
- Ready for hands-on PCB experience
- Fits naturally with I/O or system work

---

## Projects to Convert

### Project 1: Simple Logic Gate Circuit (Recommended First)

**Breadboard Circuit**: AND/OR/NAND gate with LED output

**Learning Objectives**:
- Build simple logic circuit on breadboard
- Test circuit functionality
- Convert breadboard circuit to PCB
- Migrate components from breadboard to PCB
- Compare breadboard vs PCB (reliability, wire stability)

**Time Required**: 3 weeks
- Week 1: Breadboard build and test
- Week 2: PCB design and fabrication
- Week 3: Migration and comparison

**Materials**:
- Logic gate IC (74LS08, 74LS32, or 74LS00)
- LEDs and resistors
- Breadboard and jumper wires
- Copper-clad board
- Ferric chloride etchant
- Acetone
- PCB drill

---

### Project 2: LED Flasher Circuit

**Breadboard Circuit**: 555 timer LED flasher

**Learning Objectives**:
- Build timing circuit on breadboard
- Test timing functionality
- Convert to PCB
- Verify same timing on PCB

**Time Required**: 3 weeks

**Materials**:
- 555 timer IC
- LEDs, resistors, capacitors
- Breadboard and jumper wires
- PCB materials (as above)

---

### Project 3: Basic Counter Circuit

**Breadboard Circuit**: 4-bit counter with display

**Learning Objectives**:
- Build counter circuit on breadboard
- Test counting sequence
- Convert to PCB
- Compare wire stability (breadboard vs PCB)

**Time Required**: 3 weeks

**Materials**:
- Counter IC (74LS93 or similar)
- 7-segment display or LEDs
- Breadboard and jumper wires
- PCB materials (as above)

---

## Detailed Workflow: Project 1 Example

### Week 1: Breadboard Build and Test

**Day 1: Circuit Design and Breadboard Build**

**Activities**:
1. Review logic gate circuit design
2. Build AND gate circuit on breadboard
3. Test circuit with different inputs
4. Document circuit (draw schematic, note component placement)

**Learning Outcomes**:
- Students understand circuit design
- Students can build on breadboard
- Students can test circuit functionality

**Common Issues**:
- Wires falling out during testing
- Loose connections causing intermittent operation
- Difficulty keeping circuit stable

**Teaching Moment**: "Notice how wires keep falling out? This is why we need PCBs!"

---

**Day 2: Testing and Documentation**

**Activities**:
1. Comprehensive testing of breadboard circuit
2. Document all connections
3. Take photos of breadboard circuit
4. Create connection list (what connects to what)

**Deliverables**:
- Working breadboard circuit
- Circuit schematic
- Connection list
- Photos of breadboard circuit
- Test results

---

### Week 2: PCB Design and Fabrication

**Day 1: PCB Design**

**Activities**:
1. **Introduction to PCB Design Software**:
   - Introduce Fritzing or simple CAD tool
   - Show how to create PCB layout
   - Demonstrate component placement
   - Show trace routing

2. **Create PCB Layout**:
   - Place components on PCB layout
   - Route traces between components
   - Add power and ground planes (simple)
   - Check design rules

3. **Export for Fabrication**:
   - Export PCB layout as image (mirror image for toner transfer)
   - Verify scale (1:1)
   - Print on glossy paper

**Resources**:
- Fritzing tutorial
- [Placeholder: YouTube video - PCB design basics]
- [Placeholder: YouTube video - Fritzing tutorial]

**Deliverables**:
- PCB layout design
- Printed PCB design (mirror image)

---

**Day 2: Toner Transfer**

**Activities**:
1. **Prepare Copper Board**:
   - Cut copper-clad board to size
   - Clean copper surface with fine sandpaper
   - Clean with isopropyl alcohol

2. **Toner Transfer**:
   - Place printed design face-down on copper
   - Apply heat with iron (150-180°C)
   - Apply even pressure for 5-10 minutes
   - Cool board
   - Soak in warm water
   - Gently peel paper, leaving toner on copper

3. **Inspect Transfer**:
   - Check toner transfer quality
   - Touch up any gaps with permanent marker
   - Verify all traces transferred

**Safety**:
- Wear heat-resistant gloves
- Work in well-ventilated area
- Use iron on heat-resistant surface

**Resources**:
- [Placeholder: YouTube video - Toner transfer method]
- [Placeholder: YouTube video - PCB etching tutorial]

**Deliverables**:
- Copper board with toner transfer
- Inspection notes

---

**Day 3: Etching**

**Activities**:
1. **Prepare Etchant**:
   - Set up etching station (well-ventilated)
   - Prepare ferric chloride solution
   - Ensure safety equipment available

2. **Etch Board**:
   - Submerge board in etchant
   - Agitate occasionally
   - Monitor etching progress (10-20 minutes)
   - Remove when unwanted copper dissolved

3. **Clean Board**:
   - Rinse board thoroughly with water
   - Remove toner with acetone
   - Inspect traces
   - Touch up any issues

**Safety**:
- **MANDATORY**: Gloves and safety goggles
- Well-ventilated area
- Proper chemical handling
- Neutralize etchant before disposal

**Resources**:
- [Placeholder: YouTube video - PCB etching process]
- Chemical safety guide

**Deliverables**:
- Etched PCB
- Safety compliance checklist

---

**Day 4: Drilling**

**Activities**:
1. **Drill Component Holes**:
   - Mark hole positions
   - Use appropriate drill bit sizes
   - Drill all component holes
   - Clean up burrs

2. **Inspect PCB**:
   - Check all holes drilled correctly
   - Verify trace integrity
   - Check for any shorts or opens

**Safety**:
- Eye protection mandatory
- Secure board during drilling
- Proper drill bit selection

**Deliverables**:
- Drilled PCB ready for components

---

### Week 3: Migration and Comparison

**Day 1: Component Migration**

**Activities**:
1. **Remove Components from Breadboard**:
   - Carefully remove components
   - Keep track of component values
   - Clean components if needed

2. **Solder Components to PCB**:
   - Place components on PCB
   - Solder in place
   - Verify correct orientation
   - Trim leads

3. **Test PCB Circuit**:
   - Test PCB circuit functionality
   - Compare with breadboard behavior
   - Verify identical operation

**Deliverables**:
- Completed PCB with components
- Test results

---

**Day 2: Comparison and Documentation**

**Activities**:
1. **Side-by-Side Comparison**:
   - Test breadboard circuit (if still intact)
   - Test PCB circuit
   - Compare reliability
   - Test wire stability (wiggle test)

2. **Documentation**:
   - Write comparison report
   - Document advantages of PCB
   - Note any issues encountered
   - Create process documentation

**Comparison Points**:
- **Reliability**: Which is more reliable?
- **Wire Stability**: Do wires stay in place?
- **Durability**: Which lasts longer?
- **Professionalism**: Which looks more professional?
- **Portability**: Which is easier to transport?

**Deliverables**:
- Comparison report
- Process documentation
- Reflection on learning

---

## Assessment

### Formative Assessment

**Breadboard Circuit** (30%):
- Circuit works correctly
- Proper documentation
- Testing completed

**PCB Fabrication** (40%):
- PCB design quality
- Etching quality
- Drilling accuracy
- Safety compliance

**Migration and Comparison** (30%):
- Successful component migration
- PCB works identically to breadboard
- Comparison report quality
- Process documentation

### Assessment Criteria

**Excellent (A)**:
- Breadboard circuit works perfectly
- PCB design is clean and well-routed
- Etching is clean with no shorts/opens
- Migration successful, PCB works identically
- Comprehensive comparison report
- Excellent safety compliance

**Good (B)**:
- Breadboard circuit works
- PCB design is adequate
- Etching has minor issues (fixed)
- Migration mostly successful
- Good comparison report
- Good safety compliance

**Satisfactory (C)**:
- Breadboard circuit works with minor issues
- PCB design has some problems
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
- Neutralize before disposal (add baking soda)
- Store in labeled container

**Acetone**:
- Flammable - no open flames
- Well-ventilated area
- Avoid inhalation
- Use in small quantities

### Equipment Safety

**Iron (Toner Transfer)**:
- Temperature-controlled iron
- Heat-resistant surface
- Avoid burns
- Proper ventilation

**Drilling**:
- Eye protection mandatory
- Secure board
- Proper bit selection
- Supervised use

---

## Resources

### Professional PCB Design Reference

**RC2014 Backplane Pro GERBER Files** (Optional Reference):
- **Source**: [RC2014 Backplane Pro](https://rc2014.co.uk/backplanes/backplane-pro/)
- **Value**: Professional PCB design files (GERBER) for study and reference
- **Use**: Analyze professional PCB design patterns, component placement, routing
- **When**: After students create their first PCBs, compare with professional design
- **Reference**: See `../resources/RC2014_BACKPLANE_PRO_ANALYSIS.md` for detailed analysis

**GERBER File Analysis Activities** (Optional):
1. Download RC2014 Backplane Pro GERBER files
2. Open in GERBER viewer (KiCad, GerbView, or online viewer)
3. Analyze PCB layers (copper, solder mask, silkscreen, drill)
4. Study component placement patterns
5. Analyze trace routing
6. Compare with student PCB designs
7. Identify design improvements

**Educational Value**:
- ✅ See professional PCB design standards
- ✅ Learn design patterns (power distribution, decoupling, routing)
- ✅ Understand GERBER file format
- ✅ Compare student designs with professional designs
- ✅ Identify areas for improvement

**Note**: RC2014 uses different CPU (Z80) and architecture, so use as **design reference only**, not as hardware to build.

### Software
- **Fritzing**: Free, beginner-friendly PCB design
- **KiCad**: Free, professional PCB design (optional for advanced students)

### Materials

#### Option 1: Toner Transfer Method (Basic)
- **Copper-clad board** (FR4, single-sided, plain)
- **Ferric chloride etchant**
- **Acetone**
- **Glossy paper** (for toner transfer)
- **PCB drill and bits**
- **Safety equipment** (gloves, goggles)

#### Option 2: Presensitized PCB Method (Advanced/Professional)

**Presensitized PCB Boards** (UV exposure method - more professional):
- **[Amazon: Presensitized PCB Board](https://www.amazon.com/dp/B08257VSVX)** - Single-sided presensitized board
- **[Parts Express: Presensitized Board](https://www.amazon.com/Parts-Express-Presensitized-Board-Single/dp/B0002BGBM8/)** - Single-sided presensitized board
- **[Fortex Engineering: Presensitized FR4 Board](https://www.fortex.co.uk/product/pcb-laminate-presensitized-board-single-sided/)** - High-quality FR4 presensitized board (UK supplier)

**Presensitized Method Advantages**:
- ✅ **Higher Quality**: Better resolution, finer traces
- ✅ **More Professional**: Industry-standard method
- ✅ **Consistent Results**: More reliable than toner transfer
- ✅ **Fine Lines**: Can achieve finer trace widths
- ✅ **Better Contrast**: Easier to inspect during development

**Presensitized Method Requirements**:
- **UV Exposure Unit**: UV light source (can be DIY with UV LEDs)
- **Developer Solution**: Chemical developer (usually sodium carbonate)
- **Positive Artwork**: Transparent film with circuit pattern (printed on transparency or film)
- **Etchant**: Ferric chloride or similar
- **Stripper**: To remove photoresist after etching

**When to Use Presensitized Method**:
- **Year 2 (Advanced)**: For students who want higher quality results
- **Year 3-4**: Recommended for SAP-1 module PCBs (better reliability)
- **Professional Results**: When fine traces or professional finish needed

**Note**: Presensitized boards require UV exposure equipment. This can be a DIY UV exposure box or commercial unit. For Year 2 introduction, toner transfer is simpler and requires less equipment.

### YouTube Videos (Placeholders - to be added)
- [Placeholder: Year 2 PCB fabrication tutorial]
- [Placeholder: Toner transfer method]
- [Placeholder: PCB etching process]
- [Placeholder: Breadboard to PCB migration]
- [Placeholder: PCB design basics]

### Books

**Circuit Theory and Design**:
- **"Fundamentals of Electric Circuits"** (ISE Edition) - ISBN-13: 978-1260570793
  - [Amazon: Fundamentals of Electric Circuits](https://www.amazon.com/ISE-Fundamentals-of-Electric-Circuits/dp/1260570797)
  - **Useful for**: Home PCB workshops, understanding circuit fundamentals, circuit design principles
  - **Value**: Comprehensive circuit theory and analysis, essential for designing circuits before PCB fabrication

**PCB Fabrication**:
- "Build Your Own Printed Circuit Board" by Al Williams
- PCB fabrication tutorials (online)

---

## Troubleshooting

### Common Issues

**Toner Transfer Problems**:
- **Issue**: Toner doesn't transfer completely
- **Solution**: Increase heat, apply more pressure, use better paper

**Etching Problems**:
- **Issue**: Etching too slow
- **Solution**: Agitate more, check etchant concentration, increase temperature

**Drilling Problems**:
- **Issue**: Holes not aligned
- **Solution**: Mark positions carefully, use drill guide

**Circuit Problems**:
- **Issue**: PCB doesn't work like breadboard
- **Solution**: Check connections, verify component placement, test continuity

---

## Extension Activities

### For Advanced Students

1. **Add Silk Screening**:
   - Create component labels
   - Apply silk screen layer
   - Professional finishing

2. **Multiple Circuits**:
   - Convert multiple breadboard circuits
   - Build portfolio of PCBs

3. **Design Improvements**:
   - Optimize PCB layout
   - Reduce board size
   - Improve routing

---

## Integration with Curriculum

### Links to Year 2 Topics

- **Logic Gates**: PCB project reinforces gate concepts
- **I/O Systems**: PCB provides permanent I/O circuit
- **System Integration**: PCB is more reliable for system use

### Preparation for Year 3

- Students understand PCB structure
- Ready for module PCBs in SAP-1
- Appreciate value of permanent circuits

---

## Next Steps

After completing Year 2 PCB projects, students are ready for:
- **Year 3**: SAP-1 module PCBs (more complex, system integration)
- **Year 4**: Advanced DIY PCBs (professional finishing)
- **Year 6**: Professional manufacturing (appreciate value after DIY experience)

---

**Document Created**: 2025-12-15  
**Purpose**: Guide for Year 2 breadboard → PCB conversion activities
