# PathSense — Smart Cane for Safer Navigation

A smart cane prototype built for **Build X by Blankspace** (Arduino-sponsored hackathon).

PathSense adds three layers of protection to a standard cane:
- **Side obstacle detection** — dual ultrasonic sensors sense objects left and right
- **Ground depth sensing** — detects sudden drops (potholes) or rises (curbs/steps) ahead
- **Emergency SOS** — a button triggers an audible alarm for nearby help

## Team
4-member team, Amal Jyothi College of Engineering

## Problem

The traditional white cane has real limitations: it only detects ground-level obstacles, missing hazards at chest lvl or below. Worse, it cannot sense depth changes ahead — potholes, open drains, or curbs are noticed only after the user has already stepped into danger. There's also no built-in way to alert others during a fall or emergency. These gaps matter especially in regions like Kerala, where uneven roads and monsoon puddles are common daily hazards.

## System Diagram

![Cane component layout](diagram.svg)

## How It Works

1. **Sense** — Ultrasonic sensors continuously scan the path ahead and below
2. **Process** — A microcontroller checks readings against safe-distance thresholds
3. **Alert** — Vibration feedback (or SOS alarm) tells the user what to do

## Detachable Electronics Housing

The Arduino and battery sit in a cylindrical pod, matching the cane's rod diameter, that twist-locks onto a permanent base mounted on the rigid shaft just below the rubber grip (so the grip itself stays untouched). The same pod twists into a charging dock using an identical thread pattern and contact layout, so one pod works for both the cane and charging.

- **Permanent base** — fixed collar on the rigid shaft, wired to the shaft sensors, with a threaded rim and contact pins
- **Removable pod** — houses the Arduino, battery, and SOS button; matching contact pads connect power/data when twisted in
- **Charging dock** — same thread + contact pattern as the cane base, so the pod docks directly for charging

Electrical contact between the pod and either base is made using **pogo pin connectors** — spring-loaded pins that connect simply by being seated together
## Components

## Components

**Core electronics**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| Arduino Nano | ATmega328P | 1 | Main microcontroller |
| HC-SR04 | Ultrasonic sensor | 2 | Left/right obstacle detection |
| VL53L0X | ToF laser distance sensor | 1 | Ground-depth/pothole detection at tip |
| Vibration motor | 3V coin/pancake type | 1 | Haptic feedback |
| Push button | 6mm/12mm tactile | 1 | SOS trigger |
| Buzzer | 5V active buzzer | 1 | SOS alarm sound |
| On/off switch | SPDT slide or toggle | 1 | Power on/off |

**Power system**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| Li-ion battery | 18650, 3.7V | 1 | Power source |
| TP4056 charging module | With built-in charge-status LEDs | 1 | Safe charging + charge/full indicator |
| Battery holder | 18650 holder w/ leads | 1 | Secure battery mount |

**Driving the vibration motor** (motor can't connect directly to an Arduino pin)

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| NPN transistor | 2N2222 or similar | 1 | Switch motor current safely |
| Resistor | 1kΩ | 1 | Transistor base current limit |
| Flyback diode | 1N4001 | 1 | Protect circuit from motor voltage spikes |

**Wiring & assembly**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| Jumper wires | M-M, M-F, F-F assorted | 1 pack | All connections |
| Breadboard or perfboard | Mini size | 1 | Prototype/solder circuit |
| Heat shrink tubing / electrical tape | Assorted | — | Insulate soldered joints |

**Housing**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| 3D-printed sleeve + collar | PLA, custom design | 1 set | Houses electronics, slides on/off |
| Pogo pin connectors | 2–4 pin, spring-loaded | 1 pair | Electrical contact when sleeve seats into base |

**Base structure**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| Walking stick / cane | Rigid, adjustable | 1 | Base structure for prototype |


## Status

Currently in pitch/prototype stage — circuit logic tested in [Wokwi](https://wokwi.com) simulator.
