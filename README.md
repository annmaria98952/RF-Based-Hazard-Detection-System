# RF-Based Multi-Zone Hazard Detection System

## Overview

The RF-Based Multi-Zone Hazard Detection System is an embedded safety project designed to detect fire, hazardous gas conditions, and abnormal temperature changes across multiple zones. It uses 433 MHz RF communication to transmit hazard alerts from distributed sensor units to a central monitoring hub without requiring an internet connection.

Each zone device uses an Arduino Nano to process sensor inputs and transmit hazard information. The central hub uses an ESP32, an RF receiver, an LCD display, and a buzzer to identify the affected zone and provide immediate alerts.

## Objectives

- Detect fire, hazardous gas conditions, and abnormal temperature changes.
- Implement wireless communication between multiple sensor zones and a central hub.
- Identify the zone in which a hazard is detected.
- Display hazard alerts and activate an audible alarm.
- Develop a low-cost monitoring system that operates without internet connectivity.

## System Architecture

The system consists of two main units:

### 1. Zone Device

Each zone device monitors its surrounding environment using sensors connected to an Arduino Nano.

**Components:**
- Arduino Nano — sensor monitoring and hazard processing
- MQ gas sensor — hazardous gas and air-quality detection
- Flame sensor (HW-201) — flame detection
- LM35 — temperature measurement
- 433 MHz RF transmitter — wireless hazard alert transmission

When a sensor detects a condition that crosses its configured threshold, the Arduino Nano processes the input and transmits the corresponding hazard information to the central hub.

### 2. Central Monitoring Hub

The central hub receives and processes wireless alerts from the zone devices.

**Components:**
- ESP32 — central processing and alert handling
- 433 MHz RF receiver — reception of wireless messages
- 16×2 LCD — display of hazard type and affected zone
- Buzzer — audible hazard alert

## Working Principle

1. **Environmental monitoring:** Each Arduino Nano continuously reads its connected gas, flame, and temperature sensors.
2. **Hazard detection:** Sensor readings are evaluated against predefined thresholds or detection conditions.
3. **RF transmission:** When a hazard is detected, the zone device transmits an alert identifying the hazard and its zone.
4. **Central processing:** The RF receiver passes the incoming alert to the central hub for processing.
5. **Alert generation:** The LCD displays the detected hazard and corresponding zone, while the buzzer provides an audible warning.

## Hardware Components

| Component | Function |
|---|---|
| Arduino Nano | Zone-level sensor interfacing and processing |
| ESP32 | Central hub processing |
| 433 MHz RF transmitter | Wireless alert transmission |
| 433 MHz RF receiver | Wireless alert reception |
| MQ gas sensor | Gas and air-quality sensing |
| HW-201 flame sensor | Flame detection |
| LM35 temperature sensor | Temperature sensing |
| 16×2 LCD | Visual hazard notification |
| Buzzer | Audible alert |

## Implementation and Testing

The prototype was assembled using separate zone devices and a central hub. The project report documents a successful fire-detection demonstration in Zone 1.

When the fire sensor was triggered, the central hub received the RF alert, displayed the message indicating a fire at Zone 1 on the LCD, and activated the buzzer.

## Key Features

- Multi-zone hazard monitoring architecture
- Wireless communication using 433 MHz RF modules
- Zone-specific hazard identification
- Visual and audible alerts
- Internet-independent operation
- Modular design that can be extended to additional zones

## Applications

- Industrial and manufacturing safety
- Warehouses and storage facilities
- Commercial buildings and offices
- Residential hazard monitoring
- Remote locations with limited network connectivity

## Limitations

- RF communication range depends on the environment and installation.
- RF interference may affect message reception.
- The system requires a continuous power supply unless backup power is provided.
- Internet-independent operation does not provide remote monitoring without additional connectivity hardware.
- Sensor calibration and threshold selection influence detection reliability.

## Future Improvements

- Add RF communication error detection and improved message reliability.
- Introduce backup battery support.
- Extend the system to additional monitoring zones.
- Add optional IoT connectivity for remote notifications.
- Perform systematic testing of detection response, RF range, and sensor thresholds.

## Tools and Technologies

- Arduino Nano
- ESP32
- Arduino IDE / embedded C++
- 433 MHz RF communication
- Environmental sensors
- LCD and buzzer interfacing

