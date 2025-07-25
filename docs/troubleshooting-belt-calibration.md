---
id: troubleshooting-belt-calibration
title: Belt Extension & Calibration Troubleshooting
sidebar_label: Belt & Calibration Issues
---

# Belt Extension & Calibration Troubleshooting Guide

This guide addresses common issues with the "Extend All Belts" step extending more than needed and calibration failures that follow. The information is compiled from the [Maslow CNC Forums](https://forums.maslowcnc.com/c/troubleshooting/12) community discussions.

## Common Issues & Solutions

### 1. Belts Extending Too Much During "Extend All Belts"

**Problem**: The "Extend All Belts" step causes belts to extend beyond the expected range, leading to calibration failures.

**Related Forum Discussions**:
- [Belt Not Extending Enough](https://forums.maslowcnc.com/t/belt-not-extending-enough/24525) - Multiple users discuss belt extension problems
- [Lower Right Belt Loosening and Unwinding During Cut](https://forums.maslowcnc.com/t/lower-right-belt-loosening-and-unwinding-during-cut/24309) - 16 replies about belt tension issues

**Solutions**:
1. **Check Belt Tension**: Ensure belts are properly tensioned before starting the extend process
2. **Verify Motor Connections**: Confirm all stepper motors are properly connected and responding
3. **Check for Obstructions**: Ensure the sled can move freely without hitting any obstacles
4. **Reset Belt Lengths**: If belts have extended too much, you may need to reset the belt length values

### 2. Calibration Failure After Belt Extension

**Problem**: After the "Extend All Belts" step, calibration fails with low fitness scores or gets stuck in specific areas.

**Related Forum Discussions**:
- [Fitness not close, not converging](https://forums.maslowcnc.com/t/fitness-not-close-not-converging/24515) - 38 replies about calibration fitness issues
- [Calibration failure. Can't get fitness above like 0.2](https://forums.maslowcnc.com/t/calibration-failure-cant-get-fitness-above-like-0-2/24517) - 8 replies about low fitness scores
- [Endless Calibration, always gets stuck in bottom right corner](https://forums.maslowcnc.com/t/endless-calibration-always-gets-stuck-in-bottom-right-corner-lifting-sled-unsure-where-to-go-now/24479) - 11 replies about calibration getting stuck

**Solutions**:
1. **Check Belt Lengths**: Verify that belt lengths are properly recorded after extension
2. **Reset and Retry**: If calibration fails, reset the system and try the extend process again
3. **Check Sled Movement**: Ensure the sled can move to all calibration points without obstruction
4. **Verify Motor Steps**: Confirm that motor step counts are accurate for your specific setup

### 3. "Belt Lengths Unknown" Error

**Problem**: After calibration, the system reports "Belt lengths are unknown" and refuses to move.

**Related Forum Discussions**:
- [After Calibration: Maslow is not ready to move - Belt lengths are unknown](https://forums.maslowcnc.com/t/after-calibration-maslow-is-not-ready-to-move-belt-lengths-are-unknown/24392) - 7 replies specifically about this issue

**Solutions**:
1. **Restart Ground Control**: Close and reopen Ground Control software
2. **Check Serial Connection**: Ensure stable connection between computer and Maslow
3. **Reset Belt Values**: Manually reset belt length values if they become corrupted
4. **Re-run Calibration**: If belt lengths are lost, re-run the full calibration process

### 4. Calibration Getting Stuck in Bottom Right Corner

**Problem**: Calibration process gets stuck in the bottom right corner, often with the sled lifting off the work surface.

**Related Forum Discussions**:
- [Sled lifting off the work surface](https://forums.maslowcnc.com/t/sled-lifting-off-the-work-surface/24591) - 11 replies about sled stability issues
- [Endless Calibration, always gets stuck in bottom right corner](https://forums.maslowcnc.com/t/endless-calibration-always-gets-stuck-in-bottom-right-corner-lifting-sled-unsure-where-to-go-now/24479) - 11 replies about this specific issue

**Solutions**:
1. **Check Sled Weight**: Ensure the sled has sufficient weight to stay in contact with the work surface
2. **Adjust Belt Tension**: Uneven belt tension can cause the sled to lift
3. **Check Frame Squareness**: Ensure the frame is properly squared and level
4. **Verify Anchor Points**: Confirm that all anchor points are secure and properly positioned

## Step-by-Step Troubleshooting Process

### When "Extend All Belts" Extends Too Much:

1. **Stop the Process**: Immediately stop the extend process if belts are extending beyond normal range
2. **Check Physical Setup**: Verify that the sled can move freely and there are no obstructions
3. **Reset Belt Values**: If available, reset the belt length values to default
4. **Check Motor Connections**: Ensure all stepper motors are properly connected
5. **Restart Ground Control**: Close and reopen the software
6. **Try Manual Movement**: Test manual movement commands to verify system response
7. **Re-run Extend Process**: Attempt the extend process again with careful monitoring

### When Calibration Fails After Belt Extension:

1. **Check Fitness Score**: Note the fitness score achieved during calibration
2. **Verify Belt Lengths**: Confirm that belt lengths are properly recorded
3. **Check for Error Messages**: Look for specific error messages in Ground Control
4. **Test Manual Movement**: Try moving the sled manually to verify system functionality
5. **Reset and Retry**: If necessary, reset the system and start the process over
6. **Check Forum Solutions**: Refer to the specific forum threads listed above for detailed solutions

## Additional Resources

- [Maslow CNC Troubleshooting Forum](https://forums.maslowcnc.com/c/troubleshooting/12) - Main troubleshooting category
- [4.1 Calibration Issues and Questions](https://forums.maslowcnc.com/t/4-1-calibration-issues-and-questions/23825) - 181 replies about general calibration issues
- [Apply tension issue](https://forums.maslowcnc.com/t/apply-tension-issue/24423) - 5 replies about tension-related problems

## Community Support

If you continue to experience issues after trying these solutions, consider:

1. **Searching the Forums**: Use the search function to find similar issues
2. **Creating a New Post**: Share your specific setup and error messages
3. **Including Details**: Provide information about your Maslow version, firmware, and setup
4. **Adding Photos/Videos**: Visual documentation can help others understand your issue

---

*This guide is compiled from community discussions on the [Maslow CNC Forums](https://forums.maslowcnc.com/). For the most up-to-date information and community support, please visit the forums directly.* 