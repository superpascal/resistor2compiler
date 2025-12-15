# Year 4: PCB Fabrication Guide - System Enhancement Module Conversion

## Overview

This guide supports the integration of DIY PCB fabrication into Year 4, converting 8-bit system enhancement modules to production-quality PCBs. Students build enhancement modules on breadboards first, then convert them to professional-quality DIY PCBs.

**Core Learning**: Enhanced system works but needs better reliability → Professional-quality DIY PCBs provide production-grade results.

---

## When to Introduce

**Recommended Timing**: 
- **Term 1, Weeks 7-9** (after Memory Expansion breadboard work)
- **Term 2, Weeks 22-24** (after I/O Subsystems breadboard work)

**Rationale**:
- Students have enhanced 8-bit system on breadboards
- System is getting complex, needs better reliability
- Preparation for 16-bit system (professional manufacturing in Year 6)
- Students ready for professional-quality DIY results

---

## Modules to Convert

### Module 1: Memory Expansion Module (Term 1, after Weeks 4-6)

**Breadboard Circuit**: Memory expansion for 8-bit system

**Learning Objectives**:
- Build memory expansion on breadboard
- Test memory operations in enhanced system
- Convert memory expansion to PCB
- Use PCB module in enhanced system
- Apply professional finishing (silk screening)

**Time Required**: 4-5 weeks
- Week 1: Breadboard module build and test
- Week 2: PCB design (more complex)
- Week 3: PCB fabrication (toner transfer or UV photoresist)
- Week 4: Silk screening and migration
- Week 5: Integration, testing, and comparison

**Materials**:
- Memory chips (RAM, EEPROM)
- Address decoding logic
- Supporting components
- Breadboard and jumper wires
- Copper-clad board
- PCB fabrication materials
- Silk screen materials
- UV photoresist materials (optional)

---

### Module 2: I/O Interface Module (Term 2, after Weeks 19-21)

**Breadboard Circuit**: I/O interface for 8-bit system

**Learning Objectives**:
- Build I/O interface on breadboard
- Test I/O operations in enhanced system
- Convert I/O interface to PCB
- Integrate PCB module
- Professional finishing

**Time Required**: 4-5 weeks

**Materials**:
- I/O chips (VIA, ACIA, or similar)
- Supporting logic
- Breadboard and jumper wires
- PCB materials
- Silk screen materials

---

### Module 3: Video Interface Module (Term 2, after Weeks 22-24) - Optional

**Breadboard Circuit**: Simple video interface for 8-bit system

**Learning Objectives**:
- Build video interface on breadboard
- Test video output
- Convert to PCB
- Professional finishing

**Time Required**: 4-5 weeks

**Materials**:
- Video interface components
- Supporting logic
- Breadboard and jumper wires
- PCB materials

---

### Module 4: Audio Interface Module (Term 2, after Weeks 25-27) - Optional

**Breadboard Circuit**: Simple audio interface for 8-bit system

**Learning Objectives**:
- Build audio interface on breadboard
- Test audio output
- Convert to PCB
- Professional finishing

**Time Required**: 4-5 weeks

**Materials**:
- Audio interface components
- Supporting logic
- Breadboard and jumper wires
- PCB materials

---

## Detailed Workflow: Memory Expansion Module Example

### Week 1: Breadboard Module Build and Test

**Day 1-2: Build Memory Expansion on Breadboard**

**Activities**:
1. **Review Memory Expansion Design**:
   - Review memory expansion requirements
   - Understand address decoding
   - Review component requirements
   - Plan breadboard layout

2. **Build on Breadboard**:
   - Build memory expansion module
   - Connect to enhanced 8-bit system
   - Test memory operations
   - Document connections

**Learning Outcomes**:
- Students understand memory expansion
- Students can build complex module on breadboard
- Students experience complexity (many connections, potential issues)

**Teaching Moment**: "This module has many connections. A PCB would make this much more reliable and professional."

---

**Day 3-4: Test in Enhanced System**

**Activities**:
1. **Integrate with Enhanced System**:
   - Connect memory expansion to 8-bit system
   - Test memory operations
   - Verify address decoding
   - Test with various memory operations

2. **Document Module**:
   - Document all connections
   - Create detailed connection list
   - Take photos
   - Note any issues

**Deliverables**:
- Working memory expansion on breadboard
- Module integrated into enhanced system
- Comprehensive documentation
- Photos

---

### Week 2: Advanced PCB Design

**Day 1-2: Complex PCB Layout**

