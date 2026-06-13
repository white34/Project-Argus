# Inspection-Rover
An autonomous inspection rover that navigates industrial facilities and scans structures both visually and with IR in extreme environments so engineers don't have to.


# Project Argus

An autonomous modular inspection rover built for industrial 
deployment in the UAE.

Argus uses a Raspberry Pi 5 with a Hailo-8 AI accelerator to 
run onboard computer vision inference, combining thermal imaging, 
laser distance sensing, and environmental monitoring to detect 
anomalies and generate inspection reports — without a human 
entering the space.

Target deployment: industrial lighting and facility inspection 
at BEEAH and similar UAE industrial clients.

## Why

Industrial inspection in the UAE involves large facilities, 
extreme heat, and environments where sending a human is slow, 
expensive, or dangerous. Argus is built to operate in those 
spaces autonomously, flagging thermal anomalies and obstacles 
in real time via a Flask web dashboard accessible remotely.

The rover is designed as a modular platform — sensor bays 
swap in under three minutes using GX12 aviation connectors 
for electrical disconnect and cam levers on 2020 aluminium 
extrusion for mechanical lock. One chassis, multiple 
inspection configurations.

## Hardware

**Compute**
- Raspberry Pi 5 8GB
- Raspberry Pi Active Cooler
- Raspberry Pi AI HAT+ 26 TOPS (Hailo-8 accelerator)
- ESP32 WROOM-32 DevKit V1 (motor and low-level sensor control)

**Propulsion**
- 4x JGB37-520 12V 200RPM DC motors with encoders
- 4x BTS7960 43A H-bridge motor drivers (one per motor)
- 4x 120mm rubber off-road wheels, direct 6mm D-shaft mount

**Power**
- Gens Ace 3S 11.1V 5000mAh 50C LiPo, XT60
- Dual 10A 50W IP68 synchronous buck converters (5V rail)
- 30A inline fuse, panel-mount kill switch
- 1000uF 16V low-ESR capacitors on Pi 5V input

**Sensors**
- MLX90640 32x24 IR thermal array, 55° FOV
- Pi Camera Module 3 Standard, 75°, on DS3218 pan/tilt servo
- 2x VL53L1X laser ToF distance sensors
- BME280 temperature, humidity, pressure (I2C)
- 3x DS18B20 waterproof temperature probes (1-Wire)
- INA219 current and voltage monitor (battery telemetry)

**Structure**
- Aluminium chassis plate, 4mm 6061-T6, laser cut
- 2020 aluminium extrusion upper sensor rack
- IP67 ABS electronics enclosure, ~245x95x85mm internal
- GX12 6-pin aviation connectors (tool-free electrical disconnect)
- M5 cam levers + dowel pins (tool-free mechanical modularity)
- 2x Jamicon 40mm 12V fans, cross-flow ventilation
- 18AWG silicone wire throughout

## Software Stack

- Python
- OpenCV + Hailo RT for onboard CV inference
- MLX90640 thermal threshold and anomaly detection
- Flask web dashboard (live feed, sensor telemetry, remote control)
- Auto-generated PDF inspection reports
- GPIO and I2C for sensor integration
- ESP32 over UART for motor control

## Current Status

Active build. Parts arriving June 2026.
Target: functional inspection demo, August 2026.
Pitched to MBRIF and BEEAH for UAE industrial deployment.
Submitted as part of Hack Club Stardance 2026.

## Build Milestones

- [ ] Chassis assembly and motor control via ESP32
- [ ] Pi 5 + AI HAT+ bring-up and thermal camera integration
- [ ] Flask dashboard with live thermal and visual feed
- [ ] VL53L1X obstacle detection
- [ ] Environmental sensor logging (BME280, DS18B20, INA219)
- [ ] Autonomous waypoint navigation
- [ ] Auto-generated PDF inspection report
- [ ] Field test at industrial site
- [ ] BEEAH facility demonstration
