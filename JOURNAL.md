# Rocket Flight Computer (Journal)

## BOM Optimization & Documentation  
**Week 3 (12/16/2025) – 8 Hours**

### Days Worked
- **Monday:** 2 hours  
- **Tuesday:** 1 hour  
- **Wednesday:** 2 hours  
- **Thursday:** 2 hours  
- **Friday:** 1 hour  

### BOM and Sourcing
- Created the full BOM with all **LCSC part numbers** (via JLC).
- Reduced cost by selecting **older resistor and capacitor versions** where possible.
- Checked **availability** for all components.
- Calculated **total cost**, including **PCB assembly**.
<img width="1518" height="663" alt="image" src="https://github.com/user-attachments/assets/af562b38-bcc2-4e44-a1fe-80e0eb2bcd1f" />

### Documentation
- Generated **Gerbers**, **BOM**, **pick-and-place**, and all exportable fabrication files.
- Created a spreadsheet mapping **ESP32 GPIO assignments**.
- Documented **I²C addresses** and **pin usage** for each module.
- Exported a **clean schematic PDF** with net labels for debugging.
<img width="1869" height="604" alt="image" src="https://github.com/user-attachments/assets/3ae12cf6-a746-41bd-ac40-8ab939908031" />

### Final Checks
- Verified all **power rails** can handle required amperage.
- Checked all **data connections** for correctness and interference.
- Verified **MOSFET type** and **gate drive voltage** (N-channel).
- Confirmed **FRAM** wiring.
- Double-checked **LoRa** connections.

### Software
- Selected **VS Code** and **Arduino IDE** for development.
- Located and validated all required **libraries**.
- Began researching **sensor fusion filters** (e.g., Kalman filter).
- Researched **E22 LoRa module** operation and coding approach.

## PCB Layout & Routing  
**Week 2 (12/09/2025) – 10 Hours**

### Days Worked
- **Monday:** 2 hours  
- **Tuesday:** 3 hours  
- **Wednesday:** 2 hours  
- **Thursday:** 2 hours  
- **Friday:** 1 hour  

### Power Block / System Layout
- Researched **LM61495** and followed recommended placement.
- Placed LM61495 near the **XT60 connector** on the right side.
- Positioned **2.7 µH inductor** at the switching node; minimized loop area to reduce EMI.
- Placed **five 22 µF input capacitors** close to VIN.
- Calculated **trace widths** for a **2 A draw**.
- Positioned **AP2114H** centrally for sensor access.
<img width="203" height="485" alt="image" src="https://github.com/user-attachments/assets/aec10269-3b3a-45a4-979a-4e9a79d4eba7" />

### Sensor Block / System Layout
- Placed sensors close to the **ESP32**, prioritizing pin proximity.
- Positioned **BMP390** near the board edge.
- Aligned **both IMUs** to match the rocket’s coordinate system.
- Kept the **magnetometer** at least **15 mm** from high-current paths.
- Routed **I²C lines** as short as possible.
- Added **100 nF decoupling capacitors**.
<img width="113" height="145" alt="image" src="https://github.com/user-attachments/assets/141c6e4c-49a3-4e18-8476-33dc68a2979b" />
<img width="224" height="346" alt="image" src="https://github.com/user-attachments/assets/d7257212-4761-4aa0-8645-5bc2c5a18049" />

### MCU and Memory Block / System Layout
- Placed **ESP32 module** bottom-left with **USB-C** on the edge.
- Ensured **BOOT** and **RESET** buttons are accessible.
- Routed **USB D+ / D−** as a differential pair.
- Placed **FRAM** near the ESP32 to minimize SPI trace length.
- Routed all **SPI signals**.
<img width="171" height="211" alt="image" src="https://github.com/user-attachments/assets/82ed49a5-36f4-42fc-a656-0308ea331131" />
<img width="450" height="736" alt="image" src="https://github.com/user-attachments/assets/ef1b4990-32b8-4a1e-87b9-1953fe950878" />

