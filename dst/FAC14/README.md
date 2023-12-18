# FAC14 Firmware Updating

<img width="1173" alt="image" src="https://github.com/FactoryOptic/UPDI/assets/78292477/b7626299-5fdc-41b0-b9d5-b1f4dc0597b1">

## Connecting UPDI to board

* FAC34 Board with USB A to USB C cable, connected USB A to PC (for power only)
<img width="1052" alt="image" src="https://github.com/FactoryOptic/UPDI/assets/78292477/458bf80b-2e56-494b-9f28-2e90dc18c6ae">
* USB C to USB C cable from FAC34 to FAC14
* [Paul Evans UPDI Programmer](https://www.tindie.com/products/leonerd/avr-updi-programmer-with-12v/)
<img width="1221" alt="image" src="https://github.com/FactoryOptic/UPDI/assets/78292477/89807cac-cd6e-473a-a7c5-b0338bb53009">

The UPDI programmer should have black (GND) and yellow (UPDI) wires. Connect this to GND & UPDI on FAC34.

note: ch340 not happy with the FAC34 board

## Update from Arduino, from source

* If compiling from source, setup the following options in Arduino

  * Board: ATTINY3224/...
  * Chip: ATTiny1624
  * Clock: 10MHz
  * millis()/micros() TCB1
  * Startup Time: 64mS
  * COM Port: COM9 (or your COM port, see device manager)

* Hit upload

## Upload hex file

* Copy `fac14.hex` to `c:\`
* Open terminal
* CD to directory where python3 is located. (best to find this by first uploading the blink example to ATTiny device and seeing where this file is located)
  * `cd C:\Users\pc\AppData\Local\Arduino15\packages\megaTinyCore\tools\python3\3.7.2-post1\`
* Run firmware upload (modify location of prog.py as needed and location of fac22v3firmware.hex as needed)
  * `python3 -u C:\Users\pc\AppData\Local\Arduino15\packages\megaTinyCore\hardware\megaavr\2.6.10/tools/prog.py -t uart -u COM5 -b 230400 -d attiny1624 --fuses 0:0b00000000 2:0x02 6:0x07 7:0x00 8:0x00 -fC:\fac14.ino.hex -a write -v`

* A successful upload should cause LED (LED4 HB2) to blink about 1hz at 10% duty cycle.
* For reference, the terminal output should be similar to this: updi_upload_output.md

## Write protection

* Set lockbits, open Terminal and type the following
  * `pymcuprog -t uart -u COM9 -d attiny1624 write -m lockbits -l 0`
  * Response should look like this:
  ```
  Connecting to SerialUPDI
  Pinging device...
  Ping response: 1E942A
  Writing literal values...
  Done.
  ```

* Confirm lockbits are set
  * `pymcuprog -t uart -u COM9 -d attiny1624 read -m user_row`

* If it shows the user row, the device is not protected

* Response should look like this:
```
  Connecting to SerialUPDI
  The device is in a locked state and is not accessible; a chip erase is required.
  Locked AVR UPDI devices can:
   - be unlocked using command: erase --chip-erase-locked-device
   - write user row values using command: write -m user_row --user-row-locked-device
```

## Erase CHIP if not blank or if you need to start over

* From terminal
  * `pymcuprog -t uart -u COM9 -d attiny1624 erase -C`
