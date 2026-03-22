# 📦 MPU6050 Controlled Rotating Object on OLED (ESP32)

## 📌 Project Overview

This project demonstrates how to use an **MPU6050 sensor** with an **ESP32** to control a rotating object displayed on an **SSD1306 OLED screen**.

When the sensor is tilted or rotated:

* The OLED displays a rotating square (cube-like effect)
* Motion is smooth and responsive using sensor fusion

This project is ideal for learning:

* I2C communication
* Sensor interfacing
* Real-time graphics rendering
* Embedded systems design

---

## 🎯 Features

* Real-time rotation based on motion
* Smooth animation using complementary filter
* Flicker-free OLED rendering
* Works fully in simulation (Wokwi) or real hardware

---

## 🧰 Components Required

### Hardware

* ESP32
* MPU6050 (Accelerometer + Gyroscope)
* SSD1306 OLED Display (128x64, I2C)

---

## 🔌 Circuit Connections

### I2C Connection (Shared Bus)

| Device | ESP32 Pin |
| ------ | --------- |
| SDA    | GPIO 21   |
| SCL    | GPIO 22   |
| VCC    | 3.3V      |
| GND    | GND       |

> Both MPU6050 and OLED share the same I2C lines.

---

## 📚 Libraries Used

Install the following libraries in Arduino IDE:

* Adafruit GFX
* Adafruit SSD1306
* MPU6050
* Wire (built-in)

---

## ⚙️ Working Principle

### 1. Sensor Data Acquisition

* Accelerometer provides tilt (ax, ay, az)
* Gyroscope provides rotation speed (gx, gy, gz)

### 2. Angle Calculation

* Accelerometer gives stable angle
* Gyroscope gives smooth motion
* Combined using **Complementary Filter**

### 3. Graphics Rendering

* A square is defined using 2D points
* Points are rotated using trigonometric transformation
* Lines are drawn between points on OLED

---

## 🧠 Complementary Filter Formula

```
angle = 0.98 * (angle + gyro * dt) + 0.02 * accel_angle
```

* Reduces noise
* Eliminates drift
* Provides smooth output

---

## ▶️ How to Run

### In Wokwi:

1. Create ESP32 project
2. Add MPU6050 and OLED
3. Connect as per diagram
4. Paste the code
5. Start simulation
6. Adjust tilt/rotation sliders

### On Real Hardware:

1. Connect components
2. Upload code using Arduino IDE
3. Tilt the sensor to observe motion

---

## 🎥 Output

* A rotating square appears on OLED
* Rotation changes with sensor movement
* Smooth and stable visualization

---

## ⚠️ Troubleshooting

| Issue         | Solution                              |
| ------------- | ------------------------------------- |
| Blank display | Check I2C address (0x3C)              |
| No motion     | Verify MPU6050 connections            |
| Flickering    | Avoid clearing full screen every loop |
| Shaky motion  | Increase smoothing factor             |

---

## 🚀 Future Improvements

* Add pitch and roll value display
* Upgrade to 3D cube rendering
* Use Kalman filter for advanced smoothing
* Create motion-controlled game
* Add menu system using buttons

---

## 📁 Project Structure

```
mpu6050-oled-project/
│── main.ino
│── README.md
```

---

## 🎓 Learning Outcomes

* Embedded system design
* Sensor fusion techniques
* Real-time data visualization
* ESP32 programming

---

## 🏁 Conclusion

This project is a great starting point for motion-based systems. It combines hardware and software concepts to create an interactive and visually engaging application.

---

V.Venkata Harinath
Diploma 2nd year ECE
SVGP TIRUPATI
