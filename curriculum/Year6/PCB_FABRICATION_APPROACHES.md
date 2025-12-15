# PCB Fabrication Approaches for the Curriculum

## Overview

This document outlines two approaches to PCB fabrication in the curriculum:
1. **Professional PCB Manufacturing** (Year 6, A-Level) - Using manufacturers like PCBWay
2. **Cottage Industry PCB Production** (Formative Years) - Teaching DIY methods including etching, toner transfer, and silk screening

---

## Approach 1: Professional PCB Manufacturing (Year 6, A-Level)

### When: Year 6 Term 1 (A-Level Students, Age 18)

### Rationale
- **Professional Quality**: Students produce production-quality PCBs suitable for final project
- **Industry Standard**: Experience with professional PCB manufacturing workflow
- **Time Efficiency**: Faster turnaround allows focus on assembly and testing
- **Complex Designs**: Supports complex multi-layer designs needed for 16-bit system
- **Real-World Experience**: Mirrors professional engineering practices

### Process
1. **Design**: Complete PCB schematic and layout in professional CAD software
2. **Design Review**: Peer and instructor review of design
3. **Gerber Generation**: Export Gerber files and drill files
4. **Manufacturer Submission**: Submit to PCBWay or similar manufacturer
5. **Quality Control**: Inspect received PCBs for defects
6. **Assembly**: Populate and solder components

### Learning Outcomes
- Professional PCB design workflow
- Gerber file generation and verification
- Manufacturer communication and ordering
- Quality control and inspection
- Cost estimation and budgeting

### Resources
- PCBWay, JLCPCB, or similar manufacturers
- Professional PCB CAD software (KiCad, Altium, etc.)
- Gerber file viewers
- PCB design review checklists

---

## Approach 2: Cottage Industry PCB Production (Formative Years)

### When: Years 2-4 (Ages 14-16, GCSE Years)

### Rationale
- **Hands-On Learning**: Students understand PCB manufacturing from first principles
- **Cost Effective**: No external manufacturing costs for practice boards
- **Educational Value**: Deep understanding of PCB structure and production
- **Skill Building**: Develops practical skills applicable to prototyping
- **Foundation**: Prepares students for professional manufacturing in Year 6

### Methods

#### Method 1: Toner Transfer and Etching (Primary Method)

**Process**:
1. **Design**: Create PCB layout in CAD software (Fritzing, KiCad, EasyEDA)
2. **Print**: Print design on glossy paper using laser printer (mirror image)
3. **Transfer**: Transfer toner to copper-clad board using heat (iron)
4. **Etch**: Etch board in ferric chloride solution to remove unwanted copper
5. **Clean**: Remove toner with acetone
6. **Drill**: Drill component holes
7. **Silk Screen** (Optional): Apply component labels using toner transfer or stencil

**Materials**:
- Copper-clad board (FR4, single-sided)
- Laser printer and glossy paper
- Household iron
- Ferric chloride etchant
- Acetone
- PCB drill and bits
- Safety equipment (gloves, goggles, ventilation)

**Safety Considerations**:
- Work in well-ventilated area
- Wear protective gloves and goggles
- Handle chemicals carefully
- Proper disposal of etchant (neutralize before disposal)
- Supervised access to chemicals

**Learning Outcomes**:
- Understanding of PCB structure (substrate, copper, solder mask, silk screen)
- Chemical etching process
- Toner transfer technique
- Component hole drilling
- Quality control and troubleshooting

**Best For**: Years 2-3 (simple single-sided boards for logic circuits, small modules)

---

#### Method 2: UV Photoresist Method (Advanced DIY)

**Process**:
1. **Design**: Create PCB layout and print on transparency film
2. **Prepare Board**: Apply photoresist to copper-clad board
3. **Expose**: Expose board to UV light through transparency
4. **Develop**: Develop photoresist to reveal copper pattern
5. **Etch**: Etch board in ferric chloride
6. **Strip**: Remove remaining photoresist
7. **Drill and Finish**: Drill holes and apply finish

