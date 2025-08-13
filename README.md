# Smart Helmet - Distance & Accident Detection

This project implements a **simplified smart helmet system** using an **ESP32** that:
- Monitors **distance** with an ultrasonic sensor
- Detects **accidents** with an MPU6050 accelerometer
- Detects **button presses** for manual actions
- Turns on an **LED** if the detected distance is below a threshold

---

## Features
- **Distance Monitoring**: Ultrasonic sensor checks the distance to obstacles.
- **Accident Detection**: MPU6050 detects high-impact collisions.
- **Push Button Input**: Can be used for SOS, manual reset, or custom actions.
- **LED Warning**: Lights up when the distance to an obstacle is less than the threshold.

---

## Components Required
- ESP32 Development Board
- HC-SR04 Ultrasonic Sensor
- MPU6050 Accelerometer + Gyroscope
- Push Button
- LED + Resistor
- Jumper Wires
- Breadboard

---

## Pin Connections

| Component      | ESP32 Pin |
|----------------|-----------|
| HC-SR04 Trig   | GPIO 5    |
| HC-SR04 Echo   | GPIO 18   |
| LED            | GPIO 2    |
| Push Button    | GPIO 15   |
| MPU6050 SDA    | GPIO 21   |
| MPU6050 SCL    | GPIO 22   |

---

## Code Logic

1. **Measure Distance**
   - Send a pulse to the ultrasonic sensor
   - Measure the echo time and calculate distance
   - If the distance is below `thresholdDistance` (default: 10 cm), turn on the LED

2. **Detect Accident**
   - Read acceleration values from MPU6050
   - If acceleration magnitude exceeds **3.0g**, mark as an accident

3. **Button Press**
   - Detect when the button is pressed for manual triggers

---

## Installation
1. Install **Arduino IDE**
2. Install the following libraries via Arduino Library Manager:
   - `MPU6050`
   - `Wire`
3. Connect the components as per the pin connections table
4. Upload the code to the ESP32

---

## Usage
- **LED ON** → Object is within the threshold distance
- **"Accident Detected!" message** → Strong impact detected by MPU6050
- **Button Press** → Displays "Button Pressed" in Serial Monitor

---

## Future Enhancements
- Send accident alerts via Blynk or SMS
- Add GPS to locate accident location
- Make LED blink in accident mode

---

## License
This project is open-source under the MIT License.
