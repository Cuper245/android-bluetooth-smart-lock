# Hardware

This folder contains the PCB design, BOM, and enclosure information.

## Subfolders
- `pcb/` PCB project files (KiCad/Altium sources)
- `bom/` bill of materials (CSV/Excel)
- `enclosure/` 3D models (STEP/STL) if used

## Notes (target)
- Separate rails if actuator is noisy
- Include protection: reverse polarity, fuse, flyback diode/snubber, TVS (optional)
- Add test points for power + UART
