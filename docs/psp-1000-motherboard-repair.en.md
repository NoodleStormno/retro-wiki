# PSP 1000 Motherboard Repair - Complete Guide

> Your PSP 1000 exhibits strange issues: won't power on, frequent crashes, partial function loss, or complete bricking. Root causes often lie in the motherboard. As PSP's core, motherboard repair requires electronics skills but isn't impossible!

## Required Tools
- Phillips screwdriver, PH00 size
- Plastic spudger or guitar pick
- Digital multimeter
- Soldering iron and solder
- Hot air station (for BGA work)
- Magnifier or microscope
- 99% isopropyl alcohol and cotton swabs
- Flux and desoldering braid
- Anti-static gloves and mat
- Temperature-controlled soldering station (recommended)

## Repair Procedure

### 1. Safe Disassembly & Board Extraction
1. **Complete power down**: Remove battery and all detachable parts
2. **Full disassembly**: Follow standard PSP teardown procedure
3. **Disconnect all connections**:
   - Screen ribbon cable
   - Button ribbon cables
   - UMD drive ribbon cable
   - Speaker ribbon cable
   - WiFi module ribbon cable
4. **Remove motherboard**: Remove all motherboard mounting screws
5. **Extract motherboard**: Carefully extract, avoid bending

### 2. Motherboard Visual Inspection
1. **Visual check**:
   - Look for burn marks
   - Check capacitors for bulging/leaking
   - Check chips for physical damage
   - Check solder joints for cracks
2. **Smell check**: Burnt electronics odor?
3. **Touch check**: Gently touch main chips, check for abnormal heat

### 3. Power Circuit Check
#### Battery Power Section
1. **Measure battery interface**: Check battery contact voltage
2. **Check fuses**: Locate and test motherboard fuses
3. **Check charging chip**: Inspect charging management IC circuitry
4. **Check DC-DC converters**: Measure various voltage output points

#### Voltage Measurement Points
| Test Point | Normal Voltage | Function |
|------------|----------------|----------|
| Battery interface | 3.6-4.2V | Battery input |
| Main power output | 5.0V | System main power |
| Core voltage | 1.2V | CPU/GPU power |
| Memory voltage | 2.5V | Memory power |
| Screen power | 3.3V | Screen backlight power |

### 4. Common Fault Repairs
#### Fault 1: Complete No Power (Black Brick)
1. **Check power button**: Measure button functionality
2. **Check crystals**: 32.768kHz and 22.xxxMHz crystals
3. **Check power IC**: Power management chip
4. **Check BIOS chip**: Firmware corruption check

#### Fault 2: Crashes After Boot
1. **Check memory**: Run memory test program
2. **Check CPU power**: Measure CPU power stability
3. **Check cooling**: Thermal paste and heatsink
4. **Check clock signals**: Clock generator

#### Fault 3: Partial Function Failure
1. **WiFi not working**: Check WiFi module and antenna
2. **Audio issues**: Check audio chip and speakers
3. **USB not recognized**: Check USB port and chip
4. **Button failure**: Check button ribbon cables and connectors

### 5. Chip-Level Repair
#### BGA Chip Reballing
1. **Apply flux**: Apply appropriate flux around chip
2. **Even heating**: Use hot air station for uniform heating
3. **Gentle push**: Use tweezers to gently nudge chip
4. **Cooling check**: Natural cooling, inspect solder quality

#### SMD Component Replacement
1. **Mark orientation**: Record component installation direction
2. **Heat removal**: Remove old component with hot air or iron
3. **Clean pads**: Use desoldering braid to clean pads
4. **Solder new component**: Align position, solder new component

## PSP 1000 Motherboard Architecture

### 🏗️ Main Chip Overview
1. **MIPS R4000 CPU**: 333MHz, PSP's brain
2. **Media Engine**: Media decoding processor
3. **GPU**: Graphics Processing Unit
4. **Memory**: 32MB (4MB VRAM)
5. **Power Management IC**: Manages all power rails
6. **Audio chip**: Wolfson WM8750
7. **WiFi chip**: Marvell 88W8385

### 🔌 Motherboard Interface Guide
1. **Power interface**: Battery and charger connections
2. **Screen interface**: LCD screen connection
3. **UMD interface**: UMD drive connection
4. **Button interface**: All button connections
5. **Expansion interface**: Memory Stick and WiFi module

## Repair Difficulty: ★★★★★
## Estimated Time: 4-8 hours
## Success Rate: 50% (simple faults), 20% (chip-level faults)

---

