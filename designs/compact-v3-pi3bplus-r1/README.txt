JARVIS INTERCOM / COMPACT ENCLOSURE V3 / PI 3 B+ / FLAT 2 MM RING / R1
Public geometry snapshot, October 23, 2026.

Eight original parts, one of each, in STL and STEP. Units are millimeters.
STL files are unitless; import at millimeter scale. Each file is a separate part.
This is unsliced geometry, not a printer plate or printer-specific G-code.

Main body:140 x140 x46 mm, excluding projecting bezel, Jabra and rubber pads.
Hardware:Pi3B+, Jabra Speak410 USB, 1.9-inch170x320 ST7789 SPI module,
GeeekPi/52Pi F-0011 5V40x40x10mm three-wire fan, suitable micro-USB supply,
microSD, eight display jumper leads, heatsink and adhesive rubber pads.
Aim for6-8mm intake clearance under the base on a hard surface.

FASTENERS
Base/shell:4xM2.3x12 self-tapping, underside through recesses into shell pilots.
Pi/base:4xM2.3x6 self-tapping through PCB into printed pilots.
Fan retainer:2xM2.3x8 self-tapping into pocket posts outside fan housing.
Rear insert:2xM2.3x6 self-tapping, from inside shell.
Screen retaining frame:2xM2.5x6, not8mm; thin front skin.
Bezel/shell:2xM3x10, from inside shell.
Top ring/seat:four matching screws; thin-ring length remains to be verified.
Do not reuse the older thick-collar M2.5x12 length without checking engagement.

KNOWN FIT CHECKS
The2mmflat ring was preferred in physical fitting. This is not certification
of every frozen component or every installed station. The original bezel may
need solder/header clearance for your exact module. If it sits high, do not
force it down with screws. The later fit-pending pin-relief revision is excluded.

ASSEMBLY
Power disconnected:clean support and brim; fit rear insert and display in empty
shell; align Jabra seat/ring cable split; fit fan in base with air blowing up;
fit Pi; connect internal JabraUSB, display and fan with service slack; bench
test; shut down/unplug; fit base and rubber pads. Keep wires away from blades.

PRINTING
Recorded common settings:whitePLA,0.4mmnozzle,0.20mmlayers,4walls.
Shell:top face down,25%grid, manual support under rear opening roof. Keep
Jabra opening,vents and screw holes clear. Base:underside down,25%grid,
no support/brim in recorded job. Fan retainer flat. Ring:flat,15%grid,no
support,3mmouterbrim/0.1mmseparation in actual saved job. Review other parts
and local insert overhangs in your own slicer. Original orientations preserved.
220C nozzle was used; U1 bed60C, FlashForge bed60Cfirst/55Clater.
Calibrate for your filament/printer; no G-code or machine profiles included.

SOFTWARE
Application runtime, trained models and SD image are not included. The guide
describes the private project's architecture and reference behavior. Geometry
sharing is not a claim that a universal software installer is available.
Reference settings and wiring are in public-reference-settings.json.
SHA256SUMS.json verifies all16 geometry files. No vendor reference models,
household credentials, network addresses or machine receipts are included.
