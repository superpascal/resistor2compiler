# Week 10-12: Introduction to 65C816 CPU - Teaching Guide

## Overview

This teaching guide supports the introduction to 65C816 CPU architecture over 4 weeks. Students learn about modern microprocessors and compare to their SAP-1 experience.

## Learning Objectives

By the end of this week-block, students will:
- Understand 65C816 CPU architecture
- Compare SAP-1 to 65C816
- Understand 16-bit and 24-bit concepts
- Map SAP-1 components to 65C816
- Understand addressing modes

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Term 1 (Enhanced SAP-1)
- ✅ Understand CPU architecture
- ✅ Understand memory systems
- ✅ Can read datasheets
- ✅ Have access to Malvino & Brown textbook

## Book Integration

**Primary Reference**: **Malvino & Brown, Digital Computer Electronics**

This week-block uses the book as the **primary conceptual reference** for understanding CPU enhancements and microprocessor concepts.

### Before Class

**Required Reading** (assign 1 week before):
- **Chapter 11-5** (SAP-2: Jump and Call Instructions) ⭐ **KEY CONCEPT**
  - Read sections on JMP, conditional jumps (JM, JZ, JNZ), CALL/RET
  - Study example programs using jumps and subroutines
  - Understand how subroutines work (stack-based return addresses)
- **Chapter 13** (Intro to Microprocessors): Sections 13-1 to 13-5
  - General microprocessor concepts
  - Register models (accumulator, index registers, stack pointer)
  - Addressing concepts
  - Instruction types
- **Chapter 15** (System Overview): Sections 15-1 to 15-5
  - Microprocessor architecture patterns
  - Register organization
  - Memory models

**Pre-Class Assignment**:
- Read SAP-2 jump example (Chapter 11-5, Example 11-3)
- Identify: What does JMP do? What does CALL do?
- Compare: How are SAP-2 jumps different from SAP-1 (which has no jumps)?

### During Class

**Discussion Points** (link book to 65C816):

1. **SAP-2 Jumps → 65C816 Branches**:
   - SAP-2: JMP (unconditional), JM/JZ/JNZ (conditional)
   - 65C816: JMP (unconditional), BEQ/BNE/BCC/BCS (conditional)
   - **Key Insight**: Same concept (program flow control), different implementation

2. **SAP-2 Subroutines → 65C816 Subroutines**:
   - SAP-2: CALL (saves return address), RET (returns)
   - 65C816: JSR (Jump to Subroutine), RTS (Return from Subroutine)
   - **Key Insight**: Both use stack for return addresses (automatic)

3. **Book's Microprocessor Examples → 65C816**:
   - Book shows: 6502, 6800, 8080/8085, 8086/8088
   - 65C816: Similar concepts (registers, addressing, instructions)
   - **Key Insight**: Concepts are universal, implementations vary

**Demonstration**:
- Show SAP-2 program with CALL/RET (from book Example 11-4)
- Translate to 65C816 using JSR/RTS
- Compare: Same functionality, different syntax

**Practice Exercise**:
- Give students SAP-2 program using JMP (from book)
- Have them translate to 65C816 JMP
- Have them translate SAP-2 CALL to 65C816 JSR

### After Class

**Assignment**:
- Translate 3 SAP-2 programs (from book Chapter 11-5 examples) to 65C816
- Compare SAP-2 addressing modes to 65C816 addressing modes
- Explain: How does 65C816 implement the same concepts as SAP-2?

**Assessment Question**:
- From Chapter 11-5: Explain how SAP-2 implements subroutine calls. How does 65C816 implement the same concept? What are the similarities and differences?

**Resources**:
- **65C816 Concept Bridging Guide** (`../65C816_CONCEPT_BRIDGING.md`) - Detailed mapping of book concepts to 65C816
- **SAP-2/SAP-3 Conceptual Mapping** (`../../../../docs/SAP2_SAP3_CONCEPTUAL_MAPPING.md`) - How SAP-2/SAP-3 concepts map to 65C816

## Week-by-Week Breakdown

### Week 13: 65C816 Architecture Study

**Theory Session (45 min)**:
- 65C816 introduction
- Key features and capabilities
- Register set
- Instruction set overview
- Addressing modes overview

**Lab Session (90 min)**:
- Read 65C816 datasheet
- Study architecture
- Document key features
- Create architecture summary
- Research 65C816 systems

**Key Points**:
- 65C816 is 16-bit CPU
- 24-bit addressing
- Many registers
- Many instructions
- Many addressing modes

