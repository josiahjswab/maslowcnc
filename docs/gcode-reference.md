---
id: gcode-reference
title: G-Code Reference
sidebar_label: G-Code Commands
---

# G-Code Reference for Maslow CNC

This reference covers G-code commands supported by Maslow CNC controllers, including usage examples and best practices.

## G-Code Basics

G-code is the standard language for controlling CNC machines. Each line contains commands that tell the machine how to move, when to turn the spindle on/off, and other operational parameters.

### Basic Structure
```gcode
G01 X10.5 Y20.0 F1000
```
- **G01**: Movement command (linear interpolation)
- **X10.5**: X-axis destination position
- **Y20.0**: Y-axis destination position  
- **F1000**: Feed rate (mm/min)

### Coordinate Systems
- **Absolute positioning (G90)**: Coordinates relative to work zero
- **Relative positioning (G91)**: Coordinates relative to current position
- **Work coordinates**: G54-G59 coordinate systems

## Supported G-Commands

### Motion Commands

#### G00 - Rapid Positioning
```gcode
G00 X50 Y30
```
- **Purpose**: Fast movement to position (non-cutting)
- **Usage**: Positioning moves, tool changes, clearance moves
- **Note**: Router should be off during rapid moves

#### G01 - Linear Interpolation
```gcode
G01 X25 Y15 F1500
```
- **Purpose**: Straight-line cutting movement
- **Usage**: Most common cutting command
- **Parameters**: X, Y, Z positions and F (feed rate)

#### G02 - Clockwise Circular Interpolation
```gcode
G02 X20 Y20 I10 J0 F1000
```
- **Purpose**: Clockwise arc movement
- **Parameters**: 
  - X, Y: End point
  - I, J: Arc center relative to start point
  - F: Feed rate

#### G03 - Counterclockwise Circular Interpolation
```gcode
G03 X20 Y20 I10 J0 F1000
```
- **Purpose**: Counterclockwise arc movement
- **Parameters**: Same as G02
- **Usage**: Creating smooth curved cuts

### Positioning and Coordinate Commands

#### G90 - Absolute Positioning
```gcode
G90
G01 X10 Y20 ; Move to X=10, Y=20 from origin
```
- **Purpose**: All coordinates relative to work zero
- **Default**: Most CAM software uses absolute positioning

#### G91 - Incremental Positioning
```gcode
G91
G01 X5 Y5 ; Move 5mm right and 5mm up from current position
```
- **Purpose**: Coordinates relative to current position
- **Usage**: Useful for repetitive operations

#### G92 - Set Position
```gcode
G92 X0 Y0 Z0
```
- **Purpose**: Set current position as specified coordinates
- **Usage**: Establishing work zero without physical movement
- **Caution**: Use carefully to avoid position confusion

### Work Coordinate Systems

#### G54-G59 - Work Coordinate Systems
```gcode
G54 ; Select work coordinate system 1
G01 X10 Y10 ; Move relative to G54 origin
```
- **Purpose**: Multiple coordinate systems for different setups
- **Usage**: Production work with multiple fixtures
- **Note**: G54 is default for most operations

## Supported M-Commands

### Spindle Control

#### M03 - Spindle On (Clockwise)
```gcode
M03 S18000
```
- **Purpose**: Start spindle rotation
- **Parameter**: S value sets RPM (if supported)
- **Usage**: Start cutting operations

#### M05 - Spindle Stop
```gcode
M05
```
- **Purpose**: Stop spindle rotation
- **Usage**: End of cutting, tool changes, safety stops

### Program Control

#### M00 - Program Stop
```gcode
M00
```
- **Purpose**: Pause program execution
- **Usage**: Manual tool changes, inspection points
- **Resume**: User must restart program manually

#### M01 - Optional Stop
```gcode
M01
```
- **Purpose**: Conditional program stop
- **Usage**: Optional inspection points
- **Control**: Can be enabled/disabled in controller

#### M02 - Program End
```gcode
M02
```
- **Purpose**: End of program
- **Usage**: Final command in G-code file
- **Effect**: Stops program execution

#### M30 - Program End and Rewind
```gcode
M30
```
- **Purpose**: End program and return to beginning
- **Usage**: Alternative to M02
- **Effect**: Resets program to start

### Coolant Control (Limited Support)

#### M07/M08 - Coolant On
```gcode
M08 ; Flood coolant on (if supported)
```
- **Purpose**: Turn on coolant/mist systems
- **Note**: Limited hardware support on most Maslow setups

#### M09 - Coolant Off
```gcode
M09
```
- **Purpose**: Turn off coolant systems
- **Usage**: End of operations requiring coolant

