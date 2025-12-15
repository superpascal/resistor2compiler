# Keyboard and Input Interface: Curriculum Integration Analysis

## Overview

This document analyzes keyboard and input device integration throughout the Resistor2Compiler curriculum. It determines what input methods are feasible at each stage, from simple buttons in SAP-1 to full PS/2 keyboard interface in Year 6.

**Purpose**: Understand input device progression and determine curriculum integration points.

**Key Question**: At what stage can students actually interface a keyboard with their computer?

---

## Current State Analysis

### Year 3: SAP-1 Input (Buttons)

**Current Implementation**:
- **Single-step button**: Manual step-through of CPU cycles
- **Run/halt switch**: Control CPU execution
- **Memory programming**: Manual switches for program/data entry
- **No keyboard**: SAP-1 is too simple for keyboard interface

**Ben Eater's SAP-1 Approach**:
- Uses **buttons and switches** for input
- **Separate from LCD**: Input and output are separate (educational value)
- **Manual control**: Students manually control CPU operation
- **Simple interface**: Direct button-to-control-signal connections

**Why No Keyboard?**:
- **Limited instruction set**: SAP-1 has ~6-8 instructions
- **No interrupt capability**: Can't handle keyboard interrupts
- **No serial interface**: No hardware for PS/2 protocol
- **Educational focus**: Buttons teach input fundamentals without complexity

### Year 6: PS/2 Keyboard (Planned)

**Planned Implementation**:
- **PS/2 keyboard interface**: Full keyboard support
- **Device driver**: Keyboard driver in software
- **Interrupt support**: Keyboard interrupts
- **Key processing**: Scan code translation
- **Input API**: High-level input interface

**Hardware Requirements**:
- **65C816 CPU**: Capable of handling interrupts
- **Serial interface**: PS/2 protocol (clock + data)
- **Interrupt controller**: Handle keyboard interrupts
- **Sufficient memory**: Buffer key presses

---

## Input Device Progression

### Stage 1: Simple Buttons (Year 3 - SAP-1)

**What**: Direct button-to-control-signal connections

**Implementation**:
- **Single-step button**: Triggers one CPU cycle
- **Run/halt switch**: Controls continuous execution
- **Reset button**: Resets CPU state
- **Memory switches**: Manual program/data entry

**Educational Value**:
- ✅ **Direct control**: Students see button → signal → CPU action
- ✅ **Simple interface**: No protocol, no encoding
- ✅ **Foundation**: Understands that input is just signals
- ✅ **Debugging**: Manual control for debugging

**Limitations**:
- ❌ **No text input**: Can't type characters
- ❌ **Manual only**: Requires manual button presses
- ❌ **Limited functionality**: Only control signals, no data

**When**: **Year 3 SAP-1** (already implemented)

### Stage 2: Matrix Keypad (Year 4 - Possible Enhancement)

**What**: 4×4 or 4×3 matrix keypad for numeric/text input

**Implementation**:
- **Matrix scanning**: Scan rows/columns to detect key presses
- **Debouncing**: Software debouncing of key presses
- **Key encoding**: Convert key position to character code
- **Memory-mapped I/O**: Keypad appears as I/O port

**Hardware Requirements**:
- **Matrix keypad**: 4×4 or 4×3 keypad module
- **I/O port**: 8-bit I/O port (4 rows + 4 columns)
- **Pull-up resistors**: For column inputs
- **Scanning logic**: Software or hardware scanning

**Educational Value**:
- ✅ **Matrix scanning**: Learn keypad scanning technique
- ✅ **Debouncing**: Understand switch bounce and debouncing
- ✅ **I/O programming**: Memory-mapped I/O for input
- ✅ **Text input**: Can enter numbers and some characters

**Limitations**:
- ❌ **Limited keys**: Only 12-16 keys
- ❌ **No full keyboard**: Can't type all characters
- ❌ **Polling required**: Must poll keypad regularly

**When**: **Year 4** (possible SAP-1 enhancement or 65C816 system)

**Feasibility**: **HIGH** - Simple hardware, educational value

