# MQTT Communication Flow for IoT Smart Home

This document describes the MQTT topics, message formats, and flow of communication between devices and the backend.

---

## 1. MQTT Broker

- The MQTT broker acts as a central message relay.  
- Devices publish sensor data and subscribe to control commands.  
- Backend subscribes to sensor topics and publishes commands to devices.

---

## 2. Topic Structure

All topics follow this general format:

