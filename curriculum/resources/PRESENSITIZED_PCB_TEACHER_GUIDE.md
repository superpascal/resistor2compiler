# Presensitized PCB Fabrication: Comprehensive Teacher Guide

## Overview

This guide provides comprehensive instructions for teachers conducting presensitized PCB fabrication workshops. This method uses UV light exposure and chemical development to create high-quality printed circuit boards with fine traces and professional results.

**⚠️ CRITICAL SAFETY WARNING**: This process involves hazardous chemicals and requires **strict supervision** and **proper safety equipment**. This is a **highly supervised activity** that must be conducted with appropriate safety protocols.

**Target Audience**: Teachers and workshop supervisors  
**Student Level**: Years 2-4 (with strict supervision)  
**Complexity**: Moderate to High  
**Safety Level**: **HIGH RISK** - Requires proper safety equipment and supervision

---

## Table of Contents

1. [Safety Requirements](#safety-requirements)
2. [Materials and Equipment](#materials-and-equipment)
3. [Workshop Setup](#workshop-setup)
4. [Process Overview](#process-overview)
5. [Step-by-Step Process](#step-by-step-process)
6. [Chemical Handling](#chemical-handling)
7. [Troubleshooting](#troubleshooting)
8. [Student Supervision Guidelines](#student-supervision-guidelines)
9. [Emergency Procedures](#emergency-procedures)
10. [Resources and References](#resources-and-references)

---

## Safety Requirements

### ⚠️ MANDATORY Safety Equipment

**Personal Protective Equipment (PPE)**:
- ✅ **Chemical-resistant gloves** (nitrile or neoprene)
- ✅ **Safety goggles** (chemical splash protection)
- ✅ **Lab coat or apron** (chemical-resistant)
- ✅ **Closed-toe shoes** (no sandals or open footwear)
- ✅ **Long pants** (no shorts)
- ✅ **Well-ventilated area** (fume hood or outdoor area)

**Workshop Safety Equipment**:
- ✅ **Eye wash station** (within 10 seconds of work area)
- ✅ **Emergency shower** (if available)
- ✅ **First aid kit** (with chemical burn treatment)
- ✅ **Spill containment** (absorbent materials, neutralizers)
- ✅ **Fire extinguisher** (Class B for chemical fires)
- ✅ **Material Safety Data Sheets (MSDS)** for all chemicals

### ⚠️ Chemical Hazards

**Chemicals Used**:
1. **Developer Solution** (Sodium Carbonate/Sodium Hydroxide):
   - **Hazard**: Corrosive, skin/eye irritant
   - **Exposure**: Can cause burns, respiratory irritation
   - **Handling**: Use gloves, goggles, work in well-ventilated area

2. **Etchant** (Ferric Chloride or Ammonium Persulfate):
   - **Hazard**: Corrosive, toxic if ingested
   - **Exposure**: Can cause skin burns, eye damage
   - **Handling**: Use gloves, goggles, avoid inhalation

3. **Stripper** (Sodium Hydroxide solution):
   - **Hazard**: Highly corrosive, severe burns
   - **Exposure**: Can cause severe skin/eye burns
   - **Handling**: Extreme caution, full PPE required

4. **Acetone** (for cleaning):
   - **Hazard**: Flammable, skin/eye irritant
   - **Exposure**: Can cause dizziness, skin irritation
   - **Handling**: Use in well-ventilated area, avoid flames

### Safety Rules for Students

**MANDATORY Rules**:
1. ✅ **No unsupervised access** to chemicals
2. ✅ **PPE must be worn** at all times when handling chemicals
3. ✅ **No eating or drinking** in workshop area
4. ✅ **Wash hands** after handling chemicals
5. ✅ **Report spills immediately** to teacher
6. ✅ **Follow teacher instructions** exactly
7. ✅ **No horseplay** or distractions during chemical processes

---

## Materials and Equipment

### Presensitized PCB Boards

**Recommended Suppliers**:
- **[Amazon: Presensitized PCB Board](https://www.amazon.com/dp/B08257VSVX)** - Single-sided presensitized board
- **[Parts Express: Presensitized Board](https://www.amazon.com/Parts-Express-Presensitized-Board-Single/dp/B0002BGBM8/)** - Single-sided presensitized board
- **[Fortex Engineering: Presensitized FR4 Board](https://www.fortex.co.uk/product/pcb-laminate-presensitized-board-single-sided/)** - High-quality FR4 presensitized board (UK supplier)

**Board Specifications**:
- **Type**: Positive photoresist (most common)
- **Thickness**: 1.6mm (standard)
- **Copper**: 35μm or 70μm (1oz or 2oz)
- **Photoresist**: Pre-coated, light-sensitive layer
- **Protection**: Blue light-proof film (remove before exposure)

### UV Exposure Equipment

**Option 1: Commercial UV Exposure Unit**
- Professional UV exposure box
- Even UV light distribution
- Timer and intensity control
- **Cost**: $200-500

**Option 2: DIY UV LED Exposure Box** (✅ **RECOMMENDED for Education**)
- **Complete Project Guide**: See `UV_EXPOSURE_UNIT_PROJECT.md` for detailed build instructions
- **Cost**: ~€60-100 (vs. €200-500 for commercial units)
- **Teacher/Parent-Assisted**: Can be built as class-shared unit or by individual students
- **Components**: UV LED strips (395-405nm), storage box, 12V power supply, switches
- **Reference**: Based on [Zebra Dry Plates: Affordable UV LED Exposure Box](https://zebradryplates.com/how-i-built-myself-affordable-uv-led-exposure-box/) and [YouTube Build Video](https://www.youtube.com/watch?v=rBBAUWRy0Mc)
- **Advantages**: Affordable, educational, effective, customizable, low heat, instant on

**UV Light Requirements**:
- **Wavelength**: 350-450nm (UV-A range)
- **Intensity**: ~50mJ/cm²
- **Exposure Time**: 2.5-3.5 minutes (varies by board and light source)
- **Even Distribution**: Critical for consistent results

### Chemical Supplies

**Developer Solution**:
- **Sodium Carbonate** (Na₂CO₃) - Milder, recommended for students
  - **Concentration**: 1% solution (10g per liter of water)
  - **Temperature**: 20-25°C (room temperature)
  - **Alternative**: Sodium Hydroxide (NaOH) - stronger, more hazardous

**Etchant**:
- **Ferric Chloride** (FeCl₃) - Most common
  - **Concentration**: 30-40% solution
  - **Temperature**: 40-50°C (warm, speeds etching)
  - **Alternative**: Ammonium Persulfate - faster, but more expensive

**Stripper** (Optional - for removing photoresist after etching):
- **Sodium Hydroxide** (NaOH) solution
  - **Concentration**: 3-5% solution
  - **Temperature**: 50-60°C (warm)
  - **Alternative**: Acetone (for some photoresist types)

**Neutralizer** (for waste disposal):
- **Sodium Carbonate** or **Calcium Carbonate** (for acid neutralization)
- **pH indicator** (to verify neutralization)

### Artwork Preparation

**Positive Artwork** (transparent film with circuit pattern):
- **Method 1**: Laser printer on transparency film
  - **Resolution**: 600 DPI minimum (1200 DPI preferred)
  - **Film**: Clear transparency film for laser printers
  - **Print**: Mirror image (flipped horizontally)
  - **Ink**: Must be opaque (black toner)

- **Method 2**: Inkjet printer on transparency film
  - **Resolution**: 600 DPI minimum
  - **Film**: Clear transparency film for inkjet printers
  - **Print**: Mirror image
  - **Ink**: Must be opaque (may need multiple passes)

- **Method 3**: Professional photoplotting
  - **Resolution**: 2540 DPI or higher
  - **Film**: Professional photoplotting film
  - **Cost**: Higher, but best quality

**Artwork Requirements**:
- **Mirror Image**: Must be flipped horizontally (circuit pattern reversed)
- **Opaque**: Must block UV light completely (no light leaks)
- **Clean**: No dust, fingerprints, or smudges
- **Accurate**: 1:1 scale (verify with ruler)

### Other Equipment

**Workshop Equipment**:
- **Glass or Acrylic Sheet**: For UV exposure (pressure plate)
- **Rubber Roller**: For applying pressure during exposure
- **Developing Tray**: Plastic or glass tray for developer
- **Etching Tray**: Plastic tray for etchant (non-metallic)
- **Agitation**: Rocking table or manual agitation
- **Thermometer**: For monitoring solution temperatures
- **Timer**: For exposure and development timing
- **Measuring Equipment**: Graduated cylinders, scales
- **Cleaning Supplies**: Isopropyl alcohol, lint-free cloths
- **Drilling Equipment**: PCB drill, appropriate drill bits

---

## Workshop Setup

### Pre-Workshop Preparation

**1. Safety Check** (Before Each Workshop):
- ✅ Verify all safety equipment is present and functional
- ✅ Check eye wash station (test water flow)
- ✅ Verify ventilation is working
- ✅ Ensure MSDS sheets are accessible
- ✅ Check first aid kit is complete
- ✅ Verify spill containment materials are ready

**2. Chemical Preparation**:
- Prepare developer solution (if not pre-mixed)
- Prepare etchant solution (if not pre-mixed)
- Label all chemical containers clearly
- Store chemicals in appropriate containers (non-reactive)
- Prepare neutralizer solution for waste disposal

**3. Equipment Setup**:
- Set up UV exposure unit (test UV light)
- Prepare developing tray
- Prepare etching tray
- Set up agitation equipment
- Prepare artwork (verify mirror image, check for defects)

**4. Student Preparation**:
- Brief students on safety procedures
- Demonstrate proper PPE usage
- Explain process overview
- Review emergency procedures
- Assign student roles (if working in groups)

### Workspace Layout

**Recommended Layout**:
```
[UV Exposure Unit]  [Developing Station]  [Etching Station]  [Cleaning Station]
     (Area 1)            (Area 2)            (Area 3)            (Area 4)

[Safety Equipment]  [Chemical Storage]  [Waste Disposal]  [First Aid]
   (Station)            (Locked)            (Area)          (Station)
```

**Workflow**:
1. **Area 1**: UV Exposure (clean, dry area)
2. **Area 2**: Development (well-ventilated, with developer tray)
3. **Area 3**: Etching (well-ventilated, with etching tray)
4. **Area 4**: Cleaning (sink area, with acetone/alcohol)

---

## Process Overview

### Complete Process Flow

```
1. Artwork Preparation
   ↓
2. Board Preparation (Remove protective film)
   ↓
3. UV Exposure (Transfer circuit pattern)
   ↓
4. Development (Remove exposed photoresist)
   ↓
5. Inspection (Verify pattern quality)
   ↓
6. Etching (Remove unwanted copper)
   ↓
7. Stripping (Remove remaining photoresist)
   ↓
8. Cleaning (Final board preparation)
   ↓
9. Drilling (Component holes)
   ↓
10. Final Inspection
```

### Key Concepts

**Positive Photoresist**:
- **Unexposed Areas**: Photoresist remains hard, protects copper during etching
- **Exposed Areas**: Photoresist becomes soft, removed during development
- **Result**: Circuit pattern (traces) protected, unwanted copper removed

**UV Exposure**:
- UV light passes through transparent areas of artwork
- Exposes photoresist in those areas
- Unexposed areas (circuit pattern) remain protected

**Development**:
- Developer solution removes exposed (softened) photoresist
- Reveals copper in exposed areas
- Protected areas (circuit pattern) remain covered

**Etching**:
- Etchant removes exposed copper
- Protected copper (under photoresist) remains
- Result: Circuit pattern in copper

---

## Step-by-Step Process

### Step 1: Artwork Preparation

**Objective**: Create transparent positive artwork with circuit pattern

**Teacher Actions**:
1. **Design Verification**:
   - Verify circuit design is correct
   - Check for design rule violations (trace width, spacing)
   - Verify component placement

2. **Artwork Creation**:
   - Print circuit design on transparency film
   - **CRITICAL**: Print as **mirror image** (flipped horizontally)
   - Verify print quality (opaque, no light leaks)
   - Check scale (1:1, verify with ruler)

3. **Artwork Inspection**:
   - Check for dust, fingerprints, smudges
   - Verify all traces are opaque
   - Check for any defects or missing areas
   - Clean if necessary (lint-free cloth, isopropyl alcohol)

**Student Role** (Supervised):
- Observe artwork preparation
- Learn about mirror image requirement
- Understand print quality requirements

**Common Issues**:
- **Not mirror image**: Circuit will be reversed
- **Light leaks**: Will cause etching problems
- **Poor print quality**: Will result in poor circuit definition

---

### Step 2: Board Preparation

**Objective**: Prepare presensitized board for UV exposure

**Teacher Actions**:
1. **Remove Protective Film**:
   - Remove blue light-proof protective film
   - **CRITICAL**: Do this in **dim light** (not direct sunlight)
   - Handle board by edges only (avoid touching photoresist)
   - Work quickly to minimize exposure to ambient light

2. **Board Inspection**:
   - Check for defects in photoresist coating
   - Verify board is clean (no dust, fingerprints)
   - Check board size matches artwork

3. **Clean Board** (if needed):
   - Use lint-free cloth
   - Isopropyl alcohol (if necessary)
   - Avoid touching photoresist surface

**Student Role** (Supervised):
- Observe board preparation
- Learn about photoresist sensitivity
- Understand importance of clean handling

**Safety Notes**:
- ⚠️ **Dim Light**: Work in dim light to avoid premature exposure
- ⚠️ **Handle Carefully**: Avoid touching photoresist surface
- ⚠️ **Work Quickly**: Minimize time in ambient light

---

### Step 3: UV Exposure

**Objective**: Transfer circuit pattern to photoresist using UV light

**Teacher Actions**:
1. **Setup UV Exposure**:
   - Place artwork (circuit side up) on UV exposure unit
   - Place presensitized board (photoresist side down) on artwork
   - Align board with artwork (verify alignment)
   - Place glass/acrylic pressure plate on top
   - Apply pressure (rubber roller or weights)

2. **Exposure Settings**:
   - **Exposure Time**: 2.5-3.5 minutes (varies by board and light source)
   - **UV Intensity**: Verify UV light is working
   - **Pressure**: Ensure good contact between artwork and board

3. **Exposure Process**:
   - Start timer
   - Monitor exposure (do not move board during exposure)
   - Ensure even light distribution
   - Complete exposure time

4. **Post-Exposure**:
   - Remove pressure plate
   - Remove board (handle carefully)
   - Inspect board (should see pattern in photoresist)
   - Store in light-proof container until development

**Student Role** (Supervised):
- Observe UV exposure setup
- Learn about exposure timing
- Understand importance of alignment and pressure

**Common Issues**:
- **Over-exposure**: Photoresist too hard, difficult to develop
- **Under-exposure**: Photoresist not exposed enough, poor pattern definition
- **Poor Contact**: Blurry pattern, poor definition
- **Misalignment**: Circuit pattern in wrong position

**Troubleshooting**:
- **Test Exposure**: Do test exposure with small board to determine optimal time
- **Check UV Light**: Verify UV light intensity and even distribution
- **Verify Contact**: Ensure good contact between artwork and board

---

### Step 4: Development

**Objective**: Remove exposed photoresist to reveal copper circuit pattern

**⚠️ CHEMICAL PROCESS - STRICT SUPERVISION REQUIRED**

**Teacher Actions**:
1. **Prepare Developer Solution**:
   - **Sodium Carbonate Developer** (Recommended):
     - Concentration: 1% solution (10g Na₂CO₃ per liter of water)
     - Temperature: 20-25°C (room temperature)
     - Mix thoroughly until dissolved
   - **Alternative: Sodium Hydroxide Developer** (Stronger, more hazardous):
     - Concentration: 0.5-1% solution (5-10g NaOH per liter of water)
     - Temperature: 20-25°C
     - **EXTREME CAUTION**: Highly corrosive, use with full PPE

2. **Development Process**:
   - Pour developer solution into developing tray
   - Immerse exposed board in developer (photoresist side up)
   - **Agitate gently** (rock tray or use agitation equipment)
   - **Monitor development** (exposed areas should clear, revealing copper)
   - **Development Time**: 30-90 seconds (varies by board and developer strength)
   - Remove board when development is complete

3. **Development Completion**:
   - **Signs of Complete Development**:
     - Exposed areas: Copper visible (photoresist removed)
     - Protected areas: Photoresist still present (circuit pattern)
     - Clear distinction between exposed and protected areas
   - **Stop Development**: Remove board immediately when complete
   - **Rinse**: Rinse board thoroughly with water (stop development)

4. **Inspection**:
   - Inspect developed board
   - Verify circuit pattern is clear
   - Check for any development issues
   - Touch up if necessary (permanent marker for small defects)

**Student Role** (Supervised - Limited Participation):
- **Observe only** during chemical handling
- May assist with gentle agitation (with teacher guidance)
- Learn about development process
- **NO direct chemical handling** by students

**Safety Requirements**:
- ⚠️ **Full PPE**: Gloves, goggles, lab coat
- ⚠️ **Well-Ventilated**: Work in well-ventilated area
- ⚠️ **No Splashing**: Handle carefully to avoid splashing
- ⚠️ **Immediate Rinse**: Rinse any skin contact immediately

**Common Issues**:
- **Over-development**: Photoresist removed from protected areas (circuit damaged)
- **Under-development**: Exposed photoresist not fully removed
- **Uneven Development**: Poor agitation, uneven developer contact
- **Developer Too Strong**: Development too fast, difficult to control

**Troubleshooting**:
- **Development Too Fast**: Dilute developer, reduce temperature
- **Development Too Slow**: Increase developer strength, increase temperature
- **Uneven Development**: Improve agitation, ensure even contact
- **Over-development**: Reduce development time, use weaker developer

---

### Step 5: Inspection and Touch-Up

**Objective**: Verify development quality and fix any defects

**Teacher Actions**:
1. **Visual Inspection**:
   - Check circuit pattern is clear and complete
   - Verify all traces are protected (photoresist present)
   - Check for any defects or missing areas
   - Verify alignment is correct

2. **Touch-Up** (if needed):
   - **Small Defects**: Use permanent marker (black, opaque)
   - **Missing Areas**: Fill in with permanent marker
   - **Light Leaks**: Cover with permanent marker
   - **Verify Touch-Up**: Check marker is opaque

3. **Quality Check**:
   - Verify board is ready for etching
   - Check all critical areas are protected
   - Document any issues for future reference

**Student Role** (Supervised):
- Observe inspection process
- Learn about quality requirements
- May assist with touch-up (with teacher guidance)

---

### Step 6: Etching

**Objective**: Remove unwanted copper, leaving circuit pattern

**⚠️ CHEMICAL PROCESS - STRICT SUPERVISION REQUIRED**

**Teacher Actions**:
1. **Select Etchant** (Choose based on availability, cost, and safety):
   
   **Option 1: Ferric Chloride (FeCl₃)** - **MOST COMMON, RECOMMENDED**
   - **Concentration**: 30-40% solution (300-400g FeCl₃ per liter of water)
   - **Temperature**: 40-50°C (warm, speeds etching significantly)
   - **Etching Time**: 10-30 minutes (varies by copper thickness and temperature)
   - **Preparation**: 
     - Add ferric chloride crystals/powder to water slowly (exothermic reaction)
     - Stir until dissolved
     - Allow to cool if solution gets too hot
   - **Advantages**:
     - ✅ Most common, widely available
     - ✅ Relatively safe (compared to other etchants)
     - ✅ Can be reused multiple times
     - ✅ Works well at room temperature (slower) or warm (faster)
   - **Disadvantages**:
     - ⚠️ Stains everything (brown/yellow stains)
     - ⚠️ Slower than some alternatives
     - ⚠️ Contains heavy metals (proper disposal required)
   - **Safety**: Corrosive, can cause skin burns, toxic if ingested
   
   **Option 2: Ammonium Persulfate ((NH₄)₂S₂O₈)** - **FASTER, CLEANER**
   - **Concentration**: 15-20% solution (150-200g per liter of water)
   - **Temperature**: 40-50°C (warm, essential for effectiveness)
   - **Etching Time**: 5-15 minutes (faster than ferric chloride)
   - **Preparation**:
     - Dissolve ammonium persulfate in warm water
     - Mix thoroughly
     - Use fresh solution for best results
   - **Advantages**:
     - ✅ Faster etching than ferric chloride
     - ✅ Clear solution (no staining)
     - ✅ Cleaner process
     - ✅ Less corrosive than ferric chloride
   - **Disadvantages**:
     - ⚠️ More expensive than ferric chloride
     - ⚠️ Shorter shelf life (degrades over time)
     - ⚠️ Requires warm temperature (less effective at room temperature)
   - **Safety**: Less corrosive than ferric chloride, but still requires PPE
   
   **Option 3: Cupric Chloride (CuCl₂)** - **REUSABLE, ADVANCED**
   - **Concentration**: 20-30% solution
   - **Temperature**: 40-50°C
   - **Etching Time**: 10-20 minutes
   - **Preparation**: More complex, requires regeneration system
   - **Advantages**:
     - ✅ Can be regenerated and reused indefinitely
     - ✅ Clear solution
     - ✅ Environmentally friendly (reusable)
   - **Disadvantages**:
     - ⚠️ More complex setup required
     - ⚠️ Requires regeneration equipment
     - ⚠️ Not commonly used in educational settings
   - **Safety**: Corrosive, requires proper handling
   
   **Option 4: Sodium Persulfate (Na₂S₂O₈)** - **ALTERNATIVE TO AMMONIUM**
   - **Concentration**: 15-20% solution
   - **Temperature**: 40-50°C
   - **Etching Time**: 5-15 minutes
   - **Similar to**: Ammonium persulfate (slightly different properties)
   - **Advantages**: Similar to ammonium persulfate
   - **Disadvantages**: Similar to ammonium persulfate
   - **Safety**: Similar to ammonium persulfate

2. **Prepare Etchant Solution**:
   - **For Ferric Chloride**:
     - Measure required amount of ferric chloride
     - Add to water slowly (in well-ventilated area)
     - Stir until dissolved
     - Allow solution to reach working temperature (40-50°C)
   - **For Ammonium Persulfate**:
     - Measure required amount of ammonium persulfate
     - Dissolve in warm water (40-50°C)
     - Mix thoroughly
     - Use fresh solution for best results

2. **Etching Process**:
   - Pour etchant solution into etching tray (**non-metallic** - plastic or glass only)
   - **Warm Etchant** (if needed): Heat to 40-50°C using water bath (NOT direct heat/flame)
   - **Temperature Control**: Use thermometer to monitor temperature
   - Immerse developed board in etchant (copper side up)
   - **Agitate continuously** (rock tray manually or use agitation equipment)
   - **Agitation Methods**:
     - Manual: Rock tray gently back and forth
     - Mechanical: Use agitation equipment (if available)
     - Air bubbling: Use aquarium pump (if available, for better agitation)
   - **Monitor etching progress**:
     - Watch for copper dissolving in exposed areas
     - Check periodically (every 2-3 minutes)
     - Look for clear distinction between protected and exposed areas
   - **Etching Time** (varies by etchant and conditions):
     - **Ferric Chloride** (warm): 10-30 minutes
     - **Ferric Chloride** (room temp): 30-60 minutes
     - **Ammonium Persulfate** (warm): 5-15 minutes
     - **Ammonium Persulfate** (room temp): 20-40 minutes

3. **Etching Completion**:
   - **Signs of Complete Etching**:
     - Unwanted copper removed (exposed areas)
     - Circuit pattern visible (protected copper)
     - No copper in exposed areas
   - **Stop Etching**: Remove board immediately when complete
   - **Rinse**: Rinse board thoroughly with water (stop etching)

4. **Post-Etching Inspection**:
   - Inspect etched board
   - Verify circuit pattern is complete
   - Check for any etching issues
   - Verify no unwanted copper remains

**Student Role** (Supervised - Limited Participation):
- **Observe only** during chemical handling
- May assist with gentle agitation (with teacher guidance)
- Learn about etching process
- **NO direct chemical handling** by students

**Safety Requirements**:
- ⚠️ **Full PPE**: Gloves, goggles, lab coat
- ⚠️ **Well-Ventilated**: Work in well-ventilated area (fumes)
- ⚠️ **No Splashing**: Handle carefully to avoid splashing
- ⚠️ **Temperature Control**: Monitor temperature, avoid overheating
- ⚠️ **Immediate Rinse**: Rinse any skin contact immediately

**Common Issues**:
- **Over-etching**: Etching too long, traces may be damaged
- **Under-etching**: Copper not fully removed
- **Uneven Etching**: Poor agitation, uneven etchant contact
- **Etching Too Slow**: Cold etchant, low concentration

**Troubleshooting**:
- **Etching Too Slow**: Warm etchant, increase agitation, check concentration
- **Etching Too Fast**: Cool etchant, reduce agitation
- **Uneven Etching**: Improve agitation, ensure even contact
- **Over-etching**: Reduce etching time, monitor progress closely

---

### Step 7: Stripping (Photoresist Removal)

**Objective**: Remove remaining photoresist from circuit pattern

**⚠️ CHEMICAL PROCESS - STRICT SUPERVISION REQUIRED**

**Teacher Actions**:
1. **Prepare Stripper Solution**:
   - **Sodium Hydroxide Stripper** (Most Common):
     - Concentration: 3-5% solution (30-50g NaOH per liter of water)
     - Temperature: 50-60°C (warm)
     - **EXTREME CAUTION**: Highly corrosive, use with full PPE
   - **Alternative: Acetone** (For some photoresist types):
     - Use pure acetone
     - **FLAMMABLE**: Work in well-ventilated area, no flames

2. **Stripping Process**:
   - Warm stripper solution to 50-60°C (if using NaOH)
   - Immerse etched board in stripper
   - **Agitate gently**
   - **Monitor stripping** (photoresist should dissolve)
   - **Stripping Time**: 1-3 minutes (varies by photoresist type)

3. **Stripping Completion**:
   - **Signs of Complete Stripping**:
     - Photoresist removed (copper traces visible)
     - Clean copper surface
   - **Stop Stripping**: Remove board when complete
   - **Rinse**: Rinse board thoroughly with water

4. **Alternative: Manual Removal** (If stripper not available):
   - Use fine steel wool or abrasive pad
   - Gently scrub photoresist
   - **Caution**: Do not damage copper traces

**Student Role** (Supervised - No Participation):
- **Observe only** during chemical handling
- Learn about stripping process
- **NO direct chemical handling** by students

**Safety Requirements**:
- ⚠️ **Full PPE**: Gloves, goggles, lab coat (especially for NaOH)
- ⚠️ **Well-Ventilated**: Work in well-ventilated area
- ⚠️ **Extreme Caution**: NaOH is highly corrosive
- ⚠️ **Temperature Control**: Monitor temperature, avoid overheating
- ⚠️ **Immediate Rinse**: Rinse any skin contact immediately

**Common Issues**:
- **Stripping Too Slow**: Increase temperature, increase concentration
- **Stripping Too Fast**: Reduce temperature, reduce concentration
- **Photoresist Not Removing**: Wrong stripper, wrong temperature

---

### Step 8: Cleaning and Final Preparation

**Objective**: Clean board and prepare for drilling

**Teacher Actions**:
1. **Final Cleaning**:
   - Clean board with isopropyl alcohol
   - Remove any remaining residue
   - Dry board thoroughly

2. **Inspection**:
   - Verify circuit pattern is complete
   - Check for any defects
   - Verify trace quality
   - Check for any remaining photoresist

3. **Preparation for Drilling**:
   - Mark drill hole positions (if not visible)
   - Verify component placement
   - Check board is ready for drilling

**Student Role** (Supervised):
- May assist with cleaning (with teacher guidance)
- Observe inspection process
- Learn about quality requirements

---

### Step 9: Drilling

**Objective**: Drill component holes

**Teacher Actions**:
1. **Drill Setup**:
   - Select appropriate drill bits (typically 0.8mm, 1.0mm, 1.2mm)
   - Set up drilling station
   - Secure board for drilling

2. **Drilling Process**:
   - Drill component holes
   - Use appropriate drill bit size for each hole
   - Drill carefully to avoid damaging traces
   - Clean up burrs after drilling

3. **Post-Drilling**:
   - Inspect drilled holes
   - Verify hole positions are correct
   - Check for any drilling issues
   - Clean board

**Student Role** (Supervised):
- May assist with drilling (with teacher guidance and supervision)
- Learn about drilling techniques
- Understand drill bit selection

**Safety Requirements**:
- ⚠️ **Eye Protection**: Safety goggles mandatory
- ⚠️ **Secure Board**: Board must be secured
- ⚠️ **Proper Technique**: Use proper drilling technique
- ⚠️ **Supervised**: Students must be supervised during drilling

---

### Step 10: Final Inspection

**Objective**: Verify PCB is complete and ready for use

**Teacher Actions**:
1. **Visual Inspection**:
   - Check circuit pattern is complete
   - Verify all traces are intact
   - Check for any defects
   - Verify hole positions

2. **Continuity Testing** (if equipment available):
   - Test trace continuity
   - Verify no short circuits
   - Check for open circuits

3. **Documentation**:
   - Document any issues
   - Note process parameters (exposure time, development time, etc.)
   - Record results for future reference

**Student Role** (Supervised):
- Observe inspection process
- Learn about quality requirements
- Understand testing procedures

---

## Chemical Handling

### Developer Solution (Sodium Carbonate)

**Preparation**:
- **Concentration**: 1% solution (10g Na₂CO₃ per liter of water)
- **Temperature**: 20-25°C (room temperature)
- **Mixing**: Add sodium carbonate to water, stir until dissolved
- **Storage**: Store in labeled container, keep sealed

**Safety**:
- ⚠️ **Corrosive**: Can cause skin/eye irritation
- ⚠️ **PPE Required**: Gloves, goggles, lab coat
- ⚠️ **Well-Ventilated**: Work in well-ventilated area
- ⚠️ **First Aid**: Rinse with water if contact occurs

**Disposal**:
- Neutralize with acid (if needed)
- Dilute with water
- Dispose according to local regulations

### Etchant Options

#### Option 1: Ferric Chloride (FeCl₃) - **MOST COMMON, RECOMMENDED**

**Preparation**:
- **Concentration**: 30-40% solution (300-400g FeCl₃ per liter of water)
- **Temperature**: 40-50°C (warm, speeds etching significantly)
  - **Room Temperature**: Works but slower (30-60 minutes)
  - **Warm (40-50°C)**: Much faster (10-30 minutes)
- **Mixing**: 
  - Add ferric chloride crystals/powder to water slowly (exothermic reaction)
  - Stir until dissolved
  - Allow to cool if solution gets too hot
  - **CAUTION**: Mixing generates heat, add slowly
- **Storage**: Store in labeled container (plastic or glass), keep sealed
- **Reuse**: Can be reused multiple times (until copper saturation)

**Etching Process**:
- **Agitation**: Continuous agitation required (rock tray or mechanical)
- **Monitoring**: Check progress every 2-3 minutes
- **Completion**: Remove when all unwanted copper is dissolved
- **Rinsing**: Rinse board immediately with water to stop etching

**Safety**:
- ⚠️ **Corrosive**: Can cause skin burns, eye damage
- ⚠️ **Toxic**: Toxic if ingested
- ⚠️ **Staining**: Stains everything brown/yellow (clothing, surfaces)
- ⚠️ **PPE Required**: Gloves, goggles, lab coat (mandatory)
- ⚠️ **Well-Ventilated**: Work in well-ventilated area (fumes)
- ⚠️ **First Aid**: Rinse with water immediately if contact occurs, seek medical attention

**Disposal**:
- **DO NOT pour down drain** (contains heavy metals - copper, iron)
- **Neutralization**: Neutralize with base (sodium carbonate or calcium carbonate)
- **Copper Recovery**: Can precipitate copper (if equipment available)
- **Hazardous Waste**: Dispose as hazardous waste according to local regulations
- **Check Local Regulations**: Some areas have specific disposal requirements

#### Option 2: Ammonium Persulfate ((NH₄)₂S₂O₈) - **FASTER, CLEANER**

**Preparation**:
- **Concentration**: 15-20% solution (150-200g per liter of water)
- **Temperature**: 40-50°C (warm, essential for effectiveness)
  - **Room Temperature**: Much slower, less effective
  - **Warm (40-50°C)**: Fast and effective (5-15 minutes)
- **Mixing**:
  - Dissolve ammonium persulfate in warm water
  - Mix thoroughly until dissolved
  - Use fresh solution for best results
- **Storage**: Store in labeled container, keep sealed, use within shelf life
- **Shelf Life**: Degrades over time, use fresh solution

**Etching Process**:
- **Agitation**: Continuous agitation required
- **Monitoring**: Check progress frequently (etches faster)
- **Completion**: Remove when all unwanted copper is dissolved
- **Rinsing**: Rinse board immediately with water

**Safety**:
- ⚠️ **Corrosive**: Less corrosive than ferric chloride, but still requires PPE
- ⚠️ **Oxidizing Agent**: Can react with other chemicals
- ⚠️ **PPE Required**: Gloves, goggles, lab coat
- ⚠️ **Well-Ventilated**: Work in well-ventilated area
- ⚠️ **First Aid**: Rinse with water if contact occurs

**Disposal**:
- **Neutralization**: Neutralize with reducing agent or base
- **Dilution**: Dilute with water
- **Check Local Regulations**: Dispose according to local regulations
- **Less Hazardous**: Generally less hazardous than ferric chloride

**Advantages Over Ferric Chloride**:
- ✅ Faster etching (5-15 minutes vs 10-30 minutes)
- ✅ Clear solution (no staining)
- ✅ Cleaner process
- ✅ Less corrosive

**Disadvantages**:
- ⚠️ More expensive
- ⚠️ Shorter shelf life
- ⚠️ Requires warm temperature

#### Option 3: Cupric Chloride (CuCl₂) - **REUSABLE, ADVANCED**

**Preparation**:
- **Concentration**: 20-30% solution
- **Temperature**: 40-50°C
- **Etching Time**: 10-20 minutes
- **Regeneration**: Can be regenerated with hydrogen peroxide and hydrochloric acid
- **Complexity**: More complex setup, requires regeneration system

**Advantages**:
- ✅ Reusable indefinitely (with regeneration)
- ✅ Clear solution
- ✅ Environmentally friendly (reusable)

**Disadvantages**:
- ⚠️ More complex setup
- ⚠️ Requires regeneration equipment
- ⚠️ Not commonly used in educational settings

**Safety**: Corrosive, requires proper handling

**Disposal**: Can be regenerated, reducing waste

#### Option 4: Sodium Persulfate (Na₂S₂O₈) - **ALTERNATIVE TO AMMONIUM**

**Similar to**: Ammonium persulfate with slightly different properties

**Preparation**: Similar to ammonium persulfate
**Safety**: Similar to ammonium persulfate
**Disposal**: Similar to ammonium persulfate

### Etchant Comparison

| Etchant | Speed | Cost | Staining | Reusability | Safety | Recommended For |
|---------|-------|------|----------|-------------|--------|-----------------|
| **Ferric Chloride** | Moderate | Low | High (brown/yellow) | Yes (multiple uses) | Moderate | **Most common, recommended for education** |
| **Ammonium Persulfate** | Fast | Moderate | None (clear) | Limited | Moderate | Fast, clean results |
| **Cupric Chloride** | Moderate | Moderate | None (clear) | Yes (with regeneration) | Moderate | Advanced, reusable systems |
| **Sodium Persulfate** | Fast | Moderate | None (clear) | Limited | Moderate | Alternative to ammonium |

**Recommendation for Education**: **Ferric Chloride** - Most common, widely available, relatively safe, cost-effective, reusable.

### Stripper (Sodium Hydroxide)

**Preparation**:
- **Concentration**: 3-5% solution (30-50g NaOH per liter of water)
- **Temperature**: 50-60°C (warm)
- **Mixing**: Add NaOH to water slowly (exothermic reaction)
- **Storage**: Store in labeled container, keep sealed

**Safety**:
- ⚠️ **Highly Corrosive**: Can cause severe burns
- ⚠️ **PPE Required**: Gloves, goggles, lab coat (mandatory)
- ⚠️ **Well-Ventilated**: Work in well-ventilated area
- ⚠️ **Extreme Caution**: Handle with extreme care
- ⚠️ **First Aid**: Rinse with water immediately if contact occurs, seek medical attention

**Disposal**:
- Neutralize with acid (dilute acid, add slowly)
- Dilute with water
- Dispose according to local regulations

### Acetone (Cleaning)

**Safety**:
- ⚠️ **Flammable**: Keep away from flames, sparks
- ⚠️ **Well-Ventilated**: Work in well-ventilated area
- ⚠️ **PPE Required**: Gloves, goggles
- ⚠️ **First Aid**: Rinse with water if contact occurs

**Disposal**:
- Dispose as flammable waste according to local regulations

---

## Troubleshooting

### Common Problems and Solutions

#### Problem: Over-Exposure

**Symptoms**:
- Photoresist too hard after exposure
- Difficult to develop
- Poor pattern definition

**Solutions**:
- Reduce exposure time
- Check UV light intensity (may be too high)
- Verify exposure time with test board
- Use weaker UV light source

#### Problem: Under-Exposure

**Symptoms**:
- Photoresist not exposed enough
- Poor pattern definition
- Incomplete development

**Solutions**:
- Increase exposure time
- Check UV light intensity (may be too low)
- Verify UV light is working
- Ensure good contact between artwork and board

#### Problem: Over-Development

**Symptoms**:
- Photoresist removed from protected areas
- Circuit pattern damaged
- Traces not protected during etching

**Solutions**:
- Reduce development time
- Use weaker developer
- Monitor development closely
- Remove board immediately when development complete

#### Problem: Under-Development

**Symptoms**:
- Exposed photoresist not fully removed
- Copper not visible in exposed areas
- Poor etching results

**Solutions**:
- Increase development time
- Use stronger developer
- Increase temperature (slightly)
- Improve agitation

#### Problem: Over-Etching

**Symptoms**:
- Traces damaged or too thin
- Circuit pattern incomplete
- Poor circuit quality

**Solutions**:
- Reduce etching time
- Monitor etching progress closely
- Remove board immediately when etching complete
- Use weaker etchant or lower temperature

#### Problem: Under-Etching

**Symptoms**:
- Copper not fully removed
- Unwanted copper remains
- Poor circuit definition

**Solutions**:
- Increase etching time
- Warm etchant (40-50°C) - **Critical for speed**
- Increase agitation (continuous agitation required)
- Check etchant concentration (may need fresh etchant)
- Verify etchant is still active (ferric chloride can lose effectiveness after multiple uses)

#### Problem: Etching Too Slow

**Symptoms**:
- Etching takes too long
- Copper not dissolving
- Process inefficient

**Solutions**:
- **Warm etchant to 40-50°C** (most effective solution - speeds etching 2-3x)
- Increase agitation (continuous, vigorous agitation)
- Check etchant concentration (may be too weak)
- Use fresh etchant (old etchant may be exhausted)
- Consider switching to ammonium persulfate (faster etchant)

#### Problem: Etching Too Fast

**Symptoms**:
- Etching completes too quickly
- Risk of over-etching
- Difficult to control

**Solutions**:
- Cool etchant (reduce temperature to room temperature)
- Reduce agitation (gentler agitation)
- Monitor more closely (check every minute)
- Use weaker etchant concentration
- Consider switching to ferric chloride (slower, more controllable)

#### Problem: Poor Pattern Definition

**Symptoms**:
- Blurry circuit pattern
- Poor trace definition
- Inconsistent results

**Solutions**:
- Check artwork quality (opaque, clean)
- Ensure good contact during exposure
- Verify UV light distribution is even
- Check development process

---

## Student Supervision Guidelines

### Supervision Levels

**Level 1: Observation Only** (Chemical Processes):
- Students observe only
- No direct chemical handling
- Teacher performs all chemical operations
- Students learn by observation

**Level 2: Assisted Participation** (Non-Chemical Processes):
- Students may assist with non-chemical steps
- Teacher supervises closely
- Students learn by doing (under supervision)
- Examples: Artwork preparation, board handling, cleaning

**Level 3: Supervised Operation** (Drilling, Final Steps):
- Students may operate equipment (with supervision)
- Teacher provides guidance and oversight
- Students learn by doing (with close supervision)
- Examples: Drilling, final inspection

### Supervision Ratios

**Recommended Ratios**:
- **Chemical Processes**: 1 teacher per 4-6 students (strict supervision)
- **Non-Chemical Processes**: 1 teacher per 8-10 students (moderate supervision)
- **Drilling**: 1 teacher per 2-3 students (close supervision)

### Student Participation Guidelines

**Allowed**:
- ✅ Observing all processes
- ✅ Assisting with artwork preparation (supervised)
- ✅ Assisting with board handling (supervised)
- ✅ Assisting with cleaning (supervised)
- ✅ Operating drilling equipment (with close supervision)
- ✅ Final inspection (supervised)

**NOT Allowed**:
- ❌ Direct chemical handling (developer, etchant, stripper)
- ❌ Mixing chemicals
- ❌ Unsupervised access to chemicals
- ❌ Operating UV exposure unit (teacher only)
- ❌ Chemical disposal (teacher only)

### Teaching Moments

**Use Supervision as Teaching Opportunity**:
- Explain each step as it's performed
- Discuss why safety measures are important
- Explain chemical reactions and processes
- Discuss troubleshooting and problem-solving
- Reinforce safety awareness

---

## Emergency Procedures

### Chemical Spill Procedures

**Small Spill** (< 100ml):
1. **Evacuate Area**: Move students away from spill
2. **Contain Spill**: Use absorbent materials
3. **Neutralize** (if appropriate): Use neutralizer
4. **Clean Up**: Use appropriate cleaning materials
5. **Ventilate**: Ensure area is well-ventilated
6. **Document**: Record spill incident

**Large Spill** (> 100ml):
1. **Evacuate Area**: Evacuate students immediately
2. **Contain Spill**: Use spill containment materials
3. **Ventilate**: Open windows, use ventilation
4. **Call for Help**: Contact appropriate authorities
5. **Secure Area**: Prevent access to spill area
6. **Document**: Record spill incident

### Chemical Contact Procedures

**Skin Contact**:
1. **Immediate Action**: Remove contaminated clothing
2. **Rinse**: Rinse affected area with water for 15 minutes
3. **Seek Medical Attention**: For corrosive chemicals (NaOH, FeCl₃)
4. **Document**: Record incident

**Eye Contact**:
1. **Immediate Action**: Use eye wash station
2. **Rinse**: Rinse eyes for 15 minutes (hold eyelids open)
3. **Seek Medical Attention**: Immediately
4. **Document**: Record incident

**Inhalation**:
1. **Immediate Action**: Move to fresh air
2. **Monitor**: Monitor breathing
3. **Seek Medical Attention**: If breathing difficulties
4. **Document**: Record incident

### Fire Procedures

**Chemical Fire**:
1. **Evacuate**: Evacuate students immediately
2. **Call Fire Department**: Call 911 (or local emergency number)
3. **Use Fire Extinguisher**: Class B fire extinguisher (if safe to do so)
4. **Do Not Use Water**: On chemical fires
5. **Secure Area**: Prevent access to fire area

---

## Resources and References

### Presensitized PCB Board Suppliers

- **[Amazon: Presensitized PCB Board](https://www.amazon.com/dp/B08257VSVX)** - Single-sided presensitized board
- **[Parts Express: Presensitized Board](https://www.amazon.com/Parts-Express-Presensitized-Board-Single/dp/B0002BGBM8/)** - Single-sided presensitized board
- **[Fortex Engineering: Presensitized FR4 Board](https://www.fortex.co.uk/product/pcb-laminate-presensitized-board-single-sided/)** - High-quality FR4 presensitized board (UK supplier)

### Chemical Suppliers

**Developer Chemicals**:
- **Sodium Carbonate (Na₂CO₃)**: Available from chemical suppliers, pool supply stores, online retailers
- **Sodium Hydroxide (NaOH)**: Available from chemical suppliers (caution: highly corrosive)

**Etchant Chemicals**:
- **Ferric Chloride (FeCl₃)**: Available from electronics suppliers, chemical suppliers, online retailers
  - **Form**: Crystals, powder, or liquid solution
  - **Common Sources**: Electronics hobby suppliers, chemical supply companies
- **Ammonium Persulfate ((NH₄)₂S₂O₈)**: Available from chemical suppliers, online retailers
  - **Form**: Powder or crystals
  - **Common Sources**: Chemical supply companies, specialty electronics suppliers
- **Cupric Chloride (CuCl₂)**: Available from chemical suppliers (advanced option)
- **Sodium Persulfate (Na₂S₂O₈)**: Available from chemical suppliers (alternative to ammonium)

**Stripper Chemicals**:
- **Sodium Hydroxide (NaOH)**: Available from chemical suppliers (caution: highly corrosive)
- **Acetone**: Available from hardware stores, chemical suppliers (flammable)

**Safety and Disposal**:
- **Neutralizers**: Sodium carbonate, calcium carbonate (for acid neutralization)
- **Spill Containment**: Absorbent materials, neutralizers

### Safety Resources

- **Material Safety Data Sheets (MSDS)**: Obtain from chemical suppliers
- **Chemical Safety Guidelines**: Local safety regulations
- **First Aid Procedures**: Standard first aid training
- **Emergency Procedures**: Local emergency services

### Educational Resources

- **Circuit Theory**: "Fundamentals of Electric Circuits" (ISE Edition) - ISBN-13: 978-1260570793
- **PCB Design**: KiCad tutorials, Fritzing tutorials
- **Photoresist Processing**: Manufacturer datasheets

### UV Exposure Equipment

**Commercial Units**:
- Professional UV exposure boxes (various suppliers)
- UV LED exposure units

**DIY UV Exposure Box**:
- **Complete Build Guide**: See `UV_EXPOSURE_UNIT_PROJECT.md` for detailed instructions
- UV LED strips (395-405nm) - SMD 5050 strips, 5m each
- Storage box (40×60cm) or wooden box
- Glass or acrylic top (optional, for protection)
- 12V power supply (5-10A), timer and switch
- **Reference**: [Zebra Dry Plates: Affordable UV LED Exposure Box](https://zebradryplates.com/how-i-built-myself-affordable-uv-led-exposure-box/) and [YouTube Build Video](https://www.youtube.com/watch?v=rBBAUWRy0Mc)

---

## Ferric Chloride Etching: Detailed Process Guide

### Quick Reference: Etchant Selection

| Etchant | Speed (Warm) | Cost | Staining | Reusability | Safety | Best For |
|---------|--------------|------|----------|-------------|--------|----------|
| **Ferric Chloride** | 10-30 min | Low | High | Yes | Moderate | **Education (Recommended)** |
| **Ammonium Persulfate** | 5-15 min | Moderate | None | Limited | Moderate | Fast, clean results |
| **Cupric Chloride** | 10-20 min | Moderate | None | Yes (regeneration) | Moderate | Advanced systems |
| **Sodium Persulfate** | 5-15 min | Moderate | None | Limited | Moderate | Alternative to ammonium |

**Recommendation**: **Ferric Chloride** for educational use - most common, cost-effective, reusable, relatively safe.

### Ferric Chloride (FeCl₃) - Primary Etchant

**Why Ferric Chloride?**
- ✅ Most common etchant for PCB fabrication
- ✅ Widely available and cost-effective
- ✅ Relatively safe (compared to other etchants)
- ✅ Can be reused multiple times
- ✅ Works at room temperature (slower) or warm (faster)
- ✅ Recommended for educational use

### Ferric Chloride Preparation

**Materials Needed**:
- Ferric chloride crystals or powder (FeCl₃)
- Water (distilled or deionized preferred, tap water acceptable)
- Non-metallic container (plastic or glass)
- Thermometer
- Stirring rod (non-metallic)
- Scale (for measuring)

**Preparation Steps**:
1. **Measure Ferric Chloride**:
   - For 30% solution: 300g FeCl₃ per liter of water
   - For 40% solution: 400g FeCl₃ per liter of water
   - **Recommended**: Start with 30-35% solution

2. **Add to Water** (CRITICAL - Add FeCl₃ to water, NOT water to FeCl₃):
   - Pour water into container first
   - Add ferric chloride slowly (exothermic reaction - generates heat)
   - **CAUTION**: Solution will heat up during mixing
   - Stir continuously until dissolved
   - Allow solution to cool if it gets too hot

3. **Temperature Control**:
   - **Room Temperature**: 20-25°C (slower etching, 30-60 minutes)
   - **Warm (40-50°C)**: Much faster etching (10-30 minutes)
   - **Heating Method**: Use water bath (NOT direct heat/flame)
   - **Monitor**: Use thermometer to monitor temperature

4. **Storage**:
   - Store in labeled, sealed container (plastic or glass)
   - Keep away from metals (will corrode)
   - Can be reused multiple times (until copper saturation)

### Ferric Chloride Etching Process

**Step-by-Step**:
1. **Setup**:
   - Pour etchant into non-metallic tray (plastic or glass)
   - Warm to 40-50°C if using warm method (water bath)
   - Ensure well-ventilated area

2. **Immerse Board**:
   - Place developed board in etchant (copper side up)
   - Ensure board is fully submerged
   - Board should not touch bottom of tray (use supports if needed)

3. **Agitation**:
   - **Continuous agitation is critical** for even etching
   - **Manual Method**: Rock tray gently back and forth continuously
   - **Mechanical Method**: Use agitation equipment (if available)
   - **Air Bubbling**: Use aquarium pump for better agitation (optional)

4. **Monitoring**:
   - Check progress every 2-3 minutes
   - Watch for copper dissolving in exposed areas
   - Look for clear distinction between protected (circuit) and exposed areas
   - **DO NOT over-etch** (remove board immediately when complete)

5. **Completion**:
   - **Signs of Complete Etching**:
     - All unwanted copper removed (exposed areas show fiberglass)
     - Circuit pattern clearly visible (protected copper)
     - No copper remaining in exposed areas
   - **Remove Board**: Remove immediately when complete
   - **Rinse**: Rinse thoroughly with water (stops etching)

6. **Post-Etching**:
   - Inspect board for completeness
   - Check for any etching issues
   - Verify circuit pattern is intact

### Ferric Chloride Safety

**Hazards**:
- ⚠️ **Corrosive**: Can cause skin burns, eye damage
- ⚠️ **Toxic**: Toxic if ingested
- ⚠️ **Staining**: Stains everything brown/yellow (clothing, surfaces, skin)
- ⚠️ **Fumes**: Can produce fumes (work in well-ventilated area)

**Safety Procedures**:
- ✅ **Full PPE**: Gloves, goggles, lab coat (mandatory)
- ✅ **Well-Ventilated**: Work in well-ventilated area or fume hood
- ✅ **No Splashing**: Handle carefully to avoid splashing
- ✅ **Temperature Control**: Use water bath for heating (NOT direct heat)
- ✅ **Immediate Rinse**: Rinse any skin contact immediately with water
- ✅ **Eye Protection**: Safety goggles mandatory (chemical splash protection)

**First Aid**:
- **Skin Contact**: Rinse with water for 15 minutes, remove contaminated clothing
- **Eye Contact**: Use eye wash station, rinse for 15 minutes, seek medical attention
- **Ingestion**: Do not induce vomiting, seek medical attention immediately
- **Inhalation**: Move to fresh air, seek medical attention if breathing difficulties

### Ferric Chloride Disposal

**⚠️ CRITICAL: DO NOT pour down drain** (contains heavy metals - copper, iron)

**Disposal Procedure**:
1. **Neutralization**:
   - Add base (sodium carbonate or calcium carbonate)
   - Stir until pH is neutral (test with pH paper)
   - Allow to settle

2. **Copper Recovery** (Optional, if equipment available):
   - Precipitate copper from solution
   - Recover copper for recycling

3. **Hazardous Waste Disposal**:
   - Dispose as hazardous waste according to local regulations
   - Contact local waste management for disposal procedures
   - **Check Local Regulations**: Some areas have specific requirements

4. **Storage** (If disposal delayed):
   - Store in labeled container
   - Keep sealed
   - Store in secure location (away from students)

### Ferric Chloride Reuse

**Can Be Reused**:
- Ferric chloride can be reused multiple times
- Effectiveness decreases as copper accumulates
- **Signs of Exhaustion**:
  - Etching takes much longer
  - Solution becomes very dark (copper saturation)
  - Etching incomplete even after extended time

**When to Replace**:
- When etching takes too long (even when warm)
- When solution is very dark (copper saturated)
- When etching is incomplete

**Reuse Tips**:
- Filter solution to remove copper particles (if possible)
- Add fresh ferric chloride to restore strength
- Monitor etching time (increasing time indicates exhaustion)

---

## Alternative Etchants

### Ammonium Persulfate - Fast, Clean Alternative

**When to Use**:
- When faster etching is needed (5-15 minutes vs 10-30 minutes)
- When clean, clear solution is preferred (no staining)
- When budget allows (more expensive than ferric chloride)

**Preparation**:
- **Concentration**: 15-20% solution (150-200g per liter)
- **Temperature**: 40-50°C (warm, essential for effectiveness)
- **Mixing**: Dissolve in warm water, mix thoroughly
- **Fresh Solution**: Use fresh solution for best results

**Etching Process**:
- Similar to ferric chloride process
- **Faster**: 5-15 minutes (warm temperature)
- **Clear Solution**: No staining
- **Continuous Agitation**: Required

**Safety**: Less corrosive than ferric chloride, but still requires PPE

**Disposal**: Neutralize and dispose according to local regulations (less hazardous than ferric chloride)

### Cupric Chloride - Reusable System (Advanced)

**When to Use**:
- For advanced workshops with regeneration equipment
- For environmentally conscious approach (reusable)
- For long-term use (can be regenerated indefinitely)

**Complexity**: Requires regeneration system (hydrogen peroxide + hydrochloric acid)

**Not Recommended**: For standard educational workshops (too complex)

---

## Conclusion

Presensitized PCB fabrication is a **professional-quality method** that produces excellent results but requires **strict safety protocols** and **careful supervision**. This guide provides comprehensive instructions for teachers to safely conduct presensitized PCB workshops.

**Key Points**:
- ✅ **Safety First**: Always prioritize safety, use proper PPE
- ✅ **Strict Supervision**: Chemical processes require teacher supervision
- ✅ **Quality Results**: Presensitized method produces professional-quality PCBs
- ✅ **Educational Value**: Students learn professional PCB fabrication methods
- ✅ **Proper Disposal**: Follow local regulations for chemical waste disposal
- ✅ **Ferric Chloride**: Recommended primary etchant for education (most common, cost-effective, reusable)

**Remember**: This is a **highly supervised activity** due to the chemicals involved. Always prioritize safety and follow proper procedures.

---

**Document Created**: 2025-12-16  
**Purpose**: Comprehensive teacher guide for presensitized PCB fabrication workshops  
**Safety Level**: **HIGH RISK** - Requires strict supervision and proper safety equipment

