# RP2040-Zero BLE I/O Rev.W

Fresh mechanical-master revision for the RP2040-Zero BLE adapter concept.

- 18 × 23.5 mm
- RP2040-Zero THT/castellation geometry from the supplied master footprint
- USB-C + BOOT + RESET on F.Cu side
- 24P FFC on B.Cu side
- MDBT50Q-1MV2 is a separate core board
- FFC 1–20 = GPIO0–15, GPIO26–29
- FFC 21 = 3V3
- FFC 22 = GND
- FFC 23 = VSYS
- FFC 24 = USB_VBUS

This is the clean mechanical/electrical-interface baseline. PCB routing is intentionally kept separate from the mechanical master so it does not silently corrupt the reference geometry.
