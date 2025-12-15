# MPPT Solar Charge Controller: Year 1 Optional Capstone Project

## Project Overview

**Duration**: 4-6 weeks (optional end-of-year capstone project)  
**Prerequisites**: 
- Completion of Year 1 curriculum
- Understanding of step-down converters
- **REQUIRED**: Completion of Toroidal Inductor Module (`TOROIDAL_INDUCTOR_MODULE.md`)
**Assistance Level**: **Teacher/Parent Assisted** (advanced project requiring supervision)  
**Outcome**: Build a 1kW MPPT (Maximum Power Point Tracking) solar charge controller for off-grid solar systems

## Learning Objectives

By completing this capstone project, students will:
- Understand solar panel operation and maximum power point tracking
- Learn about buck converter design (building on Year 1 step-down converter project)
- Understand battery charging algorithms (CC-CV charging)
- Work with microcontrollers (ESP32) and sensors
- Build a practical, real-world power electronics project
- Learn about renewable energy systems

## Project Value

This capstone project:
- **Applies Year 1 Concepts**: Builds on step-down converter knowledge
- **Real-World Application**: Practical solar energy system component
- **Advanced Learning**: Introduces power electronics, microcontrollers, and algorithms
- **Portfolio Project**: Impressive end-of-year demonstration of skills
- **Optional Challenge**: For students who want to go beyond the standard curriculum

**Note**: This is an **advanced project** that requires significant teacher/parent assistance, especially for:
- PCB design and fabrication
- Microcontroller programming
- High-power electronics (safety critical)
- Testing and calibration

---

## What is an MPPT Solar Charge Controller?

### Maximum Power Point Tracking (MPPT)

**Simple Explanation**:
- Solar panels produce different amounts of power depending on sunlight, temperature, and load
- An MPPT controller finds the "sweet spot" where the panel produces maximum power
- It then converts that power to the right voltage/current to charge batteries efficiently

**Why It Matters**:
- Without MPPT: You might only get 60-70% of available solar power
- With MPPT: You can get 90-98% of available solar power
- **Result**: Much more energy from the same solar panels!

### How It Works

**Basic Operation**:
1. **Monitor**: Continuously monitors solar panel voltage and current
2. **Calculate Power**: Calculates power (voltage × current)
3. **Find Maximum**: Uses an algorithm to find the maximum power point
4. **Convert**: Uses a buck converter to step down voltage and step up current
5. **Charge Battery**: Charges battery at optimal voltage/current

**Example**:
- Solar panel: 40V, 10A = 400W
- Battery: 12V needs 33A to use all 400W
- MPPT converts: 40V/10A → 12V/33A (with ~98% efficiency)

---

## Project Specifications

### Technical Capabilities

**Input (Solar Panel)**:
- **Voltage**: Up to 80V (solar panel open-circuit voltage)
- **Current**: Up to 30A
- **Power**: Up to 1kW (1000W)

**Output (Battery)**:
- **Voltage**: 12V, 24V, 36V, 48V (selectable)
- **Current**: Up to 35A (limited to 30A for safety)
- **Battery Types**: Li-ion, LiFePO4, Lead Acid, etc.

**Features**:
- **MPPT Algorithm**: Perturb and Observe algorithm
- **CC-CV Charging**: Constant Current / Constant Voltage battery charging
- **Efficiency**: Up to 98% peak efficiency (synchronous buck design)
- **WiFi/Bluetooth**: ESP32-based telemetry and monitoring
- **LCD Display**: Menu interface with multiple display layouts
- **Safety**: Over-temperature protection, battery disconnect recovery

### Power Capability by Battery Voltage

- **12V Battery**: 420W @ 35A
- **24V Battery**: 840W @ 35A
- **36V Battery**: 1000W @ 35A
- **48V Battery**: 1000W @ 35A

---

## Materials Required

### Core Components

