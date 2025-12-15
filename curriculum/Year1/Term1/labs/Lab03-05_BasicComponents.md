# Lab 3-5: Basic Components

## Lab Overview

**Duration**: 3 weeks (6-9 hours total)  
**Prerequisites**: Read theory material on Basic Components  
**Outcome**: Build timing circuits, generate clocks, and debounce switches

## Safety Reminders

- [ ] Check all connections before powering on
- [ ] Verify capacitor polarity (electrolytic capacitors!)
- [ ] Never short-circuit power supplies
- [ ] Report damaged equipment immediately

---

## Lab Session 1: Resistors & Capacitors (60-90 min)

### Part 1: Resistor Color Code Practice (20 min)

**Materials**:
- Assorted resistors
- Multimeter
- Resistor identification worksheet

**Activity**:
1. Select 10 resistors from your kit
2. Read color codes
3. Record values
4. Verify with multimeter
5. Check accuracy

**Check**: Can you identify resistors correctly?

### Part 2: Capacitor Types (15 min)

**Materials**:
- Ceramic capacitor (0.1µF)
- Electrolytic capacitor (10µF)
- Multimeter (capacitance mode if available)

**Activity**:
1. Identify capacitor types
2. Note polarity (electrolytic only!)
3. Measure values (if multimeter supports)
4. Compare sizes and markings

**Check**: Can you identify capacitor types and polarity?

### Part 3: RC Charging Circuit (25 min)

**Materials**:
- 10kΩ resistor
- 10µF electrolytic capacitor (watch polarity!)
- Multimeter
- Power supply (5V)

**Step-by-step**:
1. Build circuit: +5V → Resistor → Capacitor (+) → Capacitor (-) → GND
2. **Important**: Electrolytic capacitor polarity!
   - Positive leg to resistor
   - Negative leg to ground
3. Connect multimeter across capacitor
4. Apply power
5. Watch voltage rise
6. Record time to reach 63% (should be ~0.1 seconds)

**Measurements**:
- Time to 1V: ______
- Time to 2V: ______
- Time to 3V: ______
- Time constant (τ): Should be ~0.1 seconds

**Check**: Does voltage rise as expected?

---

## Lab Session 2: 555 Timer Clock (60-90 min)

### Part 1: Building Astable 555 Circuit (40 min)

**Materials**:
- 555 timer IC (NE555 or CMOS 555)
- Resistors: 1kΩ, 10kΩ
- Capacitor: 10µF electrolytic
- LED with 220Ω resistor
- Power supply (5V)

**Step-by-step Build**:

1. **Place 555 IC**:
   - Insert into breadboard (notch indicates pin 1)
   - Connect pin 8 (VCC) to +5V
   - Connect pin 1 (GND) to ground

2. **Add Timing Components**:
   - R1: Pin 8 → Pin 7 (1kΩ)
   - R2: Pin 7 → Pin 6 and Pin 2 (10kΩ)
   - C: Pin 6 → GND (10µF electrolytic - **watch polarity!**)
   - Connect Pin 2 to Pin 6

3. **Add Output Indicator**:
   - LED with 220Ω resistor from Pin 3 to GND
   - This will blink!

4. **Power On**:
   - Connect 5V power
   - **LED should blink!**

**Troubleshooting**:
- No blink? Check capacitor polarity
- Too fast/slow? Check resistor values
- Check all connections
- Verify power supply

**Check**: Is LED blinking?

### Part 2: Variable Frequency (20 min)

**Materials**:
- Your 555 circuit
- 10kΩ or 100kΩ potentiometer

**Activity**:
1. Replace R2 with potentiometer
2. Adjust pot
3. Observe LED blink rate change
4. Measure frequency (if oscilloscope available)

**Observations**:
- Clockwise rotation: Frequency ______
- Counter-clockwise rotation: Frequency ______

**Check**: Can you control blink rate?

---

## Lab Session 3: Button Debouncing (60-90 min)

### Part 1: Observing Bounce (20 min)

**Materials**:
- Push button switch
- LED with resistor
- Oscilloscope or logic analyzer (if available)

**Step-by-step**:
1. Build simple button circuit:
   - Button: One side to +5V, other to 10kΩ resistor to GND
   - Connect LED from button output to GND (through resistor)
2. Press button rapidly
3. Observe LED flickering (bounce!)

**If oscilloscope available**:
- Connect probe to button output
- Press button
- Observe bounce on screen
- Document with screenshot

**Check**: Can you see bounce?

### Part 2: Building RC Debouncer (30 min)

**Materials**:
- Your button circuit
- 0.1µF capacitor
- 74HC14 Schmitt trigger (optional but recommended)

