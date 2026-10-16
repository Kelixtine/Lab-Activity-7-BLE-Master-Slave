# Laboratory Activity 7: Master-Slave BLE Communication on ESP32

## Group & Member Roles
* **Group Name:** Team BCA IoT / Group [Insert Group Number]
* **Master Controller:** Miche Louie Acompañado — *Responsible for Master ESP32 firmware development, push button hardware integration, and multi-client BLE scanning/connection logic.*
* **Slave 1 Node:** [Insert Groupmate Name] — *Responsible for Slave 1 ESP32 BLE Server setup, Service/Characteristic UUID configuration, and GPIO 4 LED wiring.*
* **Slave 2 Node:** [Insert Groupmate Name] — *Responsible for Slave 2 ESP32 BLE Server setup, hardware debugging, and real-time response validation.*

---

## Project Overview
This laboratory activity demonstrates real-time device coordination using **Bluetooth Low Energy (BLE)** on ESP32 microcontrollers. A central **Master ESP32** reads a physical push button (GPIO 18) and broadcasts state change commands (`1` for ON, `0` for OFF) to two peripheral **Slave ESP32** boards. Each slave intercepts the characteristic write request and toggles its respective LED connected on **GPIO 4**.

---

## Hardware Configuration & Specifications

| Device Role | Board Model | MAC Address | GPIO Pin Mapping | Service UUID |
| :--- | :--- | :--- | :--- | :--- |
| **Master** | ESP32 DevKitC | `b0:3f:d3:5b:bf:be` | Push Button: `GPIO 18` | N/A |
| **Slave 1** | ESP32 DevKitC | `cc:db:a7:3d:aa:22`[cite: 2] | LED & Resistor: `GPIO 4` | `2b92513e-afed-40ac-afa6-e54c63acdceb`[cite: 2] |
| **Slave 2** | ESP32 DevKitC | `3c:8a:1f:a3:59:e2`[cite: 1] | LED & Resistor: `GPIO 4` | `2b92513e-afed-40ac-afa6-e54c63acdcec`[cite: 1] |

* **Shared Characteristic UUID:** `ea3d7c32-0013-4447-8f7b-47b959b5cddc`[cite: 1, 2, 3]

---

## Demonstration Video
* **Video Link:** [Insert Google Drive / YouTube Link to Working Demo Video]
