# Rev.J Architecture Freeze

```text
                 RP2040-Zero footprint
                         │
                    ┌────┴────┐
 USB-C ── ESD ─────▶│  IO PCB │◀── 6P Trackball
                    │  Power  │
                    └────┬────┘
                         │ 24P FFC
             20 GPIO + USB + debug + TB + GND
                         │
                    ┌────┴────┐
                    │ BLE Core│
                    │ MDBT50Q │── extra GPIO expansion
                    └─────────┘
```

### Design rule
The 20 legacy GPIOs are never multiplexed. They remain 1:1 from the original RP2040-Zero connector to the nRF52840. Added peripherals use dedicated Core GPIOs.

### Trackball
The IO-board 6P connector is carried on dedicated FFC lines TB1..TB6 and therefore does not consume any of the 20 legacy keyboard GPIOs. This is the key architectural change from Rev.I.

### FFC
24P is the final host interconnect. It carries the 20 legacy GPIOs plus 3V3, GND, VSYS and USB_VBUS. TB1..TB6 remain dedicated BLE-core expansion lines and are not part of the RP2040-Zero host FFC.


## Rev.Q mechanical correction
- IO board: 18.0 x 23.5 mm.
- RP2040-Zero 23 edge pads are mapped by the actual physical edge layout, not by the schematic P1 numbering order: left edge = 5V/VSYS, GND, 3V3, GPIO29, GPIO28, GPIO27, GPIO26, GPIO15, GPIO14; bottom edge = GPIO13..GPIO8; right edge = GPIO0..GPIO7.
- Pad centers follow the published 18.00 x 23.50 mm drawing: side X=1.38 / 16.62, first side Y=1.59, 2.54 mm pitch; bottom Y=22.12 with X=1.38..14.08 at 2.54 mm pitch.
- THT hole 0.80 mm, pad 1.60 mm.
- FFC changed to Hirose FH34SRJ-24S-0.5SH(50), 24 positions, 14.0 x 3.8 mm, placed on F.Cu on the USB-connector side.
- FFC pins 1-20 = GPIO0..GPIO15/GPIO26..GPIO29; 21=3V3, 22=GND, 23=VSYS, 24=USB_VBUS.
