# IoT Smart Home System Architecture

## Overview
The IoT Smart Home system is designed to monitor and control home devices remotely.  
It integrates ESP32-based IoT devices, a FastAPI backend, an MQTT broker for communication, and a web-based frontend dashboard.

---

## Components

### 1. Devices (ESP32)
- Microcontrollers with attached sensors and actuators
- Sensors: Temperature, Humidity, Motion, Light
- Actuators: Relays for lights, fans, and other appliances
- Devices communicate with the backend via MQTT

### 2. Backend (FastAPI)
- Handles API requests from the frontend
- Subscribes to MQTT topics from devices to receive sensor data
- Publishes control commands to devices over MQTT
- Stores device states, logs, and user data in PostgreSQL

### 3. Frontend (Web Dashboard)
- Displays real-time sensor data from devices
- Allows users to send commands to devices
- Provides authentication and user management

### 4. Communication Layer (MQTT)
- MQTT broker relays messages between devices and backend
- Topics are structured as:  
