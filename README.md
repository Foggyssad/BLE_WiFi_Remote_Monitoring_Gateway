BLE WiFi Remote Monitoring Gateway# BLE WiFi Remote Monitoring Gateway

## Overview

The BLE WiFi Remote Monitoring Gateway is an embedded system that collects
sensor data, detects monitoring events, and transmits telemetry to a remote
host over a wireless network and stores event records in the external QSPI flash memory on the board.

The system uses:

- **BLE** for configuration and provisioning
- **WiFi** for telemetry transmission

## Hardware Platform

The prototype is built around the **FRDM-RW612 development board** which
contains the RW612 MCU.

Sensors connected via **I²C**:

- INA219 – current and voltage monitoring
- BME280 – temperature, humidity, and pressure monitoring

## Operation

At startup the firmware loads configuration data from flash memory.

- If valid WiFi credentials exist, the gateway connects to WiFi.
- If not, the device starts **BLE advertising** for provisioning.

During operation the gateway:

1. Samples sensors
2. Updates observable values
3. Evaluates monitoring conditions
4. Detects events
5. Stores event records in flash
6. Sends telemetry over WiFi UDP

## Physical Deployment

The final prototype will be placed inside a protective, plastic, enclosure containing
the development board and connected sensors.

The enclosure will provide mechanical protection while allowing:

- USB power input
- wireless communication (BLE / WiFi)