### Communication Systems Layout
- Placed **GPS module** top-right with antenna clearance.
- Routed **GPS UART** away from the switching regulator.
- Added **U.FL connector** on the edge.
- Positioned **LoRa module** on the opposite side from GPS.
<img width="331" height="366" alt="image" src="https://github.com/user-attachments/assets/98f94ffc-85a1-4b4a-84be-2ac4ee6d57b0" />
<img width="495" height="830" alt="image" src="https://github.com/user-attachments/assets/00fcb739-5755-44a6-8145-3fc6c7213e49" />

### Pyro Channels Layout
- Placed **MOSFETs** near screw terminals at the bottom edge.
- Used **wide traces** for pyro current paths.
- Isolated the **pyro section** to reduce sensor interference.
<img width="519" height="241" alt="image" src="https://github.com/user-attachments/assets/ec8dd438-2783-40d8-8b77-f79524b208a9" />

### Full Layout
<img width="441" height="855" alt="image" src="https://github.com/user-attachments/assets/694c95f1-e2eb-4545-9e9c-84d342a42308" />

## Schematic Design & Component Selection  
**Week 1 (12/02/2025) – 8 Hours**

### Days Worked
- **Monday:** 2 hours  
- **Tuesday:** 1 hour  
- **Wednesday:** 2 hours  
- **Thursday:** 2 hours  
- **Friday:** 1 hour  

### Power Block / System
- Designed schematic for **LM61495 buck converter**.
- Ensured regulator outputs support all sensors/modules/LoRa.
- Selected **2.7 µH inductor (XAL7030-272MEC)** using TI’s calculator for **5 V** output (LoRa).
- Added **input capacitors (22 µF ×5)** and **output capacitors (10 µF ×2)** per datasheet.
- Added **AP2114H-3.3 LDO** for the **3.3 V sensor rail** (~1 A capacity).
<img width="758" height="536" alt="image" src="https://github.com/user-attachments/assets/d008038a-93d5-4e0d-a233-f62685a573b0" />

### Sensor Block / System
- Selected sensors:
  - **BMP390** barometer (altitude up to 30 km)
  - **H3LIS331DLTR** high-G accelerometer (400 g)
  - **IAM-20680HT** 6-axis IMU
  - **LIS3MDLTR** magnetometer
  - **AHT20** temperature sensor
- Added **I²C bus** and **pull-up resistors**.
<img width="378" height="204" alt="image" src="https://github.com/user-attachments/assets/46d29572-103a-4b0c-925b-eff1573f1816" />
<img width="879" height="230" alt="image" src="https://github.com/user-attachments/assets/400005f7-84cd-47b4-bc9c-e7fad1e12297" />
<img width="918" height="208" alt="image" src="https://github.com/user-attachments/assets/ddb38661-eee4-42e3-bb5b-ba639381bb33" />

### MCU and Memory Block / System
- Selected **ESP32-S3-WROOM-1U** with BOOT/RESET.
- Added **USB-C connector** with **ESD protection**.
- Included programming buttons with **10 kΩ pull-ups**.
- Added **FRAM (CY15B104Q-SXI, 4 Mbit)**.
<img width="636" height="364" alt="image" src="https://github.com/user-attachments/assets/5d9b2411-9de6-49c2-99d2-b0d11b8b6e01" />
<img width="1412" height="534" alt="image" src="https://github.com/user-attachments/assets/69fbb265-990c-4bcc-9d0a-2fd5f0c71328" />


### Communication Systems (LoRa-based)
- Added **MAX-M8Q GPS** with **U.FL connector** (external antenna).
- Selected **E22-400T37S LoRa module** (high power consumption).
- Integrated both into the schematic.
<img width="523" height="392" alt="image" src="https://github.com/user-attachments/assets/2aeb2518-8bf0-4935-9631-dc1f80025124" />
<img width="745" height="281" alt="image" src="https://github.com/user-attachments/assets/b62cf967-976b-4bce-a84b-12ccfa674b02" />

### Pyro Channels (2x)
- Designed **two MOSFET-driven pyro channels** using **SI7232DN (N-channel)**.
- Added **screw terminals** for e-matches.
<img width="937" height="491" alt="image" src="https://github.com/user-attachments/assets/b2fec560-c331-49b5-9c31-ddf37ffce766" />

### Full Schematic
<img width="1187" height="808" alt="image" src="https://github.com/user-attachments/assets/fa639e0f-8b6e-4926-ad64-530787102239" />
