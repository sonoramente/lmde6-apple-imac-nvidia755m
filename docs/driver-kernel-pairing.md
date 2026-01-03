# Driver + Kernel Pairing (Verified)

This document records the **exact, working kernel and NVIDIA driver pairing**
used on Apple iMac systems with the NVIDIA GeForce GT 755M (Kepler / GK107).

---

## Kernel

- **Kernel release:** 6.1.0-12-amd64
- **Distribution:** LMDE 6 (Debian 12 / bookworm base)
- **Boot mode:** UEFI (Apple EFI)

Evidence:
- `logs/pre-driver-kernel-release.txt`
- `logs/post-driver-uname.txt`

---

## NVIDIA Driver

- **Driver branch:** NVIDIA Tesla (Legacy)
- **Driver version:** 470.256.02
- **Debian package:** `nvidia-tesla-470-driver`
- **CUDA version:** 11.4

Evidence:
- `logs/post-driver-nvidia-smi.txt`
- `logs/post-driver-nvidia-module.txt`
- `logs/post-driver-nvidia-packages.txt`

---

## DKMS Status

The NVIDIA kernel module is built via DKMS against the running kernel:

nvidia-tesla-470/470.256.02, 6.1.0-12-amd64, x86_64: installed


This confirms:
- no ABI mismatch
- automatic rebuilds on future kernel updates

Evidence:
- `logs/post-driver-dkms-status.txt`

---

## Xorg Behavior

At Xorg startup:

- NVIDIA is selected as the primary driver
- nouveau is detected but **explicitly unloaded**
- Display mode is set using `nvidia-auto-select`
- VDPAU acceleration is enabled

Key log indicators:
- `UnloadModule: "nouveau"`
- `VDPAU driver: nvidia`

Evidence:
- `logs/post-driver-xorg-driver.txt`

---

## Conclusion

This pairing is **stable, supported, and reproducible**.

On LMDE 6 / Debian 12:
- Modern NVIDIA drivers (535+) **do not support Kepler**
- Debian correctly redirects to the **Tesla 470 legacy branch**
- The result is a fully accelerated, stable desktop on Apple iMac hardware

