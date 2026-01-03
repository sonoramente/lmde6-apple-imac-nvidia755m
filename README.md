# lmde6-apple-imac-nvidia755m

This repository documents a **tested, working installation of Linux Mint Debian Edition 6 (LMDE 6)** on an **Apple iMac** equipped with an **Intel i5 CPU and NVIDIA GeForce GT 755M GPU**.

The goal of this project is to provide **repeatable, documented steps** and configuration notes for running LMDE 6 reliably on this Apple hardware.

---

## Hardware Tested

- **Model:** Apple iMac (Late 2013 – A1419)
- **CPU:** Intel Core i5
- **GPU:** NVIDIA GeForce GT 755M
- **Firmware:** Apple EFI (UEFI)
- **Storage:** SATA SSD
- **Display:** Internal Retina / Thunderbolt Display (tested)

---

## Operating System

- **Distribution:** Linux Mint Debian Edition
- **Version:** LMDE 6 (Faye)
- **Desktop:** Cinnamon
- **Kernel:** Stock LMDE kernel (with NVIDIA proprietary driver)

---

## What Works

- NVIDIA proprietary driver (755M)
- Hardware acceleration
- Internal display brightness
- External Thunderbolt display
- Audio
- Networking (Ethernet / Wi-Fi)
- Sleep / resume (tested)

---

## Repository Structure (planned)

```text
.
├── install/        # Installation steps
├── hardware/       # Hardware notes and quirks
├── configs/        # GRUB, Xorg, driver configs
├── logs/           # Relevant dmesg / system logs
└── README.md

