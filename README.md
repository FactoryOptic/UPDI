# UPDI
Firmware updating UPDI

## Prerequisites

### Software

* Install Arduino v1.8.19
* Add to additional boards manager: `http://drazzy.com/package_drazzy.com_index.json`
* Update/install boards manager `megatinycore` by Spense Konde version 2.6.10
* Install python and pip
* Install pymcuprog https://pypi.org/project/pymcuprog/

### Hardware

#### UDPI Programmer

##### Modify a usb to serial (CH340G highly recommended)

* See https://github.com/SpenceKonde/AVR-Guidance/blob/master/UPDI/jtag2updi.md
* Get CH340G on ebay for about $1
* Add a resistor and diode, some wire jumpers

##### Build your own

* https://hackaday.io/project/189724-ch340-hv-serialupdi-programmer

##### Buy

* https://www.tindie.com/products/kdcircuits/updi-to-usb-serial-programming-adapter/

## Hookup and Powering up boards 

<img width="621" alt="image" src="https://github.com/FactoryOptic/UPDI/assets/78292477/e828c22d-2228-46c2-aa55-ced316a80ea4">

1. Install Teensy Micromod to FAC22
2. Install microSD card to FAC22
3. Connect both boards together with 4 pin cable (CUI terminal blocks)
4. Connect LED Board (FAC32) to FAC30 (optional)
5. Connect PoE Power to FAC30 (port labeled `From Switch`) to supply power to both boards

### Debugging power rails

* FAC30 is PoE compliant for 802.3bt up to class 8 (72W) but will work at 802.3af (12W)
* FAC30 will make 12V and output it on the 4 pin header, pin 1 +12V, pin 2 is GND. Cable has GND at RED, +12V as BLACK.
* FAC30 will make 3.3V (linear regulator)
* FAC22 will make 5V from 12V (switching regulator)
* FAC22 will make 3.3V from 5V (linear regulator) 

## Firmware Updating

* See instructions in firmware folders inside /dst
