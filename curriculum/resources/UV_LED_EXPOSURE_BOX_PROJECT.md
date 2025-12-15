# UV LED Exposure Box Project

## Project Overview

**Duration**: 1-2 weeks (4-6 hours total, teacher/parent-assisted)  
**Prerequisites**: Basic soldering skills, understanding of electrical safety  
**Outcome**: Build an affordable UV LED exposure box for presensitized PCB fabrication

**Purpose**: This exposure box is essential for the presensitized PCB fabrication method taught in Years 2-4. It provides consistent UV exposure for transferring circuit patterns to photoresist-coated boards.

**Reference**: Based on [affordable DIY UV LED exposure box build](https://zebradryplates.com/how-i-built-myself-affordable-uv-led-exposure-box/) by Nejc Urankar

---

## Learning Objectives

By completing this project, students (with teacher/parent assistance) will:
- Understand UV exposure requirements for photoresist
- Build a practical UV exposure unit
- Learn LED strip wiring and power management
- Create a reusable tool for PCB fabrication
- Understand the relationship between UV wavelength and photoresist sensitivity

---

## Project Value

This UV exposure box will be used for:
- **Year 2**: PCB fabrication introduction (presensitized method)
- **Year 3**: SAP-1 module PCB conversion
- **Year 4**: Enhanced system PCB fabrication
- **Future Projects**: All presensitized PCB work

**Cost Savings**: Commercial UV exposure units cost $200-500+. This DIY version costs approximately $60-80 (€60 as referenced in source).

---

## Materials Required

### Core Components

**UV LED Strips**:
- **2× SMD 5050 UV LED Strips** (5m each, 395-405nm wavelength)
  - **Wavelength**: 395-405nm (optimal for photoresist exposure)
  - **Type**: SMD 5050 UV LED strips
  - **Length**: 5m per strip (total 10m)
  - **Source**: Available from electronics suppliers, online retailers (Amazon, etc.)
  - **Note**: Ensure wavelength is 395-405nm (not lower wavelength which is more expensive)

**Enclosure**:
- **Plastic Storage Box**: 40cm × 60cm (external dimensions)
  - **Internal Size**: Approximately 36cm × 56cm (usable workspace)
  - **Type**: Durable, industrial-style plastic storage box
  - **Alternative**: Wooden box (heavier, requires woodworking skills)
  - **Source**: Hardware stores, storage box suppliers

**Mounting Surface**:
- **Plywood Sheet**: Thin sheet (3-5mm) to fit inside box
  - **Size**: Slightly smaller than internal box dimensions
  - **Purpose**: Mount LED strips for easier wiring
  - **Alternative**: Mount directly to box (more difficult wiring)

**Reflective Surface**:
- **Aluminum Tape**: Reflective aluminum tape
  - **Purpose**: Cover plywood surface to reflect UV light
  - **Benefit**: Increases light efficiency, more even exposure
  - **Source**: Hardware stores, HVAC suppliers

**Power Supply**:
- **12V DC Power Supply**: 5A or higher (60W+)
  - **Voltage**: 12V DC
  - **Current**: 5A minimum (for LED strips)
  - **Connector**: DC barrel jack or terminal block
  - **Source**: Electronics suppliers, online retailers

**Control Components**:
- **2× Toggle Switches**: SPST (Single Pole Single Throw)
  - **Purpose**: Control power levels (full power / half power)
  - **Rating**: 5A minimum
  - **Source**: Electronics suppliers

**Wiring**:
- **Wire**: 18-20 AWG stranded wire (red and black)
  - **Length**: Sufficient for connections
  - **Type**: Stranded (more flexible)
  - **Color**: Red (positive), Black (negative/ground)

**Connectors**:
- **DC Power Connector**: Barrel jack or terminal block
- **Wire Connectors**: Solder, wire nuts, or terminal blocks
- **Optional**: LED strip connectors (for easier connection)

### Tools Required

- **Soldering Iron**: For LED strip connections
- **Wire Strippers**: For wire preparation
- **Multimeter**: For testing connections
- **Drill**: For mounting switches and power connector
- **Screwdriver**: For assembly
- **Scissors or Wire Cutters**: For cutting LED strips
- **Measuring Tape**: For layout measurements
- **Safety Equipment**: Safety glasses, gloves (for soldering)

---

## UV Wavelength Requirements

### Why 395-405nm?

**Photoresist Sensitivity**:
- Presensitized PCB photoresist is sensitive to UV light
- **Optimal Wavelength**: 360-410nm
- **LED Strips**: 395-405nm (affordable, effective)
- **Fluorescent Bulbs**: 365-370nm (more expensive, hotter, slower startup)

**Comparison**:

| Light Source | Wavelength | Cost | Heat | Startup Time | Recommendation |
|--------------|-----------|------|------|--------------|----------------|
| **UV LED (395-405nm)** | 395-405nm | Low | Low | Instant | ✅ **Recommended** |
| **UV Fluorescent (365-370nm)** | 365-370nm | High | High | Slow | More expensive option |

**Why LEDs?**:
- ✅ **Affordable**: Much cheaper than fluorescent bulbs
- ✅ **Low Heat**: Produces minimal heat (important for photoresist)
- ✅ **Instant On**: No warm-up time
- ✅ **Compact**: Smaller, easier to mount
- ✅ **Efficient**: Lower power consumption

---

## Construction Steps

### Step 1: Prepare Mounting Surface (30 min)

1. **Cut Plywood**:
   - Measure internal box dimensions
   - Cut plywood to fit (slightly smaller than internal size)
   - Sand edges if needed

2. **Apply Reflective Tape**:
   - Cover entire front surface of plywood with aluminum tape
   - Ensure smooth, wrinkle-free application
   - **Purpose**: Reflects UV light back, increases efficiency

3. **Mark LED Strip Positions**:
   - Plan LED strip layout (rows of 50cm strips)
   - Mark positions on plywood
   - **Layout**: 20 strips of 50cm each (from 2× 5m strips)

### Step 2: Cut and Arrange LED Strips (60 min)

1. **Cut LED Strips**:
   - Cut 2× 5m strips into 20× 50cm pieces
   - **Cut Points**: Only at marked cut points (usually every 3 LEDs)
   - **CAUTION**: Do not cut between LEDs (will damage strip)
   - Use sharp scissors or wire cutters

2. **Arrange Strips**:
   - Arrange 20 strips in rows on plywood
   - **Spacing**: Even spacing for uniform exposure
   - **Orientation**: All LEDs facing same direction (toward exposure area)

3. **Mount Strips**:
   - Remove adhesive backing
   - Press strips firmly onto aluminum tape
   - Ensure good contact (strips should stick well)

### Step 3: Wire LED Strips (90 min)

**⚠️ TEACHER/PARENT SUPERVISION REQUIRED - SOLDERING INVOLVED**

1. **Plan Wiring**:
   - Determine series/parallel connections
   - **Recommended**: Parallel connection (all strips connected to same power)
   - Plan wire routing

2. **Solder Connections**:
   - Solder wires to LED strip pads
   - **Positive (Red)**: Connect to +12V pad on each strip
   - **Negative (Black)**: Connect to GND pad on each strip
   - **CAUTION**: Ensure correct polarity (LEDs won't work if reversed)

3. **Wire Management**:
   - Route wires neatly
   - Use wire ties or clips to organize
   - Leave enough wire for power supply connection

4. **Test Connections**:
   - Use multimeter to verify continuity
   - Check for short circuits
   - Verify all strips are connected

### Step 4: Install Power Supply and Controls (60 min)

1. **Mount Power Supply**:
   - Determine power supply location (inside or outside box)
   - Mount securely (if inside box, ensure ventilation)
   - Connect DC output to wiring

2. **Install Switches**:
   - Drill holes for toggle switches
   - Mount switches in accessible location
   - **Switch 1**: Full power (all strips)
   - **Switch 2**: Half power (half strips, for testing/adjustment)

3. **Wire Switches**:
   - Connect switches to control LED strips
   - **Full Power**: All strips connected
   - **Half Power**: Half strips connected (for lower intensity)
   - **CAUTION**: Ensure switches are rated for current (5A minimum)

4. **Install Power Connector**:
   - Mount DC power connector (barrel jack or terminal block)
   - Connect to power supply
   - Label clearly: "12V INPUT"

### Step 5: Final Assembly and Testing (60 min)

1. **Mount Plywood in Box**:
   - Secure plywood with LED strips inside box
   - Ensure LED strips face exposure area
   - Leave space for PCB placement

2. **Add Safety Features**:
   - Add warning label: "UV LIGHT - DO NOT LOOK DIRECTLY"
   - Add power indicator LED (optional)
   - Ensure box can be closed securely

3. **Test Exposure Box**:
   - Connect power supply
   - Turn on switches
   - Verify all LED strips light up
   - Check for even light distribution
   - Measure UV intensity (if UV meter available)

4. **Calibration** (Optional):
   - Test with sample presensitized board
   - Determine optimal exposure time
   - Document exposure settings

---

## Wiring Diagram

### Simple Parallel Connection

```
12V Power Supply (+)
  ↓
[Toggle Switch 1 - Full Power]
  ↓
[All 20 LED Strips in Parallel]
  ├─ Strip 1 (+12V, GND)
  ├─ Strip 2 (+12V, GND)
  ├─ ...
  └─ Strip 20 (+12V, GND)
  ↓
[Toggle Switch 2 - Half Power] (Optional, for half strips)
  ↓
Ground (-)
```

### Power Calculation

**LED Strip Power**:
- **Per Strip**: ~3W (typical for 50cm SMD 5050 strip)
- **20 Strips**: 20 × 3W = 60W
- **Power Supply**: 12V × 5A = 60W (minimum)
- **Recommended**: 12V × 6-7A = 72-84W (with margin)

---

## Usage Instructions

### For Presensitized PCB Fabrication

1. **Prepare Artwork**:
   - Print circuit design on transparency (mirror image)
   - Ensure artwork is opaque (no light leaks)

2. **Prepare Board**:
   - Remove protective film from presensitized board
   - Place board (photoresist side down) on artwork
   - Align carefully

3. **Expose**:
   - Place artwork + board in exposure box
   - Close box lid
   - Turn on UV lights (full power recommended)
   - **Exposure Time**: 2.5-3.5 minutes (varies by board and light intensity)
   - Use timer for accurate exposure

4. **Complete Process**:
   - Remove board after exposure
   - Continue with development process (see `PRESENSITIZED_PCB_TEACHER_GUIDE.md`)

### Exposure Time Guidelines

**Factors Affecting Exposure Time**:
- **Light Intensity**: Higher intensity = shorter time
- **Board Type**: Different photoresist sensitivities
- **Artwork Quality**: Opaque artwork = better exposure

**Typical Exposure Times**:
- **Full Power**: 2.5-3.5 minutes
- **Half Power**: 5-7 minutes (if using half power mode)
- **Test First**: Do test exposure with small board to determine optimal time

**Testing Exposure Time**:
1. Cut small test piece of presensitized board
2. Expose for different times (2 min, 2.5 min, 3 min, 3.5 min)
3. Develop all test pieces
4. Determine which exposure time gives best results
5. Use that time for future exposures

---

## Safety Considerations

### UV Light Safety

**⚠️ CRITICAL SAFETY WARNINGS**:

1. **Eye Protection**:
   - ⚠️ **NEVER look directly at UV LEDs** (can cause eye damage)
   - ⚠️ **Wear UV-blocking safety glasses** when working with exposure box
   - ⚠️ **Close box lid** before turning on UV lights

2. **Skin Protection**:
   - ⚠️ **Minimize skin exposure** to UV light
   - ⚠️ **Wear long sleeves** when operating exposure box
   - ⚠️ **Limit exposure time** (brief exposure is safe, prolonged is not)

3. **Ventilation**:
   - ⚠️ **Ensure adequate ventilation** (LEDs produce minimal heat, but box should be ventilated)
   - ⚠️ **Do not block ventilation** if power supply is inside box

4. **Electrical Safety**:
   - ⚠️ **Verify power supply voltage** (12V DC, not AC!)
   - ⚠️ **Check polarity** before connecting
   - ⚠️ **Use appropriate fuse** if recommended by power supply
   - ⚠️ **Disconnect power** when not in use

### Safety Checklist

Before Use:
- [ ] Power supply voltage verified (12V DC)
- [ ] Polarity checked (positive/negative correct)
- [ ] All connections secure
- [ ] Box lid closes properly
- [ ] Warning labels in place
- [ ] Safety glasses available

During Use:
- [ ] Box lid closed
- [ ] UV lights not visible (box closed)
- [ ] Timer set for exposure
- [ ] Adequate ventilation

After Use:
- [ ] Turn off UV lights
- [ ] Disconnect power (optional, for safety)
- [ ] Store in safe location

---

## Troubleshooting

### Problem: LED Strips Not Lighting

**Possible Causes**:
- Incorrect polarity (LEDs reversed)
- Loose connections
- Power supply not connected
- Switches not turned on

**Solutions**:
- Check polarity with multimeter
- Verify all connections are secure
- Check power supply is connected and powered
- Verify switches are in ON position

### Problem: Uneven Light Distribution

**Possible Causes**:
- LED strips not evenly spaced
- Some strips not working
- Reflective surface not covering entire area

**Solutions**:
- Rearrange LED strips for even spacing
- Check all strips are working (replace if needed)
- Ensure aluminum tape covers entire plywood surface

### Problem: Exposure Too Long/Too Short

**Possible Causes**:
- Light intensity too low/high
- Exposure time incorrect
- Board type different

**Solutions**:
- Adjust exposure time (test with small board)
- Use full power for faster exposure
- Document optimal exposure time for each board type

### Problem: Overheating

**Possible Causes**:
- Power supply inadequate
- Poor ventilation
- Too many strips for power supply

**Solutions**:
- Use larger power supply (higher current rating)
- Improve ventilation (add vents if needed)
- Reduce number of strips (if power supply inadequate)

---

## Cost Breakdown

**Approximate Costs** (based on source material):

| Component | Quantity | Approximate Cost |
|-----------|----------|------------------|
| UV LED Strips (5m) | 2× | $15-25 |
| Plastic Storage Box | 1× | $10-20 |
| Plywood Sheet | 1× | $5-10 |
| Aluminum Tape | 1× | $3-5 |
| 12V Power Supply (5A) | 1× | $10-15 |
| Toggle Switches | 2× | $3-5 |
| Wire and Connectors | - | $5-10 |
| **Total** | - | **$60-80** |

**Comparison to Commercial Units**:
- Commercial UV exposure units: $200-500+
- **Savings**: $140-440+ with DIY build

---

## Advanced Enhancements (Optional)

### Timer Integration

**Add Digital Timer**:
- Connect timer to control UV lights automatically
- Set exposure time, timer turns off lights
- Prevents over-exposure

### Light Intensity Control

**Add Dimmer/PWM Control**:
- Variable intensity control
- Adjust for different board types
- Fine-tune exposure

### Safety Interlock

**Add Lid Switch**:
- UV lights only turn on when lid is closed
- Prevents accidental UV exposure
- Safety feature for classroom use

### UV Intensity Meter

**Add UV Meter**:
- Measure actual UV intensity
- Calibrate exposure times accurately
- Monitor light output over time

---

## Integration with Curriculum

### Year 2: PCB Fabrication Introduction

**Usage**:
- Students learn presensitized PCB method
- Use exposure box for first PCB projects
- Understand UV exposure process

**Reference**: See `../Year2/PCB_FABRICATION_GUIDE.md`

### Year 3: SAP-1 Module Conversion

**Usage**:
- Students convert SAP-1 modules to PCB
- Use exposure box for module PCBs
- Practice with larger boards

**Reference**: See `../Year3/PCB_FABRICATION_GUIDE.md`

### Year 4: Enhanced System PCBs

**Usage**:
- Students fabricate advanced PCBs
- Use exposure box for complex designs
- Optimize exposure settings

**Reference**: See `../Year4/PCB_FABRICATION_GUIDE.md`

---

## Assessment

### Practical Assessment

**Construction** (60 points):
- LED strips mounted correctly (20 points)
- Wiring complete and functional (20 points)
- Power supply and controls working (20 points)

**Testing** (30 points):
- All LED strips light up (15 points)
- Even light distribution (15 points)

**Documentation** (10 points):
- Construction notes documented (5 points)
- Exposure time calibration documented (5 points)

**Total**: 100 points

### Learning Outcomes Checklist

- [ ] Understands UV wavelength requirements for photoresist
- [ ] Can wire LED strips correctly
- [ ] Can install power supply and controls
- [ ] Can test and calibrate exposure box
- [ ] Can use exposure box safely
- [ ] Understands exposure time calibration

---

## Resources

### Reference Materials

**Source Article**:
- [How I Built Myself Affordable UV LED Exposure Box](https://zebradryplates.com/how-i-built-myself-affordable-uv-led-exposure-box/) by Nejc Urankar

**PCB Fabrication Guides**:
- `PRESENSITIZED_PCB_TEACHER_GUIDE.md` - Complete presensitized PCB guide
- `../Year2/PCB_FABRICATION_GUIDE.md` - Year 2 PCB fabrication
- `../Year3/PCB_FABRICATION_GUIDE.md` - Year 3 PCB fabrication
- `../Year4/PCB_FABRICATION_GUIDE.md` - Year 4 PCB fabrication

### Component Suppliers

**UV LED Strips**:
- Electronics suppliers (Amazon, eBay, AliExpress)
- Search: "SMD 5050 UV LED strip 395nm" or "405nm"

**Storage Boxes**:
- Hardware stores
- Storage box suppliers
- Look for: 40cm × 60cm plastic storage boxes

**Power Supplies**:
- Electronics suppliers
- Look for: 12V DC, 5A+ power supplies

---

## Notes for Teachers/Parents

### Supervision Requirements

**Critical Supervision Points**:
- ⚠️ **Soldering**: Requires teacher/parent supervision
- ⚠️ **Electrical Connections**: Verify all connections before powering on
- ⚠️ **UV Safety**: Emphasize eye protection and safe operation

### Simplification Options

**For Younger Students**:
- Teacher/parent handles soldering
- Students assist with mounting and assembly
- Students learn about UV exposure and usage

**For Advanced Students**:
- Students can do soldering with supervision
- Students can design custom layouts
- Students can add enhancements (timer, etc.)

### Classroom Use

**Shared Resource**:
- One exposure box can serve entire class
- Students take turns using exposure box
- Teacher manages exposure schedule

**Individual Projects**:
- Advanced students can build their own
- Useful for students doing independent projects
- Good learning experience

### Maintenance

**Regular Maintenance**:
- Check LED strips periodically (replace if not working)
- Clean reflective surface (aluminum tape)
- Verify power supply operation
- Test exposure times periodically

**Longevity**:
- LED strips: 50,000+ hours (very long life)
- Power supply: Check periodically
- Box: Should last many years with care

---

## Conclusion

This UV LED exposure box project provides an **affordable, effective solution** for presensitized PCB fabrication. At approximately $60-80, it's a fraction of the cost of commercial units while providing excellent results.

**Key Benefits**:
- ✅ **Affordable**: 75-85% cost savings vs. commercial units
- ✅ **Effective**: Provides consistent, even UV exposure
- ✅ **Educational**: Students learn about UV exposure and LED systems
- ✅ **Reusable**: Will be used throughout Years 2-4
- ✅ **Customizable**: Can be enhanced with timers, safety features, etc.

**Remember**: This is a **teacher/parent-assisted project** due to soldering and electrical work. Safety is paramount, especially regarding UV light exposure.

---

*This exposure box will be a valuable tool for all presensitized PCB fabrication work!*

