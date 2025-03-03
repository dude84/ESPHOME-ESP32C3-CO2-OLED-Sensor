# ESPHOME-ESP32C3-CO2-OLED-Sensor
ESP32-C3 Super Mini, with SDC41 CO2 sensor and SSD1306 128x64 OLED screen implemented for ESPHOME

# SG CO₂ Sensor V2

This project is designed to monitor indoor air quality by measuring CO₂ levels using a Sensirion SDC41 sensor. The system is built on an ESP32-C3 Super Mini board running ESPHome firmware, which reads sensor data and updates an OLED display in real time.

## Features

- **CO₂, Temperature, and Humidity Monitoring:**  
  The Sensirion SDC41 sensor provides precise measurements of CO₂ concentration, ambient temperature, and humidity.

- **OLED Display (128×64):**  
  The display shows:
  - **Top Status Line:** The current CO₂ value in large text.
  - **Wi‑Fi Icon:** A 12×12 icon in the top right indicating network connectivity.
  - **Bar Indicator:** A visual bar representing the current CO₂ level relative to configurable thresholds.
  - **Status Word:** A status label (e.g. "SAFE", "WARNING", "DANGER", "CRITICAL") based on the measured CO₂.
  - **Tag Identifier:** A small tag (defined via configuration substitutions) printed in the bottom left corner.

- **Thresholds and Alerts:**  
  The system uses configurable threshold values (safe, warning, dangerous, critical) that can be adjusted via Home Assistant. This allows for dynamic updates and remote monitoring.

- **Home Assistant Integration:**  
  With ESPHome's API and template components, settings such as thresholds and brightness can be modified directly from Home Assistant.

## Hardware Connections

- **ESP32-C3 Super Mini Board:**  
  - **I2C Bus:**  
    - **SDA:** Connected to GPIO2  
    - **SCL:** Connected to GPIO3
  - **OLED Display:** Connected via I2C (address 60)
  - **SDC41 Sensor:** Connected via I2C (address 0x62)
  - **LED Output:** Connected to GPIO8 for status indication

- **Sensirion SDC41 CO₂ Sensor:**  
  A high-precision sensor that measures CO₂, temperature, and humidity using the I2C protocol.

- **OLED 128×64 SSD1306 Display:**  
  A commonly used display module with the SSD1306 driver. It communicates over I2C and shows sensor data along with custom graphics and text.

## Useful Links

- **Sensirion SDC41 CO₂ Sensor:**  
  [Sensirion SDC41 Product Page](https://www.sensirion.com/en/environmental-sensors/industrial-co2-sensor-sdc41/)

- **ESP32-C3 Super Mini Board:**  
  [ESP32-C3 DevKitM-1 Product Page](https://www.espressif.com/en/products/devkits/esp32-c3-devkitm-1)

- **OLED 128×64 SSD1306 Display:**  
  [SSD1306 OLED Display Module - Adafruit](https://www.adafruit.com/product/326)

## Project Configuration

The ESPHome configuration includes:
- Sensor readings from the SDC41.
- An OLED display with real-time data and graphical elements.
- Home Assistant integration for remote configuration.
- Customization via substitutions (e.g., setting the tag, name, and device description).

Refer to the ESPHome YAML configuration file for details on wiring, sensor setup, and display code.

---

This project is a modular, smart home air quality monitor that leverages modern sensor technology and flexible firmware. It is designed for easy integration into Home Assistant, providing real-time insights into indoor air quality.
