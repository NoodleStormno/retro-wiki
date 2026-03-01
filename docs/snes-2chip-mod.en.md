# SNES 2CHIP 50-60Hz Switchless Mod + LED Indicator - Complete Guide

![Super Nintendo Limited Edition](images/supernintendo2.webp)

## Overview

This guide details an advanced modification for Super Nintendo (SNES) consoles with 2CHIP motherboards, enabling automatic 50Hz/60Hz switching without physical switches, plus status LED indicators. This mod is particularly valuable for PAL region (50Hz) SNES owners, allowing seamless NTSC (60Hz) game compatibility with visual mode indication.

## Technical Principles

### 2CHIP Motherboard Identification
SNES has two primary motherboard designs:
1. **1CHIP**: Later design integrating PPU1 and PPU2 into a single chip
2. **2CHIP**: Early design using separate PPU1 and PPU2 chips

**This modification only works with 2CHIP motherboards**—1CHIP boards require different approaches.

### 50Hz/60Hz Switching Principle
PAL SNES defaults to 50Hz, while NTSC games are designed for 60Hz. By modifying the clock circuit, we can:
1. Detect cartridge region information
2. Automatically switch to appropriate clock frequency
3. Achieve intelligent switching without physical switches

### LED Indicator Principle
Added LEDs display:
- Current video mode (50Hz/60Hz)
- Modification circuit status
- Error states (if applicable)

## Required Tools & Components

### Electronic Components
- Microcontroller (ATtiny85 or PIC12F675 recommended)
- 16MHz crystal oscillator
- 22pF ceramic capacitors ×2
- 10kΩ resistors ×2
- 220Ω resistors ×2
- LEDs (dual-color or two single-color)
- Schottky diode (1N5817 or equivalent)
- Protoboard or custom PCB
- Fine gauge wire

### Tools
- Temperature-controlled soldering iron
- Solder and flux
- Desoldering pump or braid
- Multimeter
- Oscilloscope (recommended but optional)
- Programmer (for microcontroller)
- Drill bits (for LED mounting)
- Heat shrink tubing or electrical tape

### Software
- Microcontroller programming software
- Modification firmware (download or custom)
- Serial terminal program (for debugging)

## Safety Precautions

1. **ESD Protection**: Wear anti-static wrist strap throughout
2. **Power Off**: All soldering must be done with console completely unpowered
3. **Precision Work**: Motherboard solder points are tiny—fine soldering skills required
4. **Stage Testing**: Test at each phase to avoid cumulative errors
5. **Firmware Backup**: Backup original firmware before modifications

## Modification Steps

### Phase 1: Preparation

#### Step 1: Confirm Motherboard Type
1. Open SNES shell
2. Identify 2CHIP motherboard:
   - Look for two large PPU chips (typically labeled S-PPU1 and S-PPU2)
   - 1CHIP boards have only one PPU chip
3. Record motherboard model and revision

#### Step 2: Layout Planning
1. Determine microcontroller mounting location
2. Plan LED placement (shell or internal)
3. Route wiring to avoid interference with existing circuits

#### Step 3: Microcontroller Preparation
1. Program microcontroller:
   - Download or write 50/60Hz auto-detection firmware
   - Program using appropriate programmer
   - Test basic microcontroller functions

2. Assemble clock circuit:
   - Connect crystal oscillator and capacitors to microcontroller
   - Build complete circuit on protoboard
   - Test circuit operating frequency

### Phase 2: Motherboard Modification

#### Step 1: Locate Critical Test Points
Key connection points:
1. **Region detection point**: For cartridge region sensing
2. **Clock control point**: For 50/60Hz switching
3. **Power points**: +5V and GND
4. **Video output points** (optional): For mode detection

#### Step 2: Solder Connections
1. **Power connections**:
   - Locate stable +5V source
   - Find ground point
   - Solder fine wires, insulate with heat shrink

2. **Region detection connection**:
   - Locate region detection pins on cartridge slot
   - Solder wires to microcontroller input pins
   - Add pull-up/down resistors (as per design)

3. **Clock control connection**:
   - Locate clock circuit on motherboard
   - Find frequency control point
   - Solder control wire to microcontroller output pin

4. **LED connections**:
   - Plan LED mounting location
   - Drill hole for LED (if mounting in shell)
   - Connect LED to microcontroller output pins

#### Step 3: Install Modification Circuit
1. Secure microcontroller board:
   - Use double-sided tape or hot glue
   - Ensure no short circuits to other components
   - Verify shell closure clearance

2. Organize wiring:
   - Use cable ties or tape to secure wires
   - Prevent pinching during reassembly
   - Maintain clean appearance

### Phase 3: Testing & Debugging

#### Step 1: Basic Power Test
1. Power on without cartridge inserted
2. Verify modification circuit receives correct voltage
3. Confirm microcontroller initializes properly
4. Test LED initial state

#### Step 2: Functional Testing
1. **50Hz mode test**:
   - Insert PAL region cartridge
   - Observe LED indication (should show 50Hz mode)
   - Test game operation, check video stability

2. **60Hz mode test**:
   - Insert NTSC region cartridge
   - Observe LED indication (should show 60Hz mode)
   - Test game operation, check video stability

