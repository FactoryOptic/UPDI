# FAC30 Firmware Updating

## Connecting UPDI to board

<img width="594" alt="image" src="https://github.com/FactoryOptic/UPDI/assets/78292477/264b2f77-2a80-48a7-8706-b7a8d123f120">

The UPDI programmer should have black (GND) and yellow (UPDI) wires. Connect this to board via the 2 pin. It should fit into the board and my need some side pressure to make a good contact during programming. The UPDI pin (YEL) should connect as shown in the photo. 

## Update from Arduino, from source

* If compiling from source, setup the following options in Arduino

  * Board: ATTINY3224/...
  * Chip: ATTiny1614
  * Clock: 10MHz
  * millis()/micros() TCB1
  * Startup Time: 64mS
  * COM Port: COM9 (or your COM port, see device manager)

* Hit upload

## Upload hex file

* Copy `fac30_firmware_1614.hex` to `c:\`
* Open terminal
* CD to directory where python3 is located. (best to find this by first uploading the blink example to ATTiny device and seeing where this file is located)
  * `cd C:\Users\pc\AppData\Local\Arduino15\packages\megaTinyCore\tools\python3\3.7.2-post1\`
* Run firmware upload (modify location of prog.py as needed and location of fac22v3firmware.hex as needed)
  * `python3 -u C:\Users\pc\AppData\Local\Arduino15\packages\megaTinyCore\hardware\megaavr\2.6.10/tools/prog.py -t uart -u COM9 -b 230400 -d attiny1614 --fuses 0:0b00000000 2:0x02 6:0x07 7:0x00 8:0x00 -fC:\fac30_firmware_1614.hex -a write -v`

* A successful upload should cause LED (LED1) to blink about 1hz at 10% duty cycle.
* For reference, the terminal output should be similar to this: updi_upload_output.md

## Write protection

* Set lockbits, open Terminal and type the following
  * `pymcuprog -t uart -u COM9 -d attiny1614 write -m lockbits -l 0`
  * Response should look like this:
  ```
  Connecting to SerialUPDI
  Pinging device...
  Ping response: 1E9422
  Writing literal values...
  Done.
  ```

* Confirm lockbits are set
  * `pymcuprog -t uart -u COM9 -d attiny1614 read -m user_row`

* If it shows the user row, the device is not protected

* Response should look like this:
```
  Connecting to SerialUPDI
  The device is in a locked state and is not accessible; a chip erase is required.
  Locked AVR UPDI devices can:
   - be unlocked using command: erase --chip-erase-locked-device
   - write user row values using command: write -m user_row --user-row-locked-device
```

* If that is a match and the LED heartbeat is blinking, all done.

## Erase CHIP if not blank or if you need to start over

* From terminal
  * `pymcuprog -t uart -u COM9 -d attiny1614 erase -C`
