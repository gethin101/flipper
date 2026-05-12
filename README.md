# what flipper zero uses

| Component / Chip | Type | Frequency / Protocol | Technical Purpose | Plain English Explanation |
|------------------|------|----------------------|-------------------|---------------------------|
| **STM32WB55** | Main MCU (ARM Cortex‑M4) | — | Runs the firmware, manages all subsystems, controls peripherals | The "brain" of the Flipper — it runs everything and coordinates all modules |
| **NRF52840** | Bluetooth LE MCU | 2.4 GHz BLE | Handles Bluetooth communication, mobile app link, HID keyboard/mouse emulation | Lets the Flipper talk to your phone, act as a wireless keyboard, and connect to BLE devices |
| **ST25R3916** | NFC Reader/Writer/Emulator | 13.56 MHz | Full NFC stack: ISO14443A/B, FeliCa, NFC-A/B/F; reads/writes/emulates MIFARE & NTAG | The NFC powerhouse — reads cards, writes cards, and can *pretend to be* a card |
| **CC1101** | Sub‑GHz RF Transceiver | 300–928 MHz | Captures, decodes, transmits ASK/OOK/FSK/MSK signals; supports remotes, sensors, RF replay | The radio beast — records & replays garage doors, sensors, remotes, etc. |
| **125 kHz LF RFID Frontend** | Low‑Frequency RFID | 125 kHz | Reads & emulates EM4100, HID Prox, Indala, T5577 tags | Handles old‑school keyfobs — reads them and can *emulate* them |
| **Infrared Transceiver (IR LED + Receiver)** | IR TX/RX | 38 kHz typical | Learns IR codes, transmits IR signals | Works like a universal remote for TVs, AC units, projectors |
| **iButton Reader (1‑Wire)** | 1‑Wire Contact Interface | 1‑Wire protocol | Reads iButton keys (DS1990A, etc.) | Reads those metal “touch keys” used in hotels and industrial systems |
| **MicroSD Slot** | Storage | FAT32 | Stores captured RF signals, NFC dumps, plugins, databases | Lets you save huge amounts of data — RF captures, NFC files, scripts |
| **GPIO Pins** | Digital/Analog IO | UART/SPI/I²C | Hardware hacking, debugging, connecting external modules | Lets you hook the Flipper to other electronics like sensors or microcontrollers |
| **LCD Display (128×64)** | Display | SPI | UI rendering, menus, animations | The screen you use to navigate everything |
| **Vibration Motor** | Haptic Feedback | — | Provides vibration alerts and UI feedback | Makes the Flipper buzz when something happens |
| **Li‑Po Battery (2000 mAh)** | Power | — | Internal rechargeable power source | Keeps the Flipper running for hours; charges via USB‑C |
| **USB‑C Port** | Data + Charging | USB HID, Serial | Charging, firmware updates, USB keyboard/mouse emulation | Lets you plug into a PC, charge, or act as a USB device |

<img width="495" height="419" alt="image" src="https://github.com/user-attachments/assets/e020c096-45ee-444b-bc78-ef7c77574b3f" />

# My components atm (breakouts):


| Subsystem        | Part / Approach                         | Purpose                                      | Notes |
|------------------|------------------------------------------|----------------------------------------------|-------|
| Main MCU         | ESP32‑S3 dev board                      | Core brain, Wi‑Fi + BLE built‑in             | Mounted as a module on custom PCB |
| Display          | 1.3" 128×64 OLED (SSD1306, SPI)         | UI, menus, icons                             | Header footprint on PCB, placed near top front |
| Buttons          | 5‑way D‑pad + separate Back button      | Navigation + actions                         | Tactile switches on PCB (UP/DOWN/LEFT/RIGHT/SELECT + BACK) |
| IR (TX/RX)       | IR LED + IR receiver (discrete parts)   | Learn + send remote codes                    | At PCB edge, aligned with front case “window” |
| NFC (basic)      | PN532 breakout                          | NFC read/write/emulate (basic)               | 8‑pin header footprint; antenna side near case front |
| NFC (advanced)   | ST25R3916 breakout (future option)      | Stronger NFC + advanced emulation            | Optional header footprint for v2 |
| LF RFID (125 kHz)| EM4100/T5577 breakout + coil            | Read + emulate old keyfobs                   | Space for module + coil near case surface |
| Sub‑GHz RF       | CC1101 breakout + wire antenna          | Capture/replay 300–928 MHz remotes           | Wire antenna from PCB edge; optional SMA footprint later |
| MicroSD          | MicroSD SPI breakout                    | Store captures, configs, logs                | Short SPI traces to ESP32 |
| Battery          | 1‑cell Li‑Po (≈1200–2000 mAh)           | Portable power                               | JST‑PH connector on PCB |
| Charging         | TP4056 breakout (separate USB)          | Li‑Po charging                               | Own USB port; simple wiring |
| Power regulation | 3.3 V LDO / buck (if needed)            | Stable 3.3 V for ESP32 + modules             | Or rely on ESP32 board’s regulator if adequate |
| PCB              | Custom PCB                              | Mounts all breakouts + buttons               | Includes headers, pads, mounting holes |
| Case             | 3D‑printed shell + clear window         | Protects hardware, makes it pocketable       | Opaque PLA body, transparent/smoked PLA or acrylic over screen/IR |

## Mechanical / case notes

| Area      | Material / Idea                          | Purpose                          | Notes |
|-----------|-------------------------------------------|----------------------------------|-------|
| Screen    | Transparent or smoked PLA / acrylic      | View OLED clearly                | Thin panel, flush with case front |
| IR area   | Smoked / translucent PLA or acrylic      | Let IR pass through              | Same look as TV remote front |
| Antennas  | Under plain plastic (no metal nearby)    | NFC / LF / Sub‑GHz performance   | Keep plastic thin above antennas |
| Mounting  | PCB mounting holes + case standoffs      | Secure PCB inside case           | 2–4 holes near corners/modules |
| USB ports | Rectangular cutouts in case              | Access ESP32 + TP4056 USB ports  | Align with PCB edge connectors |
| Buttons   | Holes or caps over tact switches         | User input                       | D‑pad cluster + Back button area |



