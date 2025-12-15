# Video Hardware Educational Resources: Summary

## Overview

This document provides a quick reference summary of video hardware educational resources integrated into the Resistor2Compiler curriculum. These resources support the curriculum's philosophy of building from first principles before using IC video chips.

---

## Resource Comparison

| Resource | Level | Purpose | Cost | Build? | When |
|----------|-------|---------|------|--------|------|
| **Ben Eater VGA** | Year 4 | **REQUIRED** foundation learning | $20-30 | ✅ Yes | **REQUIRED**, Term 2 |
| **BombJack Hardware** | Year 6 | Advanced reference | Reference only | ❌ No | Optional, throughout |
| **IC Video Chips** | Year 6 | Production use | Medium | ✅ Yes | Required, Term 2 |
| **Raspberry Pi Pico** | Year 6 | Production use (alternative) | Low | ✅ Yes | Required, Term 2 |

**Note**: VERA FPGA is not used in this curriculum as it is a black box that limits educational value.

---

## Ben Eater VGA Project

**URL**: https://eater.net/vga

**Analysis**: See `BEN_EATER_VGA_ANALYSIS.md`

**Key Points**:
- ✅ Breadboard-based video card
- ✅ Discrete components (no IC)
- ✅ Teaches video fundamentals
- ✅ Hands-on building experience
- ✅ Year 4 optional module

**Integration**: Year 4, Term 2, Weeks 22-24 (I/O Subsystems) - Optional

**Educational Value**:
- Video signal generation (HSYNC, VSYNC)
- Digital-to-analog conversion (DAC)
- Frame buffering concepts
- CPU-to-video interfacing

---

## BombJack Video Hardware Repository

**URL**: https://github.com/martinpiper/BombJack

**Analysis**: See `BOMBJACK_VIDEO_HARDWARE_ANALYSIS.md`

**Key Points**:
- ✅ Professional arcade video hardware
- ✅ Multi-board modular design
- ✅ Detailed technical documentation
- ✅ Production PCB designs
- ✅ Year 6 advanced reference

**Integration**: Year 6, optional advanced reference material

**Educational Value**:
- Professional video hardware architecture
- Sprite and tile rendering logic
- Production PCB design principles
- Understanding what IC video chips do

**Usage**:
- **Term 1**: PCB design reference
- **Term 2, Week 17**: Sprite/tile concepts reference
- **Advanced Students**: Deep dive study material

---

## Educational Progression

### Year 4: Foundation (**REQUIRED**)
**Ben Eater VGA Project ("Worst Video Card Ever")**
- **REQUIRED**: Build video card from discrete components
- **Educational value is paramount**: Learn video fundamentals
- Understand video signal generation from first principles
- Hands-on experience essential for Year 6
- **Must complete before**: TMS9918/VDP or Raspberry Pi Pico integration

### Year 6, Term 1: Advanced Study (Optional)
**BombJack Hardware Reference**
- Study professional video hardware design
- Understand production PCB design
- Learn advanced graphics concepts
- Reference material only

### Year 6, Term 2: Application (Required)
**IC Video Chips (TMS9918/V9938/V9958 VDP) or Raspberry Pi Pico (RP2040/RP2350)**
- Use professional video ICs or microcontroller video co-processor
- Write device drivers
- Implement graphics features
- **Full understanding** from Year 4 Ben Eater VGA foundation
- Appreciate what IC/microcontroller does internally (from prior experience)

---

## Curriculum Philosophy Alignment

### Build Before Using Black Boxes

> "Students will build initial versions of IC's. The only black box will be:
> - MOS 65C816
> - Complex IC's (Sound, Midi, Video)"

**Progression**:
1. **Year 4**: Build discrete VGA (understand fundamentals)
2. **Year 6**: Study professional design (appreciate complexity)
3. **Year 6**: Use IC video chips (with full understanding)

### First Principles Learning

- **Ben Eater VGA**: Every component visible and understandable
- **BombJack Hardware**: Shows professional implementation
- **IC Video Chips**: Used with appreciation of internal operation

---

## Quick Reference

### For Year 4 Students
- **Primary**: Ben Eater VGA (**REQUIRED** build project)
- **Educational Value**: Essential foundational learning for Year 6
- **Reference**: None required (BombJack too advanced)

### For Year 6 Students
- **Required**: IC video chip (TMS9918/VDP) or Raspberry Pi Pico (RP2040/RP2350) integration
- **Foundation**: Ben Eater VGA completed in Year 4 (required prerequisite)
- **Recommended Reference**: BombJack hardware (for understanding)
- **Benefit**: Full understanding of video fundamentals from Year 4 foundation

### For Teachers
- **Year 4**: Use Ben Eater VGA analysis for optional module
- **Year 6**: Use BombJack analysis for advanced reference
- **Both**: Understand educational progression

---

## Document References

1. **Ben Eater VGA Analysis**: `BEN_EATER_VGA_ANALYSIS.md`
   - Detailed analysis of Ben Eater VGA project
   - Integration recommendations
   - Implementation guidance

2. **BombJack Hardware Analysis**: `BOMBJACK_VIDEO_HARDWARE_ANALYSIS.md`
   - Detailed analysis of BombJack repository
   - Advanced reference recommendations
   - Professional design insights

3. **Year 6 Video Hardware Reference**: `../Year6/VIDEO_AUDIO_HARDWARE_REFERENCE.md`
   - IC video chip documentation
   - Integration guides
   - Programming examples

---

## Key Takeaways

1. **Ben Eater VGA** provides **REQUIRED** foundation learning (Year 4) - **Educational value is paramount**
2. **BombJack Hardware** provides advanced reference (Year 6, optional)
3. **IC Video Chips (TMS9918/VDP) or Raspberry Pi Pico (RP2040/RP2350)** are the production solutions (Year 6, required)
4. **Progressive Learning**: Simple (Year 4, required) → Professional Reference (Year 6, optional) → Production (Year 6, required)
5. **Philosophy Alignment**: Build from first principles before using black boxes
6. **Foundation Essential**: Year 4 Ben Eater VGA is required prerequisite for effective Year 6 video hardware integration

---

**Document Created**: 2025-12-16  
**Purpose**: Quick reference summary of video hardware educational resources  
**Status**: Summary complete

