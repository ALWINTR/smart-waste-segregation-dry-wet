# Automated Wet and Dry Waste Classification System

[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-00f0ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ALWINTR/smart-waste-segregation-dry-wet)
[![Developer](https://img.shields.io/badge/Developer-Alwin_T_R-0284c7?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alwintr)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

An automated dual-compartment waste classifier that differentiates dry waste and organic wet waste using soil moisture conductivity sensing, ultrasonic fill-level monitoring, and high-speed servo diversion flaps.

---

## System Architecture

```
                  +------------------------------+
                  |    Incoming Waste Deposit    |
                  +--------------+---------------+
                                 |
                                 v
                  +------------------------------+
                  |  Capacitive / Moisture Probe |
                  +--------------+---------------+
                                 |
                 +---------------+---------------+
                 v                               v
        [Moisture >= Threshold]        [Moisture < Threshold]
           (Wet / Organic)                    (Dry)
                 |                               |
                 v                               v
        +-------------------+           +-------------------+
        | Servo Divert Left |           | Servo Divert Right|
        | (Wet Bin Compart) |           | (Dry Bin Compart) |
        +-------------------+           +-------------------+
```

---

## Hardware Bill of Materials (BOM)

| Component | Technical Specification | Functional Role |
| :--- | :--- | :--- |
| **Microcontroller** | Arduino Uno (ATmega328P, 16MHz) | Master classification logic and servo timing |
| **Moisture Sensor** | Capacitive / Resistive Moisture Probe | Wet vs Dry dielectric conductivity sensing |
| **Bin Level Sensor** | HC-SR04 Ultrasonic Sensor | Real-time bin fill level and overflow monitor |
| **Actuator** | TowerPro SG90 9g Micro Servo | Bi-directional diverter trapdoor (0 to 180 degrees) |
| **Visual Indicators** | Blue LED (Wet) / Green LED (Dry) | Immediate classification feedback |

---

## Circuit Pinout Table

| Module Pin | Arduino Uno Pin | Signal Type | Description |
| :--- | :--- | :--- | :--- |
| **Moisture Sensor Analog** | Analog Pin A0 | 10-Bit ADC In | Conductance measurement (Wet < 500) |
| **Ultrasonic Trigger** | Digital Pin D2 | Output Pulse | 10 microsecond ultrasonic sonar trigger |
| **Ultrasonic Echo** | Digital Pin D3 | Input Pulse | Echo travel time measurement |
| **Servo PWM Signal** | Digital Pin D9 | PWM (50Hz) | 45 degree (Wet) vs 135 degree (Dry) diverter |
| **Wet Indicator LED** | Digital Pin D6 | Output | Active upon organic waste detection |
| **Dry Indicator LED** | Digital Pin D7 | Output | Active upon dry waste detection |

---

## Author

**Alwin T R** - Robotics and Automation Engineer  
- LinkedIn: [linkedin.com/in/alwintr](https://www.linkedin.com/in/alwintr)  
- Portfolio: [alwintr.github.io](https://alwintr.github.io)  
- GitHub: [github.com/ALWINTR](https://github.com/ALWINTR)

---

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.
