# LCD Display Output Guide for Early Years

## Overview

This document provides guidance on implementing LCD character display output for Years 2-3 and early Year 4, before students build the Ben Eater VGA project. LCD displays provide essential output capability for students to see their computer's operation and program results.

**Purpose**: Ensure students have functional output displays throughout the curriculum, from Year 2 manual computers through Year 3 SAP-1 to Year 4 (before VGA project).

---

## Quick Recommendation: Year 3 SAP-1 LCD

**Best Option for Year 3 SAP-1**: **Matrix Orbital LCD2041-GW-V-E (20×4 Parallel LCD)**

- **Part Number**: Matrix Orbital LCD2041-GW-V-E
- **Interface**: **Parallel 8-bit** (HD44780-compatible)
- **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
- **Educational Value**: Maximum - direct bus connection, all signals visible
- **Availability**: Mouser Electronics
- **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)

**Why This LCD for Year 3?**
- ✅ **Parallel interface**: Direct bus connection (maximum educational value)
- ✅ **No touch/buttons**: Input separate (aligns with Ben Eater's educational approach)
- ✅ **20×4 size**: More display area than 16×2
- ✅ **HD44780-compatible**: Standard controller, well-documented
- ✅ **Professional quality**: Reliable manufacturer

**Comparison**:
- **Matrix Orbital LCD2041-GW-V-E**: 20×4 parallel interface, maximum educational value ✅ **RECOMMENDED for Year 3**
- **Microtips Technology NMTC-S20200XFYHSAY-10B**: 20×2 parallel interface, budget alternative ✅ **BUDGET OPTION**
- **HD44780 + I2C Backpack**: ~$7-15, easier wiring but less educational (I2C adapter is black box)
- **Other 20×4 HD44780 LCDs**: Parallel interface, alternative if Matrix Orbital not available

**See detailed comparison below for all options.**

---

## Why LCD Displays?

### Educational Benefits

- **Immediate Feedback**: Students can see program output and system state
- **Text Output**: Display messages, numbers, and program results
- **Simple Interface**: Easier than video hardware for early years
- **Foundation for Later**: Understanding character output prepares for Year 4 VGA and Year 6 video drivers

### Alignment with Ben Eater's SAP-1

Ben Eater's SAP-1 project uses a **2-row or 4-row LCD character display** for output. This aligns perfectly with our curriculum approach:
- Simple, understandable interface
- Educational value (students see how character data becomes display)
- Foundation for later video hardware

---

## LCD Display Options

### HD44780-Based Character LCDs

**Standard Interface**: Most character LCDs use the HD44780 controller (or compatible chips like KS0066).

**Common Sizes**:
- **16×2** (16 characters × 2 rows) - Most common, good for SAP-1
- **20×4** (20 characters × 4 rows) - More display area, better for debugging
- **16×4** (16 characters × 4 rows) - Good balance
- **20×2** (20 characters × 2 rows) - Wider display

**Recommendation**: **20×4 LCD** provides best educational value:
- More display area for program output
- Can show multiple values simultaneously
- Better for debugging and system status
- Still simple enough for early years

### Interface Options

#### Option 1: I2C Backpack Adapter (RECOMMENDED - Lowest Barrier to Entry)

**Connection**: HD44780 LCD with I2C backpack/adapter module (PCF8574-based)

**Advantages**:
- ✅ **Lowest Barrier**: Easiest to integrate, minimal wiring
- ✅ **Fewer Wires**: Only 4 wires (VCC, GND, SDA, SCL)
- ✅ **Low Cost**: I2C adapter ~$2-5, total system ~$7-15
- ✅ **Easy Integration**: Simple I2C interface
- ✅ **Widely Available**: Pre-made modules readily available
- ✅ **Well Documented**: Extensive examples and libraries
- ✅ **Standard**: I2C is well-understood protocol

**Disadvantages**:
- ❌ **Small Black Box**: I2C adapter hides parallel interface details
- ❌ **Less Transparent**: Students don't see direct bus connection
- ❌ **Requires I2C**: CPU/system needs I2C capability

**Wiring**:
```
LCD I2C Backpack:
VCC → 5V
GND → Ground  
SDA → I2C Data (with pull-up resistor, typically 4.7kΩ)
SCL → I2C Clock (with pull-up resistor, typically 4.7kΩ)
```

**I2C Address**: Typically 0x27 or 0x3F (some adapters have address jumpers)

**Cost**: LCD (~$5-10) + I2C adapter (~$2-5) = **~$7-15 total**

**Recommendation**: **Use I2C backpack for lowest barrier to entry**, especially for Years 2-3. This is the easiest option and gets students displaying output quickly.

#### Option 2: Parallel Interface (Direct) - Most Educational

**Connection**: Direct 8-bit parallel connection to data bus

**Advantages**:
- ✅ **Most Educational**: Students see direct bus connection
- ✅ **Transparent**: All signals visible and understandable
- ✅ **Foundation**: Prepares for understanding memory-mapped I/O
- ✅ **No Black Boxes**: Everything is visible and understandable

**Disadvantages**:
- ❌ **More Pins**: Requires 8 data lines + control lines (~11-14 wires)
- ❌ **Bus Loading**: Must use tri-state buffers if on shared bus
- ❌ **More Complex**: More wiring and signal management

**Interface Signals**:
- **D0-D7**: 8-bit data bus
- **RS** (Register Select): 0 = command, 1 = data
- **E** (Enable): Clock pulse for data transfer
- **R/W**: Read/Write (can tie to ground for write-only)
- **VSS, VDD, V0**: Power and contrast

**Memory-Mapped I/O Example**:
```
Address $9000: Data register (RS=1)
Address $9001: Command register (RS=0)
Address $9002: Status register (read-only)
```

**Cost**: LCD (~$5-10) + supporting components (~$2-3) = **~$7-13 total**

**Recommendation**: Use **parallel interface for maximum educational value** in Year 3 SAP-1, especially for advanced students who want to understand bus interfacing.

#### Option 3: Matrix Orbital Intelligent Display (Not Recommended for Curriculum)

**Connection**: Matrix Orbital MOI-AL204B intelligent LCD via I2C

**Specifications**: See [Matrix Orbital MOI-AL204B](https://www.matrixorbital.com/matrix-orbital/economy-display/moi-al204b)

**Advantages**:
- ✅ Very easy integration (I2C, intelligent controller)
- ✅ Additional features (GPOs, bar graphs, software contrast)
- ✅ Professional quality
- ✅ Good documentation

**Disadvantages**:
- ❌ **High Cost**: ~$77.89 USD (vs ~$7-15 for standard LCD + adapter)
- ❌ **Proprietary Protocol**: Matrix Orbital command protocol (less standard)
- ❌ **Large Black Box**: Intelligent controller hides all implementation
- ❌ **Less Educational**: Too much abstraction for learning
- ❌ **Overkill**: More features than needed for educational projects

**Recommendation**: **Not recommended for curriculum** due to:
1. **Cost**: ~5-10× more expensive than standard solution
2. **Educational Value**: Too much abstraction, less learning
3. **Barrier to Entry**: High cost creates barrier for students/schools

**Best For**: Commercial products, not educational curriculum

---

## Integration by Year

### Year 2: Manual Computer Output

**Purpose**: Display system state and simple output

**Implementation**:
- **Recommended**: I2C backpack adapter (lowest barrier to entry)
- **Alternative**: Parallel LCD interface (more educational, more complex)
- Display counter values, register contents
- Show manual computer operation

**LCD Size**: 16×2 or 20×4 (**20×4 recommended** for more display area)

**Interface Options**:
1. **I2C Backpack** (Recommended - Easiest): 4 wires, ~$7-15 total cost
2. **Parallel Interface** (More Educational): Direct bus connection, ~$7-13 total cost

**Educational Value**: Students learn:
- Character display basics
- I2C communication (if using I2C backpack)
- Memory-mapped I/O concepts (if using parallel)
- Bus interfacing (if using parallel)

### Year 3: SAP-1 Output Display

**Purpose**: Display program output and system state

**Implementation Options**:

**Option A: Matrix Orbital LCD2041-GW-V-E (REQUIRED - Parallel Interface)**
- **Part Number**: Matrix Orbital LCD2041-GW-V-E
- **Interface**: Parallel 8-bit (HD44780-compatible)
- **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
- **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)
- Direct bus connection for maximum educational value
- Memory-mapped I/O at specific address
- **Best for**: **Year 3 SAP-1 (REQUIRED)** - Maximum educational value, Ben Eater alignment

**Option B: Other HD44780 Parallel LCD (Alternative)**
- Standard 20×4 HD44780 LCD with parallel interface
- Direct bus connection for educational value
- Memory-mapped I/O at specific address
- **Best for**: Alternative if Matrix Orbital LCD2041 not available

**Option C: I2C Backpack (Not Recommended for Year 3)**
- I2C backpack adapter for minimal wiring
- 4 wires (VCC, GND, SDA, SCL)
- **Not recommended**: I2C adapter is black box, reduces educational value
- **Best for**: Year 2 optional use only (not for Year 3 SAP-1)

**LCD Size**: **20×4 recommended** (matches Ben Eater's 4-row option, more display area)

**Memory Map Example** (for SAP-1, if using parallel interface):
```
$0E: LCD Data Register (write data to display)
$0F: LCD Command Register (send commands)
```

**I2C Interface** (if using I2C backpack):
- I2C address: 0x27 or 0x3F
- Use I2C write commands to send data/commands

**SAP-1 Integration**:
- Connect LCD to output port (OUT instruction)
- Display accumulator value after operations
- Show program execution results
- Display memory contents for debugging

**Ben Eater Alignment**: Ben Eater's SAP-1 uses 2-row or 4-row LCD. We recommend 4-row (20×4) for better educational value and more display capability.

**Educational Value**: Students learn:
- Output device interfacing
- Character display programming
- Memory-mapped I/O in practice
- Foundation for Year 4 VGA and Year 6 video drivers

### Year 4: Pre-VGA Output

**Purpose**: Output display before building Ben Eater VGA project

**Implementation**:
- Continue using LCD from Year 3
- Or upgrade to larger LCD (20×4 or multiple displays)
- Use for system status, debugging, program output

**Timeline**: 
- **Weeks 1-21**: Use LCD for output
- **Weeks 22-24**: Build Ben Eater VGA project (replaces LCD for video output)

**Transition**: LCD provides output until VGA project is complete, then VGA becomes primary output.

---

## Technical Implementation

### HD44780 LCD Controller

**Key Features**:
- **Character Generator**: Built-in character set (ASCII)
- **Display Memory**: Internal RAM for display content
- **Cursor Control**: Software-controlled cursor
- **Command Set**: Standard command set for initialization and control

**Common Commands**:
- **Clear Display**: `0x01`
- **Return Home**: `0x02`
- **Entry Mode Set**: `0x04` (cursor direction)
- **Display Control**: `0x08` (display on/off, cursor on/off)
- **Function Set**: `0x20` (interface width, lines, font)
- **Set DDRAM Address**: `0x80 + address` (cursor position)

### Parallel Interface Circuit

**Components Needed**:
- HD44780-compatible LCD (20×4 recommended)
- Tri-state buffers (74HC245) if on shared bus
- Address decoder for chip select
- Pull-up resistors for control lines
- Potentiometer for contrast (V0)

**Circuit Design**:
```
SAP-1 Data Bus → 74HC245 (tri-state) → LCD D0-D7
SAP-1 Address → Decoder → LCD CS (chip select)
SAP-1 Control → Logic → LCD RS, E, R/W
```

**Power**: +5V for LCD (VDD), ground (VSS), contrast adjustment (V0 via potentiometer)

### Initialization Sequence

**Required Steps**:
1. Power-on delay (wait for LCD to initialize)
2. Function set command (8-bit mode, 2-line, 5×8 font)
3. Display control (display on, cursor off)
4. Clear display
5. Entry mode set (increment cursor)

**Assembly Example** (for SAP-1 or 65C816):
```assembly
; LCD initialization
init_lcd:
    ; Wait for LCD to power up
    JSR delay_50ms
    
    ; Function set: 8-bit, 2-line, 5×8 font
    LDA #$38
    STA LCD_CMD
    
    ; Display control: display on, cursor off
    LDA #$0C
    STA LCD_CMD
    
    ; Clear display
    LDA #$01
    STA LCD_CMD
    JSR delay_2ms
    
    ; Entry mode: increment cursor
    LDA #$06
    STA LCD_CMD
    
    RTS
```

### Display Text Example

**Simple Text Output**:
```assembly
; Display "HELLO" on LCD
display_hello:
    LDA #'H'
    STA LCD_DATA
    LDA #'E'
    STA LCD_DATA
    LDA #'L'
    STA LCD_DATA
    LDA #'L'
    STA LCD_DATA
    LDA #'O'
    STA LCD_DATA
    RTS
```

**Display Numbers**:
```assembly
; Display accumulator value as hex
display_hex:
    PHA
    LSR A
    LSR A
    LSR A
    LSR A
    JSR hex_digit
    PLA
    AND #$0F
    JSR hex_digit
    RTS

hex_digit:
    CMP #$0A
    BCC digit_0_9
    ADC #$06        ; A-F
digit_0_9:
    ADC #$30        ; ASCII '0'-'9' or 'A'-'F'
    STA LCD_DATA
    RTS
```

---

## Component Recommendations

### Year 3 SAP-1: Matrix Orbital LCD2041-GW-V-E (REQUIRED)

**Best Option for Year 3 SAP-1**: **Matrix Orbital LCD2041-GW-V-E (20×4 Parallel LCD)**

**Why This LCD for Year 3?**
- ✅ **Parallel Interface**: Direct bus connection (maximum educational value)
- ✅ **No Touch/Buttons**: Input separate (aligns with Ben Eater's educational approach)
- ✅ **20×4 Size**: More display area than 16×2
- ✅ **HD44780-Compatible**: Standard controller, well-documented
- ✅ **Professional Quality**: Reliable manufacturer (Matrix Orbital)
- ✅ **Available**: Mouser Electronics (EU and US)

**Specifications**:
- **Part Number**: Matrix Orbital LCD2041-GW-V-E
- **Display**: 20 characters × 4 rows
- **Interface**: Parallel 8-bit (HD44780-compatible)
- **Controller**: HD44780 or compatible
- **Power**: 5V
- **Features**: 
  - **No touch screen** (input separate, per Ben Eater approach)
  - **No buttons** (input separate, per Ben Eater approach)
  - Pure display for educational value
- **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)

**Supporting Components** (for parallel interface):
- **Tri-State Buffers**: 74HC245 (for data bus)
- **Address Decoder**: 74HC138 (for chip select)
- **Pull-up Resistors**: 10kΩ for control lines
- **Potentiometer**: 10kΩ for contrast adjustment
- **Decoupling Capacitors**: 0.1µF near LCD power pins

**Educational Value**: 
- Students see direct bus connection
- All signals visible and understandable
- Understand memory-mapped I/O
- Foundation for Year 4 VGA project
- Aligns with Ben Eater's SAP-1 approach

### Alternative Options

**Option 1B: Other HD44780 LCDs + I2C Backpack (Year 2 Only, Not for Year 3)**

**Components**:
- Standard 20×4 HD44780 LCD (~$5-10)
- I2C backpack adapter (~$2-5)
- **Total Cost**: **~$7-15**

**Why Not for Year 3?**
- ❌ I2C adapter is black box (reduces educational value)
- ❌ Doesn't show direct bus connection
- ❌ Less transparent than parallel interface

**Best For**: Year 2 optional use only (not for Year 3 SAP-1)

### LCD Display Options Comparison

#### Option 1: Matrix Orbital LCD2041-GW-V-E (REQUIRED for Year 3 SAP-1)

**Components**:
- **Matrix Orbital LCD2041-GW-V-E** (20×4 parallel LCD)
- Supporting components (tri-state buffers, address decoder, etc.)

**Specifications**:
- **Part Number**: Matrix Orbital LCD2041-GW-V-E
- **Display**: 20 characters × 4 rows
- **Interface**: **Parallel 8-bit** (HD44780-compatible)
- **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
- **Availability**: Mouser Electronics
- **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)

**Advantages**:
- ✅ **Maximum educational value**: Parallel interface shows direct bus connection
- ✅ **No black boxes**: All signals visible and understandable
- ✅ **Ben Eater alignment**: No touch/buttons (input separate for educational purposes)
- ✅ **Professional quality**: Reliable manufacturer
- ✅ **20×4 size**: More display area than 16×2
- ✅ **HD44780-compatible**: Standard controller, well-documented

**Disadvantages**:
- ❌ More wiring (8 data lines + control lines)
- ❌ Requires bus management (tri-state buffers, address decoding)
- ❌ More complex than I2C solution

**Best For**: **Year 3 SAP-1 (REQUIRED)** - Maximum educational value, Ben Eater alignment

#### Option 1B: Microtips Technology NMTC-S20200XFYHSAY-10B (Budget Alternative - 20×2 Parallel LCD)

**Components**:
- **Microtips Technology NMTC-S20200XFYHSAY-10B** (20×2 parallel LCD)
- Supporting components (tri-state buffers, address decoder, etc.)

**Specifications**:
- **Part Number**: Microtips Technology NMTC-S20200XFYHSAY-10B
- **Display**: 20 characters × 2 rows
- **Interface**: **Parallel 8-bit** (HD44780-compatible)
- **Features**: No touch screen, no buttons (input separate per Ben Eater approach)
- **Availability**: Mouser Electronics
- **Mouser Link**: [NMTC-S20200XFYHSAY-10B](https://eu.mouser.com/ProductDetail/Microtips-Technology/NMTC-S20200XFYHSAY-10B)

**Advantages**:
- ✅ **Budget-friendly**: Lower cost than 20×4 LCD
- ✅ **Parallel interface**: Direct bus connection (maximum educational value)
- ✅ **No black boxes**: All signals visible and understandable
- ✅ **Ben Eater alignment**: No touch/buttons (input separate for educational purposes)
- ✅ **HD44780-compatible**: Standard controller, well-documented
- ✅ **20×2 size**: Adequate for SAP-1 output (matches Ben Eater's 2-row option)

**Disadvantages**:
- ❌ Less display area than 20×4 (2 rows vs 4 rows)
- ❌ More wiring (8 data lines + control lines)
- ❌ Requires bus management (tri-state buffers, address decoding)
- ❌ More complex than I2C solution

**Best For**: **Year 3 SAP-1 (Budget Option)** - Students with budget constraints, still provides maximum educational value with parallel interface

**Note**: While 20×4 LCD is recommended for more display area, this 20×2 LCD is a valid budget alternative that still provides the same educational value through its parallel interface.

#### Option 2: Other HD44780 LCDs - Parallel Interface (Alternative)

**Components**:
- Standard 20×4 HD44780 LCD (~$5-10)
- Tri-state buffers, address decoder (~$2-3)
- **Total: ~$7-13**

**Advantages**:
- ✅ Most educational (direct bus connection)
- ✅ All signals visible
- ✅ Foundation for memory-mapped I/O understanding
- ✅ No black boxes

**Disadvantages**:
- ❌ More wiring (8 data lines + control lines)
- ❌ More complex interface
- ❌ Requires bus management

**Best For**: **Alternative to Matrix Orbital LCD2041, if specific part not available**

#### Option 3: Matrix Orbital MOI-AL204B (Intelligent Display)

**Components**:
- Matrix Orbital MOI-AL204B intelligent LCD
- **Total: ~$77.89 USD** (single unit, lower in quantity)

**Specifications** (from [Matrix Orbital](https://www.matrixorbital.com/matrix-orbital/economy-display/moi-al204b)):
- 20×4 Character LCD
- I2C interface (100Kbps)
- Built-in ATMega8535 controller
- Matrix Orbital command protocol
- 3 General Purpose Outputs (GPOs)
- Software-controlled contrast and brightness
- Large format LCD

**Advantages**:
- ✅ Very easy integration (I2C, intelligent controller)
- ✅ Additional features (GPOs, bar graphs)
- ✅ Professional quality
- ✅ Good documentation and support
- ✅ Made in Canada, long life cycle

**Disadvantages**:
- ❌ **High cost** (~$77.89 vs ~$7-15 for standard LCD + adapter)
- ❌ Proprietary command protocol (less standard)
- ❌ Intelligent controller is larger black box
- ❌ Less educational (more abstraction)
- ❌ May be overkill for educational projects

**Best For**: Commercial products, projects requiring additional features, when cost is not primary concern

**Recommendation**: **Not recommended for curriculum** due to high cost and reduced educational value compared to standard HD44780 + I2C adapter.

### Standard HD44780 LCD Options

**Recommended**: **Matrix Orbital LCD2041-GW-V-E (20×4 Parallel LCD)**

**Specifications**:
- **Part Number**: Matrix Orbital LCD2041-GW-V-E
- **Display**: 20 characters × 4 rows
- **Interface**: **Parallel 8-bit** (HD44780-compatible)
- **Controller**: HD44780 or compatible
- **Power**: 5V
- **Features**: 
  - **No touch screen** (input separate, per Ben Eater approach)
  - **No buttons** (input separate, per Ben Eater approach)
  - Pure display for educational value
- **Availability**: Mouser Electronics (EU and US)
- **Mouser Link**: [LCD2041-GW-V-E](https://eu.mouser.com/ProductDetail/Matrix-Orbital/LCD2041-GW-V-E)

**Why This LCD?**
- ✅ **Parallel interface**: Direct bus connection (educational value)
- ✅ **No touch/buttons**: Input separate (aligns with Ben Eater's educational approach)
- ✅ **20×4 size**: More display area than 16×2
- ✅ **HD44780-compatible**: Standard controller, well-documented
- ✅ **Professional quality**: Matrix Orbital is reliable manufacturer
- ✅ **Available**: Readily available from Mouser

**Alternative Options**:

**Budget Alternative**: **Microtips Technology NMTC-S20200XFYHSAY-10B (20×2 Parallel LCD)**
- **Part Number**: Microtips Technology NMTC-S20200XFYHSAY-10B
- **Display**: 20 characters × 2 rows
- **Interface**: Parallel 8-bit (HD44780-compatible)
- **Mouser Link**: [NMTC-S20200XFYHSAY-10B](https://eu.mouser.com/ProductDetail/Microtips-Technology/NMTC-S20200XFYHSAY-10B)
- **Best For**: Students with budget constraints, still provides parallel interface educational value

**Other Options**:
- Other 20×4 HD44780-compatible LCDs from various manufacturers
- **16×2**: Smaller, cheaper (~$3-5), less display area
- **16×4**: Good balance, moderate cost
- **20×2**: Wider but fewer rows (see Microtips option above)

**Alternative Sizes**:
- **16×2**: Smaller, cheaper (~$3-5), less display area
- **16×4**: Good balance, moderate cost
- **20×2**: Wider but fewer rows

### Supporting Components

**Tri-State Buffers**: 74HC245 (if on shared bus)
**Address Decoder**: 74HC138 (for chip select)
**Pull-up Resistors**: 10kΩ for control lines
**Potentiometer**: 10kΩ for contrast adjustment
**Decoupling Capacitors**: 0.1µF near LCD power pins

---

## Integration with Ben Eater's SAP-1

### Ben Eater's Approach

Ben Eater's SAP-1 uses a **2-row or 4-row LCD character display** connected to the output port. This provides:
- Simple text output
- Display of accumulator values
- Program result display
- System status information

### Our Implementation

**Alignment**: We follow Ben Eater's approach but recommend **20×4 LCD** for:
- More display area (4 rows vs 2 rows)
- Better for debugging and system status
- More educational value (can show more information)

**Connection**: Parallel interface to SAP-1 output port, similar to Ben Eater's design.

**Educational Progression**:
1. **Year 2**: Learn LCD basics with manual computer
2. **Year 3**: Integrate LCD with SAP-1 (Ben Eater approach)
3. **Year 4**: Continue using LCD until VGA project
4. **Year 4, Weeks 22-24**: Build Ben Eater VGA (replaces LCD)
5. **Year 6**: Use professional video hardware (with understanding from VGA)

---

## Assessment and Learning Outcomes

### Year 2 Learning Outcomes

By end of Year 2, students can:
- Connect LCD to data bus
- Initialize LCD display
- Display text and numbers
- Understand memory-mapped I/O basics

### Year 3 Learning Outcomes

By end of Year 3, students can:
- Integrate LCD with SAP-1 output port
- Display program results on LCD
- Show system state (registers, memory)
- Understand character display programming
- Prepare for Year 4 VGA project

### Year 4 Learning Outcomes

By end of Year 4 (before VGA):
- Use LCD for system output and debugging
- Understand character vs. graphics display
- Appreciate why VGA project is needed (graphics capability)
- Transition from LCD to VGA output

---

## Troubleshooting

### Common Issues

**LCD Not Displaying**:
- Check power connections (5V, ground)
- Adjust contrast potentiometer
- Verify initialization sequence
- Check data/control line connections

**Garbled Text**:
- Verify timing (add delays between commands)
- Check data bus connections
- Ensure proper initialization sequence

**No Response**:
- Check chip select/address decoding
- Verify control signals (RS, E, R/W)
- Test with known-good LCD
- Check for bus conflicts

---

## Resources

### Educational Materials

- **LCD Technology and Interfacing Guide**: `LCD_TECHNOLOGY_EDUCATION.md`
  - Comprehensive guide on how LCDs work (physics, controller internals)
  - Signaling and timing details
  - ASCII character encoding
  - Assembly and Pascal programming examples
  - Educational exercises

### Datasheets

- **HD44780 Datasheet**: Hitachi HD44780 LCD Controller
- **LCD Module Datasheets**: Various manufacturers (check specific LCD model)

### Reference Projects

- **Ben Eater SAP-1**: Uses 2-row or 4-row LCD for output
- **Homebrew Computer Projects**: Many use HD44780 LCDs

### Online Resources

- HD44780 command reference
- LCD initialization guides
- Character LCD programming examples

---

## Conclusion

LCD character displays provide essential output capability for Years 2-4, ensuring students have functional displays throughout the curriculum. The **Matrix Orbital LCD2041-GW-V-E (20×4 parallel LCD)** is **REQUIRED** for Year 3 SAP-1, providing maximum educational value with its parallel interface and alignment with Ben Eater's SAP-1 approach (no touch, no buttons, input separate).

**Progression**:
- **Year 2**: LCD basics with manual computer
- **Year 3**: LCD with SAP-1 (Ben Eater approach, 4-row recommended)
- **Year 4**: LCD until VGA project (Weeks 22-24)
- **Year 4, Weeks 22-24**: Build Ben Eater VGA (replaces LCD)
- **Year 6**: Professional video hardware (with full understanding)

This ensures students always have output capability while building foundational knowledge that prepares them for advanced video hardware in later years.

---

**Document Created**: 2025-12-16  
**Purpose**: Provide LCD display output guidance for Years 2-4  
**Status**: Complete

