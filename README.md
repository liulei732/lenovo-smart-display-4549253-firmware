# Lenovo Smart Display firmware 4549253 — firmware-only archive

Provided for the firmware-archiving request in [LANovo issue #12](https://github.com/ygelfand/LANovo/issues/12#issuecomment-6863772688).

## Build identification

- Android 7.0, API 24, userdebug, test-keys.
- Incremental build: `4549253`; Android Things: `0.4.5-N`.
- Kernel: `3.18.48-perf-g50fcc55df39`.
- Userspace: `armeabi-v7a` / `zygote32`.
- Fingerprint: `Things/iot_msm8x53_som/msm8x53_som:7.0/NYC/4549253:userdebug/test-keys`.
- Existing OEM software reports `amber`. Physical board/panel identity has not been independently confirmed, so this archive is not asserted to be a validated flash package for a particular screen size.

## Contents

The ZIP contains original, unmodified images from an explicit firmware-only selection: boot, system, vendor, OEM, SBL, aboot, RPM, TrustZone, devcfg, common library, Keymaster firmware, lksecapp firmware, OEM bootloader, DSP, modem firmware, Bluetooth firmware, vbmeta, and DRM firmware.

Identical A/B pairs are represented by the A image, with both original slot names and their equality recorded in `manifest.json`. Bluetooth A and B differ and are both included. This is 19 image files representing 18 firmware components.

`partition-layout.tsv` provides partition names, offsets and sizes only. `manifest.json` and `SHA256SUMS` provide image sizes and SHA-256 checksums. The archive itself has a separate `.sha256` file.

## Exclusions and review scope

No `userdata`, `persist`, `devinfo`, `factory`, `factory_bootloader`, `keystore`, `config`, `misc`, `modemst1`, `modemst2`, `fsg`, `fsc`, `ssd`, `DDR`, `sec`, `limits`, `dip`, `syscfg`, `mcfg`, `apdp`, `msadp`, or `dpo` images are included. No raw GPT, full-disk image, diagnostic logs, local recovery manifest, disk/partition GUIDs, or private audit report is included.

Local checks compared each included image with its previously verified export checksum; checked firmware pairs for equality; searched the selected images for recorded device/network identifiers and PEM private-key material; inventoried filesystem files; and inspected 103 APK/JAR archives for private-key files/material and OAuth token candidates. These checks found no selected-identifier or secret-material matches. The stock Wi-Fi configuration has no active network blocks or credential assignments. This review is bounded and is not a guarantee that every possible form of embedded data has been identified.

## Intended use

This is an archival/research selection, **not a complete recovery bundle or a tested installation package**. It includes no flashing scripts. Private/calibration/state partitions and the original GPT are deliberately omitted. Cross-device restoration and upgrades from this build have not been validated.

Firmware ownership and copyright remain with the respective rights holders. No new license over third-party firmware is asserted.
