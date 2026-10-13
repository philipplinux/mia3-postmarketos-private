# Mi A3 (laurel_sprout): firmware, stock images, vendor sources

Companion to [mia3-postmarketos](https://github.com/philipplinux/mia3-postmarketos): the third-party files that repo needs but
doesn't ship. Kept here for reference and for restoring a phone.

## Not my work, no licence granted

Everything here belongs to its owners: Qualcomm, Xiaomi, Maxim Integrated, the kernel GPL authors, and the Nura project (logo). I claim no rights and
add no licence. The firmware and stock images are as dumped from my own phone. The vendor sources stay GPL-2.0 as published.
If you are a rights holder and want something removed, open an issue.

## What and where from

| Folder | What | Source |
|---|---|---|
| `firmware/` | `/lib/firmware` tree as on the phone: modem, ADSP, CDSP, Wi-Fi (`bdwlan.*`, ath10k `board-2.bin`), GPU zap shader, Bluetooth (`qca/`) | stock Android 11 (security patch 2022-08-01) `modem_a` / `vendor_a` / `bluetooth_a`, extracted with [`firmware/extract-firmware.sh`](https://github.com/philipplinux/mia3-postmarketos/blob/main/firmware/extract-firmware.sh) |
| `stock/images/` | stock `boot_a.img`, `dtbo_a.img`, `bt_a.img` (bluetooth_a) | the same phone's slot a partitions |
| `stock/dt/` | decompiled stock device trees: `b_*.dts` (boot dtbs), `dtbo_a_*.dts` (overlays; speaker amp and battery profile live here) | `boot_a.img` / `dtbo_a.img` with `dtc -I dtb -O dts` |
| `stock/btfw/` | Bluetooth firmware as extracted | `bt_a.img` |
| `vendor-src/max98937.c/.h` | Xiaomi's MAX98937 amp driver (GPL-2.0), register reference for `audio/max98937-init.sh` | [LineageOS android_kernel_xiaomi_sdm660 @ 49688d8](https://github.com/LineageOS/android_kernel_xiaomi_sdm660/blob/49688d8750f2fca28271f936cfcfec5d97c0d7a4/techpack/audio/asoc/codecs/max98937.c) |
| `vendor-src/max98927.c/.h` | Xiaomi's MAX98927 driver (GPL-2.0) | [xiaomi-msm8953-devs android_kernel_xiaomi_msm8953 @ dcaf331](https://github.com/xiaomi-msm8953-devs/android_kernel_xiaomi_msm8953/blob/dcaf331bd84a5faf23b8641ff195e4833a5c47bc/techpack/audio/titanium/asoc/codecs/max98927.c) |
| `media/nura-logo.png` | Nura (formerly postmarketOS) logo, rendered to PNG for forum posts | [postmarketos.org/static/img/2026-09/logo-new.svg](https://postmarketos.org/static/img/2026-09/logo-new.svg), © the Nura project |

## Use

Check this repo out next to mia3-postmarketos: its `deploy.sh` copies `firmware/` to the phone with `cp -an` (never
overwrites). By hand: `sudo cp -a firmware/. /lib/firmware/`.
