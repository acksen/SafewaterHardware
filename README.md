# SafewaterHardware
Safewater UV-C Rainwater Sanitisation Controller for Arduino

## Introduction

Hardware design for the UV-C Rainwater Sanitisation Controller, designed by Acksen Ltd (http://www.acksen.com https://www.aquaductor.com) for the Safewater Research Initiative (https://www.safewater-research.com/).

The Safewater Ultraviolet Water Purification Controller is designed to automatically provide safe,
sanitised and potable water for you and your family.

The controller automatically takes untreated water from your storage tank and treats it, to ensure that you
have a steady supply of clean water. No manual intervention is needed – the controller will function by
itself and notify you via an alarm if any problems occur.

This is designed for a system which:
- Collects rainwater into an untreated water tank.
- Uses a UV-C sanitisation lamp to disinfect the collected rainwater and ensure that it is safe for
human consumption.  A filter is also used to remove physical contaminants.
- Disinfected water is placed into a treated water tank.
- When the treated water tank reaches a lower bound float switch (Switch T1), the controller automatically refills it using water from the treated tank.
- When the upper bound float switch on the treated tank is triggered (Switch T2), disinfection and pumping stops.
- The untreated water tank features a float switch at the base (Switch S) to confirm that there is rainwater to pump and disinfect.

The controller features a number of safety features, such as:
- Warm-up period for the UV-C Lamp to ensure it has reached operating temperature
- Automatically ends the pumping sequence after a timeout period (based around the tank size/pump rate).
This is presently set for the Safewater systems deployed to Mexico and Colombia, and is altered using a external jumper on an input line.
- Override button to immediately start the disinfection sequence and provide water, regardless of present state.
- Uses Hardware Watchdog Timer on the Microcontroller to reboot if normal firmware operation is interrupted
- Checks the UV-C Lamp operating current while disinfecting, to ensure that it is operating correctly.
- Provides user alarms for UV-C Lamp Fault, Maximum Runtime Exceeded (due to e.g. Water Pump Fault), Treated Tank Float Switch Fault 
and Source Tank Empty Fault.
- Anti-cycling management
- Automatic retry system in case of transient faults

## Description

This is the hardware design for the UV-C Rainwater Sanitisation Controller, designed by Acksen Ltd
(http://www.acksen.com https://www.aquaductor.com) for the Safewater Research 
Initiative (https://www.safewater-research.com/).

This hardware is designed around the ATMega328P 32-Pin TQFP Microcontroller (also used in the Arduino Uno SMD).

This repository includes PCB and schematic designs, controller documentation for installation, operation and troubleshooting, along with testing documentation.

- [PCB Design](./pcb)

PCB and Schematic in [Labcenter Proteus Professional](https://www.labcenter.com/) Format.  This is commercial software, however a free demo is available via the website which allows viewing and printing.

PDF exports of the Schematic and PCB Layout are also available.

- [Documentation](./docs)

The available documentation is:
- [Controller Manual in English and Spanish](./docs/manual/).  This is written using Microsoft Word, with PDF exports available.
- [Installation and Faults Overview](./docs/installation_and_faults_overview).  This is available in PDF format only at present.
- [Wiring and Troubleshooting](./docs/wiring_and_troubleshooting).  This is available in PDF format only at present.
- [Wiring Diagrams in English and Spanish](./docs/wiring_diagrams).  These are available in Corel Draw (.cdr) format, with PDF exports available.

Selection of Manufacturer Datasheets for parts used in the Safewater Controller.

- [Datasheets](./datasheets)

The available Specification documentation is:
- [Specifications](./specifications)

- [Microcontroller Connectivity](./specifications/microcontroller_connectivity).  This lists the microcontroller pin allocations for the ATMega328P 32-pin TQFP part used in the controller.  This is written using Microsoft Excel, with PDF export available.

Please note that other specifications include operating flowcharts are available in the Firmware repository. (https://www.github.com/acksen/SafewaterFirmware)

- [Testing](./testing)

The available Testing documentation is:
- [Safewater Controller Test Script](./testing/test_script).  This lists tests to carry out on the Safewater controller to help ensure that it meets correct operating guidelines.  This is written using Microsoft Excel, with PDF export available.

## Firmware

- This firmware can be easily ported to other 8-bit Atmel Microcontrollers, and is also available on Github (https://www.github.com/acksen/SafewaterFirmware)

- Further information is available on the Aquaductor website for the commercial implementation of the controller, including instruction manuals, Wiring Diagrams, Troubleshooting, Installation & Faults Overview.
(https://www.aquaductor.com/resources)

## Author
Designed and Written by Keith Stafford and Richard Phillips for Acksen Ltd.

## License
These files are licenced using the GNU General Public License version 3.

Copyright (c) 2020, 2021, 2022 Acksen Ltd, All rights reserved.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.