### Stage 3: PS/2 Keyboard (Year 5-6 - 65C816 System)

**What**: Standard PS/2 keyboard interface

**Implementation**:
- **PS/2 protocol**: Serial protocol (clock + data)
- **Scan codes**: Receive key press/release codes
- **Interrupt support**: Keyboard interrupts
- **Key translation**: Convert scan codes to key codes
- **Input buffering**: Buffer key presses

**Hardware Requirements**:
- **65C816 CPU**: Interrupt capability
- **PS/2 interface**: Clock and data lines
- **Interrupt controller**: Handle keyboard interrupts
- **Pull-up resistors**: For PS/2 lines
- **Sufficient memory**: For key buffer

**Educational Value**:
- ✅ **Serial protocol**: Learn PS/2 serial protocol
- ✅ **Interrupts**: Understand interrupt-driven I/O
- ✅ **Scan codes**: Learn keyboard scan code system
- ✅ **Full keyboard**: Complete text input capability

**Limitations**:
- ❌ **Complex protocol**: PS/2 protocol is more complex
- ❌ **Requires interrupts**: Needs interrupt capability
- ❌ **More hardware**: Requires interrupt controller

**When**: **Year 5-6** (65C816 system with interrupts)

**Feasibility**: **MEDIUM-HIGH** - Requires interrupt capability, but standard interface

---

## Detailed Analysis by Year

### Year 2: Manual Computer Input

**Current State**: Manual switches and buttons for data entry

**Input Method**:
- **Switches**: Manual data entry
- **Buttons**: Control operations
- **No keyboard**: Too early in curriculum

**Educational Focus**: Understanding that input is electrical signals

### Year 3: SAP-1 Button Interface

**Current State**: ✅ **IMPLEMENTED** - Buttons for control

**Input Methods**:
1. **Single-step button**: Manual CPU cycle stepping
2. **Run/halt switch**: Execution control
3. **Reset button**: CPU reset
4. **Memory switches**: Manual program/data entry

**Hardware**:
- **Direct connections**: Buttons → control signals
- **No encoding**: Direct signal control
- **No protocol**: Simple on/off signals

**Educational Value**:
- Students see direct button → signal → CPU action
- Foundation for understanding input devices
- Simple enough for early learning

**Limitations**:
- No text input capability
- Manual operation only
- Limited to control signals

**Recommendation**: **KEEP** - Essential for SAP-1, provides foundation

### Year 4: Possible Matrix Keypad

**Current State**: **NOT IMPLEMENTED** - Could be added

**Proposed Input Method**: **4×4 Matrix Keypad**

**Why Year 4?**:
- **Enhanced SAP-1**: More capable system
- **I/O expansion**: Can add I/O ports
- **Educational progression**: Next step after buttons
- **Before keyboard**: Simpler than PS/2 keyboard

**Implementation Options**:

**Option A: Matrix Keypad on Enhanced SAP-1**
- Add I/O port to SAP-1
- Connect 4×4 keypad
- Software scanning
- **Feasibility**: **MEDIUM** - Requires I/O expansion

**Option B: Matrix Keypad on 65C816 System**
- Use 65C816 I/O capabilities
- Connect 4×4 keypad
- Software scanning
- **Feasibility**: **HIGH** - 65C816 has I/O capability

**Hardware Requirements**:
- **4×4 Matrix Keypad**: ~$3-5
- **I/O Port**: 8-bit port (4 rows + 4 columns)
- **Pull-up resistors**: 10kΩ for columns
- **Scanning logic**: Software-based

**Educational Value**:
- ✅ Matrix scanning technique
- ✅ Debouncing concepts
- ✅ I/O port programming
- ✅ Text/numeric input

**Recommendation**: **CONSIDER** - Good educational progression, feasible in Year 4

### Year 5: PS/2 Keyboard Preparation

**Current State**: **NOT IMPLEMENTED** - Preparation phase

**Focus**: Prepare for keyboard interface

**Learning Objectives**:
- Understand serial protocols
- Learn interrupt handling
- Study PS/2 protocol
- Design keyboard interface

