# 🩺 Smart Saline Bottle Monitoring System using Arduino and HX711

## 📘 Project Overview

This project presents a real-time monitoring system for saline bottles using an **HX711 load cell** and **Arduino Uno**. The system triggers a **buzzer alert** when the saline level drops below a preset weight, preventing reverse blood flow into a patient—a critical safety issue in hospital care.

---

## ⚙️ Components Used

| Component               | Quantity |
|-------------------------|----------|
| Arduino Uno             | 1        |
| HX711 Module + Load Cell| 1        |
| Active Buzzer           | 1        |
| LDR Module (optional)   | 1        |
| Jumper Wires            | As needed |
| Breadboard (optional)   | 1        |

---

## 🔌 Circuit Connections

- **HX711** is connected to Arduino using pins D2 (SCK) and D3 (DT).
- **Buzzer** is connected to pin D9 for alerts.
- **Optional LDR** is connected to analog pin A0 for ambient light detection.
- All modules are powered via Arduino's 5V and GND.

---

## 🧠 How It Works

- The **load cell** measures the real-time weight of the saline bottle.
- When the weight drops below a **safe threshold**, the **buzzer is activated** to notify medical staff.
- The system ensures that action is taken before the saline bottle empties and reverse blood flow begins.
- The **LDR** can optionally provide context-aware behavior (e.g., silent mode at night).

---

## 📊 Features

- Accurate saline level detection using weight sensing.
- Real-time buzzer alert when critical levels are reached.
- Can be customized for different bottle sizes and thresholds.
- Optional ambient light sensing.
- Scalable and affordable for hospital-wide deployment.

---

## 🚀 Future Enhancements

- Integration with Wi-Fi modules for remote alerts.
- LCD display to show exact saline weight.
- Multiple sensor support for multiple patients.
- Battery backup for uninterrupted monitoring.
