# Deurnode_ESP32-PoE
KiCad design Deurnode for the MakerSpace Leiden, based on the Olimex ESP32-PoE

**KiCaD (concept) design Deurnode nieuw**

Current version: V0.4

This repository contains the KiCad design for Deurnode nieuw, a deurnode for the Makerspace Leiden. This new design is based on the use of an Olimex ESP32-PoE.

**This Deurnode Nieuw has the following features:**

- Two digital inputs are available. By means of a jumper the following options are available:

Option 1:

-
  - 1x Simple digital switch input (to be used for the Grote Schakelaar e.g.)
  - 1x Opto coupler input

Option 2:

-
  - 2x opto coupler input

Both opto couplers can be used to detect 230V AC available or not. By changing the input resistors of the optocouplers the inputs can be used for other voltages as well

- 1 digital output is available. By means of two jumpers the following options are available:
  - Digital output, to directly control a buzzer
  - Digital output to switch a coil or so. There are two options:
    - A relais controlled output (max. 250V AC/10A)
    - A FET based output based on Polu Breakout A4988.

The FET can handle DC \&lt; 55/V35 A. In that case the FET most likely must be kept cool by means of a small cool block.

- SPI based RFID reader connection
- Step motor output

**Power supply:**

Depending on how the deurnode is used, there are two options to provide power to the deurnode print:

1. The ethernet port of the Olimex ESP32-PoE board is directly connected to the MSL LAN. J19 must be removed in this situation. In that case there is no 12V available. It is however possible to provide 12V with an external PSU. Without external 12 V the step motor and the buzzer will not function at all and also the 12V output for the FET will not be available.
2. To power the board via an external PSU (only). J19 must be installed and the ethernet board of the Olimex board should not be connected to a PoE cable.

The following solution is available to couple the deurnode directly to a PoE connection of MSL LAN and also provide 12V to the deurnode board. See the following diagram below:

 ![](data:image/*;base64,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)

For this solution a PoE splitter is used. On the Deurnode board jumper J19 must be installed.

**Protection 230V circuits for the opto couplers**

To prevent hazardous shocks, plexiglass plates can be mounted on the board. The board contains 6b holes to mount these plates.

For more information over these protection plates, see the DeurnodeProtection-230V.pdf or the Autocad DeurnodeProtection-230V.dwg files.
