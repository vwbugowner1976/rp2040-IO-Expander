# RP2040-Zero mechanical interface validation — Rev.J

The IO board uses an 18.0 x 23.5 mm board outline and a 23-pad edge interface matching the Waveshare RP2040-Zero pin layout.

Reference checks:
- Waveshare RP2040-Zero official documentation: 23-pin edge header, GPIO0..15, GPIO26..29, 3V3, GND, VSYS.
- Published KiCad community footprint geometry: side pad centers at x=2.54/17.78 mm, 2.54 mm pitch; five bottom pads at x=5.08..15.24 mm; overall mechanical reference approximately 18 x 23.5 mm.

Important: the community footprint itself carries a warning that it may be incorrect. Therefore it is treated as a geometry cross-check only; the official Waveshare pinout/documentation is the authority for signal numbering.

Rev.J no longer uses the previous generic 0.45 x 1.2 mm placeholder pads. The interface pads are edge-style 2.60 x 1.60 mm side lands and 1.60 x 2.60 mm bottom lands, positioned at the published 2.54 mm pitch locations.

## Rev.J follow-up mechanical correction

- RP2040-Zero interface pads 1-23 are now plated through-hole pads for 0.9 mm drill / 1.8 mm finished pad, preserving the existing pad centers and nets so standard 2.54 mm console/pogo/through-hole access can be used.
- The 40P FH34SRJ connector is now oriented vertically. Its 0.5 mm-pitch contact row runs along the 23.5 mm board dimension, keeping the connector envelope within the 18.0 x 23.5 mm PCB outline.
- The 40P pin-to-net mapping is unchanged from PINMAP.csv.
- Final fabrication clearance still requires verification against the exact HRS mechanical drawing and the physical RP2040-Zero mating arrangement.


## Rev.M mechanical correction
- RP2040-Zero interface corrected to the physical perimeter arrangement: 9 pads per long side plus 5 pads on the USB-opposite end.
- All 23 interface pads remain plated through-holes, 0.9 mm drill / 1.8 mm pad, with original logical nets preserved.
- FFC footprint remains vertical and was moved inward so the modeled connector envelope is inside the 18 x 23.5 mm board outline.
- This is a layout correction; exact HRS mechanical drawing and final KiCad DRC still require verification before fabrication.


## Rev.M follow-up
- RP2040-Zero 23-pad perimeter geometry corrected to the documented physical arrangement: 9 pads per long side plus 5 pads on the USB-opposite end, 2.54 mm pitch.
- Added the missing TYPE-C-31-M-12 USB-C receptacle footprint at the top edge.
- Moved the 40P FH34SRJ connector to the B.Cu side and inside the 18 x 23.5 mm outline; the simplified envelope is 4 x 21 mm after rotation.
- Final HRS/HRO mechanical drawings and KiCad DRC are still required before fabrication.


## Rev.N mechanical correction
- RP2040-Zero 23-pad edge interface was corrected using the Waveshare pad numbering/order and the measured castellated-pad geometry: 9 pads on the right edge, 5 pads on the USB-opposite short edge, and 9 pads on the left edge.
- Through-hole conversion retains the original pad-edge offsets; finished drill centers are inset from the PCB edge rather than simply placing hole centers on the old SMD pad anchors.
- Con-through / pin-header compatibility: 0.8 mm finished drill, 2.6 x 1.6 mm side pads / 1.6 x 2.6 mm short-edge pads.
- FH34SRJ-24S-0.5SH(50) is centered at x=9.0 mm, y=11.75 mm and rotated 90 degrees. The connector envelope is modeled as 22.0 x 3.8 mm, giving 0.75 mm clearance at both ends along the 23.5 mm board dimension.
- 40-pin contact row remains 0.5 mm pitch and all 40 net assignments are unchanged.
- USB-C footprint remains present on the F.Cu side.
- This is a mechanical/pin-placement correction; full KiCad DRC and exact vendor 3D interference checking still require KiCad/vendor model verification.


## Rev.Q mechanical correction
- IO board: 18.0 x 23.5 mm.
- RP2040-Zero 23 edge pads are mapped by the actual physical edge layout, not by the schematic P1 numbering order: left edge = 5V/VSYS, GND, 3V3, GPIO29, GPIO28, GPIO27, GPIO26, GPIO15, GPIO14; bottom edge = GPIO13..GPIO8; right edge = GPIO0..GPIO7.
- Pad centers follow the published 18.00 x 23.50 mm drawing: side X=1.38 / 16.62, first side Y=1.59, 2.54 mm pitch; bottom Y=22.12 with X=1.38..14.08 at 2.54 mm pitch.
- THT hole 0.80 mm, pad 1.60 mm.
- FFC changed to Hirose FH34SRJ-24S-0.5SH(50), 24 positions, 14.0 x 3.8 mm, placed on F.Cu on the USB-connector side.
- FFC pins 1-20 = GPIO0..GPIO15/GPIO26..GPIO29; 21=3V3, 22=GND, 23=VSYS, 24=USB_VBUS.


## Rev.R checks
- Edge.Cuts: 18.0 x 23.5 mm.
- 23 RP2040-Zero THT drill centers all lie inside the outline.
- 24P FFC simplified envelope: X=2.0..16.0 mm, Y=5.1..8.9 mm; fully inside outline.
- No KiCad offset pad syntax is used.
