# VNA_Calibration_Board

Theory Documentation : Advanced PCB Layout


## Purpose:

The VNA Calibration Board is used as a second printed circuit board creation project. 
The VNA Calibration Board allows for a way to easily calibrate a vector network analyzer for radio frequency use.
This board will show the characteristics of a lowpass filter configuration. 
This board will utilize 50 ohm traces, SMA connectors, a 0603 resistor, and a 0603 capacitor. 
This board additionally contains connections for through, open, and a lowpass filter configurations.


## How does a VNA work to analyze the Calibration Board?

A VNA, vector network analyzer, allows for testing to occur on the specifications of components. 
A VNA also allows for simulation verification, and to show component signal integrity at different stages for transmitting and receiving. 
Some ways a VNA shows signal integrity is through received signal isolation from the transmitted signal, and unwanted signal filtering. 
The VNA provides a source input signal to enter into one SMA of the Calibration Board. 
A reflected signal will then transfer to the receiver of the VNA, and an output signal will exit through the other end of the board. 
Both reflected signal and output signal will transfer to the receivers, and then be displayed thorugh either a PC or a display.
Then a frequency range, dynamic range, trace noise, and measurement speed will be displayed, which are some characteristics of the lowpass filter we are looking to analyze.

## Connections:

Three different configurations are instilled within the given VNA Calibration test card, a through, open, and lowpass filter. 
Connector to VNA was chosen through an SMA connector. 
Footprint of given SMA connector is attached in files.
50 ohm traces were used to make connections between connectors and to components.
A ground plane was attached to the bottom.
Ground shapes were added to the top. 
When adding ground shapes to the top layer of the board, it is important to ensure that the distance between the ground shapes and the output trace is far enough away to ensure signal integrity is upheld.
Using a microstrip calculator the distance found to create a 50 ohm trace from the top ground shape must be at least 0.47mm, which was calculated using the standard FR-4 substrate.
The length of the microstrip also needs to uphold the 3*Width theory, which states that the distance found between the 50 ohm trace and top ground shape must be multiplied by 3.
This distance will then be used to show the length of the microstrip, which should be 1.41mm.
Based off of VNA Calibration Board design, minimum clearance is ensured.
Vias were also added to the board to ensure an equal current plane throughout the board.
Additional logos were added to the board based on aesthetic decisions. 

## Problems when designing: 

An integral problem to the design was ensuring that enough thermal relief points were adding to the ground pads of the SMA.
Two thermal relief points are necessary at a minimum to avoid errors. 
To fix this concern, thermal relief points were added to the bottom and sides of each SMA ground pad. 
Another integral problem was found through connection concerns from the output traces. 
All output traces were throwing warnings when the output 50 ohm traces had the same net name.
To fix this problem, different net names were added to the output traces named from the configuration.

### Side note:

Board is subject to change. 
Ensure that microstrip distance between ground shapes are within minimum acceptable clearance.
Minimum clearance can also be found in IPC-2221 standard.


## References:

- [SMA Connector](https://www.digikey.com/en/products/detail/amphenol-rf/132255-11/4948012?utm_adgroup=Connectors%20and%20Interconnects&utm_source=google&utm_medium=cpc&utm_campaign=Shopping_Supplier_Amphenol%20RF_0115_Co-op&utm_term=&utm_content=Connectors%20and%20Interconnects&gclid=Cj0KCQjw8e-gBhD0ARIsAJiDsaUrfOlJ-fbGHJ9TSMtNrpHwP0aa9LQ3nOot902IX43sAEF8okGkE1EaAjHVEALw_wcB)
- [0603 Resistors](https://www.digikey.com/en/products/detail/vishay-dale/CRCW0603249RFKEBC/7928698?utm_adgroup=Resistors&utm_source=google&utm_medium=cpc&utm_campaign=Shopping_Supplier_Vishay&utm_term=&utm_content=Resistors&gclid=Cj0KCQjw8e-gBhD0ARIsAJiDsaVE2eXfdvGD4j4WN10YVxKx1yiL2tfwIAedk80d4FrehSMFS40kiNoaAhX7EALw_wcB)
- [0603 Capacitors](https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL10B104KA8NNNC/3886664)
- [VNA Calibration](http://rfic.eecs.berkeley.edu/142/labs/resources/Calibration.pdf)
- [VNA Theory](https://download.tek.com/document/70W_60918_0_Tek_VNA_PR.pdf)
- [Microstrip Impedance Calculator](https://www.allaboutcircuits.com/tools/microstrip-impedance-calculator/)
