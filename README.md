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

## Firmware Updating

* See instructions in firmware folders inside /dst