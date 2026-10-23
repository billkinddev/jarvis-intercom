# Jarvis Intercom

A Raspberry Pi room-to-room intercom built around a USB speakerphone, a small status display, and a printed enclosure.

**[Interactive build guide and 3D explorer](https://whamlink.com/ShSPh8W8)** · **[Download the STL + STEP kit](https://github.com/billkinddev/jarvis-intercom/releases/tag/compact-v3-pi3bplus-r1)**

Say “Hey Jarvis,” wait for the beep, then ask to call a room. Or use the speakerphone’s green button to start a command. The current system supports SIP calls, ringing or automatic drop-in, an optional arrival chime, speaker volume, wake enablement, health reporting, and safe shutdown through a private management panel.

This repository contains **hardware design files and public build documentation**. The application is still a private project. There is no public software installer, trained-model bundle, or ready-made SD image here.

## Explore the build

The [guide](https://whamlink.com/ShSPh8W8) includes an interactive assembled/exploded 3D view. Rotate and zoom, move the separation slider, hide the shell, or isolate individual parts. It also includes assembly instructions, an interactive physical-pin wiring map, print settings, software architecture, and lessons from earlier builds.

The complete self-contained guide is also in [`guide/index.html`](guide/index.html). Download it and open it in a browser; its diagrams and 3D viewer do not require external scripts or services.

## Reference hardware

| Part | Quantity | Notes |
| --- | --- | --- |
| Raspberry Pi 3 Model B+ | 1 | Reference board, with matching rear insert |
| Jabra Speak 410 USB | 1 | Speaker, microphone, buttons and audio processing |
| ST7789 1.9-inch SPI display | 1 | 170 × 320 pixels, eight pins, no touch |
| GeeekPi / 52Pi F-0011 fan | 1 | 5 V, 40 × 40 × 10 mm, three wires |
| MicroSD card | 1 | 32 GB class used in the reference setup |
| Micro-USB supply | 1 | Quality regulated supply; official Pi 3 supply is 5.1 V / 2.5 A |
| Female-to-female jumper leads | 8 | Display connections; fan has its own leads |
| Low-profile heatsink and rubber pads | 1 set | Keep the bottom intake clear |
| Printed parts and fasteners | 1 set | See the matched kit and joint-specific screw list |

A separate always-on Linux machine runs the shared Asterisk switchboard. The existing system uses a Pi 5 for central services.

## Design files

[`designs/compact-v3-pi3bplus-r1/`](designs/compact-v3-pi3bplus-r1/) contains eight original parts in both STL and STEP:

1. Shell
2. Base
3. Pi 3 B+ rear insert
4. Fan retainer
5. Lower Jabra seat
6. Flat 2 mm top ring
7. Screen bezel
8. Screen retainer

The main body is **140 × 140 × 46 mm**, excluding the projecting screen bezel, Jabra and rubber pads. Import STL files in millimeters. These are unsliced models, not a printer plate or machine-specific G-code.

The package includes public build notes, reference settings, and SHA-256 checksums. Geometry is preserved from the selected Compact v3 / Pi 3 B+ / flat-ring r1 design. The enclosure revision remains in filenames so similar-looking variants do not get mixed together.

### Fit details still worth checking

- The flat 2 mm ring was preferred during physical fit testing. Its final screw length is not yet recorded. Do not assume the older thick collar’s screw length is suitable.
- The original screen bezel may need clearance around the exact module’s soldered header. Do not pull a tilted module flat with screws. A later fit-pending bezel is not substituted into this kit.
- Printed meshes in the viewer match these files. Electronics are simplified illustrations. The thin ring is shown in a nominal flange-on-deck pose; exploded motion is illustrative, not a clearance simulation.

## Reference settings

The guide and [`public-reference-settings.json`](designs/compact-v3-pi3bplus-r1/public-reference-settings.json) document the reference configuration.

- **Display:** SPI0 CE0, 8 MHz, 320 × 170 logical canvas, row offset 35. Rotation depends on mounting. This display has no touch interface.
- **Fan:** on at 70°C, off below 60°C, with native `gpio-fan` control. Pi 3 B+ firmware thermal limits are unchanged; its default 60°C soft limit can reduce clock speed before the fan starts.
- **Wake:** openWakeWord with the Hey Jarvis model, Silero VAD and local Vosk command recognition.
- **Calling:** Baresip on stations, Asterisk on the shared server.
- **Management:** stations report status and acknowledge settings through a private HTTPS service.
- **Mute:** Jabra’s native control. Disabling the wake word is not microphone mute.
- **Quiet hours:** planned, not implemented in the documented build.

## Build and print notes

The reference prints used white PLA, a 0.4 mm nozzle, 0.20 mm layers and four walls. The shell prints with its cosmetic top face on the bed and selective support under the rear opening. The recorded base and fan-retainer print used no supports. The selected flat ring used a removable outer brim.

The [full guide](https://whamlink.com/ShSPh8W8) records temperatures, orientations, fasteners, support placement and the limits of historical print estimates. Review the parts in your own slicer and use a calibrated profile for your printer.

## Project status

This is a working home project being documented for other builders, not a finished consumer product or universal software release. Screen and fan operation were confirmed on the reference Pi 3 B+ build; calls and repeated button use were exercised across existing stations. Each new assembly needs its own audio, wiring and thermal check.

Wake and room-command recognition run locally. Normal operation does not save raw microphone recordings, but recognized command text appears in local service logs. Calls send voice to the other endpoint through the switchboard.

## Upstream projects

[Raspberry Pi](https://www.raspberrypi.com/products/raspberry-pi-3-model-b-plus/) · [openWakeWord](https://github.com/dscripka/openWakeWord) · [Vosk](https://alphacephei.com/vosk/) · [Baresip](https://github.com/baresip/baresip) · [Asterisk](https://www.asterisk.org/)

Upstream software and trained models have their own licenses and are not redistributed in this design kit.