**Step-by-step**:

1. **Add Debouncing**:
   - Add 0.1µF capacitor from button output to GND
   - Add 10kΩ resistor in series (if needed)
   - Now press button - should be clean!

2. **Add Schmitt Trigger** (optional):
   - Insert 74HC14 between debouncer and LED
   - Provides clean digital signal
   - Better for feeding into logic circuits

**Testing**:
- Press button
- Observe clean signal (no bounce!)
- Compare to previous (with bounce)

**If oscilloscope available**:
- Observe before debouncing: Bouncy signal
- Observe after debouncing: Clean signal
- Document difference

**Check**: Is signal clean now?

---

## Lab Session 4: Signal Observation (60-90 min)

### Part 1: 555 Timer Waveform (20 min)

**Materials**:
- Your 555 timer circuit
- Oscilloscope or logic analyzer

**Activity**:
1. Connect 555 output to oscilloscope
2. Observe square wave
3. Measure period (time for one cycle)
4. Calculate frequency: f = 1 / period
5. Compare to calculated frequency

**Measurements**:
- Period: ______ seconds
- Calculated frequency: ______ Hz
- Expected frequency: ~6.9 Hz
- Match? Yes / No

**Check**: Does measured frequency match calculation?

### Part 2: Button Bounce Comparison (20 min)

**Materials**:
- Button with bounce
- Button with debouncer
- Oscilloscope or logic analyzer

**Activity**:
1. Connect button (with bounce) to scope
2. Press button, observe bounce
3. Connect debounced button to scope
4. Press button, observe clean signal
5. Document before/after

**Observations**:
- Bounce duration: ______ ms
- Debounced signal: Clean / Still bouncy

**Check**: Can you see the difference?

### Part 3: RC Charging Curve (20 min)

**Materials**:
- RC charging circuit
- Oscilloscope

**Activity**:
1. Connect RC circuit to oscilloscope
2. Apply step input (switch or signal generator)
3. Observe exponential charging curve
4. Measure time constant
5. Compare to calculated value

**Measurements**:
- Time constant (measured): ______ seconds
- Time constant (calculated): 0.1 seconds
- Match? Yes / No

**Check**: Does measured time constant match calculation?

---

## Lab Session 5: Assessment (60-90 min)

### Practical Assessment (40 min)

**Task 1: Build 555 Timer Clock** (20 min)
- Build astable 555 circuit from scratch
- Must calculate component values for specific frequency (e.g., 5 Hz)
- Must measure actual frequency
- Must document circuit

**Task 2: Build Debouncer** (20 min)
- Build button debouncer
- Must demonstrate clean signal (with scope/analyzer if available)
- Must explain how it works

### Written Assessment (20 min)

**Topics**:
- Resistor color code quiz
- Capacitor types and uses
- 555 timer frequency calculation
- Debouncing explanation

### Lab Notebook Entry

**Record**:
1. Resistor values identified
2. RC timing measurements
3. 555 timer frequency (calculated and measured)
4. Debouncing observations
5. Signal waveforms (if captured)

---

## Troubleshooting Guide

### 555 Timer Doesn't Oscillate

**Check**:
1. Capacitor polarity (electrolytic!)
2. All connections correct
3. Power supply voltage
4. Component values

**Fix**:
- Verify capacitor polarity
- Check pin connections
- Measure power supply
- Verify resistor values

### Debouncer Doesn't Work

**Check**:
1. Capacitor value (0.1µF typical)
2. Resistor value (10kΩ typical)
3. Connections correct

**Fix**:
- Try larger capacitor
- Adjust resistor value
- Check connections

### Oscilloscope Shows Nothing

**Check**:
1. Probe connected correctly
2. Timebase setting
3. Voltage scale
4. Trigger setting

**Fix**:
- Check probe connection
- Adjust timebase
- Adjust voltage scale
- Set trigger correctly

---

## Success Criteria

**You've successfully completed this lab when**:
- [ ] You can read resistor color codes
- [ ] You can identify capacitor types
- [ ] You built working RC timing circuit
- [ ] You built working 555 timer clock
- [ ] You built working debouncer
- [ ] You can observe signals (if equipment available)
- [ ] You've documented everything in lab notebook

---

## Extension Activities (Optional)

**For advanced students**:
1. Design 555 circuit for specific frequency (e.g., 1 Hz, 10 Hz)
2. Build tone generator (555 + speaker)
3. Advanced: Build PWM circuit with 555
4. Research 555 timer applications

---

## Next Lab

After completing this lab:
- Review theory on Boolean logic (Week 6-8)
- Read next lab material
- Prepare for logic gate circuits

---

*Lab work is where theory becomes reality - build to understand!*
