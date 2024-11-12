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

# Installation Instructions

## 1. Clone the repository
Clone the project to your local machine or directly to your Arduino IDE project folder:

```bash
git clone https://github.com/yourusername/esp32-dht11-mqtt.git
```
## 2. Install the necessary libraries
Open Arduino IDE and go to Sketch -> Include Library -> Manage Libraries. Search for and install the following libraries:
```bash
- Adafruit Sensor
- DHT sensor library
- PubSubClient
```
### 3. Upload the Code

1. Open the `esp32-dht11-mqtt.ino` file in the Arduino IDE.
2. In the Arduino IDE, go to **Tools** > **Board** and select your ESP32 board model.
3. Go to **Tools** > **Port** and select the correct port for your ESP32.
4. Click the **Upload** button (the right arrow icon) to upload the code to the ESP32.



## Usage

### Connect the DHT11 Sensor:
- Connect the **Data** pin of the DHT11 to GPIO 14 on the ESP32.
- Connect **VCC** to the 3.3V pin and **GND** to the ground pin on the ESP32.

### Monitor the Data:
- Upon powering the ESP32, it connects to the specified WiFi and MQTT broker.
- Temperature and humidity data are published every 5 seconds to the MQTT topics:
  - `W014/temp/thomas` - for temperature data
  - `W014/hum/thomas` - for humidity data

### View Data:
- Subscribe to these topics in your MQTT client to view the live data updates.

## Code Overview

- **`initWifi()`**: Initializes the WiFi connection.
- **`reconnect()`**: Ensures connection with the MQTT broker, reconnecting if necessary.
- **`callback()`**: Handles incoming messages (currently set to print received messages to the serial console).
- **`setup()`**: Sets up WiFi, MQTT, and DHT11 configurations.
- **`loop()`**: Continuously reads sensor data and publishes it to the MQTT broker.

## Example Output

Example output on the serial monitor:
```plaintext
WLAN verbunden!
IP-Adresse: 192.168.1.2
Verbindung zum MQTT-Broker wird hergestellt...
Verbunden mit MQTT-Broker!
Luftfeuchtigkeit: 45.00 %
Temperatur: 23.50 °C
