# Laboratory Activity 7: Master-Slave BLE Communication on ESP32

## 👥 Group & Member Details
* **Group Name:** Team BSCA_IoT 
* **Master Controller:** 
  * **Student Name:** Miche Louie B. Acompañado
  * **Role & Contributions:** Developed the Master ESP32 firmware, integrated the push button on GPIO 18, and implemented the multi-client BLE scanning and connection logic.
* **Slave 1 Node:** 
  * **Student Name:** Emmery Kelsey V. Mendoza
  * **Role & Contributions:** Configured the Slave 1 ESP32 BLE Server, set up the unique Service and Characteristic UUIDs, and wired the LED circuit on GPIO 4.
* **Slave 2 Node:** 
  * **Student Name:** Shyane Novelle R. Canayan
  * **Role & Contributions:** Configured the Slave 2 ESP32 BLE Server, handled hardware debugging, and verified real-time command responses.

---

## 📋 Project Overview & Specifications
This project implements a Master-Slave Bluetooth Low Energy (BLE) network using ESP32 microcontrollers. The Master reads a physical button press and wirelessly transmits state commands to multiple Slaves to toggle their external LEDs simultaneously.

| Device Role | Board Model | MAC Address | GPIO Pin Mapping | Service / Characteristic UUIDs |
| :--- | :--- | :--- | :--- | :--- |
| **Master** | ESP32 DevKitC | `b0:3f:d3:5b:bf:be` | Push Button: `GPIO 18` | N/A |
| **Slave 1** | ESP32 DevKitC | `cc:db:a7:3d:aa:22`[cite: 2] | LED & Resistor: `GPIO 4`[cite: 2] | Service: `2b92513e-afed-40ac-afa6-e54c63acdceb`<br>Char: `ea3d7c32-0013-4447-8f7b-47b959b5cddc`[cite: 2] |
| **Slave 2** | ESP32 DevKitC | `3c:8a:1f:a3:59:e2`[cite: 1] | LED & Resistor: `GPIO 4`[cite: 1] | Service: `2b92513e-afed-40ac-afa6-e54c63acdcec`<br>Char: `ea3d7c32-0013-4447-8f7b-47b959b5cddc`[cite: 1] |

---

## 🔍 Part 2: MAC Address Finder Sketch
To resolve connectivity issues and target specific devices during multi-client scanning, each board's Bluetooth address was retrieved using this script:

```cpp
#include <Arduino.h>
#include <BLEDevice.h>

void setup() {
  Serial.begin(115200);
  BLEDevice::init("MAC_Checker");
  Serial.println("Bluetooth initialized!");
  Serial.print("Device MAC Address: ");
  Serial.println(BLEDevice::getAddress().toString().c_str());
}

void loop() {
  delay(2000);
}
```

## 🎥 Demonstration Video
* **Video File:** [Watch the System Operation Video](documentation/demo_video.md)
