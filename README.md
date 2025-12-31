# SkyTach MKII

This project is a custom-designed rocket flight computer intended to track altitude, location, velocity, and other flight parameters. It integrates multiple sensors, a single microcontroller, and dual pyro channels to support high-power and experimental rocketry applications.

# Project Function

The board performs the following primary functions:

- Real-time flight data acquisition from multiple IMUs, pressure, and environmental sensors  
- Telemetry transmission to ground control via LoRa  
- GPS tracking for post-flight recovery  
- Two pyro channels for parachute deployment and stage separation  
- Data logging to non-volatile FRAM for post-flight analysis  
- Single-MCU architecture based on the ESP32-S3  

# Project Components

- **MCU**
  - ESP32-S3
- **GPS**
  - MAX-M8Q-0 with external antenna support
- **Sensors**
  - AHT20 – temperature
  - H3LIS331DLTR – 3-axis high-g accelerometer
  - BMP390 – barometric pressure sensor
  - LIS3MDLTR – magnetometer
  - IAM-20680HT – 6-axis IMU
- **Memory**
  - CY15B104Q FRAM (4 Mbit, non-volatile)
- **Telemetry**
  - LoRa module
- **Power**
  - LM61495 buck converter (5V rails)
- **Interfaces**
  - USB-C
- **Outputs**
  - 2× MOSFET-driven pyro channels (parachutes/staging)
- **Connectors**
  - XT60 battery input
  - Screw terminals for pyro channels
 
# BOM

<img width="1518" height="663" alt="image" src="https://github.com/user-attachments/assets/40847a41-3dac-4544-8844-6afb28d1cca9" />
Total Cost: $404.72

# Hardware Description

The system is divided into the following subsystems:

## 1. Power Block
The LM61495 buck converter generates a regulated 5V rail from the primary Li-Po / Li-Ion battery input. Filtering capacitors are used to reduce noise and ensure clean power delivery to both digital and analog subsystems.
## 2. Processing Unit
- **ESP32-S3**  
  Handles sensor fusion, telemetry, data logging, and overall flight logic.
## 3. Sensor Block
Redundant inertial and environmental sensors provide robust state estimation, including acceleration, orientation, altitude, temperature, and magnetic field data.
## 4. Telemetry
A LoRa module enables long-range, low-power communication with the ground station during flight.
## 5. Data Logging
Mission-critical data is stored in FRAM, ensuring persistence even in the event of sudden power loss.
## 6. Actuation
- Two independent pyro channels are used for parachute deployment and stage separation.
## 7. Communication & Debugging
A USB-C interface supports firmware flashing, debugging, and direct telemetry monitoring during ground testing.

# Software

The onboard software is not publicly released, as it could be reverse-engineered and misused. Access to firmware requires prior approval.

# Finished Render
The PCB renderings show the completed flight computer design.

![Screenshot 2025-12-30 175227](https://github.com/user-attachments/assets/4b39e753-c889-49bb-a918-cf5e65749c01)