### 🔧 Power Circuit Deep Repair
#### Charging Circuit Fault
1. **Symptoms**: Won't charge, charge light off
2. **Check points**:
   - Charging port integrity
   - Charging fuse continuity
   - Charging management IC damage
   - Related capacitor condition
3. **Repair**: Replace damaged components, repair circuits

#### Battery Detection Fault
1. **Symptoms**: Inaccurate battery display, sudden shutdown
2. **Check points**:
   - Battery detection resistors
   - ADC detection circuit
   - Related filter capacitors
3. **Repair**: Replace detection resistors, repair detection circuit

### 🛠️ BIOS Recovery & Programming
If motherboard is bricked, BIOS recovery may be needed:

#### Hardware BIOS Programming
1. **Required equipment**: Programmer or test jig
2. **Extract BIOS**: Extract BIOS file from working PSP
3. **Write to chip**: Program BIOS to faulty board's chip
4. **Risk**: Incorrect operation may permanently damage board

#### Software Recovery
1. **Pandora battery**: Create magic battery
2. **Recovery mode**: Enter recovery mode for firmware flash
3. **Prerequisite**: Basic motherboard functions must work

---

### 🔍 Motherboard Diagnostic Flow
#### Step 1: Power Check
1. Measure battery interface voltage → If normal
2. Measure main power output → If normal
3. Measure chip power rails → If normal
4. Proceed to next step

#### Step 2: Clock Check
1. Check 32.768kHz crystal → If normal
2. Check main clock crystal → If normal
3. Check clock distribution → If normal
4. Proceed to next step

#### Step 3: Reset Check
1. Check reset circuit → If normal
2. Check reset signals → If normal
3. Check chip resets → If normal
4. Proceed to chip-level diagnosis

#### Step 4: Chip Check
1. Check CPU operation → If normal
2. Check memory communication → If normal
3. Check bus signals → If normal
4. May require BGA rework

---

### 💡 Motherboard Maintenance & Protection
#### Daily Use Protection
1. **ESD protection**: Touch metal before handling
2. **Moisture protection**: Avoid humid environments
3. **Overheat prevention**: Avoid extended high-load operation
4. **Shock protection**: Avoid drops and vibration

#### Repair Precautions
1. **ESD protection**: Use anti-static wrist strap
2. **Temperature control**: Don't exceed soldering temperatures
3. **Time control**: Heat each joint ≤3 seconds
4. **Cleaning**: Thorough cleaning after repair

---

### 🎯 Repair Cost-Benefit Analysis
#### Worth Repairing Cases
1. **Sentimental value**: PSP with special meaning
2. **Rare versions**: Limited editions or special colors
3. **Simple faults**: Fuses, capacitors, simple components
4. **Learning purpose**: Want to learn electronics repair

#### Not Recommended Cases
1. **BGA chip damage**: High cost, low success rate
2. **Inner layer damage**: Unrepairable multilayer board damage
3. **Severe corrosion**: Extensive corrosion
4. **Low value**: Used PSP 1000 worth only ¥100-200

---

### 📊 PSP 1000 Motherboard Version Differences
#### Different Production Batches
1. **TA-079**: Earliest version, best quality
2. **TA-081**: Mid-era version, most common
3. **TA-082**: Later version, some component changes
4. **TA-086**: Final version, most simplified

#### Motherboard Compatibility
1. **Screen compatibility**: All versions screens interchangeable
2. **Case compatibility**: Same dimensions, mounting holes
3. **Firmware compatibility**: Different versions may need different firmware
4. **Repair differences**: Component locations may vary

---

### 🔬 Professional Repair Equipment Recommendations
#### Basic Equipment
1. **Multimeter**: Fluke or UNI-T brands
2. **Temperature-controlled station**: Hakko or Quick brands
3. **Hot air station**: 858D or similar
4. **Magnifier**: LED illuminated magnifier

#### Advanced Equipment
1. **Oscilloscope**: 100MHz bandwidth sufficient
2. **BGA rework station**: Professional chip repair
3. **Microscope**: Electronics repair microscope
4. **Programmer**: BIOS programming equipment

---

**Repair Experience**: PSP 1000 motherboard design is quite mature—most faults concentrate in power section. Capacitor issues have high repair success rates. BGA chip problems require professional equipment—not recommended without.

**Safety First**: Motherboard repair involves high voltage and precision work. Without experience, seek professional help. Incorrect repairs can cause further damage or safety risks.

**Final Advice**: Before deciding to repair, evaluate PSP value versus repair cost. Sometimes replacing entire motherboard (used ¥80-120) is more economical. But for learning or nostalgia, the repair process itself is rewarding.