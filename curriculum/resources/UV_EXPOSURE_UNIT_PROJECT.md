# UV LED Exposure Unit Project

## Project Overview

**Duration**: 1-2 weeks (4-6 hours total)  
**Prerequisites**: Basic soldering skills, understanding of electrical safety  
**Outcome**: Build a UV LED exposure unit for presensitized PCB fabrication  
**Assistance Level**: Teacher/Parent assisted (suitable for Year 2+ students with supervision)

## Learning Objectives

By completing this project, students will:
- Understand UV light requirements for photoresist exposure
- Build a practical UV exposure unit from LED strips
- Learn LED strip wiring and power supply selection
- Create a reusable tool for PCB fabrication
- Understand light distribution and evenness

## Project Value

This UV exposure unit is essential for:
- Presensitized PCB fabrication (Years 2-4)
- Alternative photography processes (cyanotype, etc.)
- Screen printing (if applicable)
- Any UV-sensitive material processing

**Usage**: Can be built as a **class-shared unit** (one per class) or **individual units** (for keen students)

---

## Materials Required

### Core Components

**UV LED Strips**:
- **2× 5m SMD 5050 UV LED Strips** (395-405nm wavelength)
  - **Wavelength**: 395-405nm (ideal for photoresist exposure)
  - **Type**: SMD 5050 (standard size, easy to work with)
  - **Length**: 5 meters each (total 10m, cut into 50cm pieces)
  - **Source**: Available from electronics suppliers, Amazon, AliExpress
  - **Cost**: ~€10-15 per 5m strip

**Enclosure**:
- **1× Plastic Storage Box** (40×60cm external, 36×56cm internal minimum)
  - **Material**: Durable plastic (thick-walled, industrial grade)
  - **Size**: Minimum 40×60cm (can be larger)
  - **Features**: Should have a flat bottom, removable lid
  - **Source**: Hardware stores, storage box suppliers
  - **Alternative**: Wooden box (heavier but more durable)

**Mounting Surface**:
- **1× Plywood Sheet** (3-5mm thick, 36×56cm to fit inside box)
  - **Purpose**: Mount LED strips on plywood for easier wiring
  - **Alternative**: Mount directly to box (harder to wire)

**Reflective Surface**:
- **1× Aluminum Reflective Tape** (or aluminum foil)
  - **Purpose**: Reflects UV light back, improves efficiency
  - **Coverage**: Cover front of plywood (or inside of box lid)

**Power Supply**:
- **1× 12V DC Power Supply** (5A minimum, 10A recommended)
  - **Voltage**: 12V DC (standard for LED strips)
  - **Current**: 5-10A (depends on number of LEDs)
  - **Connector**: DC barrel jack or screw terminals
  - **Source**: Electronics suppliers, Amazon

**Wiring Components**:
- **LED Strip Connectors** (optional, for easier connection)
- **Wire**: 18-20 AWG stranded wire (red/black for power)
- **Wire Strippers**: For preparing wire ends
- **Heat Shrink Tubing**: For insulation (optional)

**Control Components**:
- **1× Power Switch** (SPST toggle switch, rated for 12V/10A)
- **1× Timer** (optional, for automatic exposure timing)
  - **Simple Timer**: Mechanical timer or digital timer
  - **Advanced**: Arduino-based timer with display

**Safety Components**:
- **1× Fuse Holder** with 5A fuse (safety protection)
- **1× Power Indicator LED** (optional, shows unit is on)

### Tools Required

- **Soldering Iron** and solder
- **Wire Strippers**
- **Multimeter** (for testing)
- **Scissors** or **Utility Knife** (for cutting LED strips)
- **Drill** (for mounting switch, power connector)
- **Screwdriver** (for assembly)
- **Measuring Tape** (for layout)

### Optional Components

- **Glass or Acrylic Sheet** (for covering LEDs, protecting from dust)
- **Rubber Feet** (for stability)
- **Handle** (for portability)
- **Ventilation** (small fan, if unit gets warm)

