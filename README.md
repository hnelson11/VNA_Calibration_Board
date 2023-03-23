# VNA_Calibration_Board

Theory Documentation : Advanced PCB Layout


## Purpose:

The Infrared Keyboard is used as a first printed circuit board creation project. 
The Infrared Keyboard will allow infrared light to transmit data to a personal computer rather than transmitting through a traditional hardwired connection.
This keyboard will utilize the Attiny85-20SU microcontroller, USB power 10119194-001LF, and infrared receiver vs1838b.


## How does it work?

As stated above the Infrared Keyboard will allow infrared light to transmit data to a personal computer rather than transmitting through a traditional hardwired connection.
The ATtiny85 will control the IR receiver's input and output through the RCV LED shown in the IR_Schematic. 
The RCV LED will turn on when a signal is received from the receiver. 
Similarly, a PWR LED will be 


## Electrical Connections:

All pinnout connections within this schematic have been made according to component data sheets made in the reference section below. 
Voltage input and ground connections are connected properly to the ATtiny85, which is shown on page 2 of the ATtiny85 data sheet.
The USB2.0 voltage and ground connections are shown on page 1 of the USB2.0 data sheet, and the IR receiver voltage and ground connections are found on page 1 through 3 of the vs1838b data sheet.
Any additional electrical component connections to ground and voltage input are connected properly according to part specification. 
The ATtiny85 has connections to the USB connector through the D- and D+ pins of the USB. 
The D- pin should be connected to the PB3 pinnout of the ATtin85, which is the CLK1.
The D+ pin should be connected to the ATtiny85 PB4 pin, which is CLK 0. 
The IR receiver will be connected to the PB1 pin of the ATtiny85, which is the MISO connection. 
This pinnout willl allow the microcontroller to receive the data that is being transmitted from the IR receiver.
Shunt Capacitors are connected to pin 8, Vcc pin of the ATtiny85, to prevent high frequency voltage spikes.
Additionally the reset pin is set to pin 8 of the ATtiny85 to set the reset pin as high.


## Programmer:

While programming the ATtiny85, use the IR2USB_Keyboard.ino and the IR2USB_Serial.ino found on Stefan Wagner's github repository listed in reference below.
Pins that need to be programmed through arduino or the Analog Discovery2 are as listed: PB5, PB3, PB4, and PB2. 
The PB1 pin will be connected to the IR receiver, the PB0 pin will be connected to the PWR LED, pin 8 will connect to Vcc, and pin 4 will connect to GND.
Please make sure you BURN THE BOOTLOADER!
You want your ATtiny85 to have code if it is a SMT component.


### Side note:

The ATtiny85 will be in control of the keyboard, so its placement was made towards the middle of the schematic / PCB due to preference.
This is shown through the IRKeyboard_Schematic, as well as much of the rest of the schematic was placed in the correct orientation as will be placed in the PCB.
Voltage concerns should not be an issue, because the maximum voltage that the IR receiver can withstand is 5.5V and the minimum voltage is 2.7V.
The voltage connected to the ATtiny85 will be 5V.
To ensure that voltage entering the ATtiny85 remains at 5V and not larger, 3.6V voltage regulators will be placed near the PB3 and PB4 pins of the ATtiny85 to act as voltage regulators for the board.
These zener diodes are able to ensure that the microcontroller can fully run on 5V power as they limit the USB voltage output.
Also please ensure that the voltage used during testing purposes is limited to 5V, and that all electrical component (i.e. Diodes, Capacitors, etc...) are placed in the correct orientation for current flow.
ALSO DOWNLOAD DIGIKEY X KICAD LIBRARY!!

## References:

- [Stefan Wagner Git](https://github.com/wagiminator)
