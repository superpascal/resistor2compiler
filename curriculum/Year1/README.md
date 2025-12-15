# Year 1: Computing Foundations & Physical Logic (Age 13)

## Overview

Year 1 establishes the foundational electronics and digital logic knowledge that students need before building CPUs. This year focuses on **hands-on learning** and **intuitive understanding** rather than abstract theory.

**Key Principle**: No programming pressure. Students learn by building, observing, and experimenting.

## Curriculum Structure

Year 1 is organized by **Term**, with each term containing all materials:

```
Year1/
├── Term1/
│   ├── theory/          # Theoretical content
│   ├── labs/            # Practical lab work
│   ├── teaching/        # Teaching guides
│   ├── reading/         # Student reading materials
│   ├── resources/       # Additional resources
│   ├── worksheets/      # Practice worksheets
│   └── assessments/     # Assessment rubrics
├── Term2/
│   └── [same structure]
├── Term3/
│   └── [same structure]
└── workshops/           # Optional enrichment workshops
    └── PRACTICAL_ELECTRONICS_WORKSHOPS.md
```

## Learning Outcomes

By the end of Year 1, students will:

- Understand voltage, current, and resistance (Ohm's law)
- Build and test basic circuits safely
- Use breadboards, multimeters, and basic tools
- Understand Boolean logic and truth tables
- Build combinational logic circuits (adders, multiplexers)
- Understand sequential logic (flip-flops, registers, counters)
- Build a simple ALU subsystem
- Understand how information is represented in binary
- Understand the concept of state and memory

## Year Structure

- **Term 1**: Electronics Basics and Lab Skills (Weeks 1-12)
- **Term 2**: Sequential Logic and Building Blocks (Weeks 13-24)
- **Term 3**: Integration and ALU Construction (Weeks 25-36)

## How to Use This Curriculum

### For Teachers

**Before Each Week**:
1. Read theory material (`TermX/theory/Week##-##.md`)
2. Review lab material (`TermX/labs/Lab##-##.md`)
3. Review teaching guide (`TermX/teaching/Week##-##.md`)
4. Prepare materials and components
5. Review reading materials to assign

**During Teaching**:
1. Present theory (30-45 min) using theory materials
2. Conduct lab (60-90 min) using lab materials
3. Follow teaching guide for pacing and key points
4. Assign reading for reinforcement

**After Each Week**:
1. Review student work
2. Assess using rubrics
3. Plan next week
4. Address any gaps

### For Students

**Before Lab**:
1. Read theory material
2. Read assigned reading chapters
3. Review lab material
4. Prepare questions

**During Lab**:
1. Follow lab instructions
2. Build circuits step-by-step
3. Document in lab notebook
4. Ask questions when stuck

**After Lab**:
1. Review reading materials
2. Complete worksheets
3. Update portfolio
4. Reflect on learning

## Materials Overview

Each student/team will need:
- Breadboards (2-3 full-size)
- Jumper wires kit
- Basic components (resistors, LEDs, capacitors)
- Logic ICs (74HC series)
- Multimeter
- Power supply (5V)

See individual lab materials for specific component lists.

## Practical Projects

### Dual Step-Down Converter Project

**Location**: `projects/DUAL_STEPDOWN_CONVERTER.md`

A comprehensive 2-3 week project to build a dual-output power supply (3V and 5V) from 12V or 24V input. This project:
- Teaches step-down converter principles
- Provides a reusable power supply for all Year 1 circuits
- Includes breadboard construction and PCB conversion
- Can be started after Weeks 1-2 (basic electricity understanding)

**When to Use**: Recommended for Term 1, after students understand basic voltage/current concepts. The completed power supply will be used throughout Year 1 for powering all circuits.

**See**: `projects/DUAL_STEPDOWN_CONVERTER.md` for complete project guide and `projects/STEPDOWN_CONVERTER_THEORY.md` for theory material.

### Toroidal Inductor Module: Prerequisite for MPPT Project

**Location**: `projects/TOROIDAL_INDUCTOR_MODULE.md`

A comprehensive 2-3 week module on toroidal inductors covering theory, construction, calculations, and practical applications. This module:
- Teaches how inductors work and store energy
- Explains toroidal inductor advantages and construction
- Includes hands-on project to build a custom toroidal inductor
- Covers selecting and using off-the-shelf inductors
- **REQUIRED PREREQUISITE** for MPPT Solar Charge Controller project

**When to Use**: Complete before attempting MPPT Solar Charge Controller capstone project. Can be integrated into Term 2 or Term 3.

**See**: `projects/TOROIDAL_INDUCTOR_MODULE.md` for complete module guide.

### MPPT Solar Charge Controller: Optional Capstone Project

**Location**: `projects/MPPT_SOLAR_CHARGE_CONTROLLER_CAPSTONE.md`

An advanced 4-6 week optional capstone project to build a 1kW MPPT (Maximum Power Point Tracking) solar charge controller. This project:
- Applies Year 1 step-down converter knowledge to real-world renewable energy
- Introduces power electronics, microcontrollers (ESP32), and MPPT algorithms
- Builds a practical solar energy system component
- Requires teacher/parent assistance (high-power electronics, safety critical)
- **REQUIRES**: Completion of Toroidal Inductor Module

**When to Use**: Optional end-of-year capstone for students who want an advanced challenge. Requires completion of Year 1 curriculum, strong understanding of electronics fundamentals, and completion of Toroidal Inductor Module.

**See**: `projects/MPPT_SOLAR_CHARGE_CONTROLLER_CAPSTONE.md` for complete project guide.

**Reference**: [Instructables: DIY 1kW MPPT Solar Charge Controller](https://www.instructables.com/DIY-1kW-MPPT-Solar-Charge-Controller/) and [YouTube Tutorial](https://www.youtube.com/watch?v=ShXNJM6uHLM)

### 4500W Pure Sine Wave Inverter: Optional Advanced Project

**Location**: `projects/SINE_WAVE_INVERTER_PROJECT.md`

An advanced 4-6 week optional project to build a 4500W pure sine wave inverter using 8 IRFZ44N MOSFETs. This project:
- Converts 12V/24V DC to 110V/220V AC (pure sine wave)
- Introduces H-bridge circuits, PWM sine wave generation, and transformer operation
- Complements MPPT project for complete solar power system
- **REQUIRES**: Mandatory teacher/parent assistance (high-power, high-voltage, safety critical)

**When to Use**: Optional advanced project for students who want to build a complete solar power system. Requires completion of Year 1 curriculum, strong understanding of power electronics, and completion of MPPT project recommended.

**See**: `projects/SINE_WAVE_INVERTER_PROJECT.md` for complete project guide.

**Reference**: [YouTube: 4500W Pure Sine Wave Inverter Tutorial](https://www.youtube.com/watch?v=QS-aeVLagxA) and [Circuits DIY: IRFZ44N Inverter Circuit](https://www.circuits-diy.com/inverter-circuit-using-irfz44-mosfets-diy-electronics/)

**⚠️ CRITICAL**: This project involves **HIGH POWER (4500W)** and **HIGH VOLTAGE (110V/220V AC)**. **DEATH OR SEVERE INJURY** can result from improper handling. **MANDATORY TEACHER/PARENT SUPERVISION** required.

## Optional Workshops

**Practical Electronics for Inventors Workshops**: Additional hands-on workshops based on "Practical Electronics for Inventors, Fourth Edition" are available in `workshops/PRACTICAL_ELECTRONICS_WORKSHOPS.md`. These workshops:
- Provide extra practice with curriculum concepts
- Make learning more enjoyable with fun projects
- Can be run as enrichment, homework, or club activities
- Directly support Year 1 learning objectives

See the workshops document for 12 different workshop activities spanning Terms 1-2.

## Assessment

- **Formative**: Weekly practical assessments
- **Summative**: Term projects demonstrating understanding
- **Portfolio**: Students document their learning journey

See `TermX/assessments/` folders for detailed rubrics.

## Prerequisites

- None! This is the entry point for the curriculum.
- Students should be comfortable with basic arithmetic.
- Interest in hands-on building and experimentation.

## Delivery Options

This year can be delivered as:
- After-school club
- Elective module
- Enrichment track
- Pre-GCSE option
- Integrated into science/technology curriculum

## Safety

**Critical**: All lessons begin with safety briefings. Students must:
- Understand electrical safety
- Know how to use tools properly
- Follow lab protocols
- Report any issues immediately

## Quick Start Guide

**Week 1, Session 1**:
1. Teacher: Read `Term1/teaching/Week01-02_TeachingGuide.md`
2. Students: Read `Term1/reading/01_ElectricityBasics.md`
3. Class: Theory session using `Term1/theory/Week01-02_ElectricityBasics.md`
4. Class: Lab session using `Term1/labs/Lab01-02_LabIntroduction.md`

**This pattern continues for all 36 weeks!**

---

*Year 1: Building the foundation for understanding computers*
