# Washing Machine Controller

## Overview
This project is a **digital system design** implementation of a **washing machine controller** using **Logisim Evolution**. The system supports both **manual mode** and **predefined automatic washing programs** and is built using finite state machines and digital circuits.
![Washing Machine Diagram]([https://raw.githubusercontent.com/your-username/your-repo/main/images/washing_machine_diagram.png](https://github.com/VictorCraciunas/Washing-Machine/blob/main/proiect.png?raw=true))

## Features
- **Manual Mode:**
  - Set temperature: **30°C, 40°C, 60°C, 90°C**
  - Set rotation speed: **800, 1000, 1200 RPM**
  - Optional **prewash** and **additional rinse**
- **Automatic Modes:**
  - Quick Wash: **30°C, 1200 RPM**
  - Shirts: **60°C, 800 RPM**
  - Dark Colors: **40°C, 1000 RPM (with additional rinse)**
  - Dirty Laundry: **40°C, 1000 RPM (with prewash)**
  - Anti-allergic: **90°C, 1200 RPM (with additional rinse)**
- **Program Execution:**
  - Water filling, heating, spinning, rinsing, and centrifugation
  - **Door locking mechanism** (machine will not start with the door open)
  - **7-segment display** shows remaining washing time

## Design Components
- **Control Unit (CU):** Manages the washing process states
- **Execution Unit (EU):** Handles data processing
- **Multiplexer (13:1):** Selects program duration
- **Counter:** Keeps track of remaining time
- **Time Converter:** Converts time into BCD format for display
- **7-Segment Display (SSD):** Displays remaining time
- **Frequency Divider:** Adjusts clock frequency
- **Program Manager:** Tracks program execution states using cascaded counters

## State Diagram
The controller operates using a finite state machine, ensuring smooth transitions between different washing cycles. The program states include:
1. **Idle** (waiting for user input)
2. **Washing** (main wash, prewash if selected)
3. **Rinsing** (standard or additional)
4. **Spinning** (centrifugation at selected RPM)
5. **Complete** (door unlocks after 1 minute)

## User Guide
### Manual Mode
1. **Close the door** (ensure door switch is ON)
2. **Press the MANUAL button**
3. **Select temperature and spin speed**
4. **(Optional) Enable prewash/additional rinse**
5. **Press START to begin the cycle**
6. **Monitor the remaining time on the display**

### Automatic Mode
1. **Close the door** (ensure door switch is ON)
2. **Select one of the predefined programs**
3. **Press START to begin the cycle**
4. **Monitor the remaining time on the display**

## Technical Justifications
- The design was implemented in **two iterations**:
  - **First iteration:** Used a register to store program values dynamically
  - **Second iteration:** Optimized design by removing unnecessary components and simplifying logic gates
- **Optimized logic:**
  - **Replaced** a separate adder and multiplexer with a **12:1 multiplexer**
  - **Button inputs** directly determine program start conditions
  - **State tracking** using cascaded counters instead of a single complex counter

## Future Enhancements
- Expand **temperature options** using unused multiplexer select values
- Extend **program duration** using available counter bits
- Implement a **START/STOP mechanism** without requiring a RESET
- Replace **switches with buttons**, enabling **stored user selections**
- Enhance **error handling** for invalid input combinations

## References
- Digital System Design – Lectures & Laboratories
- Logic Design – Lectures & Laboratories
- Octavian Creț, Lucia Văcariu, “Logic Design Problems for Digital Systems” (U.T. Press, 2013)
- Octavian Creț, Lucia Văcariu, “Limbaj de programare VHDL”