---

## Design Specifications

### UV Light Requirements

**Wavelength**: 360-410nm (ideal for photoresist)
- **LED Strips**: 395-405nm (readily available, cost-effective)
- **Fluorescent Bulbs**: 365-370nm (better wavelength, but more expensive and hotter)

**Why LED Strips?**
- ✅ **Cost-Effective**: Much cheaper than fluorescent bulbs
- ✅ **Low Heat**: Produce minimal heat (important for photoresist)
- ✅ **Instant On**: No warm-up time
- ✅ **Compact**: Easy to mount in storage box
- ✅ **Adjustable**: Can control power levels

### Layout Design

**LED Strip Arrangement**:
- Cut 5m strips into **20× 50cm pieces**
- Arrange in **rows** (10 rows × 2 strips = 20 pieces)
- **Spacing**: Even spacing across mounting surface
- **Coverage**: Ensure even light distribution

**Power Distribution**:
- Connect strips in **parallel** (all positive together, all negative together)
- Use **thick wire** for power distribution (reduces voltage drop)
- **Fuse Protection**: Fuse in series with positive supply

**Control**:
- **Power Switch**: On/off control
- **Optional Timer**: Automatic exposure timing
- **Optional Power Levels**: Two power levels (full/half) using switch

---

## Construction Steps

### Step 1: Prepare Mounting Surface (60 min)

1. **Cut Plywood** (if needed):
   - Measure box interior dimensions
   - Cut plywood to fit (slightly smaller than interior)
   - Sand edges smooth

2. **Apply Reflective Surface**:
   - Cover front of plywood with aluminum tape
   - Ensure smooth, wrinkle-free application
   - **Alternative**: Use aluminum foil (less durable but works)

3. **Mark LED Strip Positions**:
   - Measure and mark positions for LED strips
   - **Layout**: Even spacing (e.g., 5cm spacing between strips)
   - **Rows**: 10 rows of 2 strips each (20 total pieces)

### Step 2: Cut and Prepare LED Strips (90 min)

1. **Cut LED Strips**:
   - Cut 5m strips into 20× 50cm pieces
   - **Cut Points**: Cut at marked cut points (between LED segments)
   - **CAUTION**: Do NOT cut through LED segments
   - Use sharp scissors or utility knife

2. **Test Each Strip** (optional but recommended):
   - Connect each strip to 12V power supply
   - Verify all LEDs light up
   - Check for any damaged segments

3. **Prepare Connection Points**:
   - Identify positive (+) and negative (-) terminals
   - Clean connection points (if needed)
   - Prepare for soldering

### Step 3: Mount LED Strips (120 min)

1. **Mount Strips to Plywood**:
   - Remove adhesive backing from LED strips
   - Press strips firmly onto plywood (on aluminum tape side)
   - **Alignment**: Ensure strips are straight and evenly spaced
   - **Pressure**: Apply firm pressure for good adhesion

2. **Verify Layout**:
   - Check all strips are properly aligned
   - Verify spacing is even
   - Check for any gaps or overlaps

### Step 4: Wire LED Strips (120 min)

**⚠️ TEACHER/PARENT SUPERVISION REQUIRED - SOLDERING INVOLVED**

1. **Plan Wiring**:
   - Design power distribution (parallel connection)
   - Plan wire routing (keep wires organized)
   - Identify connection points

2. **Solder Connections**:
   - **Power Distribution**: Solder thick wire (18 AWG) along strips
   - **Positive Bus**: Connect all positive terminals together
   - **Negative Bus**: Connect all negative terminals together
   - **Soldering Tips**:
     - Use adequate heat (350-400°C)
     - Clean connection points
     - Good solder joints (shiny, not dull)
     - Use heat shrink tubing for insulation

3. **Connect Power Supply**:
   - Solder power supply wires to distribution bus
   - **Positive**: Red wire to positive bus
   - **Negative**: Black wire to negative bus
   - **Fuse**: Install fuse in series with positive wire