**Activities**:
1. **Create Advanced PCB Layout**:
   - Use KiCad (recommended for complex designs)
   - Place all components
   - Route complex connections
   - Plan power distribution
   - Add decoupling capacitors
   - Design for manufacturability

2. **Optimize Design**:
   - Minimize trace lengths
   - Avoid signal integrity issues
   - Plan component placement
   - Consider thermal management
   - Optimize routing

3. **Design Silk Screen**:
   - Professional component labels
   - Pin numbers
   - Module identification
   - Warning labels (if needed)
   - Export silk screen layer

**Resources**:
- [Placeholder: YouTube video - Advanced PCB design]
- [Placeholder: YouTube video - Complex module PCB layout]
- KiCad tutorials

**Deliverables**:
- Advanced PCB layout design
- Professional silk screen design
- Design review completed

---

**Day 3-4: Design Review**

**Activities**:
1. **Peer Review**:
   - Review PCB design with peers
   - Check for errors
   - Verify connections
   - Optimize if needed

2. **Instructor Review**:
   - Instructor reviews design
   - Provides feedback
   - Approves for fabrication

3. **Finalize Design**:
   - Make any necessary changes
   - Export final designs
   - Prepare for fabrication

**Deliverables**:
- Reviewed and approved PCB design
- Final design files

---

### Week 3: PCB Fabrication (Advanced Methods)

**Day 1: Method Selection**

**Activities**:
1. **Choose Fabrication Method**:
   - **Option 1**: Toner Transfer (simpler, from Years 2-3)
   - **Option 2**: UV Photoresist (higher quality, optional for advanced students)

2. **Prepare for Selected Method**:
   - Gather materials
   - Set up workspace
   - Review safety protocols

**Method Comparison**:
- **Toner Transfer**: Simpler, adequate quality, familiar
- **UV Photoresist**: Higher quality, finer traces, more complex

---

**Day 2-3: Fabrication**

**Option A: Toner Transfer (Recommended)**
- Follow Year 2-3 process
- Improved technique
- Better results than earlier years

**Option B: UV Photoresist (Advanced)**
1. **Prepare Board**:
   - Apply photoresist (if not pre-coated)
   - Dry photoresist

2. **Expose**:
   - Print design on transparency
   - Align on board
   - Expose to UV light
   - Develop photoresist

3. **Etch**:
   - **Select Etchant**: Ferric chloride (recommended) or ammonium persulfate (alternative)
   - **Ferric Chloride Process**:
     - Prepare 30-40% solution (300-400g per liter)
     - Warm to 40-50°C for faster etching (highly recommended)
     - Continuous agitation required
     - Etching time: 10-30 minutes (warm) or 30-60 minutes (room temp)
     - Monitor progress closely (check every 2-3 minutes)
   - **Ammonium Persulfate Process** (Alternative):
     - Prepare 15-20% solution (150-200g per liter)
     - Warm to 40-50°C (essential for effectiveness)
     - Continuous agitation required
     - Etching time: 5-15 minutes (warm)
   - **See**: `../resources/PRESENSITIZED_PCB_TEACHER_GUIDE.md` for comprehensive etchant guide including ferric chloride, ammonium persulfate, cupric chloride, and sodium persulfate options
   - Strip photoresist (sodium hydroxide stripper or acetone)
   - Clean board thoroughly

**Resources**:
- [Placeholder: YouTube video - UV photoresist method]
- [Placeholder: YouTube video - Advanced PCB etching]
- Year 2-3 guides (reference)

**Deliverables**:
- Etched PCB
- Quality inspection completed

---

**Day 4: Drilling and Preparation**

**Activities**:
1. **Drill Holes**:
   - Drill all component holes
   - Use appropriate bit sizes
   - Verify alignment

2. **Prepare Board**:
   - Clean board thoroughly
   - Inspect for issues
   - Touch up if needed

**Deliverables**:
- Drilled and prepared PCB

---

### Week 4: Professional Finishing and Migration

**Day 1-2: Silk Screening**

**Activities**:
1. **Apply Silk Screen**:
   - **Method 1**: Toner Transfer (simpler)
     - Transfer silk screen design
     - Fill with paint/ink
     - Seal with clear coat
   - **Method 2**: Stencil (more professional)
     - Create stencil
     - Apply paint/ink through stencil
     - Remove stencil
     - Seal with clear coat

2. **Professional Finishing**:
   - Apply clear coat for protection
   - Add any additional labels
   - Final inspection

