---
id: webcontrol-setup
title: WebControl Setup and Usage
sidebar_label: WebControl
---

# WebControl Setup and Usage Guide

WebControl is the primary control software for Maslow CNC machines. This guide covers installation, setup, and usage of both basic and advanced features.

## What is WebControl?

WebControl is a web-based control interface that runs on your computer and connects to your Maslow CNC. It provides:
- Machine control and monitoring
- G-code file management and execution  
- Real-time position tracking
- Calibration tools and wizards
- Advanced configuration options

## Installation Options

### Option 1: Windows/Mac/Linux Installation

#### System Requirements
- **Operating System**: Windows 7+, macOS 10.12+, or Linux
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 2GB free space
- **USB Port**: For connecting to Maslow controller

#### Installation Steps
1. **Download WebControl** from the official Maslow repository
2. **Extract files** to a dedicated folder
3. **Install Node.js** if not already installed
4. **Run installation script** or follow platform-specific instructions
5. **Launch WebControl** and navigate to localhost:8000

### Option 2: Raspberry Pi Setup

Running WebControl on a Raspberry Pi allows for dedicated, always-on control.

#### Required Hardware
- **Raspberry Pi 3B+ or 4** (recommended)
- **MicroSD card**: 16GB minimum, Class 10
- **Power supply**: Official Pi power adapter
- **Case with ventilation**: To prevent overheating

#### Installation Process
1. **Download pre-configured image** from community resources
2. **Flash image** to SD card using Raspberry Pi Imager
3. **Boot Raspberry Pi** and connect to network
4. **Access WebControl** via Pi's IP address in web browser

> **Detailed Instructions**: [WebControl Setup on Raspberry Pi](https://forums.maslowcnc.com/t/webcontrol-setup-on-raspberry-pi/12473)

## Initial Setup and Configuration

### First Connection

#### Hardware Connection
1. **Connect USB cable** from computer to Maslow controller
2. **Power on** the Maslow controller
3. **Launch WebControl** in your web browser
4. **Select serial port** from the connection dropdown

#### Connection Troubleshooting
**Port not appearing:**
- Check USB cable connection
- Verify controller is powered on
- Install Arduino drivers if needed
- Try different USB ports

**Connection drops frequently:**
- Check for loose connections
- Use shorter, higher-quality USB cable
- Avoid USB hubs when possible

### Basic Configuration

#### Machine Profile Setup
1. **Select machine type**: Chain Maslow or Belt Maslow (M4)
2. **Enter basic dimensions**:
   - Distance between motors
   - Motor height above workpiece
   - Sled/frame specifications
3. **Set units**: Metric (mm) or Imperial (inches)

#### Safety Settings
- **Set work area limits** to prevent crashes
- **Configure emergency stop** behavior
- **Set maximum feed rates** for safety
- **Enable software limits** for X, Y, Z axes

## Basic WebControl Features

### Main Interface Overview

#### Control Panel
- **Jog controls**: Move the router manually
- **Speed controls**: Adjust movement speed
- **Position display**: Current X, Y, Z coordinates
- **Connection status**: Shows link to controller

#### File Management
- **Upload G-code files** for cutting
- **File browser**: Organize and select files
- **File validation**: Check G-code before running
- **History**: Track recently used files

### Operating Your Machine

#### Manual Control (Jogging)
1. **Set jog distance**: Choose step size (0.1mm to 10mm)
2. **Use directional arrows** or keyboard shortcuts
3. **Adjust speed** using the speed slider
4. **Set zero positions** using the "Set Zero" buttons

#### Running G-Code
1. **Upload your G-code file** using the file browser
2. **Review file information**: Cut time, bounds, etc.
3. **Set work zeros** (X, Y, Z positions)
4. **Start the job** and monitor progress

#### Real-Time Monitoring
- **Position tracking**: Watch current location
- **Progress indicator**: See completion percentage
- **Feed rate display**: Current cutting speed
- **Emergency controls**: Pause, stop, emergency stop

## Advanced Features

### Calibration Tools

#### Automatic Calibration Wizard
1. **Access from Settings menu**
2. **Follow step-by-step prompts**
3. **Perform required measurements**
4. **Run test cuts** for verification

#### Manual Calibration Override
- **Custom parameter entry**: For experienced users
- **Backup/restore settings**: Save successful configurations
- **Multi-profile support**: Different setups for different projects

### Advanced Configuration

#### Motor Settings
- **Steps per millimeter**: Fine-tune movement accuracy
- **Maximum speeds**: Set safe operating limits
- **Acceleration limits**: Control movement smoothness
- **Direction inversion**: Correct for wiring differences

#### Z-Axis Configuration
- **Z-probe setup**: Configure automatic probing
- **Safety height**: Set clearance for moves
- **Plunge rates**: Control cutting entry speed
- **Multiple tool support**: Tool change procedures

### Custom Features

#### Macros and Custom Commands
- **Create reusable sequences**: Common operations
- **Custom G-code snippets**: Frequently used commands
- **Workflow automation**: Streamline repetitive tasks

#### Advanced G-Code Features
- **Parameter passing**: Use variables in G-code
- **Conditional execution**: Logic-based operations
- **Subroutines**: Reusable code blocks

## Workflow Tips and Best Practices

### File Preparation
1. **Validate G-code** before loading to machine
2. **Check file bounds** against your material size
3. **Verify tool requirements** match your setup
4. **Estimate cut time** for planning

### Safety Procedures
- **Always test** new G-code with dry runs
- **Keep emergency stop** within easy reach
- **Monitor first few minutes** of any cut closely
- **Never leave machine unattended** during cuts

### Optimization Tips
- **Use appropriate feed rates** for your material
- **Optimize tool paths** to minimize cut time
- **Plan efficient workflows** to reduce setup time
- **Keep backups** of successful configurations

## Troubleshooting Common Issues

### Connection Problems
**Symptoms**: Can't connect, frequent disconnects
**Solutions**:
- Check USB cable and connections
- Restart WebControl and controller
- Update USB drivers
- Try different USB port or cable

### Performance Issues
**Symptoms**: Slow response, interface lag
**Solutions**:
- Close unnecessary browser tabs
- Restart WebControl
- Check system resources (RAM, CPU)
- Use wired internet connection for Pi setups

### G-Code Execution Problems
**Symptoms**: Jobs stop unexpectedly, position errors
**Solutions**:
- Verify G-code compatibility
- Check for mechanical binding
- Review acceleration settings
- Ensure adequate power supply

## Community Resources and Support

### Official Documentation
- **User Manual**: Comprehensive feature documentation
- **Video Tutorials**: Step-by-step visual guides
- **FAQ**: Common questions and answers

### Community Support
- **Forum Discussions**: [WebControl: how to use the basic and advanced features](https://forums.maslowcnc.com/t/webcontrol-how-to-use-the-basic-and-advanced-features/13241)
- **Community Wiki**: User-contributed guides and tips
- **Live Help**: Real-time support from experienced users

### Advanced Resources
- **Source Code**: For developers and advanced customization
- **Plugin Development**: Extend WebControl functionality
- **Beta Testing**: Try new features before official release

## Next Steps

After mastering WebControl basics:
1. **Explore advanced features** like macros and custom commands
2. **Optimize your workflow** with automation features
3. **Contribute to the community** by sharing tips and solutions
4. **Consider Raspberry Pi setup** for dedicated machine control

---

*WebControl is continuously evolving with community input. Stay engaged with the forums for the latest features and improvements!*