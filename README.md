# Mi A3 (laurel_sprout) — non-redistributable files (PRIVATE)

Companion to [mia3-postmarketos](https://github.com/philipplinux/mia3-postmarketos). Proprietary or copyrighted
files that the public-ready repo must not contain. Keep this repo private.

| Folder | What | Source |
|---|---|---|
| `firmware/` | `/lib/firmware` tree as on the phone: modem, ADSP, CDSP, Wi-Fi (`bdwlan.*`, ath10k `board-2.bin`), GPU zap shader, Bluetooth (`qca/`) | stock `modem_a` / `vendor_a` / `bluetooth_a` via `firmware/extract-firmware.sh` |
| `stock/images/` | stock `boot_a.img`, `dtbo_a.img`, `bluetooth_a` image (slot a = stock Android) | phone partitions |
| `stock/dt/` | decompiled stock dtbo / dtb overlays (`spkamp@3a` etc. in `dtbo_a_10.dts`) | `dtbo_a.img` |
| `stock/btfw/` | Bluetooth firmware as extracted | `bluetooth_a` |
| `vendor-src/` | Xiaomi kernel `max98937.c/.h` (GPL, LineageOS sdm660 49688d87, `techpack/audio/asoc/codecs`), `max98927.c/.h` (msm8953-devs); register reference for `audio/max98937-init.sh` | GitHub |

Restore firmware on a fresh install: `sudo cp -a firmware/. /lib/firmware/`.
Firmware © Qualcomm / Xiaomi.
