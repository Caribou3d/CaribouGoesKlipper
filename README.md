--------------------
--------------------
--------------------
--------------------
# There is a new home for Caribou Klipper configs - check out https://github.com/Caribou3d/CaribouGoesKlipper

--------------------
--------------------
--------------------
--------------------
# Klipper config for my Caribou 320 mk3s

Forked from https://github.com/Frix-x/klipper-prusa-i3mk3s and modified for my printer - to be used with mainsail.

Notable changes:
- Inverted y Axis (as my Y stepper connector is flipped)
- Extruder steps adjusted for geared bondtech extruder
- Added a menu to choose between different flexplates and store the selected offset to a txt file to persist during reboots. (thx to alexz on voron discord) See menus/flexplate.cfg
- PID tuning for my MK52 155W Heated bed (PID_CALIBRATE HEATER=heater_bed TARGET=60)
- PID tuning for my Dragon Hotend (PID_CALIBRATE HEATER=extruder TARGET=170)


# How to get this running


### Install Moonraker, Mainsail & Klipper on your raspberry Pi
Probably the easiest way to get your pi up & running would be the preinstalled SD-Card image of mainsail-OS. Installation instructions here: 
https://docs.mainsail.xyz/setup/mainsail-os
After successful installation, you should be able to open the mainsail webinterface in your browser and also connect to the distribution using SSH with username "pi" /and password "raspberry"

### Flash klipper firmware to the Einsy Board
Klipper includes the tools to flash the board directly when connected to the Pi over USB.
Step by step guide can be found here:
https://github.com/KevinOConnor/klipper/blob/master/docs/Installation.md#building-and-flashing-the-micro-controller

### Copying this config
After the board is flashed, you can use this config to your ~/klipper_config folder on the Pi.
Make sure to update the serial of the Einsy Board in the /hardware/printer.cfg file - otherwise klipper won't talk to your board.
After the config is copied and adjusted, you can issue a "firmware restart" from the webinterface. When the connection is established correctly, you will see the klipper menu popping up on your printer LCD.

### Slicer settings & GCODEs
- Pressure Advance (equivalent of Marlin Linear Advance) values need to be calibrated and placed in your start gcodes (SET_PRESSURE_ADVANCE advance=xxxxx) guide can be found here:
https://github.com/KevinOConnor/klipper/blob/master/docs/Pressure_Advance.md
