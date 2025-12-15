# Dual Step-Down Converter Project

## Project Overview

**Duration**: 2-3 weeks (6-9 hours total)  
**Prerequisites**: Basic understanding of voltage, current, and resistance (Weeks 1-2)  
**Outcome**: Build a dual-output power supply (3V and 5V) from 12V or 24V input, usable throughout Year 1 and beyond

## Learning Objectives

By completing this project, students will:
- Understand step-down (buck) converter principles
- Build a practical power supply from discrete components
- Learn voltage regulation and current limiting
- Practice breadboard circuit construction
- Convert breadboard design to PCB
- Create a reusable tool for future projects

## Project Value

This power supply will be used throughout Year 1 and beyond for:
- Powering breadboard circuits (3V and 5V logic)
- Testing components and circuits
- Providing stable power for logic ICs (74HC series)
- Future PCB projects

---

## Part 1: Breadboard Construction

### Materials Required

**Core Components**:
- **2× LM2596 Step-Down Converter Modules** (or equivalent buck converter ICs)
  - Alternative: LM2576, LM2595, or similar adjustable buck converters
  - **Note**: Using modules simplifies construction; advanced students can build from discrete components
- **2× 100µF Electrolytic Capacitors** (input filtering, 25V+ rating)
- **2× 220µF Electrolytic Capacitors** (output filtering, 10V+ rating)
- **2× 100nF Ceramic Capacitors** (decoupling, 50V+ rating)
- **2× 1kΩ Resistors** (feedback divider, 1% tolerance recommended)
- **2× 2.2kΩ Resistors** (feedback divider, 1% tolerance recommended)
- **2× 10kΩ Potentiometers** (variable output voltage adjustment - allows fine-tuning of 3V and 5V outputs)
- **2× 1N4007 Diodes** (reverse polarity protection)
- **2× LEDs** (power indicators, any color)
- **2× 220Ω Resistors** (LED current limiting)

**Supporting Components**:
- **Input Connector**: DC barrel jack (2.1mm or 2.5mm) for 12V/24V input
- **Output Connectors**: 
  - 2× Screw terminals or banana jacks for 3V output
  - 2× Screw terminals or banana jacks for 5V output
- **Fuse**: 1A or 2A fuse with holder (safety)
- **Heat Sinks**: Small heat sinks for regulator ICs (if using discrete ICs, not modules)

**Tools**:
- Breadboard (full-size recommended)
- Jumper wires
- Multimeter
- Wire strippers
- Soldering iron (for connectors)

**Optional (for advanced students building from discrete components)**:
- **2× LM2596 ICs** (or LM2576, LM2595)
- **2× Schottky Diodes** (1N5822 or similar, for switching)
- **2× Inductors** (100µH, 1A+ rating)
- **Additional capacitors** for input/output filtering

---

**Note on Variable Current Resistors**: The potentiometers in this design provide **variable output voltage adjustment** (not variable current limiting). For variable current limiting, additional current-limiting circuits would be needed (transistor-based or IC-based). For Year 1, variable voltage adjustment is sufficient and more educational. Advanced students can add current limiting as an optional enhancement.

### Circuit Design

#### Option 1: Using Pre-Built Modules (Recommended for Year 1)

**Simplified Approach**: Use LM2596 adjustable buck converter modules (readily available, inexpensive, includes all components).

**Circuit Connections**:
```
Input (12V or 24V)
  ↓
[Fuse] → [Reverse Polarity Protection Diode]
  ↓
[Input Filter Capacitor 100µF]
  ↓
[LM2596 Module 1] → [Output Filter 220µF] → [3V Output with Potentiometer]
[LM2596 Module 2] → [Output Filter 220µF] → [5V Output with Potentiometer]
  ↓
[LED Indicators]
```

**Module Connections**:
- **Input**: Connect to input power (12V or 24V)
- **Output**: Connect to output terminals
- **Adjustment**: Connect potentiometer to feedback pin (varies by module)

