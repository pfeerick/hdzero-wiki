#Betaflight Setup

##Canvas Mode 
Currently only Betaflight supports msp_displayport. Do not attempt to perform this CLI update on INAV. Please make sure that the FC firmware version is the latest 
version of BetaFlight. The current (2021/03/12) is version 4.2.8. For a better experience, please wait for the release of version 4.3.0.

    1. Connect VTX UART to FC’s serial port, such as UART3.

    2. In the Ports interface, turn on the MSP function corresponding to the Identifier (UART3), the baud rate is 115200, Save and Reboot.

    3. After opening the CLI, make the following settings:

    A.  Set osd_device to msp: 
    set osd_displayport_device = MSP
    B.  Specify the serial port of msp_displayport as 2 (the number in this place should be the serial port number minus 1): 
    set displayport_msp_serial = 2
    C. Save and exit: 
    save
    The setup is complete.