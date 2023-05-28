# HDZero Goggles


## Wireless Head Tracker

Using the ELRS backpack in the goggles, you can use the HDZero goggles as a wireless head tracker. This will allow you to control the pan and tilt of your camera using the goggles.

!!! warning
    This feature is still in development and may not work as expected. Please report any issues you have to the developers.

You need version 1.3 of the backpack firmware on the TX module backpack and the goggles backpack. You need to flash the `master` branch of ELRS to the TX module (until ELRS v3.3 is released). Then in the Lua script enter the Backpack menu, make sure Backpack in On, HT Enable is On or an Aux channel if you want to enable it via a switch. And finally set HT Start Chan to a aux channel for Pan (tilt and roll will then be chan+1 and chan+2 respectively). To get the smoothest operation you will want to be running 333 Full or 100 Full. Also the switch mode you choose will determine how many channels are available to use and therefore which aux channels you can use for the pan/tilt/roll (see [Switch Config](https://www.expresslrs.org/software/switch-config) in the ELRS documentation)

On the goggles you need to enter the Head tracking menu and turn the Tracking option on.

## Analog Modules

### ImmersionRC RapidFire
The ImmersionRC RapidFire is considered by some to be the best analog module on the market. It is a dual receiver module that uses advanced algorithms to combine the best parts of two analog signals into one. Using [Paul Kendall's mod](https://github.com/pkendall64/hdzero-goggle/wiki/Analog-Module-Backpack-Control), it is possible to control the RapidFire module with the HDZero goggles. This will allow you to use the ELRS VTX Administrator functionality or the jog dial on the goggles to change channels and change between rapidFIRE in the goggles menu.


[ImmersionRC Product Page](https://www.immersionrc.com/fpv-products/rapidfire/)

### TBS Fusion

A popular analog module for goggles with a Fatshark compatible module bay is the TBS Fusion. Similar to the ImmersionRC Rapidfire, it uses "active video fusion" to reduce image breakup and increase usable video range. While it has a Wifi backpack, out of the box it does not work with the ELRS VTX Administrator functionality. However, it is possible to flash the module with ELRS backpack firmware, which will allow you to use the Fusion with ELRS. You can also use [Paul Kendall's mod](https://github.com/pkendall64/hdzero-goggle/wiki/Analog-Module-Backpack-Control) to switch between the eight configured favorite channels on the Fusion using the jog dial on the goggles.

[TBS Product Page](https://www.team-blacksheep.com/products/prod:tbs_fusion)

#### ELRS Backpack Flashing

!!! info
    You will need a FTDI or similar USB UART/serial adapter in order to flash the Fusion. You can find them on Amazon or eBay for a few dollars if you do not have one already.

!!! warning
    This process requires you to lift the LCD screen on the Fusion. This is not a difficult process, but you should be careful not to damage the ribbon cable or the screen itself. The easiest way to do this is by powering up the module by USB, letting it run for a minute or two until it has warmed up, thus softening the adhesive. You should now be able to gently remove the display, flip it over, and now have access to the connection points underneath.

Wire up your TBS Fusion as shown below: 

![TBS Fusion Wiring](../../assets/tbs-fusion-flashing.png)

Power the module using a seperate USB connection, created a ground bridge between pins 15/18 (red) and the FTDI GND (purple), and connected the RX and TX respectively via FTDI. Put the module into Bootloader by holding the button to the left and powered it up. The screen should now show "wifi unbrick".

Then, use the ELRS configurator to build and install the backpack directly onto the module (UART method). After it was successful, disconnect all wires and put it back together.

You should be able to get the Fusion to start up the ELRS wifi page by using the ELRS Lua transmitter script (`Wifi Connectivity -> Enable VRx WiFI`). The Fusion should then show the wireless signal as no longer broken on its OSD. You should also be able to view the elrs_vrx.local page (if you gave it your home wifi credentials or are connected to its ELRS hotspot).

!!! note
    You can repeat the last section in the future to update the fusion backpack wirelessly.

The last step is to enable everything on the Fusion. Goto `Settings -> VTX Sync -> "Follow"`, and you should be good to go!

