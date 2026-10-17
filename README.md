# Cyberdeck TD Project (10/16/2026)

## Overview + goal of project
Cyberdeck Project: The main goal is to create a "cyberdeck"; essentially a laptop with personalized functionality, based around the LattePanda Mu compute module.

---

## Main Systems:


### LattePanda Mu Custom Carrier Board:
The cyberdeck is to include a custom carrier PCB to fit the size, needs, and power constraints of the user
- HDMI output
- PCIe M-key for M.2-2230 PCIe 3.0x1 NVMe SSD
- PCIe E-key for Wi-Fi capabilities
- 2x USB-A 2.0 ports
- 2x USB-A 3.2 ports
- GbE (1000Mbps) RJ45 port 
- RTC using CR2032 as CMOS battery


### Custom Keyboard:
The cyberdeck is to include a custom keyboard which can connect over both Bluetooth and an internal 4pin to USB cable.
- Connect over both Bluetooth and USB | Will be achieved using an nRF52840 SoC (henceforth "MCU")
- Built in 1100mAh battery | Will be achieved by using a 2-pin JST connector on the keyboard PCB which powers the MCU and supports USB-C charging
- USB-C connection for both data and charging | Will be achieved by a USB-C port mounted to the keyboard PCB which will allow for both data transmission and charging
- Run ZMK to handle logic and keyboard matrix | Will be achieved by programming the aforementioned MCU and flashing the open-source software to the onboard flash memory


### Battery:
The cyberdeck is to include a built in (~100Wh) battery with safe (but fast) power path charging (can be both on and charging at the same time) and USB-C hot-plug support.
- 100Wh battery | Will be achieved with a Tenergy 14.4V 7000mAh battery pack consisting of 18650 cells in a 4S2P architecture
- Integrated power path charger | Will be achieved with an LTC4612-L42 IC on the main carrier PCB, allowing for smart switching between USB-C system power + charging and exclusive battery power upon plugging in/unplugging the charging cable


### 11.6" Touchscreen:
The cyberdeck is to integrate a 11.6" touchscreen in the housing as well as optional external display.
- Built-in screen | Will be achieved with a DFRobot eDP 11.6" touchscreen to allow for "Microsoft Surface/iPad"-esque capabilities
- External optional display | Will be achieved through HDMI port and software options to allow for mirroring or second monitor extension (1)

### Enclosure:
The cyberdeck is to be enclosed in an enclosure no larger in footprint than a standard laptop (2)
- Custom main enclosure made of machined aluminum and FDM-based 3D printed PLA (3) | Will be achieved with a mixture of outsourced machining capabilities (PCBWay, JLCPCB, etc.) for the aluminum and home 3D printing
- Custom keyboard enclosure made of 3D printed PLA | Will be achieved using home 3D printing capabilities and heat-set inserts to provide increased rigidity.

Footnotes:

(1) Though, that is pushing the capabilities of the compute module itself
(2) Excluding thickness; that is for a later revision and would require a custom cooling solution, new battery design, and various other technical capabilities that are presently out of reach.
(3) The use of PLA may shift to ABS down the line if the capabilities introduce themselves, but the Bambu Labs A1 I have will not reliably print ABS in open-air environments as ABS is very prone to stringing and deformation in atmospheric conditions. This applies to all mentions of PLA in this project.

---

## Main Components
Excludes passives (Capacitors, diodes, etc.) and materials (PLA, aluminum, solder etc.)
- Main Compute Module | LattePanda Mu
- Development Carrier Board | DFRobot LattePanda Mu Carrier Board Lite (for development and testing purposes)
- Screen | DFRobot 11.6" eDP Touchscreen
- Keyboard PCB | Custom PCB
- Carrier Board PCB | Custom PCB
- Trackpad Module | Azoteq TPS43 
- Keyboard MCU | MDBT50Q-1MV2 (Nordic nRF52840 based SoC)
- Key Switches | Kailh Choc Blue V2
- Keycaps | Undetermined
- Enclosures | Custom designed multi-piece aluminum and PLA construction
- Wi-Fi card | Intel BE200 Wi-Fi 7 and Bluetooth 5.4
- Powerpath Charging | Analog Devices LTC4162-L42 IC
- USB-C Power Delivery | WCH CH224K IC for 20V input
- 3.3V and 5V regulation | Silergy SY8253ADC IC
- Gigabit Ethernet | Realtek RTL8111H-CG
- Sound | Analog Devices MAX98365


---

## Current State of Development:

### Custom Carrier Board:
The carrier board is currently in development. Current step is routing high-speed traces. This is the final main step before peer review. The ports, SODIMM slot, RTC battery, and battery screw terminal placements are more or less finalized. There may be slight shifts as the development of the enclosure progresses in order to accommodate the screen, keyboard, and battery. 

### Custom Keyboard:
The keyboard PCB is ready for fabrication as soon as the financials make sense. Some other minor modifications may be made based on any lessons learned from the carrier board as development of the two is parallel, but the design is essentially finalized. The MCU, trackpad module, and key switches are currently in the mail (as of 10/16/2026) for further hands-on testing before finalizing the PCB order to ensure proper fit, function, and pinouts as it relates to the MCU _before_ it is set in stone (or fiberglass and copper, I suppose).

### Enclosure
Cooling will be essential, as the battery, compute module and screen will be in the same enclosure in very close proximity to each other. Using an aluminum subframe to diffuse the heat is a possibility, but will require further investigation and development time. The enclosure itself is the least developed portion of the project thus far. The only thing that it is right now is a couple of STEP models in Fusion360 haphazardly slapped into a shape. The main idea is a five piece enclosure consisting of: faceplate (orange anodized aluminum), left side bracket (orange anodized aluminum), right side bracket (orange anodized aluminum), rear main chassis (black 3D printed PLA), front main chassis (black 3D printed PLA) (1)

The keyboard enclosure has been mocked up, but fastening the keyboard enclosure parts together and mounting the keyboard to the main enclosure are still unsolved challenges at this time. Potential approaches for the fastening problem include screws with heat-set inserts, flexible plastic clips, panel clips, snap together clips, or others. The keyboard is currently one massive assembly, but this is infeasible for the 3D printer that I own, and thus must be redesigned from the ground up. A 2-piece assembly is ideal, but a 3-piece assembly will offer more mechanisms to fasten the components together.

Footnotes: 

(1) Ideally, one chassis part is preferable, but this is likely unfeasible due to home 3D printing size constraints. I will see what I can make happen. Same note as before about PLA/ABS.

---

## Currently in Development:

---

## Future of Development/Improvements for Next Iteration:

---

