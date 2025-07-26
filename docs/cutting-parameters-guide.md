---
id: cutting-parameters-guide
title: Maslow CNC Cutting Parameters Guide
sidebar_label: Cutting Parameters
---

# Maslow CNC Cutting Parameters Guide

This comprehensive guide covers cutting depths, feed rates, spindle speeds, and material-specific settings based on extensive community testing and forum discussions from [Maslow CNC Forums](https://forums.maslowcnc.com/).

## Quick Reference Chart

### Conservative Starting Settings

| Material | Bit Size | Depth per Pass | Feed Rate | Spindle RPM | Router Setting |
|----------|----------|----------------|-----------|-------------|----------------|
| 3/4" Plywood | 1/4" | 0.125" - 0.2" | 500-700 mm/min | 10,000-12,000 | Ridgid Setting 1-2 |
| 1/2" Plywood | 1/8" | 2-3 mm | 500-750 mm/min | 12,000-15,000 | Ridgid Setting 2-3 |
| MDF | 1/8" | 3-4 mm | 500 mm/min | 12,000 | Ridgid Setting 2 |
| Hardwood | 1/4" | 0.1" - 0.125" | 400-600 mm/min | 10,000-12,000 | Ridgid Setting 1-2 |

## General Rules of Thumb

### Depth per Pass Guidelines

**The Golden Rule**: Depth per pass should equal **1/2 the router bit diameter**

![Cutting Depth Assessment](/img/cutting-parameters/cutting-depth-diagram.jpg)

*Pyramid chart for assessing safe cutting depths based on various factors*

- **1/4" bit**: 0.125" (3.175mm) per pass maximum
- **1/8" bit**: 0.0625" (1.6mm) per pass maximum
- **1/16" bit**: 0.03125" (0.8mm) per pass maximum

### Material Thickness Guidelines

**For 3/4" Plywood (Most Common):**
- **Conservative approach**: 3 passes at 0.25" each
- **Aggressive approach**: 4 passes at 0.2" each  
- **Total depth**: Set to 0.8" to ensure complete cut-through

**For 1/2" Plywood:**
- **1/8" bit**: 4 passes at 0.125" each
- **1/4" bit**: 3 passes at 0.18" each

## Router Bit Types Reference

![Router Bit Types](/img/cutting-parameters/router-bit-types.jpg)

*Common router bit types used with Maslow CNC*

## Bit-Specific Recommendations

### 1/4" Router Bits

**Upcut Bits (Most Common):**
- Depth per pass: 0.125" - 0.2"
- Feed rate: 500-700 mm/min (20-28 IPM)
- Spindle speed: 10,000-12,000 RPM
- Use for: Through cuts, general purpose

**Downcut Bits:**
- Depth per pass: 0.125" - 0.18"
- Feed rate: 400-600 mm/min
- Spindle speed: 10,000-12,000 RPM  
- Use for: Clean top surface, prevents sled lifting

**Single Flute vs Two Flute:**
- Single flute: Can handle faster feed rates, less heat buildup
- Two flute: Better surface finish, requires slower feeds

### 1/8" Router Bits

**Standard Settings:**
- Depth per pass: 2-3 mm (0.08-0.12")
- Feed rate: 500-750 mm/min
- Spindle speed: 12,000-15,000 RPM
- Collet adapter required: 1/4" to 1/8"

**Considerations:**
- Longer bits available but more prone to breakage
- Good for detail work and smaller projects
- Requires more passes but gives finer detail

## Material-Specific Settings

### Plywood

**3/4" Construction Grade:**
- Use conservative settings due to varying density
- Add 1mm to total depth for material inconsistency
- Watch for tear-out in cross-grain areas

**Baltic Birch:**
- Can handle more aggressive settings
- Consistent density allows for deeper passes
- Premium material justifies conservative approach

### MDF (Medium Density Fiberboard)

**Advantages:**
- Very consistent density
- No grain direction issues
- Can cut faster than plywood

**Settings:**
- 1/8" bit: 3-4 mm depth, 500 mm/min
- 1/4" bit: 5-6 mm depth, 600-800 mm/min
- Creates fine dust - ensure good dust collection

### Hardwood

**General Guidelines:**
- Use slower feeds and conservative depths
- Varies significantly by species
- Consider grain direction for tear-out prevention

**Dense Hardwoods (Oak, Maple):**
- Reduce feed rates by 25-50%
- Shallower passes (0.1" max for 1/4" bit)
- Lower spindle speeds (8,000-10,000 RPM)

## Spindle Speed Guidelines

### Router Speed vs. Maslow Speed Relationship

The Maslow's slow movement speed requires different considerations than traditional CNC:

**Key Principle**: Lower RPM generally better due to slow feed rates

### Ridgid R22002 Router Settings

| Setting | Approximate RPM | Best For |
|---------|----------------|----------|
| 1 | 10,000 | Large bits, hardwood, conservative cuts |
| 2 | 12,000 | General purpose, 1/4" bits in plywood |
| 3 | 17,000 | Small bits, detail work |
| 4 | 22,000 | 1/8" bits, soft materials |
| 5 | 27,000 | Very small bits only |
| 6 | 30,000 | Rarely used with Maslow |

### Heat vs. Speed Relationship

**Too High RPM Signs:**
- Burning smell
- Scorched cut edges
- Premature bit dulling
- Router brush wear

**Too Low RPM Signs:**
- Rough surface finish
- Excessive vibration
- Poor chip evacuation

## Feed Rate Optimization

### Feed Rate Guidelines by Material

**Conservative Starting Points:**
- Softwood: 600-800 mm/min
- Plywood: 500-700 mm/min  
- MDF: 500-600 mm/min
- Hardwood: 400-600 mm/min

### Adjusting Feed Rates

**Increase Feed Rate When:**
- Getting fine dust instead of chips
- Hearing excessive RPM drop
- Seeing burn marks on material
- Router sounds labored

**Decrease Feed Rate When:**
- Getting large tear-out
- Bits breaking frequently
- Router cannot maintain speed
- Poor surface finish

### Chipload Calculations

**Formula**: Feed Rate = RPM × Number of Flutes × Chipload

![Chipload Chart](/img/cutting-parameters/chipload-chart.jpg)

*Chipload reference chart for 2-flute and 3-flute router bits*

**Target Chipload Values:**
- Softwood: 0.003" - 0.007"
- Hardwood: 0.003" - 0.005"  
- Plywood: 0.003" - 0.006"
- MDF: 0.004" - 0.008"

## Depth Strategy for Different Operations

### Through Cuts (Most Common)

**Strategy**: Multiple shallow passes
- First passes: Standard depth per pass
- Final pass: Add 1-2mm extra depth for clean cut-through
- Use tabs to hold parts in place

### Pocketing Operations

**Progressive Depth Method:**
1. Rough passes at maximum safe depth
2. Leave 0.5-1mm stock
3. Finish pass at final dimension
4. Slower feed rate on finish pass

### V-Bit Engraving

**Depth Guidelines:**
- 30° V-bit: 0.025" depth per pass
- 60° V-bit: 0.05" depth per pass  
- 90° V-bit: 0.1" depth per pass
- Use slow feed rates (400-600 mm/min)

## Signs of Optimal vs Poor Cutting

### Optimal Cutting Signs

**Listen For:**
- Steady router sound without bogging
- Consistent chip evacuation sound
- No high-pitched squealing

**Look For:**
- Large, consistent chips (not dust)
- Clean, smooth cut edges
- No burn marks or discoloration
- Minimal tear-out

### Poor Cutting Signs

**Sounds That Indicate Problems:**
- Router RPM dropping significantly
- High-pitched squealing or chattering
- Inconsistent cutting sounds

**Visual Problems:**
- Fine dust instead of chips
- Burn marks along cut edges
- Excessive tear-out or splintering
- Rough or fuzzy cut surfaces

## Advanced Techniques

### Ramping and Climb Cutting

**Feed Rate Ramping:**
- Slow feed rate before direction changes
- Use in CAM software (Fusion 360 feed optimization)
- Helps with corner quality

**Climb Cutting (Advanced):**
- Sometimes beneficial for end grain
- Use only for very shallow finishing passes
- Requires extreme caution

### Multiple-Bit Strategies

**Rough + Finish Approach:**
1. Roughing with larger bit (1/4") leaving 1-2mm stock
2. Finishing with smaller bit (1/8") for detail
3. Significantly reduces cutting time

### Progressive Bit Sizing

**For Deep Cuts:**
1. Start with small bit for tight corners
2. Use larger bit for bulk material removal
3. Finish with appropriate size for final dimensions

## Troubleshooting Common Issues

### Problem: Sled Tilting During Cuts

**Causes:**
- Dull router bit
- Too aggressive cutting parameters
- Insufficient sled weight

**Solutions:**
- Replace or sharpen bit
- Reduce depth per pass
- Reduce feed rate
- Add weight to sled

### Problem: Inconsistent Cut Depth

**Causes:**
- Material warping
- Inconsistent material thickness
- Calibration issues

**Solutions:**
- Surface material before cutting
- Add extra depth (1mm) to cut parameters
- Re-calibrate Z-axis
- Use Z-probe for consistency

### Problem: Burning or Melting

**Causes:**
- Too high spindle speed
- Too slow feed rate
- Dull bit

**Solutions:**
- Reduce spindle RPM
- Increase feed rate
- Replace router bit
- Improve dust collection

### Problem: Poor Surface Finish

**Causes:**
- Inappropriate feed/speed combination
- Wrong bit type for material
- Machine vibration

**Solutions:**
- Optimize chipload calculations
- Switch to downcut bit for top surface
- Check machine rigidity
- Use finishing pass strategy

## Safety Considerations

### Always Remember

**Before Each Cut:**
- Emergency stop accessible
- Safety glasses and hearing protection
- Router bit properly secured (3/4 of shank engaged)
- Material properly secured
- Clear workspace

**During Cutting:**
- Never leave machine unattended
- Monitor first few minutes of each new setup
- Watch for excessive heat buildup
- Listen for unusual sounds

**Bit Safety:**
- Replace when showing signs of wear
- Never exceed manufacturer's maximum RPM
- Proper storage prevents damage

## Community Testing Results

### Forum-Tested Combinations

**Most Successful Combinations:**
1. 1/4" upcut, 0.2" depth, 600 mm/min, 12k RPM - Plywood
2. 1/8" upcut, 3mm depth, 750 mm/min, 15k RPM - MDF
3. 1/4" downcut, 0.18" depth, 550 mm/min, 10k RPM - Hardwood

### Common Mistakes from Forum Users

**Avoid These:**
- Single deep pass instead of multiple shallow passes
- Too high spindle speeds for slow feed rates
- Not adding extra depth for cut-through
- Ignoring dust collection importance

## References and Further Reading

### Maslow CNC Forum Discussions
- [How deep should I cut each pass](https://forums.maslowcnc.com/t/how-deep-should-i-cut-each-pass/6741)
- [Wood quality, bit dull or too fast/too deep?](https://forums.maslowcnc.com/t/wood-quality-bit-dull-or-too-fast-too-deep-too-slow-of-router-speed/14456)
- [I'm confused about what bit to use and what speed to use](https://forums.maslowcnc.com/t/im-confused-about-what-bit-to-use-and-what-speed-to-use/14244)
- [Duration of Router Bits](https://forums.maslowcnc.com/t/duration-of-router-bits/274)

### Additional Resources
- [Maslow CNC Forums](https://forums.maslowcnc.com/) - Community discussions
- Router bit manufacturer specifications
- CAM software documentation (Fusion 360, Easel, etc.)

---

*This guide is compiled from extensive community testing and forum discussions. Always start with conservative settings and adjust based on your specific machine, materials, and requirements.*