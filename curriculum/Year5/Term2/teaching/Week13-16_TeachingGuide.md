# Week 13-16: SuperPascal Compiler Implementation - Teaching Guide

## Overview

This teaching guide supports compiler implementation over 4 weeks. Students configure and extend the SuperPascal compiler for the 65C816 system.

## Learning Objectives

By the end of this week-block, students will:
- Understand compiler structure
- Configure compiler for 65C816
- Extend compiler with features
- Test compiler thoroughly
- Verify code generation

## Prerequisites Check

Before starting, ensure students:
- ✅ Completed Term 1 (PCB System)
- ✅ Have working system
- ✅ Understand assembly
- ✅ Understand programming concepts
- ✅ Have access to Malvino & Brown textbook

## Book Integration

**Primary Reference**: **Malvino & Brown, Digital Computer Electronics, Part 3 (Chapters 16-23)**

This week-block uses the book as the **primary reference** for understanding instruction categories used in code generation.

### Before Class

**Required Reading** (assign 1 week before):
- **Chapters 16-23**: Instruction Sets (review for code generation)
  - Review instruction categories: Data Transfer, Arithmetic, Logic, Branches, Stack, Control
  - Study book examples for each category
  - Understand how instruction categories map to high-level operations

**Pre-Class Assignment**:
- Review instruction categories from book
- Identify which categories are needed for code generation
- Study book examples for each category

### During Class

**Discussion Points** (link book to code generation):

1. **Instruction Categories → Code Generator**:
   - Book shows: Instruction categories (data transfer, arithmetic, logic, branches, stack, control)
   - Code generator needs: Map high-level operations to instruction categories
   - **Key Insight**: Book's categories structure code generator design

2. **Book Examples → Code Generation**:
   - Book shows: Examples for each instruction category
   - Code generator: Uses similar patterns when generating code
   - **Key Insight**: Book's examples inform code generation patterns

3. **Addressing Modes → Code Generation**:
   - Book shows: Different addressing modes for instructions
   - Code generator: Selects addressing modes when generating code
   - **Key Insight**: Book's addressing mode concepts guide code generation

**Demonstration**:
- Show how book's instruction categories (Chapters 16-23) structure code generator
- Show how book examples inform code generation patterns
- Demonstrate generating code using book's instruction categories

**Practice Exercise**:
- Design instruction selector using book's instruction categories
- Generate assembly code for simple expression using book's arithmetic examples
- Generate assembly code for control flow using book's branch examples

### After Class

**Assignment**:
- Design code generator instruction selector using book's instruction categories (Chapters 16-23)
- Generate assembly code for arithmetic expressions using book's arithmetic examples (Chapter 17)
- Generate assembly code for control flow using book's branch examples (Chapter 19)

**Assessment Question**:
- From Chapters 16-23: How would you use the book's instruction categories when designing a code generator? Give examples of mapping high-level operations to book's instruction categories.

**Resources**:
- **65C816 Concept Bridging Guide** (`../../../Year4/Term2/65C816_CONCEPT_BRIDGING.md`) - For translating concepts
- **65C816 Instruction Set Reference** (`../../../../docs/65C816_INSTRUCTION_SET_REFERENCE.md`) - Complete instruction set
- **Book Examples**: Use book's instruction examples as reference for code generation

## Week-by-Week Breakdown

### Week 13: Compiler Setup

**Theory Session (45 min)**:
- Compiler overview
- Compiler structure
- Configuration process
- Calling conventions

**Lab Session (90 min)**:
- Obtain compiler source
- Build compiler
- Configure for 65C816
- Test basic compilation
- Document setup

**Key Points**:
- Compiler translates high-level to machine code
- Configuration is critical
- Test incrementally
- Document everything

**Common Questions**:
- Q: How does compiler work? A: Parses, analyzes, generates code
- Q: How to configure? A: Set target, calling convention, runtime
- Q: What if fails? A: Debug, check configuration

### Week 14: Compiler Extension

**Theory Session (45 min)**:
- Compiler extension methods
- Code generation
- Runtime integration
- Extension examples

**Lab Session (90 min)**:
- Choose extension task
- Understand compiler code
- Implement extension
- Test extension
- Document changes

**Key Points**:
- Extensions add functionality
- Understand compiler structure
- Test thoroughly
- Document changes

**Common Questions**:
- Q: What to extend? A: Intrinsics, graphics, sound functions
- Q: How complex? A: Depends on feature, start simple
- Q: What if unclear? A: Study examples, ask questions

### Week 15: Compiler Testing

**Theory Session (45 min)**:
- Testing strategies
- Test program design
- Verification methods
- Debugging approaches

**Lab Session (90 min)**:
- Write test programs
- Compile and test
- Verify on hardware
- Debug issues
- Document results

**Key Points**:
- Test systematically
- Verify on hardware
- Debug carefully
- Document results

**Common Questions**:
- Q: How to test? A: Write programs, compile, run, verify
- Q: What if fails? A: Debug assembly, check runtime
- Q: What to test? A: Arithmetic, control flow, I/O

### Week 16: Compiler Verification

**Theory Session (45 min)**:
- Verification procedures
- Test suites
- Edge cases
- Performance considerations

**Lab Session (90 min)**:
- Run test suite
- Verify all tests
- Test edge cases
- Performance testing
- Final verification

**Key Points**:
- Verify completely
- Test edge cases
- Check performance
- Ready for programs

**Common Questions**:
- Q: How to verify? A: Run test suite, check all pass
- Q: What if fails? A: Debug, fix, retest
- Q: Ready for programs? A: Yes, if verified

## Teaching Strategies

### Differentiation

**Support for struggling students**:
- Provide setup guides
- Step-by-step instructions
- Extra time for work
- Pair with stronger students
- Review concepts

**Extension for advanced students**:
- Advanced extensions
- Optimization features
- Help other students

### Common Misconceptions

1. **"Compilers are magic"**
   - Clarify: Systematic translation
   - Show structure

2. **"Too complex to understand"**
   - Clarify: Built on simple concepts
   - Show progression

3. **"Can't modify compilers"**
   - Clarify: Source provided
   - Show extension process

### Assessment Checkpoints

**Week 13**: Is compiler configured?
**Week 14**: Is extension implemented?
**Week 15**: Do test programs work?
**Week 16**: Is compiler verified?

## Resources

- Compiler documentation
- Setup guides
- Extension examples
- Test program templates

## Next Week

After completing compiler, students develop Pascal programs (Week 17-20).

---

*Compiler implementation enables high-level programming on custom hardware*
