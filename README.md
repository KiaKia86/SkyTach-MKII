# *HA818I*

### A high-performance custom rocket designed entirely from scratch, using a 4-layer avionics PCB, custom airframe, and custom solid motor. The rocket is expected to reach **12,000 ft (≈3657.6 m)** at **Mach 0.6**, powered by a **385 N thrust** motor.

### The airframe is constructed with lightweight composite sections reinforced with fiberglass cloth and resin. The rocket includes 2 pyro channels, offering flexibility for multiple deployments and different control configurations.

### The avionics is built on a 4-layer PCB with one microcontroller (ESP32-S3) working to process flight data and transmit telemetry via LoRa to the ground station. The board includes multiple sensors to track acceleration, rotation, altitude, and GPS position.

<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/2bd81f1c-375b-4b6f-9b1b-cd065cfa8e5e" />

---

# Bill of Materials (BOM) (FOR Hack Club!!!)

| **Category** | **Item** | **Est. Price**  | **Purchase Link** |
|--------------|----------|-------------|----------------|
| Structure | Fiberglass Cloth (6oz) | $21.99  | https://www.amazon.com/Fiberglass-Fabric-Glass-Repair-Surfboard/dp/B0DN5FFPSV |
| Structure | Fiberglass Cloth (4oz) | $42.99 | https://www.amazon.com/YIQUEDOK-Fiberglass-48-75-Sq-Ft-Surfboard-Repair/dp/B0F74917P7 |
| Structure | Econostitch Peel (5 yards) | $29.95  | https://www.amazon.com/Fibre-Glast-Econostitch-Package-Visible/dp/B07DP3PNPJ |
| Structure | TotalBoat 5:1 Marine Epoxy | $68.99 | https://www.amazon.com/TotalBoat-Epoxy-Quart-Fast-Hardener/dp/B00HR85152 |
| Structure | Primer | $7.97 | https://www.amazon.com/Rust-Oleum-Automotive-260510-12-Ounce-Sandable/dp/B006ZLQ4HQ |
| Structure | Paint | $6.19 | https://www.amazon.com/Rust-Oleum-249127-Painters-Purpose-12-Ounce/dp/B002BWOS7Q |
| Structure | Plastic Drop Cloth | $9.47  | https://www.amazon.com/Plastic-Drop-Cloths-6-Pack-Disposable/dp/B0DQDWV1SV |
| Recovery | Parachute (36 inch) | $18.69 | https://www.apogeerockets.com/Building-Supplies/Parachutes/Larger-than-24in/36in-Printed-Nylon-Parachute/Review?reviews_id=7759 |
| Recovery | Kevlar Shock Cord | $40.69  | https://www.apogeerockets.com/Building-Supplies/Shock-Cord/Kevlar-Shock-Cord-4500-20-feet-long-3-loops |
| Structure | Bulkheads | $41.24  | N/A Custom Quote (Merchandise fee is waived, only shipping cost)  |
| Avionics | PCBA Shipping Cost | $42.22 | N/A Custom Quote (Merchandise fee is waived, only shipping cost) |
| Avionics | 433Mhz Antenna | $9.99  | https://www.amazon.com/dp/B0FB3MDJG1?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1 |
| Avionics | High Gain GPS Antenna | $12.79  | https://www.amazon.com/dp/B0B2NGKCY1?ref=ppx_yo2ov_dt_b_fed_asin_title |
| Avionics | 2.4Ghz Antenna | $8.99 | https://www.amazon.com/dp/B099R3GR91/?th=1 |

**Total Estimated Cost: $362.16**

**Note:**
The PCB cost is not included in the bom, as it is funded by an external source (JLCPCB). Filament and other materials on hand are not considered either!

---

### PCB Overview

The **4-layer PCB** serves as the core of the HA818I flight computer.  
It uses:
- **ESP32-S3** (Telemetry, communication, logging, and sensor data)  
- **LoRa radio module** for long-range ground communication  
- Multiple onboard sensors: **IMU**, **barometer**, **magnetometer**, **GPS**, and **accelerometer**  
- **Two pyro channels** for deployment   

The avionics system is designed for flexibility, allowing reuse across future rocket designs.

<img width="1844" height="907" alt="image" src="https://github.com/user-attachments/assets/f1f22f82-1174-4a93-b876-05d8aba43008" />
<img width="1834" height="903" alt="image" src="https://github.com/user-attachments/assets/71b2364a-e897-47ec-a06d-d9ac346abbb9" />

---

### Why Did I Make This Rocket?

I've wanted to design something that combines all of my passions into one project, and this is it. HA818I represents months of hard work, simulation, and testing. Everything I learned about propulsion, control, and flight dynamics has been combined into a single rocket! 

---

# Physical Build
Pictures are being edited!

# Sponsors

<div align="center">

## Proudly Sponsored By

<table>
  <tr>
    <td align="center" width="50%">
      <a href="https://jlcpcb.com" target="_blank">
        <img src="https://github.com/user-attachments/assets/c9b44859-d24b-48ba-b1d5-8fd29674d73d" alt="JLCPCB" width="400"/>
      </a>
    </td>
    <td align="center" width="50%">
      <a href="https://oshwlab.com/explore" target="_blank" rel="noopener noreferrer">
        <img src="https://github.com/user-attachments/assets/232753ed-b258-49bf-9159-06be05e877c1" alt="OSHWLab" width="400"/>
      </a>
    </td>
  </tr>
</table>

This project is made possible by the generous support of **JLCPCB** and **OSHWLab**. Their commitment to the open hardware community and maker ecosystem enables innovative projects like this to come to life.

</div>

---
