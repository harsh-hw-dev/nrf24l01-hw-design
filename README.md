# nRF24L01+ Hardware Design (2.4 GHz RF Board)

Professional hardware design of a **2.4 GHz nRF24L01+ RF transceiver** module with
proper power integrity, SPI interface, crystal network, RF matching, and antenna layout.

This project focuses on **real-world RF hardware practices**, not breakout-board shortcuts.

---

## 🔧 Features

- nRF24L01+ 2.4 GHz ISM band transceiver
- SPI interface (MOSI, MISO, SCK, CSN, CE)
- External 16 MHz crystal with load capacitors
- Dedicated analog and digital supply filtering
- RF π-matching network
- Controlled impedance RF trace
- PCB antenna / external antenna support
- EMI-aware grounding and decoupling

---

## 🧩 Schematic Highlights

### Power Supply
- Separate decoupling for VDD and VDD_PA
- Local 100 nF + bulk capacitor placement
- Short return paths to ground

### Crystal Oscillator
- 16 MHz crystal
- Symmetric routing
- Load capacitors placed close to IC pins
- No ground plane under crystal traces

### SPI Interface
- 4-wire SPI + CE interrupt control
- Series damping optional for high-speed SPI
- Compatible with STM32 / ESP32 / Arduino

---

## 📡 RF Design Details

- π matching network (L-C-L) between ANT1/ANT2 and antenna
- Impedance tuned for 50 Ω system
- RF trace length minimized
- Continuous ground reference under RF path
- Via stitching around RF section

---

## 📐 PCB Design Guidelines Followed

- Solid ground plane
- RF section isolated from digital noise
- No high-speed signals crossing RF area
- Antenna keep-out zone
- Decoupling capacitors <2 mm from VDD pins

---

## 🧪 Bring-Up Checklist

- Verify 3.3 V rail stability (TX burst current!)
- Check crystal oscillation at 16 MHz
- SPI ID read test
- RF TX power test
- Packet RX/TX validation

---

## 🧾 Tools Used

- Schematic: Altium Designer
- PCB: 2-layer / 4-layer (RF optimized)
- Simulation: Hand-calculated RF matching
- Target MCU: STM32 / ESP32

---

## 📌 Applications

- Wireless sensor nodes
- IoT devices
- Remote controllers
- Telemetry systems
- Low-power RF communication

---

## ⚠️ Disclaimer

This design is for **educational and professional evaluation purposes**.
RF performance depends heavily on PCB stackup and antenna tuning.

---

## 👤 Author

**Harsh Saini**  
Hardware Design Engineer  
📧 saini.harsh.in@gmail.com  
🔗 https://www.linkedin.com/in/sainiharsh-in/