## Feed Rate and Speed Control

### F - Feed Rate
```gcode
F1500 ; Set feed rate to 1500 mm/min
```
- **Units**: mm/min (metric) or in/min (imperial)
- **Scope**: Remains active until changed
- **Usage**: Different rates for different materials/operations

### S - Spindle Speed
```gcode
S18000 ; Set spindle to 18,000 RPM
```
- **Purpose**: Set spindle speed (if controller supports it)
- **Note**: Many Maslow setups use manual spindle speed control
- **Range**: Depends on router/spindle capabilities

## Common G-Code Patterns

### Program Start Template
```gcode
G90          ; Absolute positioning
G54          ; Work coordinate system
M03 S18000   ; Start spindle
G00 Z5       ; Rapid to safe height
G00 X0 Y0    ; Rapid to start position
```

### Safe Tool Change
```gcode
G00 Z25      ; Retract to safe height
G00 X0 Y0    ; Move to tool change position
M05          ; Stop spindle
M00          ; Pause for manual tool change
M03 S18000   ; Restart spindle after tool change
```

### Program End Template
```gcode
G00 Z25      ; Retract to safe height
G00 X0 Y0    ; Return to home position
M05          ; Stop spindle
M02          ; End program
```

## Maslow-Specific Considerations

### Chain/Belt Limitations
- **Avoid rapid direction changes**: Can cause chain skip or belt slip
- **Limit acceleration**: Gradual speed changes prevent mechanical stress
- **Consider sag compensation**: Especially important for chain systems

### Recommended Practices
- **Conservative feed rates**: Start with 1000-1500 mm/min
- **Gradual Z-moves**: Avoid rapid plunging
- **Smooth toolpaths**: Minimize sharp corners and direction changes

### Safety Commands
```gcode
G00 Z25      ; Always retract before X/Y moves
F1000        ; Use conservative feed rates initially
```

## Troubleshooting G-Code Issues

### Common Problems

#### Position Errors
**Symptoms**: Machine doesn't go where expected
**Causes**: 
- Mixing absolute and incremental positioning
- Wrong work coordinate system
- Missing G90/G91 commands

**Solution**:
```gcode
G90 G54      ; Ensure absolute positioning and correct coordinate system
```

#### Feed Rate Issues
**Symptoms**: Machine moves too fast or slow
**Causes**: Missing or incorrect F commands
**Solution**: Always specify feed rate for cutting moves
```gcode
G01 X10 Y10 F1200  ; Always include feed rate
```

#### Spindle Problems
**Symptoms**: Cutting without spindle running
**Causes**: Missing or incorrect M03 command
**Solution**: Verify spindle commands in G-code
```gcode
M03 S18000   ; Ensure spindle start command
```

## File Validation

### Pre-Flight Checks
1. **Check file header**: Verify proper initialization commands
2. **Scan for missing feed rates**: Every G01 move should have F value
3. **Verify Z-heights**: Ensure adequate clearance moves
4. **Check coordinate systems**: Confirm G90/G54 usage
5. **Validate end commands**: Proper M05, retract, and M02

### Simulation Tools
- **CAM software preview**: Use built-in simulation
- **G-code viewers**: Standalone verification tools
- **Dry run**: Test without cutting to verify movements

## Advanced G-Code Features

### Variables and Expressions
```gcode
#1 = 10.5     ; Set variable
G01 X#1 Y[#1 * 2]  ; Use variable in coordinates
```
**Note**: Support varies by controller firmware

### Conditional Operations
```gcode
IF [#1 GT 5] GOTO 100  ; Conditional branch
G01 X10
N100 G01 Y10           ; Target label
```
**Note**: Advanced feature with limited support

### Subroutines
```gcode
O100 SUB       ; Subroutine definition
G01 X5 Y5
O100 ENDSUB
M98 P100 L5    ; Call subroutine 5 times
```
**Note**: Implementation varies by controller

## Community Resources

For more information and support:
- **Forum Discussion**: [Supported G Code Commands](https://forums.maslowcnc.com/t/supported-g-code-commands/16242)
- **Community Examples**: Share and learn from working G-code
- **Testing Results**: Community validation of command support

## Best Practices Summary

1. **Always use absolute positioning** (G90) unless specifically needed
2. **Include feed rates** with every cutting move
3. **Start and stop spindle** appropriately
4. **Use safe Z-heights** for all rapid moves
5. **End programs properly** with retract and stop commands
6. **Test new G-code** with dry runs before cutting
7. **Keep files simple** - complex features may not be supported

---

*Understanding G-code gives you complete control over your Maslow CNC and enables troubleshooting when things go wrong!*