**Microcontroller**:
- **1× ESP32 WROOM32 MCU Module** (WiFi/Bluetooth capable)
  - **Purpose**: Main controller, runs MPPT algorithm
  - **Features**: Dual-core, WiFi, Bluetooth, ADC, PWM
  - **Part Number**: ESP32-WROOM-32

**Power Electronics**:
- **3× CSD19505 MOSFETs** (N-channel, high voltage, low Rds(on))
  - **Specifications**: 80V+ Vds, 30A+ Id, 2.6mΩ Rds(on) (very low!)
  - **Purpose**: Synchronous buck converter switching
  - **Part Number**: CSD19505KCS
- **1× IR2104 MOSFET Driver**
  - **Purpose**: Gate driver for MOSFET switching
  - **Part Number**: IR2104
- **1× Inductor** (high current, low resistance)
  - **Specifications**: 100µH, 35A+ saturation current
  - **Purpose**: Energy storage in buck converter
- **2× Schottky Diodes** (fast switching, low voltage drop)
  - **Purpose**: Protection and freewheeling

**Sensors**:
- **1× ADS1115 16-bit ADC** (or ADS1015 12-bit)
  - **Purpose**: Precise voltage/current measurement
  - **Part Number**: ADS1115 (16-bit) or ADS1015 (12-bit)
- **1× ACS712-30A Current Sensor**
  - **Purpose**: Input current measurement
  - **Part Number**: ACS712-30A
- **1× Temperature Sensor** (DS18B20 or similar)
  - **Purpose**: Over-temperature protection

**Display and Interface**:
- **1× 16×2 I2C Character LCD Display**
  - **Purpose**: Menu interface and data display
  - **Interface**: I2C (simplifies wiring)
- **3× Push Buttons** (for menu navigation)
  - **Note**: Button breakout board available (see PCB links)

**Supporting Components**:
- **2× XL7005A 80V 0.4A Buck Regulators**
  - **Purpose**: Power supply regulation
  - **Part Number**: XL7005A
- **1× B1212 DC-DC Isolated Converter**
  - **Purpose**: Isolated power supply
  - **Part Number**: B1212S-1W
- **1× AMS1117-3.3 LDO Linear Regulator**
  - **Purpose**: 3.3V power supply
  - **Part Number**: AMS1117-3.3
- **1× AMS1117-5.0 LDO Linear Regulator**
  - **Purpose**: 5V power supply
  - **Part Number**: AMS1117-5.0
- **1× CH340C USB to UART IC**
  - **Purpose**: USB programming interface
  - **Part Number**: CH340C
- **Voltage Dividers**: For input/output voltage sensing
- **Capacitors**: Input/output filtering (high current rated)
- **Resistors**: Voltage dividers, current sensing
- **Cooling Fan**: For thermal management (2-pin fan breakout board available)
- **Fuses**: Input/output protection
- **Connectors**: Solar panel input, battery output

**Note**: Complete parts list with all component values available in Google Drive (see Resources section)

### PCB and Enclosure

- **Custom PCB**: Designed in KiCad (or similar)
  - **Reference**: See Instructables guide for PCB design
  - **Alternative**: Can be built on prototype board (more complex)
- **Enclosure**: Weatherproof box (if for outdoor use)
- **Heat Sinks**: For MOSFETs (high power = heat)

### Tools Required

- **Soldering Station**: For PCB assembly
- **Multimeter**: For testing
- **Oscilloscope**: For debugging (optional but helpful)
- **Power Supply**: For testing (variable voltage/current)
- **Load Bank**: For testing (high power resistor or nichrome wire)

---

## Construction Overview

### Complexity Assessment

**Difficulty Level**: **ADVANCED** ⚠️

**Why It's Advanced**:
- **High Power**: Working with 1kW power levels (safety critical)
- **Complex Electronics**: Synchronous buck converter design
- **Microcontroller Programming**: ESP32 firmware development
- **PCB Design**: Multi-layer PCB with power and signal routing
- **Calibration**: Requires precise sensor calibration