3. **Auto-switching test**:
   - Alternate between different region cartridges
   - Verify mode switching speed and accuracy
   - Test video stability during transitions

#### Step 3: Advanced Testing
1. **Timing tests** (with oscilloscope):
   - Measure actual output frequency
   - Check clock signal stability
   - Measure switching time

2. **Compatibility testing**:
   - Test various game cartridges
   - Test special chip games (Super FX, etc.)
   - Test extended operation stability

3. **Temperature testing**:
   - Run games for extended periods
   - Monitor modification circuit temperature
   - Ensure no overheating

### Phase 4: Final Assembly

#### Step 1: Installation Optimization
1. Verify all connections are secure
2. Ensure no short circuit risks
3. Optimize cable routing
4. Add additional insulation if needed

#### Step 2: Shell Modifications
1. LED installation:
   - If mounting in shell, ensure clean hole
   - Use appropriate LED bezel or diffuser
   - Ensure LED visibility without glare

2. Switch installation (if desired):
   - Install micro switch for manual override
   - Ensure smooth switch operation
   - Label switch function clearly

#### Step 3: Final Testing
1. Fully reassemble console
2. Perform comprehensive functional tests
3. Verify all original functions work correctly
4. Test modification performance under various conditions

## LED Indicator Schemes

### Scheme A: Dual-color LED
- **Green**: 60Hz mode (NTSC)
- **Red**: 50Hz mode (PAL)
- **Orange** (both colors): Switching or error state

### Scheme B: Dual LEDs
- **LED1** (Blue): 60Hz mode
- **LED2** (Yellow): 50Hz mode
- **Both blinking**: Error state

### Scheme C: Single LED Mode Indication
- **Solid on**: 60Hz mode
- **Slow blink** (1Hz): 50Hz mode
- **Fast blink** (5Hz): Error or switching

## Firmware Feature Options

### Basic Functions
1. Automatic region detection
2. Automatic frequency switching
3. LED status indication

### Advanced Functions (if firmware supports)
1. Manual override mode
2. Frequency fine-tuning (for specific displays)
3. Diagnostic mode
4. Settings storage (if using EEPROM)

### Debug Functions
1. Serial output status information
2. Error code display
3. Self-test mode

## Troubleshooting Common Issues

### Issue 1: No Video Output After Modification
- **Possible cause**: Clock signal problem or soldering error
- **Solution**: Check clock connections, verify signal with oscilloscope

### Issue 2: Incorrect Mode Detection
- **Possible cause**: Region detection wiring error or firmware issue
- **Solution**: Check detection circuit, update/debug firmware

### Issue 3: LED Not Lighting or Wrong Indication
- **Possible cause**: LED wiring error or incorrect resistor values
- **Solution**: Check LED circuit, test LED and resistors

### Issue 4: Unstable Game Operation
- **Possible cause**: Unstable clock signal or interference
- **Solution**: Check power filtering, optimize routing, add shielding

### Issue 5: Modification Circuit Overheating
- **Possible cause**: Short circuit or component failure
- **Solution**: Check current draw, replace faulty components

## Advanced Optimization Options

### Power Optimization
1. Add voltage regulation for stable supply
2. Add filtering capacitors to reduce noise
3. Use low-power components to reduce heat

### Signal Optimization
1. Use shielded wire to reduce interference
2. Add buffers to strengthen signals
3. Optimize grounding to reduce noise

### Feature Expansion
1. Add RGB output enhancement (concurrent modification)
2. Add audio enhancement circuits
3. Add save state functionality

## Compatibility Considerations

### Motherboard Compatibility
- Only works with 2CHIP motherboards
- Different 2CHIP revisions may require adjustments
- Some third-party or clone boards may be incompatible

### Game Compatibility
- Most games should work correctly
- Some special chip games may need testing
- Certain homebrew or modified games may behave unexpectedly

### Display Compatibility
- Most modern displays support both 50Hz and 60Hz
- Some older displays may support only one mode
- Display settings adjustments may be necessary

## Safety & Warranty

### Safety Considerations
1. Modification voids manufacturer warranty
2. Improper modification can permanently damage console
3. Proceed only if you understand the risks

### Reversibility
1. Design modification with reversibility in mind
2. Use connectors instead of direct soldering (if possible)
3. Keep all original components

## Professional Recommendations

### Skill Requirements
1. **Intermediate electronics**: Read schematics, perform precision soldering
2. **Programming basics**: Understand and modify microcontroller code
3. **Testing capability**: Use basic test equipment for diagnostics

### Learning Resources
1. Study SNES motherboard schematics
2. Learn microcontroller programming
3. Join modification communities for support

### Progressive Approach
1. Practice on non-critical consoles first
2. Test at each stage—don't complete all modifications at once
3. Thoroughly test after each phase

## Conclusion

The SNES 2CHIP 50-60Hz switchless modification is an advanced project requiring electronics skills, programming knowledge, and patience. Successfully completed, your PAL SNES will intelligently switch video modes without manual intervention, with clear visual feedback via LED indicators.

This modification not only enhances console functionality but provides deep insight into SNES hardware architecture. Beginners should start with simpler repair projects before attempting this advanced modification.

---
*Last Updated: February 28, 2026*  
*Reference: iFixit SNES 2CHIP 50-60 Hz Switchless Mod + LED Mod Guide*