# smart-scope-ai-display
LRF-DOPE: Raspberry Pi Ballistics Computer
LRF-DOPE: Raspberry Pi Ballistics Computer

🎯 Project Overview

The LRF-DOPE project aims to create a highly accurate, portable, and customizable ballistics calculation device using a Raspberry Pi. This system integrates real-time environmental sensors and a Laser Range Finder (LRF) to quickly generate precise Data On Previous Engagements (DOPE) / firing solutions for long-range shooting.

This repository tracks the development from a simple proof-of-concept carry case prototype (Phase 1) to a final, ruggedized, scope-mounted system (Phase 3).

✨ Key Features

Real-Time Range Input: Reads distance directly from a digital LRF module via UART serial communication.

Environmental Correction: Utilizes an on-board BME280 sensor for accurate barometric pressure and ambient temperature readings, critical for air density calculations.

Angle/Cant Correction: Reads rifle inclination and cant using an IMU (MPU-6050/BNO055) to automatically adjust the firing solution.

Advanced Ballistics Solver: Employs G7 drag models for precise trajectory calculations based on user-defined bullet profiles.

User Profiles: Store and manage multiple rifle/ammunition profiles (e.g., .308 Win, 6.5 Creedmoor) via a Firebase Firestore database (Phase 2).

💻 Hardware Stack (Phase 1 MVP)

The initial phase focuses on the core electronics needed to prove the calculation engine in a simple "carry case" form factor.

Component

Model / Type

Interface

Role

Main Processor

Raspberry Pi 4 Model B

N/A

Calculation Engine and I/O Hub

Rangefinder (Prototype)

Benewake TF03 (or equivalent)

UART (Serial)

Mid-Range Distance Measurement

Atmospheric Sensor

BME280 / BMP180

I2C

Pressure, Temperature, Humidity

Angle Sensor

MPU-6050 / BNO055

I2C

Rifle Cant and Inclination

User Input

Rotary Encoder

GPIO

Navigation and Data Entry

Display

Small OLED / TFT

SPI / I2C

Displaying the Final DOPE (MILs/MOA)

🚀 Phased Development Plan

Our development strategy minimizes risk by starting small and scaling up functionality and hardware.

Phase 1: Core Ballistics Engine & Carry Case Prototype

Focus: Perfecting UART/I2C communication, implementing the base G7 ballistics math, and creating a stable Python software environment.

Goal: Achieve a working DOPE solution display using the low-cost LRF module and reading initial sensor data (Temp/Pressure).

Phase 2: Intelligence, Data Storage, and Refined Inputs

Focus: Integrating the IMU for automatic cant correction and migrating data persistence.

Goal: Implement Firebase Firestore for user profile management, ensuring profiles can be accessed and shared across user sessions. Refine the ballistics model with tilt correction.

Phase 3: Final Product Integration & HUD Deployment

Focus: High-end hardware and final packaging.

Goal: Integrate the Long-Range Industrial TOF Module (300m+). Design and build the custom, ruggedized enclosure and the optical path for the Heads-Up Display (HUD) system.

🛠️ Software Stack

Primary Language: Python 3

OS: Raspberry Pi OS Lite

Libraries: pyserial, smbus2 (for I2C), Custom Ballistics Solver, Firebase SDK integration (for Phase 2).

🤝 Contribution

We welcome contributions to the ballistics math, sensor integration scripts, and UI design. Please refer to the LICENSE before submitting any Pull Requests.
