# Laser-Tripwire-Intruder-Tracking-System
Collaborated in a 4-member team for College Skill Lab and enhanced an existing Arduino project using Laser for detection by adding Bluetooth (HC05) based room-level intrusion detection and real-time alerts using on phone application.

Overview

This project is an Arduino-based security system that **detects intrution** using a **laser-LDR tripwire mechanism**. Once the **laser is interrupted**, the system activates the intrusion monitoring and **buzzer and LED turns ON**. If the **intruder remains in the house**, the system determines the intruder's **current location** using **ultrasonic sensors** and relays the room where intruder entered in real-time through **HC-05** bluetooth module and **Bluetooth-Terminal application on phone**.

Components Used

Arduino Uno
Laser Transmitter Module
Laser Receiver Sensor Module
HC-05 Bluetooth Module
Waterproof Ultrasonic Distance Sensors (2)
LED
Buzzer
330 Ω Resistor
Jumper Wires

Working Principle
- A laser beam is continuously directed at an LDR.
- When the beam is interrupted, the system detects a potential intrusion.
- The buzzer and LED turn ON, indicating that the security has been breached.
- Two ultrasonic sensors monitor two rooms. Limited rooms were chosen for demonstration purpose.
- The Arduino compares measured distances against calibrated wall distances. Detects intruder when the room is entered by noticing the change in distance.
- The detected room occupancy status is transmitted via Bluetooth to the owner.
- The system continuously updates the intruder's location while monitoring remains active.

The video demonstartion is uploaded under "Video Demo" folder in the same repository

Team
Developed as part of the IoT Skill Lab by a 4-member team at Ramaiah Institute of Technology (AUGUST 2024).

Ciruit Diagram
Drawn by hand since Tinkercad did not support HC-05 Bluetooth at the time of work. 
<img width="1600" height="1107" alt="IMG-20240814-WA0001" src="https://github.com/user-attachments/assets/afaadeac-28a6-4c3e-933c-3ac0643d40e0" />

Reference
https://projecthub.arduino.cc/fanesahadi/laser-security-system-at-home-basic-f2a79e

Application for Bluetooth-Terminal
https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal
