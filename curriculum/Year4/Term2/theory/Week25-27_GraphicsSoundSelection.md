# Week 25-27: Graphics and Sound Hardware Selection - Theory

## Learning Objectives

By the end of this week-block, students will:
- Research video output options
- Research audio output options
- Understand trade-offs
- Prototype selected solutions
- Prepare proposals for Year 6

## Prerequisites

- Completed Weeks 22-24 (I/O Subsystems)
- Complete I/O integration
- Understanding of system design
- Research skills

## Key Concepts

### 1. Video Output Options

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

**Discrete logic**:
- Resistor ladder DAC
- Counter-based generation
- Simple but limited
- Educational value

### 2. Audio Output Options

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

**Microcontroller PWM**:
- Software-generated
- Flexible
- Requires programming
- Good quality possible

**Simple solutions**:
- 555 timer
- Basic tones
- Educational
- Limited capability

### 3. Trade-off Analysis

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

**Selection criteria**:
- Buildability on breadboard/PCB
- Cost constraints
- Educational value
- Time available
- Future expansion

### 4. Prototyping Approaches

**Video prototyping**:
- Build simple DAC
- Generate test pattern
- Test timing
- Evaluate feasibility
- Document results

**Audio prototyping**:
- Breadboard PSG chip
- Generate tones
- Test interface
- Evaluate quality
- Document results

**Prototype goals**:
- Verify feasibility
- Test interface
- Evaluate complexity
- Estimate cost
- Prepare for integration

### 5. Integration Considerations

**Video integration**:
- Bus interface
- Memory requirements (VRAM)
- Address decoding
- Control signals
- Timing considerations

**Audio integration**:
- Bus interface
- Address decoding
- Audio output filtering
- Amplification
- Speaker connection

**System impact**:
- Additional memory
- Additional I/O space
- Power requirements
- PCB complexity
- Cost increase

### 6. Research Methodology

**Research process**:
1. Identify options
2. Research each option
3. Compare features
4. Evaluate trade-offs
5. Select candidates
6. Prototype selected
7. Document findings
8. Prepare proposal

**Information sources**:
- Datasheets
- Application notes
- Project examples
- Community forums
- Technical documentation

### 7. Proposal Development

**Proposal contents**:
- Selected solution
- Rationale
- Implementation plan
- Parts list
- Cost estimate
- Timeline
- Risk assessment

**Presentation**:
- Present to class
- Explain decision
- Answer questions
- Incorporate feedback
- Finalize choice

### 8. Year 6 Preparation

**Year 6 integration**:
- Selected solutions integrated
- PCB design includes them
- Software support added
- Complete system built

**Preparation tasks**:
- Finalize selections
- Order parts
- Prepare designs
- Plan integration
- Document decisions

## Mathematical Foundations

### Video Timing

**VGA timing**:
- Horizontal sync: 31.5 kHz
- Vertical sync: 60 Hz
- Pixel clock: 25.175 MHz
- Timing critical

### Audio Frequencies

**Tone generation**:
- Frequency = clock / divider
- Human hearing: 20 Hz - 20 kHz
- Musical notes: specific frequencies
- Sampling: Nyquist rate

## Common Misconceptions

1. **"Graphics must be high-res"**
   - Clarify: Start simple, expand
   - Show progression

2. **"Sound must be perfect"**
   - Clarify: Start basic, improve
   - Show evolution

3. **"Too complex to build"**
   - Clarify: Many have done it
   - Show examples

## Connections to Weeks 19-24

- **Memory Banking**: Supports video memory
- **I/O Subsystems**: Foundation for graphics/sound
- **System Integration**: Part of system

## Connections to Year 5-6

- **PCB Design**: Includes graphics/sound
- **System Completion**: Integrated in Year 6
- **Final System**: Complete with graphics/sound

## Next Steps

After completing research, students will:
- Finalize selections for Year 6
- Prepare for Year 5 PCB design
- Plan integration

---

*Graphics and sound research prepares for complete system in Year 6*