**Resources**:
- [Placeholder: YouTube video - Professional silk screening]
- [Placeholder: YouTube video - PCB finishing techniques]

**Deliverables**:
- PCB with professional silk screening
- Professional finish applied

---

**Day 3-4: Component Migration**

**Activities**:
1. **Remove Components from Breadboard**:
   - Carefully remove all components
   - Document component values
   - Clean components

2. **Solder to PCB**:
   - Place components on PCB
   - Verify orientations
   - Solder all components
   - Inspect solder joints
   - Test connections

3. **Test PCB Module**:
   - Test module standalone
   - Verify all functions
   - Compare with breadboard

**Deliverables**:
- Completed PCB module
- Test results

---

### Week 5: Integration and Comparison

**Day 1-2: System Integration**

**Activities**:
1. **Integrate PCB Module**:
   - Remove breadboard module
   - Connect PCB module to system
   - Use proper connectors
   - Verify all connections

2. **Test in Enhanced System**:
   - Test memory operations
   - Verify system functionality
   - Test with various operations
   - Stress test

3. **Troubleshooting**:
   - Fix any issues
   - Verify signal integrity
   - Check power distribution

**Deliverables**:
- PCB module integrated into system
- System working with PCB module
- Test results

---

**Day 3-4: Comparison and Documentation**

**Activities**:
1. **Comprehensive Comparison**:
   - Compare breadboard vs PCB module
   - Test reliability
   - Test signal integrity
   - Test professional appearance
   - Document differences

2. **Documentation**:
   - Document complete process
   - Create comparison report
   - Update system documentation
   - Reflect on learning

**Comparison Points**:
- **Reliability**: Which is more reliable?
- **Signal Integrity**: Which has better signals?
- **Professionalism**: Which looks more professional?
- **Maintainability**: Which is easier to maintain?
- **Cost**: Compare costs (time and materials)

**Deliverables**:
- Comprehensive comparison report
- Process documentation
- Updated system documentation
- Reflection on learning

---

## Assessment

### Formative Assessment

**Breadboard Module** (20%):
- Module works correctly
- Integrated into system
- Comprehensive documentation

**PCB Design** (25%):
- Advanced PCB design quality
- Design optimization
- Professional silk screen design
- Design review participation

**PCB Fabrication** (30%):
- Fabrication method selection
- Etching quality
- Drilling accuracy
- Professional finishing
- Safety compliance

**Migration and Integration** (20%):
- Successful migration
- System integration
- Troubleshooting ability
- System functionality

**Documentation and Comparison** (5%):
- Process documentation
- Comparison report
- Reflection quality

### Assessment Criteria

**Excellent (A)**:
- Breadboard module works perfectly
- Advanced PCB design, well-optimized
- Professional fabrication (high quality)
- Professional finishing (silk screen)
- Migration successful, system works perfectly
- Comprehensive comparison showing clear advantages
- Excellent safety compliance

**Good (B)**:
- Breadboard module works
- Good PCB design
- Good fabrication quality
- Good finishing
- Migration mostly successful
- Good comparison report
- Good safety compliance

**Satisfactory (C)**:
- Breadboard module works with issues
- Adequate PCB design
- Adequate fabrication
- Basic finishing
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

**Photoresist Chemicals** (if using):
- Follow manufacturer safety data sheets
- Proper ventilation
- Chemical-resistant gloves
- Eye protection mandatory

### Equipment Safety

**UV Exposure** (if using photoresist):
- UV protection for eyes
- Limited exposure time
- Proper UV source

**Other Equipment**:
- Follow Year 2-3 safety protocols
- Enhanced supervision for advanced methods

---

## Resources

### Professional PCB Design Reference

