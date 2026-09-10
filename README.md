# PathSense — Smart Cane for Safer Navigation

A smart cane prototype built for **Build X by Blankspace** (Arduino-sponsored hackathon).

PathSense adds three layers of protection to a standard cane:
- **Side obstacle detection** — dual ultrasonic sensors sense objects left and right
- **Ground depth sensing** — detects sudden drops (potholes) or rises (curbs/steps) ahead
- **Emergency SOS** — a button triggers an audible alarm for nearby help

## Team
2-member team, Amal Jyothi College of Engineering

## System Diagram

![Cane component layout](diagram.png)

## How It Works

1. **Sense** — Ultrasonic sensors continuously scan the path ahead and below
2. **Process** — A microcontroller checks readings against safe-distance thresholds
3. **Alert** — Vibration feedback (or SOS alarm) tells the user what to do

## Prototype Code (Arduino Uno/Nano)

\`\`\`cpp
#include <NewPing.h>

#define TRIG_PIN 9
#define ECHO_PIN 10
#define LED_PIN 6

NewPing sonar(TRIG_PIN, ECHO_PIN, 200); // max distance 200cm

void setup() {
  pinMode(LED_PIN, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int distance = sonar.ping_cm();
  Serial.println(distance);

  if (distance > 0 && distance < 30) {
    digitalWrite(LED_PIN, HIGH);
  } else if (distance >= 30 && distance < 100) {
    digitalWrite(LED_PIN, HIGH);
    delay(200);
    digitalWrite(LED_PIN, LOW);
    delay(200);
  } else {
    digitalWrite(LED_PIN, LOW);
  }

  delay(50);
}
\`\`\`

## Components

| Component | Purpose |
|---|---|
| Arduino Nano | Microcontroller |
| HC-SR04 x2 | Left/right obstacle detection |
| ToF sensor (VL53L0X) | Ground depth sensing |
| Vibration motor | Feedback |
| Push button + buzzer | SOS alert |

## Status

Currently in pitch/prototype stage — circuit logic tested in [Wokwi](https://wokwi.com) simulator.
