# ESP32 DHT11 Sensor with MQTT Integration

This project provides an ESP32 microcontroller setup for reading temperature and humidity data from a DHT11 sensor and publishing it to an MQTT broker. The data can be monitored over an MQTT-enabled network, making it ideal for IoT applications like smart home automation or remote environmental monitoring.

## Features

- **WiFi Connectivity**: Connects to a specified WiFi network.
- **DHT11 Temperature and Humidity Readings**: Reads environmental data using the DHT11 sensor.
- **MQTT Publishing**: Publishes temperature and humidity data to a specified MQTT broker.
- **Reconnect Logic**: Ensures persistent connectivity to the MQTT broker.

## Requirements

- **Hardware**: ESP32 board, DHT11 sensor
- **Libraries**:
  - [Adafruit_Sensor](https://github.com/adafruit/Adafruit_Sensor)
  - [DHT sensor library](https://github.com/adafruit/DHT-sensor-library)
  - [PubSubClient](https://github.com/knolleary/pubsubclient)
  
  Install these libraries via the Arduino IDE Library Manager or by downloading them from GitHub.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/esp32-dht11-mqtt.git