**Materials**:
- Copper-clad board with photoresist (pre-coated or apply yourself)
- UV light source (UV LED array or sunlight)
- Transparency film
- Developer solution
- Ferric chloride etchant
- Stripper solution

**Learning Outcomes**:
- Photolithography process
- UV exposure techniques
- Higher resolution than toner transfer
- Professional manufacturing concepts

**Best For**: Year 4 (more complex boards, better quality for 8-bit system modules)

---

#### Method 3: Silk Screening (Component Labels)

**Process**:
1. **Design**: Create silk screen layer in PCB software
2. **Stencil Creation**: Create stencil from vinyl or paper
3. **Positioning**: Secure stencil on PCB
4. **Application**: Apply PCB-safe paint or ink through stencil
5. **Drying**: Allow paint to dry (12-24 hours)
6. **Sealing** (Optional): Apply clear coat for protection

**Alternative - Toner Transfer for Silk Screen**:
- Print silk screen design on glossy paper
- Transfer toner to PCB using heat
- Fill design with paint/ink
- Seal with clear coat

**Materials**:
- Vinyl or thick paper for stencil
- PCB-safe paint or ink
- Fine brushes or sponge
- Clear coat (optional)

**Learning Outcomes**:
- Component labeling and identification
- Silk screen application techniques
- Professional PCB finishing

**Best For**: Years 3-4 (when students create more complex boards needing component labels)

---

### Curriculum Integration

#### Year 2: Introduction to PCB Concepts
- **Activity**: Simple single-sided PCB for basic logic circuit (AND gate, OR gate)
- **Method**: Toner transfer and etching
- **Focus**: Understanding PCB structure, basic etching process
- **Outcome**: Students create simple PCB and solder components

#### Year 3: Intermediate PCB Production
- **Activity**: Small module PCBs (counter, register board)
- **Method**: Toner transfer and etching, introduction to silk screening
- **Focus**: Improved technique, component placement, labeling
- **Outcome**: Students create functional module PCBs

#### Year 4: Advanced DIY PCB Production
- **Activity**: 8-bit system module PCBs (memory board, I/O board)
- **Method**: UV photoresist (optional), toner transfer, full silk screening
- **Focus**: Higher quality, multi-component boards, professional finishing
- **Outcome**: Students create production-quality DIY PCBs for 8-bit system

#### Year 6: Professional Manufacturing
- **Activity**: Complete 16-bit system PCBs
- **Method**: Professional manufacturer (PCBWay)
- **Focus**: Professional workflow, quality control, cost management
- **Outcome**: Production-quality PCBs for final system

---

## Educational Resources

### Books and Guides

1. **"Build Your Own Printed Circuit Board" by Al Williams**
   - Comprehensive guide to DIY PCB production
   - Covers etching, drilling, assembly
   - ISBN: 0071427837

2. **"PCB Design and Fabrication" by Charles Hamilton**
   - Educational approach to PCB production
   - Includes safety protocols
   - Suitable for classroom use

3. **"The Art of Electronics" by Horowitz and Hill**
   - Chapter on PCB design and production
   - Professional and DIY methods
   - ISBN: 0521809266

### Online Resources

1. **Instructables PCB Etching Tutorials**
   - Step-by-step guides with photos
   - Multiple methods covered
   - Community support

2. **YouTube Channels**:
   - **GreatScott!** - Electronics projects including PCB production
   - **Electronoobs** - DIY PCB tutorials
   - **EEVblog** - Professional PCB design and manufacturing

3. **Educational Websites**:
   - **SparkFun Electronics** - Tutorials on PCB design and production
   - **Adafruit Learning System** - PCB fabrication guides
   - **All About Circuits** - PCB design and manufacturing articles

### Software Tools

1. **Fritzing** (Beginner-friendly)
   - Visual PCB design
   - Export for toner transfer
   - Free and open source

2. **KiCad** (Intermediate)
   - Professional PCB design
   - Gerber export
   - Free and open source

3. **EasyEDA** (Online)
   - Web-based PCB design
   - Direct manufacturer integration
   - Free tier available

