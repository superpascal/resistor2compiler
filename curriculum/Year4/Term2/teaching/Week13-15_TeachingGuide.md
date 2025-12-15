# Week 13-15: 65C816 System Design - Teaching Guide

## Overview

This teaching guide supports 65C816 system design over 4 weeks. Students design a complete system and create professional schematics.

## Learning Objectives

By the end of this week-block, students will:
- Design 65C816 system architecture
- Plan memory map and address decoding
- Design I/O interfaces
- Create schematics in KiCad
- Review and refine design

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Weeks 10-12 (65C816 Introduction)
- ✅ Understand 65C816 architecture
- ✅ Understand system design
- ✅ Can use KiCad (or learn)

## Week-by-Week Breakdown

### Week 17: System Architecture Design

**Theory Session (45 min)**:
- System design process
- Component selection
- Architecture planning
- Design principles

**Lab Session (90 min)**:
- Define requirements
- Select components
- Plan architecture
- Design memory map
- Design I/O map
- Document architecture

**Key Points**:
- Plan before building
- Consider all components
- Design for expansion
- Document decisions

**Common Questions**:
- Q: What components? A: CPU, memory, I/O, support circuits
- Q: How to plan? A: Start with requirements, add components
- Q: What if wrong? A: Review, revise, iterate

### Week 18: Memory Map and Address Decoding

**Theory Session (45 min)**:
- Memory map design
- Address space organization
- Address decoding principles
- Decoding implementation

**Lab Session (90 min)**:
- Design memory map
- Plan RAM organization
- Plan ROM organization
- Plan I/O space
- Design address decoding
- Create decoding table

**Key Points**:
- Memory map organizes address space
- Address decoding selects devices
- Plan for expansion
- Document map clearly

**Common Questions**:
- Q: How much memory? A: Start with 32-64KB, can expand
- Q: How to decode? A: Use decoders, higher bits select
- Q: What if conflicts? A: Review map, adjust ranges

### Week 19: Schematic Creation

**Theory Session (45 min)**:
- KiCad introduction
- Schematic symbols
- Component placement
- Connection methods
- Best practices

**Lab Session (90 min)**:
- Set up KiCad project
- Add components
- Connect components
- Add power/ground
- Add decoupling
- Label everything
- Review schematic

**Key Points**:
- KiCad is professional tool
- Clear organization important
- Label everything
- Show power distribution

**Common Questions**:
- Q: How to use KiCad? A: Tutorials, practice, ask questions
- Q: What if errors? A: Review, check connections
- Q: How detailed? A: Complete, but clear

### Week 20: Design Review and Refinement

**Theory Session (45 min)**:
- Design review process
- Error checking
- Peer review
- Refinement techniques

**Lab Session (90 min)**:
- Review schematic
- Check for errors
- Verify address decoding
- Check power distribution
- Peer review
- Incorporate feedback
- Finalize design

**Key Points**:
- Review is essential
- Peer review helps
- Fix errors before building
- Finalize completely

**Common Questions**:
- Q: What to review? A: Everything: connections, decoding, power
- Q: What if errors? A: Fix, review again
- Q: Ready to build? A: Yes, if design complete and reviewed

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide design templates
- Step-by-step design guide
- Extra time for work
- Pair with stronger students
- KiCad tutorials

**Extension for advanced students**:
- Advanced system features
- Optimize design
- Add expansion capabilities
- Help other students

### Common Misconceptions

1. **"Design is just drawing"**
   - Clarify: Requires understanding and planning
   - Show design process

2. **"More is always better"**
   - Clarify: Appropriate for needs
   - Show balance

3. **"Schematic is optional"**
   - Clarify: Essential for complex systems
   - Show professional practice

### Assessment Checkpoints

**Week 17**: Can students design system architecture?
**Week 18**: Can students design memory map and decoding?
**Week 19**: Can students create schematics?
**Week 20**: Is design reviewed and ready?

## Resources

- KiCad tutorials
- Design templates
- Component datasheets
- Design checklists

## Next Week

After completing design, students move to breadboard prototype (Week 16-18).

---

*System design is the blueprint for construction*
