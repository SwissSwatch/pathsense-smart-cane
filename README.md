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

## How It Works

1. **Sense** — Ultrasonic sensors continuously scan the path ahead and below
2. **Process** — A microcontroller checks readings against safe-distance thresholds
3. **Alert** — Vibration feedback (or SOS alarm) tells the user what to do


## Components

**Core electronics**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| Arduino UNO | ATmega328P | 1 | Main microcontroller |
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


**Base structure**

| Component | Spec | Qty | Purpose |
|---|---|---|---|
| PVC Stick to simulate Walking cane | Rigid, adjustable | 1 | Base structure for prototype |

