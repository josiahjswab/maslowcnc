---
id: calibration-guide
title: Calibration Guide
sidebar_label: Calibration
---

# Maslow CNC Calibration Guide

Proper calibration is essential for accurate cuts. This guide covers the complete calibration process for both Chain and Belt Maslow machines.

## Understanding Calibration

Calibration teaches your Maslow the physical dimensions and characteristics of your specific machine setup. Poor calibration is the leading cause of:
- Inaccurate cut dimensions
- Wavy or curved cuts that should be straight
- Circles that aren't round
- Parts that don't fit together properly

## Before You Begin

### Required Tools
- Measuring tape (metric recommended)
- Calculator
- Test material (plywood or MDF)
- Router with a straight cutting bit

### Safety Preparation
- Ensure emergency stop is accessible
- Clear the work area
- Have safety equipment ready

## Chain Maslow Calibration

### Step 1: Basic Machine Dimensions

#### Distance Between Motors
1. **Measure carefully** between motor shaft centers
2. **Standard dimension**: 2438mm (8 feet) for most setups
3. **Enter exact measurement** in your control software

#### Motor Height Above Workpiece
1. **Measure vertically** from workpiece surface to motor shaft centers
2. **Typical range**: 400-600mm
3. **Account for sled thickness** in your measurements

#### Sled Specifications
- **Weight**: Weigh your complete sled (router + mount + ring)
- **Ring/Linkage dimensions**: Measure your specific ring kit
- **Router offset**: Distance from ring center to bit center

### Step 2: Chain Calibration Process

#### Rotational Radius
The rotational radius compensates for chain wrap around the sprockets:

**For Ring Kits:**
- Standard value: 139.75mm
- Verify with your specific ring documentation
- [Reference: Ring Kit Rotational Radius](https://forums.maslowcnc.com/t/ring-kit-rotational-radius/6113)

**For Triangular Linkage:**
- Measure from sprocket center to chain attachment point
- Typical values: 110-150mm

#### Chain Sag Correction
Chain sag affects accuracy, especially in lower areas:
1. **Enable chain sag correction** in settings
2. **Start with default values** (typically 10-20)
3. **Fine-tune based** on test cuts

### Step 3: Test and Verify

#### Calibration Test Cut
1. **Cut a test square**: 200mm x 200mm
2. **Measure all dimensions**: width, height, diagonals
3. **Check for square**: corners should be 90°

**Expected Results:**
- Dimensions within ±1mm of target
- Diagonals equal (indicating square corners)
- Smooth, straight edges

## Belt Maslow (M4) Calibration

### Step 1: Belt Extension Calibration

#### Initial Setup
1. **Run "Extend All Belts"** function
2. **Measure actual extensions** with ruler
3. **Input measured values** into calibration wizard

> **Troubleshooting**: If belts extend too far, see our [Belt Calibration Troubleshooting](troubleshooting-belt-calibration.md) guide

#### Belt Length Verification
- **Check belt tension**: Should be snug but not overly tight
- **Verify even extension**: All belts should extend similar amounts
- **Document final positions**: For future reference

### Step 2: Machine Geometry

#### Motor Spacing
- **Standard M4 setup**: 1200mm between top motors
- **Measure your actual spacing**: Enter exact dimensions
- **Verify level mounting**: Motors should be at same height

#### Frame Dimensions
- **Work area**: Input your available cutting area
- **Frame height**: Distance from top to bottom of work area
- **Safety margins**: Leave adequate buffer zones

## Advanced Calibration Techniques

### Multi-Point Calibration
For improved accuracy across the entire work area:

1. **Cut test squares** at multiple positions:
   - Center
   - Four corners
   - Midpoints of each side

2. **Measure and record** dimensions for each location

3. **Adjust calibration** to minimize overall error

### Accuracy Issues Troubleshooting

#### Common Problems and Solutions

**Cuts are consistently oversized/undersized:**
- Check motor distance measurement
- Verify rotational radius setting
- Recalibrate chain/belt lengths

**Circles aren't round:**
- Check chain sag settings
- Verify level motor mounting
- Test with smaller circles first

**Wavy cuts on straight lines:**
- Check for binding in movement
- Verify proper tension (chains/belts)
- Check for frame flex

**Accuracy varies by location:**
- Use multi-point calibration
- Check work surface flatness
- Verify consistent material thickness

### Fine-Tuning Tips

#### Incremental Adjustments
- Make small changes (1-2% at a time)
- Test after each adjustment
- Keep detailed records of changes

#### Environmental Factors
- **Temperature**: Wood and frame expand/contract
- **Humidity**: Affects wood dimensions
- **Wear**: Chains and belts stretch over time

## Calibration Maintenance

### Regular Checks
- **Monthly**: Quick dimensional check with test cuts
- **After major use**: Verify calibration hasn't drifted
- **Seasonal**: Account for temperature/humidity changes

### When to Recalibrate
- After any hardware changes
- If accuracy degrades noticeably  
- When switching between different materials
- After replacing chains/belts

## Documentation and Records

### Keep Track Of
- Final calibration values
- Test cut results and dates
- Any adjustments made
- Environmental conditions

### Backup Settings
- Export calibration files
- Document all custom values
- Take photos of physical setup

## Community Resources

- **Forum Discussion**: [Accuracy Issues and Calibration Overview](https://forums.maslowcnc.com/t/accuracy-issues-and-calibration-overview/5896)
- **Video Tutorials**: Check the community YouTube channels
- **Live Help**: Join discussions in the [Maslow CNC Forums](https://forums.maslowcnc.com/)

## Next Steps

After successful calibration:
1. **Document your settings** for future reference
2. **Practice with complex shapes** to verify accuracy
3. **Learn advanced features** like automatic calibration routines
4. **Help others** by sharing your calibration experience

---

*Good calibration takes time but pays dividends in every cut you make. Don't rush this critical step!*