4. **Install Control Components**:
   - **Power Switch**: Install in positive wire (before fuse)
   - **Power Indicator**: Install LED with resistor (optional)
   - **Timer**: Install timer if using (optional)

### Step 5: Install in Box (60 min)

1. **Mount Plywood in Box**:
   - Place plywood with LEDs in box
   - **Position**: LEDs facing up (toward lid)
   - **Secure**: Use screws or adhesive (if needed)

2. **Install Power Components**:
   - **Power Connector**: Drill hole for DC barrel jack
   - **Power Switch**: Drill hole for toggle switch
   - **Mount**: Secure all components

3. **Wire Management**:
   - Organize wires neatly
   - Secure wires (cable ties, clips)
   - Ensure no wires can short circuit

4. **Optional: Add Glass/Acrylic Cover**:
   - Cut glass or acrylic to fit over LEDs
   - **Purpose**: Protects LEDs from dust, provides flat surface
   - **Mount**: Secure to box or plywood

### Step 6: Testing and Calibration (60 min)

1. **Electrical Testing**:
   - **Continuity**: Check for short circuits (multimeter)
   - **Voltage**: Verify 12V at LED strips
   - **Current**: Measure current draw (should be 5-10A)
   - **Fuse**: Verify fuse is correct rating

2. **Light Testing**:
   - **Power On**: Turn on unit (use safety glasses - UV can damage eyes)
   - **Evenness**: Check light distribution (should be even)
   - **Intensity**: Verify UV intensity (should be strong)
   - **Coverage**: Check coverage area (should cover entire workspace)

3. **Exposure Testing**:
   - **Test Exposure**: Expose a test PCB (small piece)
   - **Time**: Test different exposure times (2-5 minutes)
   - **Results**: Check for proper exposure (photoresist should develop correctly)
   - **Calibration**: Determine optimal exposure time

4. **Safety Check**:
   - **No Short Circuits**: Verify no exposed wires
   - **Fuse Working**: Test fuse (should blow if shorted)
   - **Heat**: Check temperature (should be warm, not hot)
   - **Ventilation**: Ensure adequate ventilation (if needed)

---

## Usage Instructions

### Basic Usage

1. **Prepare PCB**:
   - Remove protective film from presensitized board
   - Place artwork (transparency) on board
   - Align and secure (glass/acrylic pressure plate)

2. **Place in Exposure Unit**:
   - Place board (artwork side up) in exposure unit
   - Close lid (if unit has lid)
   - Ensure good contact between artwork and board

3. **Expose**:
   - Turn on power switch
   - Set timer (if using)
   - **Exposure Time**: Typically 2.5-3.5 minutes (calibrate for your unit)
   - Monitor exposure (do not move board during exposure)

4. **Complete Exposure**:
   - Turn off power
   - Remove board
   - Proceed to development step

### Calibration

**Initial Calibration**:
1. **Test Exposure**: Expose small test board
2. **Vary Time**: Test 2, 2.5, 3, 3.5, 4 minutes
3. **Check Results**: Determine optimal exposure time
4. **Document**: Record optimal time for future use

**Factors Affecting Exposure Time**:
- **LED Intensity**: Higher intensity = shorter time
- **Distance**: Closer LEDs = shorter time
- **Photoresist Type**: Different boards require different times
- **Artwork Opacity**: More opaque = longer time needed

---

## Safety Considerations

### UV Light Safety

**⚠️ CRITICAL: UV Light Can Damage Eyes**
- **NEVER look directly at UV LEDs** (can cause eye damage)
- **Use Safety Glasses**: UV-blocking safety glasses when testing
- **Lid/Cover**: Keep lid closed during exposure (protects eyes)
- **Supervision**: Always supervise students during use

### Electrical Safety

