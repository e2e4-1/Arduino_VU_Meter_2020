# Arduino VU Meter 2020

This project is based on [Stereo NeoPixel Ring VU Meter](https://www.hackster.io/ericBcreator/stereo-neopixel-ring-vu-meter-b28e78) by [ericBcreator](https://www.hackster.io/ericBcreator).

## The idea

I found many projects for a VU Meter on Adruino, but all of them did not suit me. They were not colorful or functional enough. Therefore, I decided to remake someone else’s UV Meter project that would meet my requirements - the final product must be made on a PCB, in a separate case with adjustments, and LED strips must also be in separate cases, connected to the main one.

## Hardware

* Arduino Nano
* SCSL(DS1002-1) 15pin + PLSS(DS1004) 15pin * 2 pairs , if you do not want to solder the Arduino directly to the PCB
* Capacitor(C1) 10uF 25V
* Resistors(R4,R7) 470 0.25W 2pcs
* Resistors(R3,R5,R6,R8) 10k 0.25W 4pcs
* Resistor for power LED(R), in my case 1k 0.25W
* Potentiometers(R1,R2) B10k R-0904N 2pcs
* PLS connector 3pin DS1021 + Jumper 2.54mm
* Connectors 3pin for connecting LED strips WF-3R+HU-3(DS1070) 2 pairs 
* Switch(SW1) 3pin L-KLS7-SS-12F20A-G5
* Tactile switch(B1) 6mm THT KLS7-TS6601
* Audio connectors(J1,J2) 3.5mm ST-212 2pcs
* DC Power jack DS-201
* Power LED 3mm
* Power switch(SW2) Rocker-type 10.5x15mm
* Main case 100x50x25mm Gainta G1005025B+G1005025L
* WS2812B LED stripes or rings
* Wires and cables
* Power supply 5v 500mA, depends on the number of LEDs you have

Display 7.1:
* Led Display 7+1 Segment 2.0" SMD
* 74HC595PW TSSOP-16 or CD4094BPW TSSOP-16
* Resistor Array 270 SMD 0603x4 2pcs
* PLS2 connectors 5pin DS1025-01

## Schematic and PCB Layout

* Schema - version w/o display [Arduino_VU_Meter_2020_Schema.png](Arduino_VU_Meter_2020_Schema.png)

* Schema - version w display [Arduino_VU_Meter_2020_Display_Schema.png](Arduino_VU_Meter_2020_Display_Schema.png)
* Display schema var1 - 74HC595 [Arduino_VU_Meter_2020_DS_74HC595_Schema.png](Arduino_VU_Meter_2020_DS_74HC595_Schema.png)
* Display schema var2 - CD4094B [Arduino_VU_Meter_2020_DS_CD4094B_Schema.png](Arduino_VU_Meter_2020_DS_CD4094B_Schema.png)

* Main PCB gerber (version w/o display) - [Arduino_VU_Meter_2020_gerber.zip](gerber/Arduino_VU_Meter_2020_gerber.zip)

* Main + Display74HC595 PCB gerber - [Arduino_VU_Meter_2020_Display_gerber.zip](gerber/Arduino_VU_Meter_2020_Display_gerber.zip)

* Display74HC595 PCB gerber - [Arduino_VU_Meter_2020_DS_74HC595_gerber.zip](gerber/Arduino_VU_Meter_2020_DS_74HC595_gerber.zip)
* DisplayCD4094B PCB gerber - [Arduino_VU_Meter_2020_DS_CD4094B_gerber.zip](gerber/Arduino_VU_Meter_2020_DS_CD4094B_gerber.zip)


## Code

For compilation and uploading you will need Arduino IDE and additional libraries. If your configuration is different from mine, you will need to change the settings. There are a lot of detailed comments in the sketch.

[Arduino_VU_Meter_2020.ino](Arduino_VU_Meter_2020.ino)

### Changes

* Version 1.3
  * Add 7.1 segment numeric display

* Version 1.2
  * Store color settings in EEPROM (req EEPROM library)

* Version 1.1
  * Add auto change color scheme for Button1 pressed > 1sec (req arduino-timer-api library)

* Version 1.0
  *  Add 24 led 2 strips
  * Adopt setup value
  * Change Color Schemas (gradients, rainbows, etc. 16 in total)
