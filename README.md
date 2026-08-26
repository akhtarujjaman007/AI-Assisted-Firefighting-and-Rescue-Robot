## AI-Assisted Firefighting and Rescue Robot

FireRescue-X is a physical firefighting and rescue robot developed to
assist in hazardous environments by combining autonomous obstacle
avoidance, flame detection, fire suppression, manual wireless control,
and camera-based monitoring.

![FireRescue-X Prototype](prototype.png)

## Overview

The robot was developed as a multifunctional firefighting and rescue
platform. The prototype combines Arduino-based low-level control,
multiple flame sensors, ultrasonic obstacle detection, motor control,
a water pump, Bluetooth communication, and an ESP32-CAM for live
visual monitoring.

The original system was designed several years ago. The project is
now being prepared for modernization using lightweight real-time
computer vision models running on a local machine.

## Key Features

- Autonomous obstacle avoidance
- Fire/flame detection
- Fire suppression using a water pump
- Manual Bluetooth control
- ESP32-CAM live video monitoring
- Human detection through computer vision
- Real physical robotic prototype
- Local-machine image processing architecture

## Operating Modes

### Automatic Mode

The robot uses its sensors to detect fire and obstacles and performs
navigation and firefighting actions.

### Manual Mode

The robot can be controlled wirelessly using commands from a mobile
device through the Bluetooth module.

## Hardware

- Arduino UNO R3
- ESP32-CAM
- HC-06 Bluetooth module
- L298N motor driver
- DC motors
- Ultrasonic sensor
- Flame sensors
- Servo motor
- Water pump
- Robot chassis

# 🏗️ System Architecture

The Firefighting and Rescue Robot consists of an Arduino-based
embedded control system, sensing and actuation components, and an
ESP32-CAM-based visual monitoring system.

<p align="center">
  <img src="system-architecture.png"
       alt="Firefighting and Rescue Robot System Architecture"
       width="850">
</p>

<p align="center">
  <b>Figure 1 — System architecture of the firefighting and rescue robot.</b>
</p>

The Arduino UNO handles the main robotic operations, including sensor
readings, motor control, obstacle avoidance, flame detection, servo
control, water-pump activation, and wireless commands.

The ESP32-CAM provides the live visual feed. The visual-processing
pipeline is handled separately on a developer/local machine, allowing
the developer to use modern lightweight computer-vision models without
requiring a complete redesign of the robot hardware.

---

# 🔄 System Flowchart

The following flowchart represents the overall operating process of
the robot, including automatic firefighting, obstacle avoidance, and
manual control.

<p align="center">
  <img src="flowchart.png"
       alt="Firefighting and Rescue Robot Flowchart"
       width="850">
</p>

<p align="center">
  <b>Figure 2 — Operational flowchart of the firefighting and rescue robot.</b>
</p>

---

# 📷 Visual Processing

The ESP32-CAM is responsible for capturing and providing the live
camera feed. **Image processing is performed on the developer's local
machine rather than being restricted to the ESP32-CAM.**

This is particularly important because the original project was
developed several years ago. Modern lightweight computer-vision models
can now provide significantly more capable real-time processing on
ordinary local computers.

Therefore, developers can use their preferred modern lightweight model
for the live camera stream.

```text
              ESP32-CAM
                  │
                  │ Live Video Feed
                  ▼
          Developer's Local Machine
                  │
                  ▼
        Real-Time Image Processing
                  │
          ┌───────┴───────┐
          │               │
          ▼               ▼
    Fire Detection   Human Detection
                          │
                          ▼
                  Partial / Occluded
                  Human Detection