**⚠️ POWER SUPPLY SAFETY**:
- **Fuse Required**: Always use fuse (protects against overcurrent)
- **Proper Wiring**: Ensure all connections are secure
- **No Exposed Wires**: All wires must be insulated
- **Grounding**: Ensure proper grounding (if applicable)

**⚠️ SOLDERING SAFETY**:
- **Ventilation**: Work in well-ventilated area
- **Heat**: Soldering iron is hot (350-400°C)
- **Supervision**: Teacher/parent must supervise soldering
- **Burns**: Be careful of hot components

### General Safety

- **Heat**: Unit may get warm during use (normal, but monitor)
- **Ventilation**: Ensure adequate ventilation (if unit gets hot)
- **Storage**: Store in safe location (away from students when not in use)
- **Maintenance**: Regular inspection for damage

---

## Troubleshooting

### Problem: LEDs Not Lighting

**Possible Causes**:
- Power supply not connected
- Fuse blown
- Wiring incorrect (polarity reversed)
- LED strip damaged

**Solutions**:
- Check power supply (multimeter)
- Check fuse (replace if blown)
- Verify wiring (positive/negative correct)
- Test individual strips

### Problem: Uneven Light Distribution

**Possible Causes**:
- LED strips not evenly spaced
- Some LEDs not working
- Reflective surface not applied correctly

**Solutions**:
- Recheck LED strip spacing
- Test individual strips (replace if needed)
- Reapply reflective surface (smooth, wrinkle-free)

### Problem: Exposure Too Long/Short

**Possible Causes**:
- LED intensity too low/high
- Distance from LEDs too far/close
- Power supply voltage incorrect

**Solutions**:
- Check power supply voltage (should be 12V)
- Adjust LED distance (if possible)
- Calibrate exposure time (test different times)

### Problem: Unit Overheating

**Possible Causes**:
- Current draw too high
- Poor ventilation
- Power supply inadequate

**Solutions**:
- Check current draw (should be 5-10A)
- Improve ventilation (add fan if needed)
- Verify power supply rating (should be 10A+)

---

## Cost Estimate

### Class-Shared Unit (One Unit)

**Materials**:
- 2× 5m UV LED strips: €20-30
- Storage box: €10-15
- Plywood: €5-10
- Aluminum tape: €2-5
- Power supply (12V/10A): €15-25
- Switches, wire, connectors: €5-10
- **Total**: ~€60-100

### Individual Unit (Per Student)

**Materials**: Same as above
**Total**: ~€60-100 per unit

**Note**: Individual units are optional - one class-shared unit is sufficient for most applications.

---

## Alternative Designs

### Option 1: Wooden Box

**Advantages**:
- More durable
- Better heat dissipation
- Professional appearance

**Disadvantages**:
- Heavier
- Requires woodworking skills
- More expensive

### Option 2: Commercial UV Exposure Unit

**Advantages**:
- Ready-made
- Professional quality
- Warranty

**Disadvantages**:
- Expensive (€200-500+)
- Less educational value
- Fixed specifications

### Option 3: Fluorescent Bulb Unit

**Advantages**:
- Better wavelength (365-370nm)
- More even light distribution

**Disadvantages**:
- More expensive (3× cost)
- Produces more heat
- Requires warm-up time
- Larger size

---

## Integration with Curriculum

### Year 2: PCB Fabrication Introduction

**Usage**: Students use UV exposure unit for presensitized PCB fabrication
**Reference**: See `PRESENSITIZED_PCB_TEACHER_GUIDE.md` for PCB fabrication process

### Year 3: SAP-1 PCB Conversion

**Usage**: Students use UV exposure unit for converting SAP-1 modules to PCB
**Reference**: See `../Year3/PCB_FABRICATION_GUIDE.md` for SAP-1 PCB conversion

### Year 4: Enhanced System PCBs

**Usage**: Students use UV exposure unit for advanced PCB fabrication
**Reference**: See `../Year4/PCB_FABRICATION_GUIDE.md` for advanced PCB fabrication