#### Option 2: Building from Discrete Components (Advanced)

**Full Circuit**: Build complete buck converter using LM2596 IC and discrete components.

**Circuit Schematic** (per output):
```
Input (12V/24V)
  ↓
[Fuse] → [1N4007 Diode] → [100µF Capacitor]
  ↓
LM2596 IC:
  - VIN: Input voltage
  - GND: Ground
  - FB: Feedback (voltage divider)
  - ON/OFF: Enable (connect to VIN for always-on)
  - OUTPUT: Switched output
  ↓
[Schottky Diode] → [Inductor 100µH] → [220µF Capacitor] → [100nF Capacitor]
  ↓
[Voltage Divider: 1kΩ + 2.2kΩ] → [Potentiometer 10kΩ]
  ↓
Output (3V or 5V)
```

**Voltage Divider Calculation**:
- **For 3V Output**: R1 = 1kΩ, R2 = 2.2kΩ (Vout = 1.23V × (1 + R2/R1) ≈ 3V)
- **For 5V Output**: R1 = 1kΩ, R2 = 2.2kΩ (adjust potentiometer for 5V)

---

### Breadboard Construction Steps

#### Step 1: Input Section (30 min)

1. **Place Input Connector**:
   - Connect DC barrel jack to breadboard
   - Label: "INPUT 12V/24V"

2. **Add Fuse**:
   - Connect fuse holder in series with positive input
   - **Safety**: Fuse protects against overcurrent

3. **Add Reverse Polarity Protection**:
   - Connect 1N4007 diode (anode to input, cathode to circuit)
   - **Purpose**: Prevents damage if input is connected backwards

4. **Add Input Filtering**:
   - Connect 100µF electrolytic capacitor (positive to input, negative to ground)
   - Connect 100nF ceramic capacitor in parallel
   - **Purpose**: Smooths input voltage, reduces noise

5. **Test Input**:
   - Connect multimeter to input
   - Verify voltage (12V or 24V)
   - Check polarity

#### Step 2: 3V Output Section (60 min)

1. **Place LM2596 Module (or discrete circuit)**:
   - Connect input to filtered input voltage
   - Connect ground to common ground

2. **Add Output Filtering**:
   - Connect 220µF electrolytic capacitor (positive to output, negative to ground)
   - Connect 100nF ceramic capacitor in parallel
   - **Purpose**: Smooths output voltage, reduces ripple

3. **Add Voltage Adjustment**:
   - Connect potentiometer to feedback pin (varies by module)
   - **For Modules**: Usually a small potentiometer on the module itself
   - **For Discrete**: Connect to FB pin via voltage divider

4. **Add Output Connector**:
   - Connect screw terminals or banana jacks
   - Label: "3V OUTPUT"

5. **Add Power Indicator**:
   - Connect LED with 220Ω resistor in series
   - Connect to 3V output
   - **Purpose**: Visual indication of power

6. **Test 3V Output**:
   - Connect multimeter to output
   - Adjust potentiometer to achieve 3.0V
   - Verify stability

#### Step 3: 5V Output Section (60 min)

1. **Repeat Step 2** for 5V output:
   - Use second LM2596 module (or discrete circuit)
   - Connect to same input
   - Adjust to 5.0V output

2. **Test 5V Output**:
   - Connect multimeter to output
   - Adjust potentiometer to achieve 5.0V
   - Verify stability

#### Step 4: Integration and Testing (60 min)

1. **Connect Common Ground**:
   - Ensure all grounds are connected together
   - Verify continuity with multimeter

2. **Load Testing**:
   - Connect a small load (e.g., LED with resistor) to each output
   - Verify voltage remains stable under load
   - Test with different loads (10mA, 50mA, 100mA)

3. **Voltage Adjustment**:
   - Test potentiometer adjustment range
   - Verify both outputs can be adjusted independently
   - Document adjustment range

