# 🩺 Smart Saline Bottle Monitoring System using Arduino and HX711

## 📘 Project Overview

This project aims to **prevent reverse blood flow** in patients by continuously monitoring the **saline bottle weight** using the **HX711 weight sensor** and **Arduino Uno**. When the saline level drops below a safe threshold, a **buzzer alert** notifies medical staff for immediate action.

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

### HX711 to Arduino:
| HX711 Pin | Arduino Pin |
|-----------|-------------|
| VCC       | 5V          |
| GND       | GND         |
| DT        | D3          |
| SCK       | D2          |

### Buzzer:
- Positive → D9  
- Negative → GND

### LDR (Optional):
- AO → A0  
- VCC → 5V  
- GND → GND

---

## 💻 Arduino Code

```cpp
#include "HX711.h"

#define DOUT  3
#define CLK   2
#define BUZZER_PIN 9

HX711 scale;

void setup() {
  Serial.begin(9600);
  scale.begin(DOUT, CLK);
  pinMode(BUZZER_PIN, OUTPUT);
  Serial.println("Initializing scale...");
  scale.set_scale();
  scale.tare();  // Reset the scale to 0

  long zero_factor = scale.read_average(); 
  Serial.print("Zero factor: "); 
  Serial.println(zero_factor);
}

void loop() {
  float weight = scale.get_units(5);
  Serial.print("Weight: ");
  Serial.print(weight);
  Serial.println(" grams");

  if (weight < 100) { // Threshold to trigger alarm
    digitalWrite(BUZZER_PIN, HIGH);
  } else {
    digitalWrite(BUZZER_PIN, LOW);
  }

  delay(1000);
}
