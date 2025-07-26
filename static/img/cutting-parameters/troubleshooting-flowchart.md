# Maslow CNC Cutting Parameters Troubleshooting Flowchart

## Problem: Poor Cut Quality

```
START: Poor Cut Quality
    ↓
Is there excessive tear-out?
    ↓ YES
    Are you using an upcut bit?
        ↓ YES → Switch to downcut bit
        ↓ NO → Reduce feed rate by 25%
    ↓ NO
Are there burn marks?
    ↓ YES
    Is spindle speed too high?
        ↓ YES → Reduce RPM to next lower setting
        ↓ NO → Increase feed rate by 25%
    ↓ NO
Are you getting dust instead of chips?
    ↓ YES → Feed rate too slow, increase by 50%
    ↓ NO
Is surface rough/fuzzy?
    ↓ YES → Bit may be dull, replace and retest
    ↓ NO → Check calibration
```

## Problem: Router Sounds Labored

```
START: Router Sounds Labored
    ↓
Is RPM dropping significantly?
    ↓ YES
    Is depth per pass > 1/2 bit diameter?
        ↓ YES → Reduce depth per pass
        ↓ NO → Reduce feed rate by 25%
    ↓ NO
Is there excessive vibration?
    ↓ YES → Check bit is properly secured
    ↓ NO → Bit may be dull, replace
```

## Problem: Bit Breaking

```
START: Bit Breaking
    ↓
What size bit broke?
    ↓ 1/8" or smaller
    Is cutting depth > bit diameter?
        ↓ YES → Reduce depth per pass by 50%
        ↓ NO → Reduce feed rate
    ↓ 1/4" or larger
    Is feed rate too aggressive?
        ↓ YES → Reduce feed rate by 25%
        ↓ NO → Check for material hardness issues
```

## Quick Reference: When to Adjust Parameters

### Increase Feed Rate When:
- Getting fine dust instead of chips
- Seeing burn marks
- Router sounds too easy/fast
- Excessive heat buildup

### Decrease Feed Rate When:
- Router sounds labored
- Getting excessive tear-out
- Bits breaking frequently
- Poor surface finish

### Increase RPM When:
- Poor surface finish on soft materials
- Using very small bits (1/8" or less)
- Getting rough edges

### Decrease RPM When:
- Getting burn marks
- Router sounds too aggressive
- Premature bit dulling
- Using large bits (1/2" or more)