**Teacher/Parent Assistance Required For**:
- ✅ PCB design and fabrication
- ✅ High-power electronics assembly
- ✅ Microcontroller programming
- ✅ Safety testing and calibration
- ✅ Troubleshooting and debugging

### Construction Phases

**Phase 1: Design and Planning** (1 week)
- Study MPPT principles
- Review circuit design
- Plan PCB layout
- Order components

**Phase 2: PCB Design and Fabrication** (1-2 weeks)
- Design PCB in KiCad
- Fabricate PCB (Year 2 PCB methods or professional)
- Test PCB (continuity, no short circuits)

**Phase 3: Component Assembly** (1 week)
- Solder components to PCB
- Verify all connections
- Test individual sections

**Phase 4: Firmware Development** (1 week)
- Install ESP32 development environment
- Load Fugu MPPT firmware (open source)
- Configure for your battery type
- Calibrate sensors

**Phase 5: Testing and Calibration** (1 week)
- Low-power testing (safety first!)
- Efficiency testing
- MPPT algorithm verification
- Battery charging tests

---

## Step-by-Step Construction

### Step 1: Study and Preparation

**Learning Resources**:
1. **Complete**: Toroidal Inductor Module (`TOROIDAL_INDUCTOR_MODULE.md`) - **REQUIRED PREREQUISITE**
2. **Read**: [Instructables: DIY 1kW MPPT Solar Charge Controller](https://www.instructables.com/DIY-1kW-MPPT-Solar-Charge-Controller/)
3. **Watch**: [YouTube: MPPT Solar Charge Controller Tutorial](https://www.youtube.com/watch?v=ShXNJM6uHLM)
4. **Understand**: Buck converter principles (from Year 1 step-down converter project)
5. **Review**: ESP32 basics (if not familiar)

**Key Concepts to Understand**:
- Buck converter operation (voltage step-down, current step-up)
- MPPT algorithm (perturb and observe)
- Battery charging (CC-CV profile)
- PWM control (pulse width modulation)

### Step 2: PCB Design

**PCB Options**:

**Option 1: Purchase Pre-Made PCBs (Recommended)**:
- **Main MPPT Board**: [PCBWAY - Main MPPT Board](https://bit.ly/3gGccE7)
- **Button Breakout Board**: [PCBWAY - Button Breakout Board](https://bit.ly/3kuwHF6)
- **2-Pin Fan Breakout Board**: [PCBWAY - 2-Pin Fan Breakout Board](https://bit.ly/3jsmWIn)
- **Advantages**: Professional quality, ready to use, saves time

**Option 2: Use PCB Files from Google Drive**:
- **PCB Files**: Available in [Google Drive](https://drive.google.com/drive/folder...) (see Resources section)
- **Fabrication**: Order from PCBWAY, JLCPCB, or similar
- **Advantages**: Customizable, lower cost in quantity

**Option 3: Design Your Own** (Advanced):
- Use Instructables guide as reference
- Requires significant PCB design experience
- Not recommended for Year 1 students

**Key Design Considerations**:
- **Power Traces**: Wide traces for high current (minimum 2mm, recommended 3mm+)
- **Ground Plane**: Use ground plane for better noise immunity
- **Component Placement**: Keep power components close together
- **Heat Management**: Adequate spacing for heat sinks
- **Isolation**: Separate power and signal sections

**PCB Fabrication** (if using Option 2 or 3):
- **PCBWAY**: [Main MPPT Board](https://bit.ly/3gGccE7), [Button Breakout](https://bit.ly/3kuwHF6), [Fan Breakout](https://bit.ly/3jsmWIn)
- **Alternative**: JLCPCB, PCBWay, or similar professional PCB services
- **Note**: Year 2 DIY PCB methods are not suitable for this complexity (multi-layer, fine traces, power routing)

### Step 3: Component Assembly

**⚠️ TEACHER/PARENT SUPERVISION REQUIRED**

**Assembly Order**:
1. **Passive Components**: Resistors, capacitors (low profile first)
2. **IC Sockets**: If using (easier troubleshooting)
3. **ICs**: ESP32, ADC, current sensor
4. **Power Components**: MOSFETs (with heat sinks), inductor
5. **Connectors**: Input/output terminals
6. **Display**: LCD and buttons

**Critical Assembly Points**:
- **Polarity**: Verify all polarized components (capacitors, diodes, MOSFETs)
- **Heat Sinks**: Properly mount heat sinks on MOSFETs
- **Solder Quality**: Good solder joints (especially for high current paths)
- **No Short Circuits**: Verify no solder bridges

### Step 4: Firmware Installation

**Fugu MPPT Firmware**:
- **GitHub Releases**: [FUGU-AR Firmware Releases](https://github.com/AngeloCasi/FUGU-AR...)
- **Google Drive**: Also available in [Google Drive](https://drive.google.com/drive/folder...) (see Resources section)
- **Open Source**: Free to use and modify
- **Features**: MPPT algorithm, CC-CV charging, WiFi telemetry, LCD interface

**Installation Steps**:
1. **Install Arduino IDE**: With ESP32 board support
2. **Download Firmware**: From Instructables G-Drive
3. **Configure**: Set battery type, voltage, current limits
4. **Calibrate Sensors**: Follow calibration guide in Instructables
5. **Upload**: Upload firmware to ESP32

**Configuration**:
- **Battery Type**: Select (Li-ion, LiFePO4, Lead Acid)
- **Battery Voltage**: Set max/min voltage
- **Charging Current**: Set maximum charging current
- **WiFi**: Configure WiFi credentials (optional)

### Step 5: Testing and Calibration

**⚠️ SAFETY FIRST - START WITH LOW POWER**

**Initial Testing**:
1. **No Power Test**: Verify no short circuits (multimeter)
2. **Low Power Test**: Test with low voltage/current (12V, 1A)
3. **Verify Operation**: Check LCD display, basic functions
4. **Gradual Increase**: Slowly increase power (monitor temperature)

**Calibration**:
1. **Voltage Calibration**: Calibrate input/output voltage sensors
2. **Current Calibration**: Calibrate current sensor (ACS712)
3. **MPPT Verification**: Test MPPT algorithm (find maximum power point)
4. **Efficiency Test**: Measure input/output power, calculate efficiency

**Full Power Testing**:
- **Only After**: Low power tests successful
- **Monitor**: Temperature, voltage, current continuously
- **Safety**: Have fire extinguisher ready, work in well-ventilated area

---

## Safety Considerations

### ⚠️ CRITICAL SAFETY WARNINGS

**High Power Electronics**:
- ⚠️ **1kW Power**: Can cause severe burns, fires, or explosions if mishandled
- ⚠️ **High Voltage**: Up to 80V input (can be dangerous)
- ⚠️ **High Current**: Up to 35A output (can cause severe burns)
- ⚠️ **Batteries**: Can explode if overcharged or shorted
- ⚠️ **Supervision Required**: Teacher/parent must supervise all testing

**Safety Procedures**:
- ✅ **Start Low**: Always test at low power first
- ✅ **Fuses**: Use appropriate fuses (input and output)
- ✅ **Heat Management**: Monitor temperature, use cooling fan
- ✅ **Fire Safety**: Have fire extinguisher nearby
- ✅ **Ventilation**: Work in well-ventilated area
- ✅ **Protective Equipment**: Safety glasses, insulated tools

**Battery Safety**:
- ⚠️ **Never Short**: Never short battery terminals
- ⚠️ **Correct Polarity**: Always verify polarity before connecting
- ⚠️ **Battery Type**: Configure firmware for correct battery type
- ⚠️ **Overcharge Protection**: Verify overcharge protection works

---

## Usage Instructions

### Basic Setup

1. **Connect Solar Panel**:
   - Connect solar panel to input terminals
   - **Verify**: Panel voltage is within limits (check Voc)
   - **Polarity**: Verify correct polarity

2. **Connect Battery**:
   - Connect battery to output terminals
   - **Verify**: Battery voltage matches configuration
   - **Polarity**: Verify correct polarity

3. **Power On**:
   - MPPT will start automatically
   - LCD will display status
   - MPPT algorithm will begin tracking

4. **Monitor**:
   - Watch LCD display for status
   - Monitor temperature (should stay cool)
   - Check battery charging progress

### Configuration

**LCD Menu Navigation**:
- Use buttons to navigate menu
- Configure battery type, voltage, current
- Set fan temperature, shutdown temperature
- Enable/disable WiFi

**WiFi Telemetry** (Optional):
- Connect to WiFi network
- Use phone app (Blynk) to monitor remotely
- View real-time data, graphs, history

---

## Troubleshooting

### Problem: No Output

**Possible Causes**:
- Battery not connected
- Battery voltage too low/high
- Fuse blown
- MOSFET failure

**Solutions**:
- Check battery connection
- Verify battery voltage is within limits
- Check fuse (replace if blown)
- Test MOSFETs (may need replacement)

### Problem: Low Efficiency

**Possible Causes**:
- Poor PCB design (narrow traces)
- MOSFET Rds(on) too high
- Inductor saturation
- Poor calibration

**Solutions**:
- Verify PCB power traces are wide enough
- Check MOSFET specifications
- Verify inductor current rating
- Recalibrate sensors

### Problem: Overheating

**Possible Causes**:
- Current too high
- Poor heat sinking
- Fan not working
- Poor ventilation

**Solutions**:
- Reduce charging current
- Verify heat sinks properly mounted
- Check fan operation
- Improve ventilation

---

## Assessment

### Capstone Project Assessment

**Design and Planning** (20 points):
- Circuit design understanding (10 points)
- Component selection rationale (10 points)

**Construction** (30 points):
- PCB design/fabrication (10 points)
- Component assembly (10 points)
- Soldering quality (10 points)

**Functionality** (30 points):
- MPPT algorithm working (15 points)
- Battery charging working (15 points)

**Testing and Documentation** (20 points):
- Efficiency testing (10 points)
- Documentation and report (10 points)

**Total**: 100 points

### Learning Outcomes Checklist

- [ ] Understands MPPT principles
- [ ] Understands buck converter operation
- [ ] Can assemble high-power electronics safely
- [ ] Can program ESP32 microcontroller
- [ ] Can calibrate sensors
- [ ] Can test and troubleshoot MPPT
- [ ] Understands battery charging algorithms
- [ ] Can document project and results

---

## Resources

### Primary Resources

- **[Instructables: DIY 1kW MPPT Solar Charge Controller](https://www.instructables.com/DIY-1kW-MPPT-Solar-Charge-Controller/)** - Complete build guide with schematics, PCB files, firmware
- **[YouTube: MPPT Solar Charge Controller Tutorial](https://www.youtube.com/watch?v=ShXNJM6uHLM)** - Video tutorial

### PCB Purchase Links (PCBWAY)

- **Main MPPT Board**: [PCBWAY - Main MPPT Board](https://bit.ly/3gGccE7)
- **Button Breakout Board**: [PCBWAY - Button Breakout Board](https://bit.ly/3kuwHF6)
- **2-Pin Fan Breakout Board**: [PCBWAY - 2-Pin Fan Breakout Board](https://bit.ly/3jsmWIn)

### Design Files and Documentation

- **Google Drive**: [Schematics, PCB Files, Parts List, Firmware](https://drive.google.com/drive/folder...)
  - Contains: Complete schematics, PCB Gerber files, parts list (Excel), firmware source code
  - **Note**: Refer to Excel sheet for complete component list with values

### Firmware

- **GitHub Releases**: [FUGU-AR Firmware Releases](https://github.com/AngeloCasi/FUGU-AR...)
  - Latest stable firmware releases
  - Source code and documentation
- **Google Drive**: Also available in Google Drive (see above)

### Component Suppliers

**Global Suppliers**:
- **[LCSC](https://lcsc.com/)** - Global electronics components
- **[AliExpress](https://aliexpress.com/)** - Global marketplace
- **[Mouser Electronics](https://www.mouser.com/)** - Global distributor

**Regional Suppliers**:
- **[E-Gizmo](https://www.e-gizmo.net/oc/index.php)** - Philippines
- **[Shopee](https://www.shopee.com/)** - Southeast Asia

**Component Sourcing Tips**:
- Compare prices across suppliers
- Check shipping costs and delivery times
- Verify component specifications match requirements
- Order extras for testing and mistakes

### Related Curriculum

- **Year 1 Toroidal Inductor Module**: `TOROIDAL_INDUCTOR_MODULE.md` - **REQUIRED PREREQUISITE** - Understanding toroidal inductors
- **Year 1 Step-Down Converter Project**: `DUAL_STEPDOWN_CONVERTER.md` - Foundation for understanding buck converters
- **Year 1 Step-Down Converter Theory**: `STEPDOWN_CONVERTER_THEORY.md` - Buck converter principles

### Additional Learning

- **MPPT Algorithms**: Research perturb and observe, incremental conductance
- **Battery Charging**: CC-CV charging profiles for different battery types
- **Power Electronics**: Buck, boost, buck-boost converter topologies
- **Renewable Energy**: Solar panel characteristics, off-grid systems

---

## Notes for Teachers

### Project Suitability

**Who Should Attempt This**:
- ✅ Students who completed Year 1 with strong understanding
- ✅ Students interested in power electronics
- ✅ Students who want a challenging capstone project
- ✅ Students with teacher/parent support available

**Who Should NOT Attempt This**:
- ⚠️ Students who struggled with basic electronics
- ⚠️ Students without teacher/parent assistance
- ⚠️ Students uncomfortable with high-power electronics

### Teaching Approach

**Option 1: Full Build** (4-6 weeks)
- Complete build from scratch
- Maximum learning, maximum time

**Option 2: Simplified Build** (2-3 weeks)
- Use pre-made PCB (from Instructables)
- Focus on assembly and programming
- Less time, still valuable learning

**Option 3: Demonstration Project** (1 week)
- Teacher builds, students observe and learn
- Focus on understanding principles
- Good for whole class learning

### Safety Supervision

**Critical Supervision Points**:
- ⚠️ **PCB Design**: Verify power traces adequate
- ⚠️ **Assembly**: Supervise all soldering, especially power components
- ⚠️ **Testing**: Always supervise testing, start low power
- ⚠️ **Calibration**: Help with sensor calibration
- ⚠️ **Usage**: Supervise initial solar panel/battery connections

### Integration with Curriculum

**Year 1 Concepts Applied**:
- Step-down converter principles (buck converter)
- Power supply design
- Component selection
- Circuit construction

**New Concepts Introduced**:
- MPPT algorithms
- Microcontroller programming
- Sensor calibration
- High-power electronics
- Renewable energy systems

---

## Conclusion

The MPPT Solar Charge Controller is an **excellent capstone project** for Year 1 students who want to apply their knowledge to a real-world, high-impact project. While it's advanced and requires significant assistance, it provides valuable learning in power electronics, renewable energy, and embedded systems.

**Key Benefits**:
- ✅ **Real-World Application**: Practical solar energy system
- ✅ **Advanced Learning**: Introduces power electronics and microcontrollers
- ✅ **Portfolio Project**: Impressive demonstration of skills
- ✅ **Foundation for Future**: Prepares for more advanced projects

**Remember**: This is an **optional, advanced project**. It's perfectly fine for students to complete Year 1 without attempting this. The standard curriculum provides excellent foundation, and this capstone is for those who want an extra challenge.

---

*This capstone project demonstrates the practical application of Year 1 electronics knowledge in a real-world renewable energy system!*

