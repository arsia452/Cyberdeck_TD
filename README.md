
# Cyberdeck TD Project

## Overview + goal of project
Cyberdeck Project: The main goal is to create a "cyberdeck"; essentially a laptop with personalized functionality, based around the LattePanda Mu compute module.

## Components:


### LattePanda Mu Custom Carrier Board:
The cyberdeck is to include a custom carrier PCB to fit the size, needs, and power constraints of the user. 
- HDMI output.
- PCIe M-key and E-key.
- 2x USB-A 2.0 ports.
- 2x USB-A 3.2 ports.


### Custom Keyboard:
The cyberdeck is to include a custom keyboard which can connect over both Bluetooth and an internal 4pin to USB cable.
- Connect over both Bluetooth and USB | Will be achieved using an nRF52840 SoC (henceforth "MCU")
- Built in 1100mAh battery | Will be achieved by using a 2-pin JST connector on the keyboard PCB which powers the MCU and supports USB-C charging
- USB-C connection for both data and charging | Will be achieved by a USB-C port mounted to the keyboard PCB which will allow for both data transmission and charging
- Run ZMK to handle logic and keyboard matrix | Will be achieved by programming the aforementioned MCU and flashing the open-source software to the onboard flash memory


### Battery:
The cyberdeck is to include a built in (~100Wh) battery with safe (but fast) power path charging (can be both on and charging at the same time) and USB-C hot-plug support.
- Tenergy 14.4V 7000mAh battery (4S2P, 18650 cells)
- Integrated power path charger (LTC4612 IC) to smart switch between USB-C and battery power upon hot-plug.


### 11.6" Touchscreen:
The cyberdeck is to integrate a 11.6" touchscreen in the housing as well as optional external display.
- DFR eDP 11.6" touchscreen.

## Current State of Development:

## Currently in Development:

## Future of Development:

