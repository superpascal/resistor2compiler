# Week 1-5: Finalizing PCB Schematics and Layout - Teaching Guide

## Overview

This teaching guide supports PCB design finalization over 5 weeks. Students create professional PCB designs ready for fabrication.

## Learning Objectives

By the end of this week-block, students will:
- Finalize all schematics
- Design power and reset circuits
- Create PCB layouts
- Route traces properly
- Generate Gerber files

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Year 4 (65C816 Prototype)
- ✅ Have working prototype
- ✅ Understand PCB design
- ✅ Can use KiCad

## Week-by-Week Breakdown

### Week 1: Schematic Finalization

**Theory Session (45 min)**:
- Schematic requirements
- Component selection
- Power distribution
- Connector planning

**Lab Session (90 min)**:
- Review breadboard design
- Finalize schematics
- Add power distribution
- Add decoupling
- Review schematics

**Key Points**:
- Complete schematics essential
- Power distribution critical
- Decoupling important
- Review carefully

**Common Questions**:
- Q: What to include? A: All components, power, connectors
- Q: How detailed? A: Complete, production-ready
- Q: What if errors? A: Review, fix, verify

### Week 2: Power and Reset Design

**Theory Session (45 min)**:
- Power supply design
- Voltage regulation
- Reset circuit design
- Decoupling strategy

**Lab Session (90 min)**:
- Design power supply
- Design reset circuit
- Plan decoupling
- Verify design
- Document requirements

**Key Points**:
- Robust power essential
- Reset must be clean
- Decoupling critical
- Document everything

**Common Questions**:
- Q: What regulator? A: LM7805 or switching
- Q: Reset circuit? A: Supervisor IC recommended
- Q: How much decoupling? A: 0.1µF per IC minimum

### Week 3: Component Placement

**Theory Session (45 min)**:
- Placement principles
- Signal integrity
- Heat considerations
- Routing planning

**Lab Session (90 min)**:
- Import to layout
- Plan placement
- Group components
- Consider routing
- Document placement

**Key Points**:
- Placement affects routing
- Group related components
- Consider signal integrity
- Plan for testing

**Common Questions**:
- Q: How to place? A: Group related, minimize traces
- Q: What order? A: Critical first, then others
- Q: What if conflicts? A: Adjust, optimize

### Week 4: PCB Routing

**Theory Session (45 min)**:
- Routing principles
- Signal integrity
- Ground planes
- Power planes

**Lab Session (90 min)**:
- Route power/ground
- Route critical signals
- Route buses
- Add ground planes
- Review routing

**Key Points**:
- Route critical first
- Use ground planes
- Short traces
- Avoid crosstalk

**Common Questions**:
- Q: What to route first? A: Power, ground, critical signals
- Q: How wide traces? A: Depends on current
- Q: What if conflicts? A: Reroute, adjust

### Week 5: Gerber Generation and Review

**Theory Session (45 min)**:
- Gerber file format
- Fabrication requirements
- Design review
- Ordering process

**Lab Session (90 min)**:
- Generate Gerber files
- Verify all layers
- Peer review
- Finalize design
- Prepare for ordering

**Key Points**:
- Verify all layers
- Review carefully
- Peer review helps
- Ready for ordering

**Common Questions**:
- Q: What are Gerber files? A: Standard PCB format
- Q: How to verify? A: Check all layers, dimensions
- Q: Ready to order? A: Yes, if reviewed and verified

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide design templates
- Step-by-step guides
- Extra time for work
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Advanced layout techniques
- Signal integrity optimization
- Multi-layer design
- Help other students

### Common Misconceptions

1. **"PCB design is easy"**
   - Clarify: Requires careful planning
   - Show complexity

2. **"Any layout works"**
   - Clarify: Layout affects performance
   - Show best practices

3. **"Can fix on PCB"**
   - Clarify: Changes are difficult
   - Show importance of review

### Assessment Checkpoints

**Week 1**: Are schematics complete?
**Week 2**: Are power/reset designed?
**Week 3**: Is placement planned?
**Week 4**: Is routing complete?
**Week 5**: Are Gerber files ready?

## Resources

- PCB design guides
- KiCad tutorials
- Design checklists
- Fabrication house guidelines

## Next Week

After completing design, students wait for boards, then assemble (Week 6-9).

---

*PCB design creates the foundation for professional hardware*
