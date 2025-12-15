# Chapter 9: Graphics and Sound Research

## Introduction

Graphics and sound add visual and audio capabilities to the computer. This chapter explains how to research and select video and audio solutions.

## Video Output Options

**Options to research**:
- TMS9918/V9958 VDP (Video Display Processor)
- FPGA-based solutions (VERA)
- Microcontroller-based solutions
- Discrete logic VGA
- LED matrix displays
- SPI TFT displays

**TMS9918/V9958**:
- Classic video chip
- Tile graphics
- Sprite support
- Composite video output
- Low resolution (256×192)

**FPGA solutions**:
- VERA (Commander X16)
- High resolution
- VGA/HDMI output
- Sprite support
- Complex to design

**Microcontroller solutions**:
- Raspberry Pi Pico
- VGA/HDMI PIO code
- Flexible
- Requires programming
- Good resolution

## Audio Output Options

**Options to research**:
- YM2149F (AY-3-8910) PSG
- SAM2695 MIDI synth
- Microcontroller PWM
- Simple DAC
- 555 timer tones

**YM2149F PSG**:
- 3-voice Programmable Sound Generator
- Classic 80s sound chip
- Square waves, noise
- Simple interface
- Well-documented

**SAM2695**:
- MIDI synthesizer
- High-quality sound
- MIDI interface
- More complex
- Professional sound

## Trade-off Analysis

**Video trade-offs**:
- **Resolution**: Higher = more complex
- **Color depth**: More colors = more memory
- **Cost**: Complex = expensive
- **Complexity**: Advanced = harder to build
- **Compatibility**: Standard = easier

**Audio trade-offs**:
- **Quality**: Better = more complex
- **Voices**: More = more complex
- **Cost**: Professional = expensive
- **Complexity**: Advanced = harder
- **Features**: More = more work

## Prototyping

**Video prototyping**:
- Build simple DAC
- Generate test pattern
- Test timing
- Evaluate feasibility

**Audio prototyping**:
- Breadboard PSG chip
- Generate tones
- Test interface
- Evaluate quality

## Proposal Development

**Proposal contents**:
- Selected solution
- Rationale
- Implementation plan
- Parts list
- Cost estimate
- Timeline

## Practice Questions

1. What video options are available?
2. What audio options are available?
3. How do we evaluate trade-offs?
4. Why prototype?
5. What goes in a proposal?

## Key Takeaways

- Multiple options for video/audio
- Each has trade-offs
- Prototype to verify
- Proposals guide integration
- Foundation for Year 6

---

*Graphics and sound research prepares for complete system in Year 6*
