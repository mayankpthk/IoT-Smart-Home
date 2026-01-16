# Hardware Setup for IoT Smart Home

This document explains how to set up the hardware components for the IoT Smart Home system.

---

## 1. Required Components

- ESP32 microcontroller (1 per device)
- DHT11/DHT22 Temperature & Humidity Sensor
- PIR Motion Sensor
- Relay modules (for controlling lights, fans, etc.)
- Jumper wires
- Breadboard (optional for testing)
- Power supply (USB or battery)
- Resistors (as required by sensors)

---

## 2. Wiring Instructions

### ESP32 → DHT Sensor
- **VCC** → 3.3V  
- **GND** → GND  
- **Data** → GPIO 4

### ESP32 → PIR Sensor
- **VCC** → 5V  
- **GND** → GND  
- **OUT** → GPIO 5

### ESP32 → Relay Module
- **VCC** → 5V  
- **GND** → GND  
- **IN1** → GPIO 12 (for first appliance)  
- **IN2** → GPIO 13 (for second appliance)

> **Note:** Refer to `wiring_diagram.png` for a complete visual layout.

---

## 3. Flashing Firmware

1. Open `hardware/esp32/firmware.ino` in Arduino IDE or PlatformIO.  
2. Connect ESP32 to your PC via USB.  
3. Select **Board → ESP32 Dev Module**  
4. Select the correct **Port**  
5. Click **Upload** to flash the firmware  

---

## 4. Configuration

1. Open `hardware/esp32/config.h`  
2. Set your **DEVICE_ID** for each ESP32 device.  
3. Enter your **MQTT broker details** (if using a local broker, set URL & port; for cloud, use credentials).  
4. Save and re-upload firmware if any changes are made.

---

## 5. Testing

- Power on the ESP32 device.  
- Check that sensors send data to the MQTT broker.  
- Verify that the backend receives sensor updates.  
- Use the frontend dashboard to toggle devices (lights, fans, etc.).  

---

## 6. Notes

- Each ESP32 device must have a **unique DEVICE_ID**.  
- Ensure the ESP32 is connected to the same network as the MQTT broker (if local).  
- Double-check wiring before powering on to avoid damaging components.  
