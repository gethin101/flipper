# what flipper zero uses

| Component / Chip | Type | Frequency / Protocol | Purpose | Notes |
|------------------|------|----------------------|---------|-------|
| **ST25R3916** | NFC Reader/Writer/Emulator | 13.56 MHz | Full NFC + MIFARE support: read, write, emulate | Replaced older PN532‑style designs; supports ISO14443A/B, FeliCa, NFC-A/B/F |
| **TI CC1101** | Sub‑GHz Transceiver | 300–928 MHz (region‑dependent) | Reads, captures, transmits RF signals (garage doors, sensors, remotes) | Supports ASK, OOK, 2-FSK, 4-FSK, MSK |
| **EM4100/EM4305 Compatible LF Frontend** | Low‑Frequency RFID | 125 kHz | Reads & emulates LF tags (HID, EM4100, Indala, T5577) | LF coil antenna built into case |
| **iButton (Maxim/Dallas 1‑Wire)** | 1‑Wire Contact Reader | 1‑Wire protocol | Reads iButton keys (DS1990A, etc.) | Metal contact pad on top |
| **Infrared Transceiver (IR LED + Receiver)** | IR TX/RX | 38 kHz typical | Learns & transmits IR remote codes | TV, AC, projector control |
| **NRF52840** | Bluetooth LE MCU | 2.4 GHz BLE | BLE communication, mobile app link, HID keyboard/mouse | Also handles some internal logic |
| **STM32WB55** | Main MCU | ARM Cortex‑M4 | Runs firmware, controls all subsystems | Core of the device |
| **MicroSD Slot** | Storage | FAT32 | Stores captured signals, databases, plugins | Up to 128GB supported |
| **GPIO Pins** | Digital/Analog IO | Various | Hardware hacking, UART/SPI/I²C access | Exposed on top edge |
| **Vibro Motor** | Haptic Feedback | — | Vibration alerts | Used for UI feedback |
| **LCD Display (128×64)** | Display | SPI | UI, menus, animations | Monochrome |
| **Battery (Li‑Po 2000mAh)** | Power | — | Internal rechargeable battery | USB‑C charging |