**Recommendation**: **PREPARATION** - Theory and design, not implementation yet

### Year 6: PS/2 Keyboard Interface

**Current State**: ✅ **PLANNED** - Device driver development

**Implementation**: **PS/2 Keyboard Driver**

**Hardware**:
- **PS/2 keyboard**: Standard PC keyboard
- **PS/2 interface**: Clock + data lines
- **Interrupt support**: Keyboard interrupts
- **65C816 system**: Full interrupt capability

**Software**:
- **PS/2 protocol handler**: Serial protocol implementation
- **Scan code translation**: Convert to key codes
- **Input buffer**: Buffer key presses
- **Input API**: High-level interface

**Educational Value**:
- ✅ Serial protocol implementation
- ✅ Interrupt-driven I/O
- ✅ Device driver development
- ✅ Full keyboard support

**Recommendation**: **IMPLEMENT** - Essential for Year 6 system

---

## Technical Feasibility Analysis

### Matrix Keypad (Year 4)

**Hardware Complexity**: **LOW-MEDIUM**
- Simple keypad module
- Basic I/O port
- Pull-up resistors
- **Feasible**: ✅ Yes

**Software Complexity**: **MEDIUM**
- Matrix scanning algorithm
- Debouncing logic
- Key encoding
- **Feasible**: ✅ Yes

**Educational Value**: **HIGH**
- Teaches matrix scanning
- I/O port programming
- Debouncing concepts
- **Recommended**: ✅ Yes

**Cost**: **LOW**
- Keypad: ~$3-5
- Components: ~$2-3
- **Total**: ~$5-8

**Recommendation**: **IMPLEMENT in Year 4** - Good progression from buttons

### PS/2 Keyboard (Year 6)

**Hardware Complexity**: **MEDIUM**
- PS/2 interface (2 wires)
- Interrupt controller
- Pull-up resistors
- **Feasible**: ✅ Yes (with 65C816)

**Software Complexity**: **HIGH**
- PS/2 protocol implementation
- Interrupt handling
- Scan code translation
- **Feasible**: ✅ Yes (with interrupts)

**Educational Value**: **HIGH**
- Serial protocol
- Interrupt-driven I/O
- Device driver development
- **Recommended**: ✅ Yes

**Cost**: **LOW**
- PS/2 keyboard: ~$5-15 (or reuse existing)
- Components: ~$2-3
- **Total**: ~$7-18

**Recommendation**: **IMPLEMENT in Year 6** - Essential for full system

---

## Curriculum Integration Recommendations

### Year 3: Keep Button Interface

**Status**: ✅ **KEEP CURRENT IMPLEMENTATION**

**Rationale**:
- Essential for SAP-1 operation
- Provides foundation for input understanding
- Simple enough for early learning
- Aligns with Ben Eater's approach

**No Changes Needed**: Current button interface is appropriate for SAP-1

### Year 4: Add Matrix Keypad (Optional Enhancement)

**Status**: ⚠️ **CONSIDER ADDING**

**Proposed Integration**:
- **Term 1 or Term 2**: Matrix keypad interface
- **I/O Subsystems**: Add keypad to I/O module
- **Lab Activity**: Interface 4×4 keypad
- **Programming**: Keypad scanning and input

**Rationale**:
- Good educational progression from buttons
- Feasible with enhanced SAP-1 or 65C816
- Teaches matrix scanning and I/O
- Prepares for PS/2 keyboard

**Recommendation**: **OPTIONAL** - Can be added if time permits, but not critical

### Year 5: PS/2 Keyboard Preparation

**Status**: 📚 **THEORY AND DESIGN**

**Focus**:
- Study PS/2 protocol
- Design keyboard interface
- Plan interrupt handling
- Prepare for Year 6 implementation

**No Hardware**: Just theory and design

### Year 6: PS/2 Keyboard Implementation

**Status**: ✅ **REQUIRED** - Already planned