**Common Questions**:
- Q: Why 65C816? A: Good for learning, well-documented, available
- Q: How complex? A: More than SAP-1, but same concepts
- Q: Can we build with it? A: Yes, many have done it

### Week 14: SAP-1 to 65C816 Comparison

**Theory Session (45 min)**:
- Comparison methodology
- Component mapping
- Instruction set comparison
- Addressing mode comparison
- Capability comparison

**Lab Session (90 min)**:
- Create comparison table
- Map components
- Compare features
- Identify similarities
- Identify differences
- Document comparison

**Key Points**:
- Same fundamental concepts
- 65C816 is more complex
- More features and capabilities
- Built on same foundations

**Common Questions**:
- Q: How similar? A: Same concepts, more complex
- Q: What's different? A: Size, features, capabilities
- Q: Can we understand it? A: Yes, built on SAP-1 knowledge

### Week 15: Component Mapping Exercise

**Theory Session (45 min)**:
- Component mapping process
- Register mapping
- Control unit mapping
- Memory mapping
- I/O mapping

**Lab Session (90 min)**:
- Map Program Counter
- Map Instruction Register
- Map Registers
- Map Flags
- Map ALU
- Map Memory
- Map Control Unit
- Document mappings

**Key Points**:
- SAP-1 components have 65C816 equivalents
- Some 65C816 features SAP-1 doesn't have
- Mapping shows continuity
- Understanding both helps

**Common Questions**:
- Q: Do all components map? A: Most do, some are new
- Q: What's new? A: Stack, interrupts, more registers
- Q: Why map? A: Shows continuity, builds understanding

### Week 16: Addressing Modes Study

**Theory Session (45 min)**:
- Addressing mode concepts
- Immediate mode
- Direct mode
- Indexed mode
- Indirect mode
- Benefits of multiple modes

**Lab Session (90 min)**:
- Study each addressing mode
- Compare to SAP-1
- Understand benefits
- Practice examples
- Document understanding

**Key Points**:
- Multiple addressing modes
- More flexible than SAP-1
- Enables efficient programming
- Foundation for assembly

**Common Questions**:
- Q: Why so many modes? A: Flexibility, efficiency
- Q: Which to learn? A: Start with basic, add more
- Q: How complex? A: Start simple, build up

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide comparison templates
- Step-by-step mapping guide
- Extra time for study
- Pair with stronger students
- Review SAP-1 concepts

**Extension for advanced students**:
- Study advanced addressing modes
- Research 65C816 systems
- Compare to other CPUs
- Design instruction sequences

### Common Misconceptions

1. **"65C816 is completely different"**
   - Clarify: Same concepts, more complex
   - Show similarities

2. **"Too complex to understand"**
   - Clarify: Built on same foundations
   - Show progression

3. **"Can't build systems with it"**
   - Clarify: Many have built systems
   - Show examples

### Assessment Checkpoints

**Week 13**: Can students understand 65C816 architecture?
**Week 14**: Can students compare SAP-1 to 65C816?
**Week 15**: Can students map components?
**Week 16**: Can students understand addressing modes?

## Resources

**Required Reading**:
- **Malvino & Brown, Chapter 13** (Intro to Microprocessors) - General microprocessor concepts
- **Malvino & Brown, Chapter 15** (System Overview) - Microprocessor architecture patterns
- **W65C816 Datasheet** - 65C816-specific hardware reference
- **65C816 Programming Manual** - 65C816 instruction set and addressing modes
- **65C816 Concept Bridging Guide** (see `../65C816_CONCEPT_BRIDGING.md`) - Maps book concepts to 65C816 equivalents

**Conceptual Reference**: The book's Part 3 (Chapters 13-15) provides general microprocessor programming concepts that apply to all CPUs, including the 65C816. While the book uses different CPUs (6502, 6800, 8080/8085, 8086/8088) for examples, the concepts (register models, addressing modes, instruction categories) are universal. Students should:
1. Read the book for **conceptual understanding** (what are registers, addressing modes, instruction types)
2. Use the **bridging guide** to see how book examples map to 65C816 equivalents
3. Apply these concepts to **65C816 specifics** (65C816 register set, 65C816 addressing modes, 65C816 instruction set)

**Additional Resources**:
- Comparison templates
- Component mapping guides
- Addressing mode examples
- 65C816 instruction set reference (see `docs/65C816_INSTRUCTION_SET_REFERENCE.md`)
- 65C816 concept bridging guide (see `../65C816_CONCEPT_BRIDGING.md`)

## Next Week

After completing 65C816 introduction, students move to system design (Week 13-15).

---

*65C816 introduces modern CPU architecture*