**RC2014 Backplane Pro GERBER Files** (Reference):
- **Source**: [RC2014 Backplane Pro](https://rc2014.co.uk/backplanes/backplane-pro/)
- **Value**: Professional PCB design files (GERBER) for study and reference
- **Use**: Analyze professional PCB design patterns, multi-module systems, bus isolation, power management
- **When**: When designing enhanced system PCBs, use as reference for professional design standards
- **Reference**: See `../resources/RC2014_BACKPLANE_PRO_ANALYSIS.md` for detailed analysis

**GERBER File Analysis for Enhanced Systems**:
1. Download RC2014 Backplane Pro GERBER files
2. Study multi-module system design (12 slots)
3. Analyze bus isolation techniques (between slots 3-4 and 10-11)
4. Study power management design (regulator, distribution, decoupling)
5. Analyze component placement for multi-module systems
6. Study professional finishing (silk screening, component labeling)
7. Compare with enhanced system PCB designs
8. Apply professional patterns to enhanced system modules

**Educational Value**:
- ✅ Multi-module system design example
- ✅ Bus isolation techniques (relevant for enhanced systems)
- ✅ Power management design (regulator, distribution)
- ✅ Professional component placement
- ✅ Professional PCB finishing standards

**Note**: RC2014 uses different CPU (Z80) and architecture, so use as **design reference only**, not as hardware to build. Focus on PCB design patterns and multi-module architecture, not system architecture.

### PCB Fabrication Videos (Placeholders - to be added)

- [Placeholder: Advanced PCB fabrication]
- [Placeholder: UV photoresist method]
- [Placeholder: Professional silk screening]
- [Placeholder: Complex module conversion]
- [Placeholder: System integration with PCB modules]

### Books

**Circuit Theory and Design**:
- **"Fundamentals of Electric Circuits"** (ISE Edition) - ISBN-13: 978-1260570793
  - [Amazon: Fundamentals of Electric Circuits](https://www.amazon.com/ISE-Fundamentals-of-Electric-Circuits/dp/1260570797)
  - **Useful for**: Home PCB workshops, understanding circuit fundamentals, advanced circuit design principles
  - **Value**: Comprehensive circuit theory and analysis, essential for designing enhanced system module circuits before PCB fabrication

**PCB Fabrication**:
- "Build Your Own Printed Circuit Board" by Al Williams
- PCB fabrication tutorials (online)

### Software
- **KiCad**: Recommended for complex designs
- **Fritzing**: Alternative for simpler designs

### Materials

#### Presensitized PCB Boards (Recommended for Year 4)

**Professional Quality**: Presensitized boards are recommended for Year 4 to achieve production-quality results for enhanced system modules.

**Presensitized PCB Board Suppliers**:
- **[Amazon: Presensitized PCB Board](https://www.amazon.com/dp/B08257VSVX)** - Single-sided presensitized board
- **[Parts Express: Presensitized Board](https://www.amazon.com/Parts-Express-Presensitized-Board-Single/dp/B0002BGBM8/)** - Single-sided presensitized board
- **[Fortex Engineering: Presensitized FR4 Board](https://www.fortex.co.uk/product/pcb-laminate-presensitized-board-single-sided/)** - High-quality FR4 presensitized board (UK supplier)

**Additional Materials for Presensitized Method**:
- **UV Exposure Unit**: UV light source (DIY UV box or commercial unit)
- **Developer Solution**: Chemical developer (sodium carbonate solution)
- **Positive Artwork**: Transparent film with circuit pattern (high-resolution)
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
- Professional finishing materials
- PCB drill and bits
- PCB drill and bits
- Safety equipment

---

## Troubleshooting

### Common Issues

**Design Complexity**:
- **Issue**: Design too complex for single-sided PCB
- **Solution**: Simplify design, use jumpers, or consider two-sided approach

**Signal Integrity**:
- **Issue**: Signals not working correctly
- **Solution**: Check power distribution, add decoupling capacitors, verify routing

**Professional Finishing**:
- **Issue**: Silk screen not professional
- **Solution**: Practice technique, use better materials, refine process

---

## Extension Activities

### For Advanced Students

1. **UV Photoresist Method**:
   - Learn and use UV photoresist
   - Achieve higher quality results
   - Compare with toner transfer

2. **Multiple Modules**:
   - Convert multiple modules to PCBs
   - Create mostly-PCB enhanced system

3. **Advanced Finishing**:
   - Professional silk screening
   - Multiple colors
   - Advanced labeling

---

## Integration with Curriculum

### Links to Year 4 Topics

- **Memory Expansion**: PCB for memory expansion module
- **I/O Subsystems**: PCB for I/O interface
- **System Enhancement**: PCBs make enhancements reliable

### Preparation for Year 6

- Students understand professional-quality DIY PCBs
- Ready to appreciate professional manufacturing
- Understand value of professional results

---

## Next Steps

After completing Year 4 PCB projects, students are ready for:
- **Year 6**: Professional manufacturing (appreciate value after DIY experience)
- Students understand: DIY methods (Years 2-4) → Professional manufacturing (Year 6)

---

**Document Created**: 2025-12-15  
**Purpose**: Guide for Year 4 system enhancement module breadboard → PCB conversion