4. **Final Inspection**:
   - Check all connections
   - Verify no short circuits
   - Test with multimeter (voltage, continuity)

---

### Troubleshooting

**Problem**: No output voltage
- **Check**: Input voltage present? Fuse intact? Connections correct?
- **Solution**: Verify input, check fuse, verify all connections

**Problem**: Output voltage too high/low
- **Check**: Potentiometer adjustment, feedback circuit
- **Solution**: Adjust potentiometer, verify voltage divider values

**Problem**: Output voltage unstable (ripple)
- **Check**: Output capacitors, load current
- **Solution**: Increase output capacitance, check capacitor connections

**Problem**: Overheating
- **Check**: Input voltage too high? Current draw too high?
- **Solution**: Verify input voltage, reduce load, add heat sink

**Problem**: Reverse polarity damage
- **Check**: Diode protection working?
- **Solution**: Verify diode orientation, replace damaged components

---

## Part 2: PCB Conversion

### PCB Design Considerations

**Layout Priorities**:
1. **Input Section**: Fuse, diode, input capacitors near input connector
2. **Converter Modules**: Place modules with adequate spacing for heat dissipation
3. **Output Section**: Output capacitors and connectors near outputs
4. **Ground Plane**: Use ground plane for better noise immunity
5. **Trace Width**: Use wider traces for power (input/output) - minimum 0.5mm, recommended 1mm+

**Component Placement**:
- **Input Connector**: One edge of PCB
- **Converter Modules**: Center area with spacing
- **Output Connectors**: Opposite edge from input
- **Capacitors**: Close to modules (minimize trace length)
- **Potentiometers**: Accessible for adjustment

**PCB Size**: Approximately 80mm × 60mm (depends on module size)

### PCB Design Steps

1. **Create Schematic**:
   - Draw complete circuit schematic
   - Include all components and connections
   - Label all nets (power, ground, signals)

2. **Component Placement**:
   - Place input connector on one edge
   - Place converter modules in center
   - Place output connectors on opposite edge
   - Place capacitors close to modules
   - Place potentiometers for easy access

3. **Routing**:
   - Route power traces (wider traces)
   - Route ground (use ground plane if possible)
   - Route signal traces (feedback, adjustment)
   - Keep traces short for power paths

4. **Silk Screen**:
   - Label input connector: "INPUT 12V/24V"
   - Label output connectors: "3V OUTPUT", "5V OUTPUT"
   - Label potentiometers: "3V ADJ", "5V ADJ"
   - Add component values where helpful

5. **Design Review**:
   - Check for errors (DRC - Design Rule Check)
   - Verify trace widths (power traces adequate?)
   - Verify spacing (adequate clearance?)
   - Verify component footprints (correct sizes?)

### PCB Fabrication

**Follow Year 2 PCB Fabrication Guide**:
- See `../Year2/PCB_FABRICATION_GUIDE.md` for detailed process
- Use toner transfer or presensitized method
- Etch with ferric chloride (see `../resources/PRESENSITIZED_PCB_TEACHER_GUIDE.md`)

**Assembly**:
1. **Solder Components**:
   - Solder input connector
   - Solder fuse holder
   - Solder converter modules (or discrete components)
   - Solder output connectors
   - Solder all passive components

2. **Test PCB**:
   - Verify continuity (no short circuits)
   - Test with multimeter
   - Power on and test outputs

3. **Final Assembly**:
   - Add heat sinks if needed
   - Add labels/stickers
   - Add mounting holes (optional)

---

## Part 3: Usage and Applications

### Using the Power Supply

**Basic Usage**:
1. **Connect Input**: Connect 12V or 24V DC power supply to input connector
2. **Verify Power**: Check LED indicators (should light up)
3. **Adjust Outputs**: Use potentiometers to set 3V and 5V outputs
4. **Connect Load**: Connect circuits to 3V or 5V outputs as needed

