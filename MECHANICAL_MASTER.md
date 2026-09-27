# RP2040-Zero BLE I/O — Rev.W

## Mechanical master
The 23 exposed RP2040-Zero THT connection positions are derived from the supplied third-party footprint:
`is-watering/isw-kbd-lib/footprints/isw-kbd.pretty/RP2040-Zero-THT.kicad_mod`

This is used as the **mechanical/pad master**, not claimed as an official Waveshare PCB source.

Board outline: **18.0 × 23.5 mm**.

The pad geometry preserves the characteristic RP2040-Zero THT/castellation arrangement:
- right: GPIO0–8
- top: GPIO9–13
- left: GPIO14, GPIO15, GPIO26–29, 3V3, GND, VSYS
- 0.85 mm drill
- 0.50 mm inward drill offset relative to the pad center, reproducing the footprint's inner-hole/castellation geometry

## I/O architecture
- RP2040, flash, regulator and LED are intentionally removed.
- USB-C remains on the original-side area.
- BOOT and RESET remain on the same surface.
- 24P Hirose FH34SRJ-24S-0.5SH(50) footprint is on B.Cu; the mating BLE CORE uses the matching 24P host connector.
- FFC is inside the 18 × 23.5 mm outline.
- Separate BLE core target: Raytac MDBT50Q-1MV2.

## FFC mapping
See `PINMAP.csv`.

## Important validation note
KiCad PCBNew/DRC is not installed in the generation environment, so this revision has been syntactically checked and coordinate-checked but has **not** been claimed as KiCad DRC/3D-verified.
