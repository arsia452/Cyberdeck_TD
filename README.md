
# Cyberdeck TD Project (10/16/2026)

## Overview + goal of project
Cyberdeck Project: The main goal is to create a "cyberdeck"; essentially a laptop with personalized functionality, based around the LattePanda Mu compute module.

---

## Main Systems:


### LattePanda Mu Custom Carrier Board:
The cyberdeck is to include a custom carrier PCB to fit the size, needs, and power constraints of the user
- HDMI output
- PCIe M-key
- PCIe E-key
- 2x USB-A 2.0 ports
- 2x USB-A 3.2 ports
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
- External optional display | Will be achieved through HDMI port and software options to allow for mirroring or second monitor extension (though, that is pushing the capabilities of the compute module itself)

### Enclosure:
The cyberdeck is to be enclosed in an enclosure no larger in footprint than a standard laptop (excluding thickness; that is for a later revision and would require a custom cooling solution, new battery design, and various other technical capabilities that are presently out of reach). (The use of PLA may change to ABS down the line if the capabilities introduce themselves, but the Bambu Labs A1 I have will not reliably print ABS in open-air environments as ABS is very prone to stringing and deformation in atmospheric conditions) 
- Custom main enclosure made of machined aluminum and FDM-based 3D printed PLA | Will be achieved with a mixture of outsourced machining capabilities (PCBWay, JLCPCB, etc.) for the aluminum and home 3D printing
- Custom keyboard enclosure made of 3D printed PLA | Will be achieved using home 3D printing capabilities and heat-set inserts to provide increased rigidity.

---

## Main Components
Excluding passives (Capacitors, diodes, etc.) and materials (PLA, aluminum, solder etc.)
- Main Compute Module | LattePanda Mu
- Development Carrier Board | DFRobot LattePanda Mu Carrier Board Lite (for development and testing purposes)
- Screen | DFRobot 11.6" eDP Touchscreen
- Keyboard PCB | Custom PCB
- Carrier Board PCB | Custom PCB
- Trackpad Module | Azoteq TPS43 
- Keyboard MCU | MDBT50Q-1MV2
- Key Switches | Kailh Choc Blue V2
- Keycaps | Undetermined
- Enclosure | Custom designed multi-piece aluminum and PLA construction


---

## Current State of Development:

### Custom Carrier Board:
The carrier board is currently in development. Current step is routing high-speed traces. This is the final main step before peer review.

### Custom Keyboard
The keyboard PCB is ready for fabrication as soon as the financials make sense. Some other minor modifications may be made based on any lessons learned from the carrier board, but the design is essentially finalized. The MCU, trackpad module (TPS43)

---

## Currently in Development:

---

## Future of Development:

---

