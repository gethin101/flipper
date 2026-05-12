# what flipper zero uses

# Flipper Zero Internal Hardware Components (Full Table)

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