**Integration**:
- **Week 19**: Input drivers (keyboard, gamepad)
- **Device driver**: PS/2 keyboard driver
- **Input API**: High-level input interface
- **System integration**: Full keyboard support

**Rationale**:
- Essential for complete system
- Already in curriculum plan
- Full interrupt capability available
- Standard interface

**Recommendation**: **KEEP AS PLANNED**

---

## Educational Progression Summary

### Input Device Evolution

```
Year 2: Manual Switches
    ↓
Year 3: Buttons (SAP-1) ✅ IMPLEMENTED
    ↓
Year 4: Matrix Keypad (Optional) ⚠️ CONSIDER
    ↓
Year 5: PS/2 Theory (Preparation) 📚 THEORY
    ↓
Year 6: PS/2 Keyboard ✅ PLANNED
```

### Complexity Progression

**Simple → Complex**:
1. **Buttons**: Direct signals, no protocol
2. **Matrix Keypad**: Scanning, debouncing, I/O
3. **PS/2 Keyboard**: Serial protocol, interrupts, scan codes

**Educational Value**:
- Each stage builds on previous
- Progressive complexity
- Foundation → Advanced

---

## Key Findings

### What's Actually Possible

**Year 3 (SAP-1)**:
- ✅ **Buttons**: Direct control signals
- ❌ **Keyboard**: Not feasible (no interrupts, too simple)

**Year 4 (Enhanced SAP-1 or 65C816)**:
- ✅ **Buttons**: Continue using
- ✅ **Matrix Keypad**: Feasible with I/O port
- ❌ **PS/2 Keyboard**: Not yet (no interrupts)

**Year 5 (65C816 System)**:
- ✅ **Buttons**: Still available
- ✅ **Matrix Keypad**: If implemented in Year 4
- 📚 **PS/2 Theory**: Preparation only

**Year 6 (65C816 System)**:
- ✅ **Buttons**: Still available
- ✅ **Matrix Keypad**: If implemented
- ✅ **PS/2 Keyboard**: Full implementation

### Recommendations

1. **Year 3**: **KEEP** button interface (already appropriate)
2. **Year 4**: **CONSIDER** matrix keypad (optional enhancement)
3. **Year 5**: **PREPARE** for PS/2 keyboard (theory only)
4. **Year 6**: **IMPLEMENT** PS/2 keyboard (already planned)

---

## Next Steps

### Immediate Actions

1. **Document Current State**: 
   - Document SAP-1 button interface
   - Create button interface guide

2. **Year 4 Decision**:
   - Decide if matrix keypad should be added
   - If yes, create integration plan

3. **Year 6 Preparation**:
   - Ensure PS/2 keyboard is properly planned
   - Verify hardware requirements

### Curriculum Materials Needed

1. **Button Interface Guide** (Year 3):
   - How buttons connect to SAP-1
   - Button signal routing
   - Control signal generation

2. **Matrix Keypad Guide** (Year 4, if added):
   - Keypad hardware connection
   - Scanning algorithm
   - Debouncing techniques
   - I/O port programming

3. **PS/2 Keyboard Guide** (Year 6):
   - PS/2 protocol details
   - Hardware interface
   - Interrupt handling
   - Scan code translation
   - Driver implementation

---

## Conclusion

**Current State**:
- ✅ Year 3: Buttons (appropriate for SAP-1)
- ⚠️ Year 4: Could add matrix keypad (optional)
- 📚 Year 5: PS/2 theory (preparation)
- ✅ Year 6: PS/2 keyboard (planned)

**Key Insight**: 
- **Buttons are sufficient for SAP-1** (Year 3)
- **Matrix keypad is feasible in Year 4** (optional enhancement)
- **PS/2 keyboard requires Year 6** (needs interrupts)

**Recommendation**: 
- **Keep Year 3 buttons** (essential, appropriate)
- **Consider Year 4 matrix keypad** (good progression, optional)
- **Keep Year 6 PS/2 keyboard** (essential, already planned)

---

**Document Created**: 2025-12-16  
**Purpose**: Analyze keyboard/input interface integration  
**Status**: Analysis complete, recommendations provided