---

## Safety Protocols

### Chemical Safety

**Ferric Chloride (Etchant)**:
- Wear gloves and safety goggles
- Work in well-ventilated area
- Avoid skin contact
- Neutralize before disposal (add baking soda)
- Store in labeled, sealed container

**Acetone (Toner Removal)**:
- Flammable - no open flames
- Well-ventilated area
- Avoid inhalation
- Use in small quantities

**Photoresist Chemicals**:
- Follow manufacturer safety data sheets
- Proper ventilation required
- Chemical-resistant gloves
- Eye protection mandatory

### Equipment Safety

**Drilling**:
- Use proper PCB drill or Dremel with PCB bits
- Secure board during drilling
- Eye protection required
- Proper bit selection for hole sizes

**Heat Application (Iron)**:
- Use temperature-controlled iron
- Work on heat-resistant surface
- Avoid burns
- Proper ventilation for fumes

**UV Exposure**:
- UV protection for eyes
- Limited exposure time
- Proper UV source (LED array preferred over mercury lamps)

---

## Assessment and Evaluation

### Formative Assessment (Years 2-4)

**Technical Skills**:
- PCB design quality
- Etching technique
- Component placement accuracy
- Soldering quality
- Overall board functionality

**Safety Compliance**:
- Proper use of safety equipment
- Chemical handling procedures
- Workspace organization
- Cleanup procedures

**Documentation**:
- Process documentation
- Troubleshooting notes
- Design decisions
- Lessons learned

### Summative Assessment (Year 6)

**Professional Manufacturing**:
- Design review quality
- Gerber file correctness
- Manufacturer communication
- Quality control procedures
- Final PCB quality

---

## Cost Considerations

### DIY Methods (Years 2-4)

**Initial Setup** (one-time):
- Copper-clad boards: £20-30 for 10 boards
- Ferric chloride: £10-15 per liter
- Safety equipment: £30-50
- Drilling equipment: £50-100 (Dremel or PCB drill)
- **Total**: ~£150-200 for classroom setup

**Per Student Project**:
- Copper-clad board: £2-3
- Chemicals (etchant, acetone): £1-2
- Paper, toner: £0.50
- **Total**: ~£3-5 per student per board

### Professional Manufacturing (Year 6)

**PCBWay/JLCPCB** (example pricing):
- 5 boards, 2-layer, 100mm x 100mm: £15-25
- Shipping: £10-20
- **Total**: ~£25-45 per order (shared across class)

**Per Student** (if individual orders):
- 5 boards, 2-layer, 100mm x 100mm: £15-25
- Shipping: £10-20
- **Total**: ~£25-45 per student

---

## Recommendations

### For Formative Years (Years 2-4)

1. **Start Simple**: Year 2 - basic toner transfer for simple circuits
2. **Build Skills**: Year 3 - improved technique, add silk screening
3. **Advanced DIY**: Year 4 - UV photoresist option, professional finishing
4. **Safety First**: Always supervised, proper safety equipment, clear protocols
5. **Documentation**: Students document process, learn from mistakes

### For A-Level (Year 6)

1. **Professional Approach**: Use manufacturer for final project
2. **Design Focus**: Emphasize design quality over fabrication
3. **Quality Control**: Learn inspection and testing procedures
4. **Cost Management**: Understand budgeting and cost optimization
5. **Industry Experience**: Prepare for professional engineering

---

## Conclusion

**Two-Track Approach**:
- **Formative Years (2-4)**: DIY methods teach fundamentals, build skills, cost-effective
- **A-Level (Year 6)**: Professional manufacturing for production-quality results

**Benefits**:
- Students understand PCB production from first principles
- Cost-effective for practice and learning
- Professional experience in final year
- Comprehensive understanding of entire PCB lifecycle

**Outcome**: Students graduate with both practical DIY skills and professional manufacturing experience, providing comprehensive understanding of PCB production.

---

**Document Created**: 2025-12-15  
**Purpose**: Outline PCB fabrication approaches for curriculum integration
