# Technical Details
This file contains anything I deem "too technical" for the README. 
The README should be something with a high-level overview and justify my use of certain processes/components. 
This document will go into greater depth about the exact technical details of certain decisions and list more granular parts choices and their justifications.

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
- Sound | UNIMPLEMENTED


---

## Carrier Board Length Matching:

=-=-=-=-=-=-=- E-key  -=-=-=-=-=-=-=

All in one area  (<0.127mm skew) (0.1704mm trace width):
- CON_PCIE_TX_0 
[0.0000mm] + [0.0000mm] = [0.0000mm] total skew
[2.5690mm] + [104.0946mm] = [106.6636mm] total length

- HSIO_3_RX
[0.0000mm] total skew
[82.0600mm] total length

- REFCLK3
[0.0000mm] total skew
[66.8870mm] total length

=-=-=-=-=-=-=- M-key  -=-=-=-=-=-=-=

All in one area  (<0.127mm skew) (0.1704mm trace width):
- CON_PCIE_TX_1
[0.0000mm] + [0.0000mm] = [0.0000mm] total skew
[2.7606mm] + [109.3664mm] = [112.1270mm] total length

- HSIO_2_RX
[0.0000mm] total skew
[88.0080mm] total length

- REFCLK0
[0.0000mm] total skew
[149.2008mm] total length

=-=-=-=-=-=-=- GbE  -=-=-=-=-=-=-=

All in one area  (<0.127mm skew) (0.1704mm trace width):
- GbE_PCIe_TX 
[0.0055mm] + [0.0000mm] = [0.0055mm] total skew
[1.8168mm] +  [55.2107mm] = [57.0275mm] total length

- GbE_PCIe_RX
[0.0001mm] +  [0.0000mm] = [0.0001mm] total skew
[3.9770mm] +  [49.1530mm] = [53.1300.mm] total length

- GbE_PCIe_CLK
[0.0005mm] total skew
[52.5019mm] total length

=-=-=-=-=-=-=- HDMI  -=-=-=-=-=-=-=
 
All in one area (0.10 - 0.15mm skew with pairs also roughly all the same length) (0.1704mm trace width):

The brackets below are in order from HDMI connector to Mu and all of the sub-traces in between the passives.

- DDI_B_TX0 
[0.0001mm] + [0.0000mm] + [0.0001mm] + [0.0000mm] = [0.0002mm] total skew
[3.5389mm] + [4.1628mm] + [4.4761mm] + [94.2515mm] = [106.4293mm] total length

- DDI_B_TX1
[0.0001mm] + [0.0001mm] + [0.0001mm] + [0.0000mm] = [0.0003mm] total skew
[3.5409mm] + [3.7013mm] + [3.9786mm] + [94.2766mm] = [105.4974mm] total length

- DDI_B_TX2
[0.0001mm] + [0.0001mm] + [0.0000mm] + [0.0000mm] = [0.0002mm] total skew
[3.5182mm] + [3.5178mm] + [4.0990mm] + [94.2152mm] = [105.3502mm] total length

- DDI_B_TX3
[0.0001mm] + [0.0000mm] + [0.0001mm] + [0.0000mm] = [0.0002mm] total skew
[3.5170mm] + [4.1919mm] + [4.1763mm] + [94.2153mm] = [106.1005] total length

=-=-=-=-=-=-=- USB3.2  -=-=-=-=-=-=-=

All in one area  (<0.10mm skew) (0.1704mm trace width):
- HSIO_0_TX
[0.0100mm] + [0.0000mm] + [0.0000mm] = [0.0100mm] total skew
[8.8612mm] + [5.3635mm] + [54.0231mm] = [68.2478mm] total length

- HSIO_1_TX
[0.0027mm] + [0.0000mm] + [0.0000mm] = [0.0027mm] total skew
[3.9047mm] + [5.4568mm] + [54.7050mm] = [64.0665mm] total length

- CON_USB3_D 
[0.0000mm] + [0.0000mm] = [0.0000mm] total skew
[29.9915mm] + [84.4885mm] = [114.48mm] total length

- CON_USB4_D
[0.0001mm] + [0.0000mm] = [0.0000mm] total skew
[7.2915mm] + [73.4302mm] = [80.7217mm] total length

- CON_USB3_SSRX
[0.0000mm] + [0.0000mm] = [0.0000mm] total skew
[9.2867mm] + [51.9657mm] = [61.2524mm] total length

- CON_USB4_SSRX
[0.0000mm] + [0.0000mm] = [0.0000mm] total skew
[3.4665mm] + [52.8293mm] = [56.2958mm] total length

=-=-=-=-=-=-=- E-key USB  -=-=-=-=-=-=-=

(<0.10mm skew) (0.1704mm trace width):
- USB_2_P7
[0.0000mm] total skew
[79.0188mm] total length

=-=-=-=-=-=-=- USB2.0  -=-=-=-=-=-=-=

All in one area  (<0.10mm skew (0.1704mm trace width)):
- CON_USB2_D
[0.0000mm] total skew
[59.4753mm] total length

- CON_USB1_D
[0.0000mm] total skew
[66.1903] total length

