# DPF Monitor - OBD-II Diagnostic Display

Standalone OBD-II plug-in device for a 2017 Range Rover Evoque 2.0 Ingenium Diesel. Displays live DPF info (soot %, regen status, distance since last regen) without any phone/Bluetooth app.

## Hardware
- ESP32-WROOM-32E MCU
- SN65HVD230 CAN transceiver (ISO 15765-4, 11-bit CAN)
- J1962 OBD-II connector
- SSD1351-based 1.5" SPI OLED display (Newhaven NHD-1.5-128128UGC3)
- LM53601-Q1 automotive-grade buck converter (12V -> 3.3V)
- Automotive-rated reverse polarity protection + TVS diode for load dump

## Design notes
- Split into two physical boards per client spec: main board + vent-mounted display board, connected via a JST-GH cable (no soldering needed for assembly)
- 4-layer PCB, designed in KiCad 10.0.4
- Reads DPF soot % via UDS Mode 22 (ReadDataByIdentifier), DID 22042C
- USB-C port on main board for firmware flashing

## Repo structure
- `kicad-project/` - full KiCad project (schematics, PCB, BOM, gerbers, 3D models)
- `reference-images/` - client-provided reference images/PDF (view only)

**Scope:** hardware/PCB design only - firmware not included.
