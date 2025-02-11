Keyboard scanner for a Thinkpad T61 keyboard, using the original connector,
salvaged from a retired T61, and a Raspberry Pi Pico H. Components on the BOM:

* 1x Molex 54363-0489 (WM6787CT-ND on Digikey)
* 1x Raspberry Pi Pico (with or without headers)
* 1x capacitor SMD 0603 2.2 uF
* 1x capacitor SMD 0603 100 nF
* 1x p-MOSFET TSM2305CX or similar (optional, for external 5V, e.g. a battery)
* 2x n-MOSFET 2N7002 or similar
* 4x resistor SMD 0603 10 kOhm
* 1x resistor SMD 0603 22 kOhm

Based on work by thedalles77 (schematics) and WarhawkCZ (QMK variant). HDR also
had the same idea of having the keyboard connector and the MCU module on
opposite sides to save space.
- https://github.com/thedalles77/USB_Laptop_Keyboard_Controller/tree/master/Example_Keyboards/Lenovo_ThinkPad_T61/Teensy%20LC
- https://forum.thinkpads.com/viewtopic.php?t=134293
- https://github.com/HDR/USB_Laptop_Keyboard_Controller

Thanks @tpcware for the KiCad symbol, footprint and 3D model for the Raspberry
Pi Pico. I butchered the footprint to get a THT-only variant.
https://github.com/ncarandini/KiCad-RP-Pico

Good advice came from thedalles77 on instructables to lay out the connections
on a piece of paper before assigning the nets in the schematic editor.
https://www.instructables.com/How-to-Make-a-USB-Laptop-Keyboard-Controller/

When using a Pico W it might be possible to extend this with Bluetooth, hence
the solder pads for wires to an external battery charger + 5V converter. This
might not work too well though; the keyboard's bottom is a metal shield that
probably kills the wireless transmission when the Pico W is right underneath.

Ordered on JLCPCB. The via size (0.5 mm hole, 1.1 mm overall diameter) is small
enough and does not cost extra.

The 0.5 mm drills and vias could be done by hand (with wire soldered through
the hole) if making the PCB at home.

## Third-party components

The following components in this repository are not my work:

Symbols:

* AA01B-S040VA1 - probably by Jiri Panacek (WarhawkCZ)
* Molex_54363-0489:543630489 - Copyright held by EMA Design Automation, ® Inc., all rights reserved

Footprints:

* T61_Kb_Scanner:RPi_Pico_H - adapted from the one by @tpcware
* T61_Kb_Scanner:AA01B-S040VA1 - unknown
* T61_Kb_Scanner:WM6787CT-ND - unknown
* Molex_54363-0489:CON_543630489 - Copyright held by EMA Design Automation, ® Inc., all rights reserved

## License

Copyright 2023-2024 Michael Büchler
SPDX-License-Identifier: Apache-2.0 WITH SHL-2.1

The schematics and PCB design in this repository shall use the Solderpad Hardware License v 2.1 (the “License”); you may not use this file except in compliance with the License, or, at your option, the Apache License version 2.0. You may obtain a copy of the License at

https://solderpad.org/licenses/SHL-2.1/

Unless required by applicable law or agreed to in writing, any work distributed under the License is distributed on an “AS IS” BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

## Images

The keyboard case in the picture is this one:
https://www.printables.com/model/877321-thinkpad-t61-keyboard-base

![PCB top](images/front.jpg)
![PCB bottom](images/pcb.jpg)
![Assembled keyboard](images/kb.jpg)