---

## Resources

### Online Resources

- **[Zebra Dry Plates: How I Built Myself Affordable UV LED Exposure Box](https://zebradryplates.com/how-i-built-myself-affordable-uv-led-exposure-box/)** - Detailed build guide with photos
- **[YouTube: UV Exposure Box Build Video](https://www.youtube.com/watch?v=rBBAUWRy0Mc)** - Video tutorial of build process
- **[YouTube: Automated UV Exposure Box Build Video](https://www.youtube.com/watch?v=QNTBKBjc-XE)** - Video tutorial of build process
### Curriculum References

- **Presensitized PCB Teacher Guide**: `PRESENSITIZED_PCB_TEACHER_GUIDE.md` - Complete PCB fabrication process
- **Year 2 PCB Fabrication**: `../Year2/PCB_FABRICATION_GUIDE.md` - PCB fabrication introduction
- **Year 3 PCB Fabrication**: `../Year3/PCB_FABRICATION_GUIDE.md` - SAP-1 PCB conversion

### Component Suppliers

- **UV LED Strips**: Electronics suppliers, Amazon, AliExpress
- **Storage Boxes**: Hardware stores, storage suppliers
- **Power Supplies**: Electronics suppliers, Amazon
- **Components**: Electronics suppliers, local electronics stores

---

## Assessment

### Practical Assessment

**Construction** (50 points):
- LED strips mounted correctly (15 points)
- Wiring complete and correct (20 points)
- Unit tested and working (15 points)

**Functionality** (30 points):
- Unit produces even UV light (15 points)
- Exposure time calibrated (15 points)

**Documentation** (20 points):
- Construction notes documented (10 points)
- Calibration results documented (10 points)

**Total**: 100 points

### Learning Outcomes Checklist

- [ ] Understands UV light requirements for photoresist
- [ ] Can wire LED strips correctly
- [ ] Can build UV exposure unit
- [ ] Can calibrate exposure time
- [ ] Can use unit safely
- [ ] Can troubleshoot common issues

---

## Notes for Teachers

### Construction Approach

**Option 1: Teacher/Parent Built** (Recommended for Class-Shared Unit)
- Teacher/parent builds unit before class
- Students learn to use it
- One unit per class is sufficient

**Option 2: Teacher/Parent Assisted** (For Individual Units)
- Students build with teacher/parent assistance
- Teacher/parent handles soldering (safety)
- Students learn wiring and assembly
- Suitable for Year 2+ students

**Option 3: Student Built** (Advanced)
- Advanced students build independently
- Full teacher supervision required
- Suitable for Year 3+ students with experience

### Safety Supervision

**Critical Supervision Points**:
- ⚠️ **Soldering**: Teacher/parent must supervise all soldering
- ⚠️ **UV Testing**: Students must wear UV-blocking safety glasses
- ⚠️ **Electrical Testing**: Teacher/parent must verify wiring before powering on
- ⚠️ **Usage**: Always supervise students during exposure unit use

### Maintenance

**Regular Maintenance**:
- **Inspection**: Check for damaged LEDs or wiring
- **Cleaning**: Clean LEDs and reflective surface (dust reduces efficiency)
- **Calibration**: Recalibrate exposure time if LEDs degrade
- **Testing**: Test unit periodically to ensure proper function

---

## Conclusion

The UV LED Exposure Unit is an **essential tool** for presensitized PCB fabrication. Building it provides valuable learning opportunities while creating a practical tool that will be used throughout Years 2-4.

**Key Benefits**:
- ✅ **Cost-Effective**: Much cheaper than commercial units
- ✅ **Educational**: Students learn LED wiring and power supply design
- ✅ **Practical**: Essential for PCB fabrication
- ✅ **Reusable**: One unit can serve entire class

**Remember**: Safety is paramount - always supervise construction and use, especially around UV light and electrical components.

---

*This UV exposure unit will be a valuable tool for all PCB fabrication projects!*