**Safety**:
- ⚠️ **Never short outputs** (can damage converter)
- ⚠️ **Respect current limits** (typically 1-2A per output, check module specs)
- ⚠️ **Verify polarity** before connecting circuits
- ⚠️ **Use appropriate fuse** for input protection

### Applications Throughout Year 1

**Term 1**:
- Power LED circuits (3V or 5V)
- Power 555 timer circuits (5V)
- Power logic gate circuits (5V for 74HC series)

**Term 2**:
- Power sequential logic circuits (5V)
- Power counter circuits (5V)
- Power ALU circuits (5V)

**Term 3**:
- Power memory circuits (5V)
- Power control circuits (5V)
- Power integrated systems (3V and 5V)

### Advanced Features (Optional)

**Current Limiting**:
- Add current limiting circuits (transistor-based or IC-based)
- Protects against overcurrent
- Useful for testing circuits

**Voltage Monitoring**:
- Add voltmeters (analog or digital)
- Display output voltages
- Useful for adjustment

**Multiple Outputs**:
- Add additional outputs (e.g., 12V, adjustable)
- Useful for advanced projects

---

## Assessment

### Practical Assessment

**Breadboard Construction** (40 points):
- Input section working (10 points)
- 3V output working and adjustable (15 points)
- 5V output working and adjustable (15 points)

**PCB Conversion** (30 points):
- PCB design complete (10 points)
- PCB fabricated and assembled (10 points)
- PCB tested and working (10 points)

**Documentation** (20 points):
- Circuit schematic documented (10 points)
- Construction notes and troubleshooting (10 points)

**Usage** (10 points):
- Successfully used to power circuits (10 points)

**Total**: 100 points

### Learning Outcomes Checklist

- [ ] Understands step-down converter principles
- [ ] Can build power supply on breadboard
- [ ] Can adjust output voltages
- [ ] Can convert design to PCB
- [ ] Can troubleshoot power supply issues
- [ ] Can use power supply safely
- [ ] Can power circuits with appropriate voltage

---

## Resources

### Theory Materials
- See `../Term1/theory/Week01-02_ElectricityBasics.md` for voltage/current basics
- See `../Term1/theory/Week03-05_Components.md` for capacitor and diode basics

### PCB Fabrication
- See `../Year2/PCB_FABRICATION_GUIDE.md` for PCB fabrication process
- See `../resources/PRESENSITIZED_PCB_TEACHER_GUIDE.md` for etching details

### Component Datasheets
- **LM2596**: [LM2596 Datasheet](https://www.ti.com/lit/ds/symlink/lm2596.pdf)
- **LM2576**: [LM2576 Datasheet](https://www.ti.com/lit/ds/symlink/lm2576.pdf)

### Online Resources
- [Buck Converter Basics](https://www.allaboutcircuits.com/textbook/semiconductors/chpt-6/switching-regulators/)
- [LM2596 Module Tutorial](https://www.instructables.com/LM2596-DC-DC-Buck-Converter-Step-Down-Power-Supply/)

---

## Notes for Teachers

**Safety Considerations**:
- ⚠️ **Input Voltage**: 12V or 24V can cause burns if shorted
- ⚠️ **Fuse Required**: Always use fuse for input protection
- ⚠️ **Polarity**: Emphasize importance of correct polarity
- ⚠️ **Supervision**: Supervise students during construction and testing

**Simplification Options**:
- **Option 1**: Use pre-built modules (simplest, recommended for Year 1)
- **Option 2**: Build from discrete components (advanced, for students who want challenge)

**Timing**:
- **Week 1**: Breadboard construction (input + 3V output)
- **Week 2**: Breadboard construction (5V output + testing)
- **Week 3**: PCB design and fabrication (optional, can extend to Term 2)

**Integration**:
- This project can be started after Weeks 1-2 (basic electricity)
- Students can use it throughout Year 1 for all circuits
- PCB conversion can be done in Year 2 when learning PCB fabrication

---

*This power supply will be a valuable tool throughout the curriculum!*

