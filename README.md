Good. Solid engineering utility project.
If the robotic platform is your “wow”, this is your **“this guy actually knows electronics”** project.

I’ll convert your dump into a **final GitHub-ready Level-3 documentation**.
You paste → done → never touch again.

---

# Variable Bench Power Supply (0–36V, High Current)

## Overview

This project is a high-current adjustable bench power supply designed for electronics prototyping, motor testing, and continuous lab use.
It was developed as a low-cost, reliable alternative to expensive commercial lab power supplies while maintaining high current capability and stable output.

The system converts AC mains power into a regulated adjustable DC output capable of driving motors, servos, and embedded systems for extended durations.

Unlike battery-based setups, this unit enables **continuous testing without voltage drop or power interruption**, making it suitable for long-duration robotics and electronics development.

---

## Key Specifications

| Parameter                  | Value                       |
| -------------------------- | --------------------------- |
| Input Source               | 24V 6A AC-DC SMPS           |
| Output Voltage             | 1.2V – 36V adjustable       |
| Max Current (module rated) | 20A                         |
| Display Limit              | 10A (panel meter)           |
| Regulation Type            | CC/CV Buck Regulation       |
| Efficiency                 | ~95–97% (buck module rated) |
| Cooling                    | Active fan cooling          |
| Enclosure                  | Wooden custom enclosure     |
| Continuous Use             | Multi-hour stable operation |

---

# Why this project exists

Most student electronics setups rely on batteries and small buck converters, which introduce:

* Voltage drop during long tests
* Limited runtime
* Constant recharging interruptions
* Inconsistent motor and servo testing

Commercial lab power supplies with high current capability are expensive.

This project was built to create a **reliable, high-current, continuously powered bench supply** capable of:

* Running motors and servos
* Powering full robotic systems
* Testing electronics under stable voltage
* Eliminating battery dependency during development

It now serves as the primary lab power source for multiple robotics and embedded projects.

---

# System Architecture

## Input Stage

* 24V 6A AC-DC SMPS supply
  Provides stable high-voltage DC input to all buck stages.

Includes internal fuse protection for basic safety.

---

## Multi-Rail Buck Architecture

The input supply is distributed into three regulated rails:

| Buck Converter           | Purpose                          |
| ------------------------ | -------------------------------- |
| Buck 1 → 12V             | Cooling fan & display system     |
| Buck 2 → Variable (main) | Adjustable output (1.2–36V)      |
| Buck 3 → 5V              | Indicator LEDs & auxiliary loads |

### Main Output Buck Converter

* Adjustable CC/CV regulation
* Rated 20A output
* Multi-turn precision adjustment
* High efficiency (~97% rated)

This forms the primary adjustable lab output.

---

## Control & Interface

**Adjustment**

* 100k multi-turn precision potentiometers
* Fine voltage and current control

**Monitoring**

* Digital voltmeter/ammeter panel
* Rated: 100V / 10A display
* Real-time voltage & current feedback

**Indicators**

* Red LED power indicator
* Fan switch
* Main AC rocker switch

---

## Power Output Interface

* Banana connector terminals
* Suitable for high current output
* Secure connection for motors and electronics

---

# Wiring & Internal Design

| Area               | Wire Gauge |
| ------------------ | ---------- |
| High current paths | 14–16 AWG  |
| Low current logic  | 20 AWG     |

Design considerations:

* Thick wiring used for high-current paths
* Heatshrink insulation on joints
* Segregated routing for cleaner layout
* 1000µF capacitor added for voltage smoothing

The system is housed inside a **30.5 × 12.5 cm wooden enclosure** with active cooling.

---

# Thermal Management

High current buck converters generate heat under sustained load.

Cooling strategy:

* Active cooling fan powered from dedicated 12V rail
* Ventilated enclosure
* Continuous operation tested for multi-hour sessions

No thermal shutdown observed during typical electronics and motor testing.

---

# Performance & Real-World Usage

### Voltage Accuracy

Observed comparison with multimeter:

* 4.68V (multimeter) → 4.6V (display)
* 3.75A (multimeter) → 3.8A (display)

Acceptable deviation for lab usage.

### Stability

* Stable voltage under continuous load
* No shutdown during extended use
* Successfully powered robotic arms, motors, and embedded systems for hours

### Typical Uses

* Motor testing
* Servo testing
* Embedded system power
* Robotics debugging
* General electronics prototyping

This unit replaced battery-based testing entirely.

---

# Where it breaks (Limitations)

### Measurement Limit

* Display limited to 10A current reading
* Full 20A capability not visually monitorable on panel

### High Current Testing

* Not stress-tested continuously at extreme current (15–20A range)
* Requires further thermal validation at peak load

### Size & Build

* Wooden enclosure not industrial grade
* Internal wiring dense but functional
* No modular PCB-based distribution

---

# Lessons Learned

* Reliable bench power drastically improves development workflow
* Wire gauge selection directly impacts safety and efficiency
* Buck converter quality determines output stability
* Active cooling becomes mandatory above moderate current levels
* Continuous power supply is superior to battery testing for development environments

---

# Future Improvements (Optional V2)

* Metal enclosure
* Dedicated PCB power distribution
* Higher precision display module
* Digital encoder-based voltage control
* Thermal monitoring sensor
* Output protection circuits
