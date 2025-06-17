# 🤖 Line Follower Robot using Arduino + L298N

A simple autonomous line follower robot built with an Arduino, IR sensors, and L298N motor driver. It follows a black line on a white surface using two IR sensors and controls DC motors based on sensor readings.

## 📦 Components Required

- Arduino Uno/Nano
- L298N Motor Driver Module
- 2 DC Motors (Left & Right)
- IR Sensors (2) — Left and Right
- Chassis + Wheels + Caster
- Power Supply (Battery pack)
- Jumper Wires

## 🔌 Pin Configuration

| Component      | Arduino Pin | Description                     |
|----------------|-------------|---------------------------------|
| IR Sensor Left | A1          | Left line-tracking sensor       |
| IR Sensor Right| A0          | Right line-tracking sensor      |
| Motor ENA      | 10          | PWM speed control for Motor 1   |
| Motor IN1      | 9           | Motor 1 direction control       |
| Motor IN2      | 8           | Motor 1 direction control       |
| Motor IN3      | 7           | Motor 2 direction control       |
| Motor IN4      | 6           | Motor 2 direction control       |
| Motor ENB      | 5           | PWM speed control for Motor 2   |

## 🚦 Logic & Behavior

The robot reacts to line detection using the IR sensors:

| IR Left | IR Right | Action         |
|---------|-----------|----------------|
| 0       | 0         | Move Forward   |
| 0       | 1         | Turn Left      |
| 1       | 0         | Turn Right     |
| 1       | 1         | Stop (End)     |

## ⚙️ Working Principle

- Each IR sensor outputs:
  - `0` when it detects **white surface**
  - `1` when it detects **black line**
- Based on sensor states, the motors are directed to keep the robot aligned with the line.

## 🧠 Code Overview

- `analogWrite(enA, 150)` and `analogWrite(enB, 150)` control motor speed (adjust from 0–255).
- `digitalRead(A0/A1)` reads the state of IR sensors.
- `loop()` continuously monitors the sensors and adjusts motion.

## 🛠️ Setup Instructions

1. Assemble your robot chassis and connect the motors to the L298N module.
2. Connect L298N to the Arduino pins as listed above.
3. Mount the IR sensors on the front of the robot (spaced ~2-3 cm apart).
4. Upload the code to your Arduino using Arduino IDE.
5. Place the robot on a black line path with white background and power it on.

## 📷 Suggested Improvements

- Add a middle IR sensor for better accuracy.
- Use PID control for smoother line following.
- Add obstacle detection using ultrasonic sensor.

## 📜 License

This project is open-source under the MIT License — feel free to modify and share with attribution.

---

Made with 💡 by Hari Aditya

