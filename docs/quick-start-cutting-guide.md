---
id: quick-start-cutting-guide
title: Quick Start Cutting Guide
sidebar_label: Quick Start Cutting
---

# Quick Start Cutting Guide

This guide will take you from a newly assembled Maslow CNC to cutting your first project. Follow these steps in order for the best results.

## Prerequisites

Before starting, ensure you have:
- ✅ Maslow CNC machine assembled and connected
- ✅ WebControl or Makerverse software installed
- ✅ Computer connected to the Maslow controller
- ✅ Router/spindle mounted and tested
- ✅ Material secured to the work surface
- ✅ Basic understanding of safety procedures

## Step 1: Initial Setup and Connection

### Connect to Your Maslow
1. **Power on** your Maslow CNC controller
2. **Launch WebControl** or Makerverse on your computer
3. **Select the correct serial port** (usually shows as Arduino or USB device)
4. **Test the connection** - you should see the status change to "Connected"

### Safety Check
- Ensure emergency stop is accessible
- Check that all cables are secure
- Verify router is properly mounted
- Clear the work area of obstacles

## Step 2: Calibration (Critical Step)

### Basic Calibration Process
1. **Set Machine Dimensions**
   - Distance between motors (typically 2438mm for standard frame)
   - Motor height above workpiece
   - Sled weight and dimensions

2. **Chain/Belt Calibration**
   - Run "Extend All Chains/Belts" if needed
   - Measure and input actual distances
   - Follow the calibration wizard prompts

3. **Test Cuts**
   - Cut a small test square (100mm x 100mm)
   - Measure the actual dimensions
   - Adjust calibration if needed

> **Important**: Poor calibration is the #1 cause of cutting problems. Take time to get this right!

## Step 3: Z-Axis Setup

### Manual Z-Zeroing
1. **Jog the router** close to your material surface
2. **Place a piece of paper** between bit and material
3. **Lower slowly** until the paper drags slightly
4. **Set Z-Zero** in your control software

### Z-Probe Setup (Recommended)
- Consider setting up an automated Z-probe for consistent results
- See our dedicated Z-Axis Setup guide for detailed instructions

## Step 4: Prepare Your First Cut

### Choose a Simple Design
- Start with basic shapes (squares, circles)
- Use shallow cuts (1-2mm depth)
- Single pass operations

### G-Code Preparation
1. **Design your part** in CAD software (Fusion 360, Carbide Create, etc.)
2. **Generate toolpaths** with conservative settings:
   - Feed rate: 1000mm/min or slower
   - Spindle speed: 18,000 RPM (adjust for your router)
   - Depth per pass: 1-2mm maximum
3. **Export G-code** compatible with Maslow

### Material Preparation
- **Secure material** with clamps or screws
- **Check for flat surface** - use shims if needed
- **Mark your zero position** on the material

## Step 5: Your First Cut

### Pre-Flight Check
- [ ] G-code file loaded
- [ ] Zero positions set (X, Y, Z)
- [ ] Router/spindle running at correct speed
- [ ] Safety equipment on (glasses, hearing protection)
- [ ] Emergency stop within reach

### Running the Cut
1. **Start the router** and let it reach full speed
2. **Begin the G-code** program
3. **Monitor closely** for the first few minutes
4. **Watch for**:
   - Correct cutting depth
   - Smooth movement
   - Proper chip evacuation
   - No binding or unusual sounds

### If Something Goes Wrong
- **Hit emergency stop** immediately if anything looks wrong
- **Common issues**:
   - Cutting too deep → Check Z-zero and material thickness
   - Router moving erratically → Check calibration
   - Poor edge quality → Adjust feed rate or spindle speed

## Step 6: Post-Cut Activities

### After Successful Cut
1. **Turn off router** and let it stop completely
2. **Move router away** from workpiece
3. **Check cut quality** and dimensions
4. **Document settings** that worked well

### Troubleshooting Poor Results
- **Dimensions off**: Recalibrate the machine
- **Rough edges**: Adjust feed rates or router speed
- **Missed steps**: Check for binding, reduce acceleration
- **Depth variations**: Verify material flatness and Z-setup

## Quick Reference: Common Settings

### Conservative Starting Points
- **Feed Rate**: 1000 mm/min
- **Plunge Rate**: 500 mm/min  
- **Spindle Speed**: 18,000 RPM
- **Depth per Pass**: 1-2mm
- **Material**: Plywood or MDF for first cuts

### Safety Reminders
- Always wear safety glasses and hearing protection
- Keep hands away from moving parts
- Have emergency stop ready
- Never leave machine unattended during cuts

## Next Steps

Once you've successfully completed your first cut:
1. Experiment with different materials and settings
2. Try more complex designs and toolpaths
3. Set up automated Z-probing for efficiency
4. Join the [Maslow CNC Forums](https://forums.maslowcnc.com/) community for tips and support

## Need Help?

- **Calibration Issues**: See our dedicated Calibration Guide
- **WebControl Problems**: Check the WebControl Setup guide
- **Hardware Issues**: Visit the Troubleshooting section
- **Community Support**: [Maslow CNC Forums](https://forums.maslowcnc.com/)

---

*Remember: Take your time with setup and calibration. A well-calibrated machine will save you hours of frustration later!*