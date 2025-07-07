# 🤖 Hand Gesture Controlled Car

A wireless robotic car that can be controlled using intuitive hand gestures via an accelerometer-based glove. The system leverages real-time sensor data and radio-frequency modules to transmit and execute movement commands.


## 🧠 Introduction

This project aims to control a robotic car using hand gestures, removing the need for traditional remotes or joystick-based systems. The core idea revolves around detecting hand movements using an **ADXL335 accelerometer** mounted on a glove. These movements are translated into control commands and transmitted wirelessly to a car.

Applications:
- Industrial robotics
- Military reconnaissance
- Healthcare (e.g., remote surgeries)
- Hazardous material handling

---

## 🏗️ System Architecture

The system consists of two major parts:

### 🔹 Transmitter (Glove Unit)
- **ADXL335 Accelerometer**: Detects hand tilt in X and Y directions.
- **Arduino Pro Mini**: Converts analog data into digital signals.
- **nRF24L01 Module**: Wirelessly transmits the gesture data.

### 🔹 Receiver (Car Unit)
- **nRF24L01+PA+LNA**: Receives data.
- **Arduino Nano V3**: Processes and interprets the incoming signal.
- **L298N Motor Driver**: Drives the DC motors.
- **DC Motors**: Control the movement of the car.

> Communication occurs over the 2.4GHz ISM band using GFSK modulation.

---

## 🔌 Circuit Implementation

### ✋ Gesture Mapping:

| Hand Movement | Car Action     |
|---------------|----------------|
| Tilt Forward  | Move Forward   |
| Tilt Backward | Move Backward  |
| Tilt Left     | Turn Left      |
| Tilt Right    | Turn Right     |
| Stable Hand   | Stop           |

### ⚙️ Functional Flow:

1. Hand tilt detected by ADXL335 accelerometer.
2. Arduino Pro Mini reads and processes this signal.
3. Data sent to receiver using nRF24L01 module.
4. Arduino Nano interprets the command and triggers the motor driver.
5. L298N module powers the motors for directional movement.

---

## 📊 Results & Discussion

- ✅ After hardware setup, the system worked reliably for major directional commands:
  - Forward: +Y tilt
  - Reverse: -Y tilt
  - Left: -X tilt
  - Right: +X tilt
  - Stop: Stable position

- 📈 **Performance**: About **80% accuracy** in gesture recognition under moderate conditions.
- ⚠️ **Challenges**:
  - Slight lag in communication in noisy environments.
  - Limited operational range due to RF module.
  - Sensitivity to rapid hand movements or environmental vibration.

> Overall, the system demonstrated smooth and intuitive control using basic hand movements.

---

## ✅ Conclusion

This project demonstrates the successful implementation of a hand gesture-based control system for robotic cars. Using basic components like ADXL335, Arduino, and nRF24L01 modules, we were able to:
- Capture intuitive hand gestures.
- Transmit them wirelessly.
- Drive the robot car accordingly.

Such a system has the potential to revolutionize how we interact with machines, especially in fields like assistive technology, hazardous environments, and advanced gaming interfaces.

---

## 🚀 Future Scope

- 🔋 Replace bulky 9V batteries with **compact Li-ion cells** for better endurance.
- 🎥 Add **real-time video feed** to assist in remote navigation and surveillance.
- 🧠 Introduce **gesture learning using ML** for more dynamic commands (like finger gestures).
- 🎮 Integrate with **AR/VR or gaming consoles** for immersive control systems.
- 🏥 Create **miniaturized surgical robots** controllable via gestures.
- 🏠 Use in **smart home automation** to replace remotes/switches with intuitive gestures.

---

## ⚠️ Limitations

- **Limited Power**: 9V batteries offer low capacity and short runtime.
- **Range Constraints**: RF module has a range of ~30–50 meters only.
- **Interference**: Sensitive to signal interference and background motion.
- **Gesture Complexity**: Only basic X/Y axis gestures are supported in current version.

---

## 🛠️ How to Run

### 🔧 Hardware Required:
- 1 × ADXL335 Accelerometer
- 1 × Arduino Pro Mini (Transmitter)
- 1 × Arduino Nano V3 (Receiver)
- 2 × nRF24L01 Modules (with and without PA+LNA)
- 1 × L298N Motor Driver Module
- 4 × DC Motors
- 9V Batteries or external supply
- Jumper wires, breadboards, and glove

### 💻 Software:
- Arduino IDE
- Libraries: `SPI.h`, `RF24.h`

### 📂 Code Files:
- `transmitter.ino`: Captures hand gesture data and sends it over RF.
- `receiver.ino`: Receives gesture data and controls motors accordingly.



> 👨‍💻 Developed by: Mritunjay Kumar Singh
