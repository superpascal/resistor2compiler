# Video and Audio Hardware Reference

## Overview

This document provides comprehensive coverage of video and audio hardware chips for the 16-bit SuperPascal computer. It complements the curriculum by providing detailed technical information, datasheet references, integration guides, and programming examples.

**Purpose**: Bridge the gap between general microprocessor concepts (from Malvino & Brown) and specific video/audio hardware implementation required for Year 6.

---

## Table of Contents

1. [Audio Hardware](#audio-hardware)
   - [YM2149F PSG](#ym2149f-psg)
   - [SAM2695 MIDI Synthesizer](#sam2695-midi-synthesizer)
2. [Video Hardware](#video-hardware)
   - [TMS9918/V9938/V9958 VDP](#tms9918v9938v9958-vdp)
   - [VERA FPGA Video Controller (Not Used)](#vera-fpga-video-controller-not-used-in-curriculum)
   - [Microcontroller-Based Video Solutions](#microcontroller-based-video-solutions)
3. [Integration Guides](#integration-guides)
4. [Programming Examples](#programming-examples)
5. [Datasheet References](#datasheet-references)

---

## Audio Hardware

### YM2149F PSG

#### Overview

The **Yamaha YM2149F** is a 3-voice Programmable Sound Generator (PSG) chip, functionally identical to the General Instrument AY-3-8910. It was widely used in 1980s computers (Atari ST, Amstrad CPC, MSX) and provides a classic retro sound.

**Key Features**:
- **3 independent tone generators** (channels A, B, C)
- **1 noise generator** (can be mixed with any channel)
- **1 envelope generator** (can control volume of any channel)
- **2 8-bit parallel I/O ports** (can be used for other purposes)
- **16 programmable volume levels** per channel
- **Frequency range**: ~30 Hz to 125 kHz (tone generators)

#### Pin Configuration

| Pin | Name | Function |
|-----|------|----------|
| 1 | BC1 | Bus Control 1 (address/data select) |
| 2 | BC2 | Bus Control 2 (chip select) |
| 3 | BDIR | Bus Direction (read/write select) |
| 4-11 | D0-D7 | Data bus (8-bit) |
| 12 | VSS | Ground |
| 13 | A9 | Address line 9 (register select) |
| 14 | A8 | Address line 8 (register select) |
| 15 | DA0-DA7 | Parallel I/O Port A |
| 16 | DB0-DB7 | Parallel I/O Port B |
| 17 | VCC | Power (+5V) |
| 18 | MIX | Mixed audio output |
| 19 | CHA | Channel A audio output |
| 20 | CHB | Channel B audio output |
| 21 | CHC | Channel C audio output |
| 22 | VSS | Ground |
| 23 | CLK | Clock input (typically 2 MHz) |

#### Register Map

The YM2149F has **16 internal registers** (R0-R15):

| Register | Function | Bits |
|----------|----------|------|
| **R0** | Channel A Tone Period (Low) | 8-bit |
| **R1** | Channel A Tone Period (High) | 4-bit |
| **R2** | Channel B Tone Period (Low) | 8-bit |
| **R3** | Channel B Tone Period (High) | 4-bit |
| **R4** | Channel C Tone Period (Low) | 8-bit |
| **R5** | Channel C Tone Period (High) | 4-bit |
| **R6** | Noise Period | 5-bit |
| **R7** | Mixer Control | 6-bit (enable/disable tone/noise per channel) |
| **R8** | Channel A Volume | 4-bit (0-15) |
| **R9** | Channel B Volume | 4-bit (0-15) |
| **R10** | Channel C Volume | 4-bit (0-15) |
| **R11** | Envelope Period (Low) | 8-bit |
| **R12** | Envelope Period (High) | 8-bit |
| **R13** | Envelope Shape | 4-bit (attack, decay, sustain, release) |
| **R14** | I/O Port A Data | 8-bit (input/output) |
| **R15** | I/O Port B Data | 8-bit (input/output) |

#### Frequency Calculation

**Tone Generator Frequency**:
```
Frequency = Clock / (16 × Period)
```

Where:
- **Clock**: Typically 2 MHz (2,000,000 Hz)
- **Period**: 12-bit value from R0/R1, R2/R3, or R4/R5
- **Range**: ~30 Hz to 125 kHz

**Example**: To generate 440 Hz (A4 note):
```
Period = Clock / (16 × Frequency)
Period = 2,000,000 / (16 × 440)
Period = 2,000,000 / 7,040
Period ≈ 284 (decimal) = $011C (hex)
R0 = $1C (low byte)
R1 = $01 (high 4 bits)
```

#### Memory-Mapped I/O Interface

The YM2149F uses a **bus control interface** (BC1, BC2, BDIR) rather than standard address/data lines. It requires a **latch** to interface with the 65C816 bus.

**Typical Interface Circuit**:
```
65C816 Address Bus → Address Decoder → Latch Enable
65C816 Data Bus → 74HC573 Latch → YM2149F D0-D7
65C816 Control → Logic → YM2149F BC1, BC2, BDIR
```

**Memory Map Example**:
- **Register Select**: $9F00 (write register number)
- **Register Write**: $9F01 (write register data)
- **Register Read**: $9F01 (read register data, if supported)

#### Programming Example (65C816 Assembly)

```assembly
; YM2149F Register Addresses
YM2149_REG_SEL = $9F00
YM2149_REG_DATA = $9F01

; Play a note on Channel A (440 Hz, A4)
play_note_a:
    ; Set Channel A tone period low byte (R0)
    LDA #$00        ; Register 0
    STA YM2149_REG_SEL
    LDA #$1C        ; Period low = $1C
    STA YM2149_REG_DATA
    
    ; Set Channel A tone period high byte (R1)
    LDA #$01        ; Register 1
    STA YM2149_REG_SEL
    LDA #$01        ; Period high = $01 (4 bits)
    STA YM2149_REG_DATA
    
    ; Enable Channel A tone (R7: bit 0 = 0 enables tone)
    LDA #$07        ; Register 7 (Mixer)
    STA YM2149_REG_SEL
    LDA #$FE        ; Enable tone A, disable noise A (bits: 11111110)
    STA YM2149_REG_DATA
    
    ; Set Channel A volume (R8)
    LDA #$08        ; Register 8
    STA YM2149_REG_SEL
    LDA #$0F        ; Volume = 15 (maximum)
    STA YM2149_REG_DATA
    
    RTS
```

#### Audio Output Circuit

The YM2149F requires **audio filtering** and **amplification**:

**Simple Circuit**:
```
YM2149F MIX Output → RC Low-Pass Filter (10kΩ, 0.1µF) → Audio Amplifier → Speaker
```

**Recommended**: Use an LM386 audio amplifier IC for simple amplification.

#### Datasheet References

- **Official YM2149F Datasheet**: [bitsavers.trailing-edge.com](https://bitsavers.trailing-edge.com/components/yamaha/YM2149_199209.pdf)
- **AY-3-8910 Datasheet** (compatible): [dragonpluselectronics.com](https://dragonpluselectronics.com/download/ay-3-8910-datasheet/)
- **Application Notes**: Search for "YM2149 application notes" or "AY-3-8910 application notes"

---

### SAM2695 MIDI Synthesizer

#### Overview

The **SAM2695** is a low-power, single-chip MIDI synthesizer with built-in effects and codec. It provides **advanced sound capabilities** beyond the simple PSG, suitable for more sophisticated audio applications.

**Key Features**:
- **128 General MIDI voices** (instrument sounds)
- **16-voice polyphony** (can play 16 notes simultaneously)
- **Built-in effects**: Reverb, chorus, delay
- **Built-in codec**: Direct audio output (no external DAC needed)
- **Serial interface**: MIDI commands via UART
- **Low power**: Suitable for battery-powered applications
- **Small package**: QFN package (requires surface-mount soldering)

#### Pin Configuration (Key Pins)

| Pin | Name | Function |
|-----|------|----------|
| VDD | Power | 3.3V or 5V (check datasheet) |
| VSS | Ground | Ground |
| MIDI_IN | MIDI Input | Serial MIDI data input |
| MIDI_OUT | MIDI Output | Serial MIDI data output |
| AUDIO_OUT | Audio Output | Analog audio output (to amplifier) |
| RESET | Reset | Active low reset |
| CLK | Clock | External clock or crystal |

#### MIDI Interface

The SAM2695 accepts **standard MIDI messages** via serial interface:

**Common MIDI Messages**:
- **Note On**: `9n kk vv` (channel n, note kk, velocity vv)
- **Note Off**: `8n kk vv` (channel n, note kk, velocity vv)
- **Program Change**: `Cn pp` (channel n, program pp - selects instrument)
- **Control Change**: `Bn cc vv` (channel n, control cc, value vv)

**Example**: Play middle C (note 60) on channel 0 with velocity 100:
```
Note On: 90 3C 64
```

#### Interface to 65C816

The SAM2695 can be interfaced via:
1. **UART/Serial**: Connect to 65C816's ACIA (65C51) or software UART
2. **SPI**: If SAM2695 supports SPI mode (check datasheet)
3. **I2C**: If SAM2695 supports I2C mode (check datasheet)

**Typical Connection** (UART):
```
65C816 ACIA TX → SAM2695 MIDI_IN
65C816 ACIA RX ← SAM2695 MIDI_OUT (optional, for MIDI thru)
```

#### Programming Example (65C816 Assembly)

```assembly
; ACIA Addresses (example)
ACIA_DATA = $9F10
ACIA_STATUS = $9F11

; Play middle C (note 60) on channel 0, velocity 100
play_midi_note:
    ; Wait for ACIA ready
    LDA ACIA_STATUS
    AND #$02        ; Check transmit ready bit
    BEQ play_midi_note
    
    ; Send Note On: 90 3C 64
    LDA #$90        ; Note On, channel 0
    STA ACIA_DATA
    
    ; Wait for ready
wait1:
    LDA ACIA_STATUS
    AND #$02
    BEQ wait1
    
    LDA #$3C        ; Note 60 (middle C)
    STA ACIA_DATA
    
    ; Wait for ready
wait2:
    LDA ACIA_STATUS
    AND #$02
    BEQ wait2
    
    LDA #$64        ; Velocity 100
    STA ACIA_DATA
    
    RTS
```

#### Audio Output

The SAM2695 has **built-in codec**, so audio output is simpler than YM2149F:
```
SAM2695 AUDIO_OUT → Audio Amplifier → Speaker
```

No external DAC or filtering required (codec handles it internally).

#### When to Use SAM2695 vs YM2149F

**Use YM2149F when**:
- Simple sound effects needed
- Retro/chiptune aesthetic desired
- Lower cost preferred
- Through-hole components preferred

**Use SAM2695 when**:
- Realistic instrument sounds needed
- Polyphonic music required
- Modern sound quality desired
- MIDI compatibility needed

#### Datasheet References

- **Official SAM2695 Datasheet**: [docs.dream.fr](https://docs.dream.fr/pdf/Serie2000/SAM_Datasheets/SAM2695.pdf)
- **Application Notes**: Check manufacturer's website for application examples

---

## Video Hardware

### TMS9918/V9938/V9958 VDP

#### Overview

The **Texas Instruments TMS9918** and **Yamaha V9938/V9958** are Video Display Processors (VDPs) that provide tile-based graphics, sprites, and video output. They were used in MSX computers and other 1980s systems.

**TMS9918 Features**:
- **16-color palette** (15 colors + transparent)
- **Tile-based graphics** (8×8 pixel tiles)
- **32 sprites** (up to 4 per line)
- **Composite video output** (NTSC/PAL)
- **Text mode** (40×24 characters)
- **Graphics modes**: Text, Graphics I, Graphics II, Multicolor

**V9938/V9958 Enhanced Features**:
- **512-color palette** (vs 16 colors)
- **Higher resolution** (512×424 pixels)
- **More sprites** (up to 8 per line)
- **RGB output** (in addition to composite)
- **Hardware acceleration** (line drawing, area fill, etc.)
- **Backward compatible** with TMS9918

#### Pin Configuration (TMS9918 - Key Pins)

| Pin | Name | Function |
|-----|------|----------|
| D0-D7 | Data Bus | 8-bit data bus |
| A0 | Address | Address line (register/data select) |
| CS | Chip Select | Active low chip select |
| RD | Read | Read strobe |
| WR | Write | Write strobe |
| INT | Interrupt | Vertical blank interrupt |
| CLK | Clock | Video clock (typically 10.7 MHz) |
| VIDEO | Video Output | Composite video output |
| R, G, B | RGB Output | RGB outputs (V9938/V9958 only) |

#### Register Map

The VDP has **internal registers** accessed via address/data interface:

**TMS9918 Registers** (R0-R7):
- **R0**: Mode control
- **R1**: Mode control
- **R2**: Name table address
- **R3**: Color table address
- **R4**: Pattern table address
- **R5**: Sprite attribute table address
- **R6**: Sprite pattern table address
- **R7**: Text/background color

**V9938/V9958**: Additional registers for enhanced features.

#### Memory-Mapped I/O Interface

**Typical Memory Map**:
- **Register Select**: $9800 (write register number)
- **Register Data**: $9801 (write/read register data)
- **VRAM Access**: $9800/$9801 (with proper sequence)

**Interface Circuit**:
```
65C816 Address Bus → Address Decoder → VDP CS
65C816 Data Bus → VDP D0-D7
65C816 A0 → VDP A0 (register/data select)
65C816 Control → VDP RD, WR
```

#### Programming Example (65C816 Assembly)

```assembly
; VDP Addresses
VDP_REG_SEL = $9800
VDP_REG_DATA = $9801

; Initialize VDP for Graphics Mode I
init_vdp:
    ; Set mode register 0
    LDA #$00        ; Register 0
    STA VDP_REG_SEL
    LDA #$00        ; Mode 0 value
    STA VDP_REG_DATA
    
    ; Set mode register 1
    LDA #$01        ; Register 1
    STA VDP_REG_SEL
    LDA #$E0        ; Enable screen, enable interrupts
    STA VDP_REG_DATA
    
    ; Set name table address (R2)
    LDA #$02        ; Register 2
    STA VDP_REG_SEL
    LDA #$00        ; Name table at VRAM $0000
    STA VDP_REG_DATA
    
    ; Set color table address (R3)
    LDA #$03        ; Register 3
    STA VDP_REG_SEL
    LDA #$00        ; Color table at VRAM $0000
    STA VDP_REG_DATA
    
    ; Set pattern table address (R4)
    LDA #$04        ; Register 4
    STA VDP_REG_SEL
    LDA #$01        ; Pattern table at VRAM $0800
    STA VDP_REG_DATA
    
    RTS
```

#### Video Output

**TMS9918**: Composite video output (requires video amplifier and connector)
**V9938/V9958**: RGB output (can drive VGA monitor with proper sync signals)

**Simple Circuit** (TMS9918):
```
VDP VIDEO → Video Amplifier → Composite Video Connector → TV/Monitor
```

#### Datasheet References

- **TMS9918A Datasheet**: Texas Instruments Video Display Processors Data Manual
- **V9938 Technical Data Book**: [bitsavers.org](https://www.bitsavers.org/pdf/yamaha/Yamaha_V9938_MSX-Video_Technical_Data_Book_Aug85.pdf)
- **V9958 Datasheet**: [vgamuseum.info](https://www.vgamuseum.info/images/doc/yamaha/v9958.pdf)

**Note**: These chips are **discontinued** and may be difficult to source. Consider alternatives (see below).

---

### VERA FPGA Video Controller (Not Used in Curriculum)

#### Overview

**VERA** (Versatile Embedded Retro Adapter) is an **FPGA-based video controller** designed for the Commander X16 project. It provides modern video capabilities while maintaining retro aesthetics.

**Note**: While VERA is an excellent video solution used in other projects (such as the Commander X16), **it is not used in this curriculum** because it is an FPGA-based design, which constitutes a black box that limits educational value.

#### Why VERA is Not Used

**Curriculum Philosophy**: The curriculum explicitly avoids black-box abstractions and requires students to build from first principles. The curriculum states:

> "Students will build initial versions of IC's. The only black box will be:
> - MOS 65C816
> - Complex IC's (Sound, Midi, Video)"

**FPGA as Black Box**: While VERA is an excellent solution with modern capabilities (VGA/HDMI output, high resolution, sprites, tiles), it is FPGA-based. FPGAs are programmable logic devices whose internal operation is not transparent to students. Using VERA would mean:
- Students cannot see or understand the internal video hardware implementation
- The FPGA configuration is a black box (even if open-source)
- Students cannot build or modify the video hardware from first principles
- Educational value is limited to software/driver development only

**Alternative Solutions**: The curriculum uses:
- **TMS9918/V9938/V9958 VDP**: Discrete video chips with transparent register interfaces
- **Microcontroller solutions**: Can be studied and understood at the firmware level

#### VERA Capabilities (For Reference)

**Key Features** (not used, but documented for reference):
- **VGA and HDMI output** (modern displays)
- **Tile-based graphics** (8×8 and 16×16 tiles)
- **Sprite support** (128 sprites)
- **Layer system** (background + foreground layers)
- **256-color palette** (from 4096 colors)
- **Resolution**: Up to 640×480 (VGA) or 1280×720 (HDMI)
- **SPI interface** to host CPU (65C816)

#### Reference Information

For projects that do use VERA:
- **VERA Documentation**: [Commander X16 Wiki](https://github.com/commanderx16/x16-docs)
- **VERA Specifications**: Check Commander X16 project documentation

**Note**: This information is provided for reference only. VERA is not used in the Resistor2Compiler curriculum due to its FPGA-based black-box nature.

---

### Microcontroller-Based Video Solutions

#### Overview

Using a **modern microcontroller** (e.g., Raspberry Pi Pico RP2040, Raspberry Pi RP2350, Propeller, ESP32) as a **video co-processor** provides flexibility and modern capabilities while maintaining educational value.

**Approach**: The microcontroller generates video signals (VGA, HDMI) based on commands from the 65C816.

**Educational Foundation**: Students who completed Ben Eater's VGA project ("Worst Video Card Ever") in Year 4 have foundational knowledge of video signal generation, timing, and DAC principles. This makes implementing and understanding microcontroller video solutions much more effective, as students can:
- Understand what the firmware is doing (video signal generation)
- Appreciate timing and synchronization requirements
- Study firmware source code to see video implementation
- Compare discrete VGA implementation with microcontroller implementation

#### Raspberry Pi Pico (RP2040)

**Features**:
- **Dual-core ARM Cortex-M0+**
- **Programmable I/O (PIO)**: Can generate VGA/HDMI signals
- **SPI/UART/I2C interface** to 65C816
- **Low cost**: ~$4
- **Active community**: Many video generation examples
- **Firmware can be studied**: Unlike FPGA, firmware source code is accessible

**Interface Options**:
```
65C816 → UART/SPI/I2C → Raspberry Pi Pico → VGA/HDMI → Monitor
```

**HDMI Output**: Can generate HDMI signals via PIO or use HDMI adapter modules. I2C interface can be used for control/configuration.

**Programming**: Pico runs firmware that:
1. Receives graphics commands from 65C816 (via UART/SPI/I2C)
2. Generates video signals using PIO (Programmable I/O state machines)
3. Outputs VGA or HDMI

**Educational Value**: Students can study the firmware source code to understand how video signals are generated, making this more transparent than FPGA solutions.

#### Raspberry Pi RP2350

**Features**:
- **Dual-core ARM Cortex-M33** (newer than RP2040)
- **Enhanced PIO capabilities**
- **HDMI output support**
- **I2C/SPI/UART interfaces** to 65C816
- **Low cost**: Similar to RP2040
- **Modern capabilities**: Better performance than RP2040

**Interface**: Similar to RP2040, with enhanced capabilities for HDMI output.

**Educational Value**: Same as RP2040 - firmware can be studied and understood.

#### Advantages

- **Modern output**: VGA/HDMI (works with modern monitors)
- **Flexible**: Can implement any video mode
- **Low cost**: Microcontroller is inexpensive
- **Available**: Easy to source
- **Programmable**: Can update firmware
- **Educational**: Firmware source code can be studied (unlike FPGA)
- **Foundation**: Builds on Ben Eater VGA experience from Year 4

#### Disadvantages

- **Requires firmware development**: Need to program microcontroller
- **More complex system**: Two processors to coordinate
- **Communication overhead**: Commands sent via UART/SPI/I2C

#### Connection to Year 4 Foundation

Students who completed Ben Eater's VGA project in Year 4 will:
- **Understand video timing**: Know why precise timing is required
- **Appreciate signal generation**: Understand how digital data becomes video signals
- **Study firmware effectively**: Can read firmware code and understand what it does
- **Compare implementations**: Can compare discrete VGA with microcontroller implementation
- **Debug effectively**: Understand video fundamentals helps with troubleshooting

#### Example Projects

- **Pico VGA**: [GitHub projects](https://github.com/search?q=pico+vga)
- **Pico HDMI**: [GitHub projects](https://github.com/search?q=pico+hdmi)
- **RP2350 HDMI**: Check Raspberry Pi documentation for RP2350 video examples

---

## Integration Guides

### Choosing Video/Audio Hardware

**Decision Matrix**:

| Factor | YM2149F | SAM2695 | TMS9918 | VERA | Microcontroller |
|--------|---------|---------|---------|------|----------------|
| **Cost** | Low | Medium | Low (if available) | Medium | Low |
| **Availability** | Good | Good | Poor (discontinued) | Good | Excellent |
| **Complexity** | Low | Medium | Low | Medium | High |
| **Sound Quality** | Retro | Modern | N/A | N/A | N/A |
| **Video Quality** | N/A | N/A | Retro | Modern | Modern |
| **Ease of Integration** | Medium | Medium | Low | Medium | High (with firmware) |
| **Educational Value** | High | Medium | High | Low (FPGA black box) | Medium-High |

**Note**: VERA is not used in this curriculum due to its FPGA-based black-box nature, which limits educational value despite being an excellent solution.

**Recommended Combinations**:
1. **Retro Aesthetic**: YM2149F + TMS9918 (if available)
2. **Modern Capabilities**: SAM2695 + Microcontroller
3. **Budget-Conscious**: YM2149F + Microcontroller (Pico)

### Memory Map Planning

When integrating video/audio hardware, plan the **memory map** carefully:

**Example Memory Map**:
```
$0000-$7FFF: RAM (banks $00-$01)
$8000-$9FFF: I/O Devices
  $9800-$9801: VDP (TMS9918)
  $9F00-$9F01: YM2149F
  $9F10-$9F11: ACIA (for SAM2695 MIDI)
$A000-$BFFF: Expansion
$C000-$FFFF: ROM (bank $FF)
```

**Address Decoding**: Use 74HC138 or similar decoder to generate chip selects.

### Power Supply Considerations

**Power Requirements**:
- **YM2149F**: +5V, ~50mA
- **SAM2695**: 3.3V or 5V (check datasheet), ~100mA
- **TMS9918**: +5V, ~200mA
- **VERA**: +5V, ~500mA (FPGA power) - *Not used in curriculum*
- **Microcontroller**: 3.3V or 5V, ~100-200mA

**Decoupling**: Each chip needs **0.1µF ceramic capacitor** near power pins.

**Power Distribution**: Use thick traces or ground plane for power distribution.

### Signal Integrity

**Video Signals**:
- **Keep video signals away from digital noise** (separate ground if possible)
- **Use proper termination** for VGA/HDMI signals
- **Route video signals on separate layer** (if multi-layer PCB)

**Audio Signals**:
- **Filter power supply** to audio chips (ferrite bead + capacitor)
- **Keep audio traces away from digital switching**
- **Use shielded cable** for audio output (if long traces)

---

## Programming Examples

### Complete Audio Example (YM2149F)

```assembly
; YM2149F Driver for 65C816
; Assumes YM2149F at $9F00 (register select) and $9F01 (data)

YM2149_REG_SEL = $9F00
YM2149_REG_DATA = $9F01

; Initialize YM2149F
init_ym2149:
    ; Set all channels to maximum volume
    LDA #$08        ; Register 8 (Channel A volume)
    STA YM2149_REG_SEL
    LDA #$0F        ; Volume 15
    STA YM2149_REG_DATA
    
    LDA #$09        ; Register 9 (Channel B volume)
    STA YM2149_REG_SEL
    LDA #$0F
    STA YM2149_REG_DATA
    
    LDA #$0A        ; Register 10 (Channel C volume)
    STA YM2149_REG_SEL
    LDA #$0F
    STA YM2149_REG_DATA
    
    ; Enable all tones, disable noise (R7)
    LDA #$07        ; Register 7 (Mixer)
    STA YM2149_REG_SEL
    LDA #$F8        ; Enable tones, disable noise (11111000)
    STA YM2149_REG_DATA
    
    RTS

; Play note on Channel A
; Input: X = frequency period (12-bit, high 4 bits in X, low 8 bits in A)
play_note_a:
    PHA             ; Save low byte
    
    ; Set period low (R0)
    LDA #$00
    STA YM2149_REG_SEL
    PLA             ; Restore low byte
    STA YM2149_REG_DATA
    
    ; Set period high (R1)
    LDA #$01
    STA YM2149_REG_SEL
    TXA             ; Get high 4 bits
    AND #$0F        ; Mask to 4 bits
    STA YM2149_REG_DATA
    
    RTS
```

### Complete Video Example (TMS9918)

```assembly
; TMS9918 Driver for 65C816
; Assumes VDP at $9800 (register select) and $9801 (data)

VDP_REG_SEL = $9800
VDP_REG_DATA = $9801

; Initialize TMS9918 for Graphics Mode I
init_vdp:
    ; Set registers R0-R7
    LDX #$00        ; Start with register 0
    
init_loop:
    LDA vdp_init_data,X
    STA VDP_REG_SEL
    INX
    LDA vdp_init_data,X
    STA VDP_REG_DATA
    INX
    CPX #$10        ; 8 registers × 2 bytes = 16 bytes
    BNE init_loop
    
    RTS

; VDP initialization data (register, value pairs)
vdp_init_data:
    .byte $00, $00  ; R0: Mode 0
    .byte $01, $E0  ; R1: Enable screen, interrupts
    .byte $02, $00  ; R2: Name table at $0000
    .byte $03, $00  ; R3: Color table at $0000
    .byte $04, $01  ; R4: Pattern table at $0800
    .byte $05, $20  ; R5: Sprite attribute at $1000
    .byte $06, $00  ; R6: Sprite pattern at $0000
    .byte $07, $F1  ; R7: Text color (white on black)
```

---

## Datasheet References

### Audio Chips

1. **YM2149F PSG**
   - **Official Datasheet**: [bitsavers.trailing-edge.com](https://bitsavers.trailing-edge.com/components/yamaha/YM2149_199209.pdf)
   - **AY-3-8910 Datasheet** (compatible): [dragonpluselectronics.com](https://dragonpluselectronics.com/download/ay-3-8910-datasheet/)
   - **Application Notes**: Search manufacturer websites

2. **SAM2695 MIDI Synthesizer**
   - **Official Datasheet**: [docs.dream.fr](https://docs.dream.fr/pdf/Serie2000/SAM_Datasheets/SAM2695.pdf)
   - **Application Notes**: Check manufacturer's website

### Video Chips

1. **TMS9918 VDP**
   - **TMS9918A Datasheet**: Texas Instruments Video Display Processors Data Manual
   - **Application Notes**: Search for "TMS9918 application notes"

2. **V9938 VDP**
   - **Technical Data Book**: [bitsavers.org](https://www.bitsavers.org/pdf/yamaha/Yamaha_V9938_MSX-Video_Technical_Data_Book_Aug85.pdf)

3. **V9958 VDP**
   - **Datasheet**: [vgamuseum.info](https://www.vgamuseum.info/images/doc/yamaha/v9958.pdf)

4. **VERA FPGA Video Controller** (Not Used)
   - **Documentation**: [Commander X16 Wiki](https://github.com/commanderx16/x16-docs)
   - **Note**: VERA is not used in this curriculum due to its FPGA-based black-box nature

5. **Microcontroller Video Solutions**
   - **Raspberry Pi Pico**: [raspberrypi.com/documentation](https://www.raspberrypi.com/documentation/)
   - **Pico VGA Examples**: Search GitHub for "pico vga"

---

## Educational Video Hardware Resources

### Ben Eater VGA Project ("Worst Video Card Ever")

**Resource**: https://eater.net/vga

**Purpose**: **REQUIRED** foundation learning - Build video card from discrete components

**Educational Level**: Year 4 (**REQUIRED**)

**Key Features**:
- Breadboard-based VGA video card
- Discrete component design (no video IC)
- Teaches video signal fundamentals
- Hands-on building experience
- Low cost (~$20-30)

**Curriculum Integration**: 
- **Year 4**: **REQUIRED** module (Term 2, Weeks 22-24)
- **Educational value is paramount**: Essential foundational learning
- Students build VGA card before using IC video chips or microcontroller solutions
- Teaches video fundamentals from first principles
- **Required before**: TMS9918/V9938/V9958 VDP or Raspberry Pi Pico (RP2040/RP2350) integration

**See**: `curriculum/Year4/BEN_EATER_VGA_ANALYSIS.md` for detailed analysis

### BombJack Video Hardware Repository

**Resource**: https://github.com/martinpiper/BombJack

**Purpose**: Advanced reference - Study professional arcade video hardware

**Educational Level**: Year 6 (Advanced Reference)

**Key Features**:
- Professional arcade video hardware recreation
- Multi-board modular design
- Detailed technical documentation
- Sprite and tile rendering logic
- Production PCB designs

**Curriculum Integration**:
- **Year 6, Term 1**: PCB design reference
- **Year 6, Term 2, Week 17**: Sprite/tile concepts reference
- **Advanced Students**: Deep dive study material

**Educational Value**:
- Understand professional video hardware architecture
- Study sprite and tile rendering (relevant to TMS9918)
- Learn production PCB design principles
- Appreciate what IC video chips do internally

**See**: `curriculum/Year4/BOMBJACK_VIDEO_HARDWARE_ANALYSIS.md` for detailed analysis

### Educational Progression

1. **Year 4**: Build Ben Eater VGA (hands-on, fundamentals) - **REQUIRED**
2. **Year 6, Term 1**: Study BombJack (reference, professional design) - Optional
3. **Year 6, Term 2**: Use IC video chips (TMS9918/VDP) or Raspberry Pi Pico (RP2040/RP2350) - **With full understanding from Year 4 foundation**

---

## Additional Resources

### Books and References

- **Video Game Console Design**: Books on retro console architecture
- **Sound Chip Programming**: Books on PSG and sound synthesis
- **MIDI Specification**: Official MIDI specification documents

### Online Communities

- **Commander X16 Forum**: For modern retro computing (VERA is used in Commander X16, but not in this curriculum)
- **Retro Computing Forums**: For TMS9918, YM2149F discussions
- **Homebrew Computer Groups**: For integration examples

### Tools

- **VDP Pattern Editors**: Tools for creating tile graphics
- **PSG Music Trackers**: Tools for creating YM2149F music
- **MIDI Sequencers**: Tools for creating MIDI files

---

## Conclusion

This document provides comprehensive coverage of video and audio hardware for the 16-bit SuperPascal computer. Students should:

1. **Read datasheets** for detailed specifications
2. **Study integration examples** from similar projects
3. **Prototype on breadboard** before PCB design
4. **Test thoroughly** before final integration

**Key Takeaway**: Video and audio hardware integration requires careful attention to:
- **Memory mapping** (address decoding)
- **Power supply** (decoupling, filtering)
- **Signal integrity** (routing, termination)
- **Timing** (clock signals, synchronization)

With proper planning and reference to datasheets, students can successfully integrate professional-quality video and audio into their homebrew computer.

---

**Document Created**: 2025-12-15  
**Purpose**: Provide comprehensive video/audio hardware coverage for Year 6 curriculum, bridging gap identified in Malvino & Brown alignment
