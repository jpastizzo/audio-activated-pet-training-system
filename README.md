# 🐾 Audio-Activated Pet Training System

An embedded system using an **Arduino Mega** to monitor environmental sound levels and control a **NEMA 17 stepper motor** for pet training. If the ambient noise remains below a predefined decibel threshold for a specified duration, the system actuates the motor as a behavioral cue.

## Features
- **Sound-Based Actuation** – Detects low-noise environments and triggers the motor.
- **Configurable Decibel Threshold** – Adjustable sensitivity for different environments.
- **Stepper Motor Control** – Uses an **A4988 motor driver** to precisely control a **NEMA 17 stepper motor**.
- **Relay Integration** – A **5V relay module** allows additional control functionality.
- **3D-Printed Mechanisms** – Customizable structure and parts for real-world applications.

---

## Hardware Components
| Component                  | Description |
|----------------------------|-------------|
| **Arduino Mega**           | Microcontroller for processing and control. |
| **LM296**                  | Voltage regulator for stable power supply. |
| **NEMA 17 (17HS08-1004S)** | Bipolar stepper motor for mechanical actuation. |
| **A4988 Motor Driver**     | Stepper motor driver for precise control. |
| **5V Relay Module**        | Enables switching of external components. |
| **Grove Base Shield V2.0** | Expansion shield for easy connection of Grove modules. |
| **Grove Sound Sensor**     | Detects environmental sound levels to trigger actuation. |

### Additional Components:
- **3D-Printed Structure & Mechanisms** – CAD files included in repository.

---

## Purpose
This system is designed to **use audio cues for pet training** by reinforcing quiet behavior. When the environment remains below a specified noise threshold for a set period, the system activates the stepper motor to dispense a reward or trigger an interactive element.

---

## Software & Dependencies
### **Required Tools**
- **[Arduino IDE](https://www.arduino.cc/en/software)** (For writing and uploading code)
- **[A4988 Stepper Motor Library](https://github.com/laurb9/StepperDriver)** (For stepper motor control)
- **Arduino `Servo.h` Library** (For relay control if needed)
- **[Adafruit Sound Sensor Library](https://github.com/adafruit/Adafruit_Sound_Sensor)** (If using an Adafruit sound sensor)

### **Library Installation**
To install required libraries:
1. Open **Arduino IDE**.
2. Navigate to **Sketch > Include Library > Manage Libraries**.
3. Search and install:
   - `StepperDriver`
   - `Servo`
   - `Adafruit Sound Sensor` (if using Adafruit sound sensor)

---

## Wiring & Circuit Diagram
### **Connections**
| Component         | Arduino Mega Pin |
|------------------|----------------|
| **Grove Base Shield** | Mounted on Arduino Mega |
| **Grove Sound Sensor** | Connected to **A0** on Grove Shield |
| **A4988 Driver** | `DIR` → `D8`, `STEP` → `D9`, `ENABLE` → `D10` |
| **Relay Module** | `D7` (Digital Output) |
| **Motor Power** | 12V External Supply |

### **Circuit Diagram**
*(Coming Soon)* <!--*(Or use Fritzing to create a wiring diagram.)*-->

---
<!--
## 🔧 Installation & Setup
1. **Connect Hardware:** Wire the Arduino, motor, and sensors as per the circuit diagram.
2. **Upload Code:** Use the Arduino IDE to upload `main.ino` to the **Arduino Mega**.
3. **Adjust Sensitivity:** Modify the `DECIBEL_THRESHOLD` value in the code to set the noise level.
4. **Test the System:** Observe motor actuation when the environment remains quiet.

```cpp
#define SOUND_SENSOR A0
#define DECIBEL_THRESHOLD 50  // Adjust based on environment
#define ACTUATION_DELAY 5000  // 5 seconds of silence before activation

void setup() {
    pinMode(SOUND_SENSOR, INPUT);
    Serial.begin(9600);
}

void loop() {
    int soundLevel = analogRead(SOUND_SENSOR);
    Serial.println(soundLevel);

    if (soundLevel < DECIBEL_THRESHOLD) {
        delay(ACTUATION_DELAY);
        // Code to actuate motor
    }
}
```

---
-->

## Usage
1. Place the system in the pet’s environment.
2. Adjust the **decibel threshold** to match ambient conditions.
3. Observe when the pet remains quiet – the motor activates to dispense a reward.
4. Fine-tune timing and sound sensitivity as needed.

---
<!--
## Troubleshooting
| Issue                         | Solution                                              |
|-------------------------------|-------------------------------------------------------|
| **Motor Not Moving**          | Check A4988 wiring and power connections.             |
| **Too Many False Triggers**   | Increase the **DECIBEL_THRESHOLD** value in the code. |
| **Relay Not Switching**       | Ensure proper wiring and check **D7** output in code. |

--- -->

## License
This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
Shoutout to my dog Alfie

