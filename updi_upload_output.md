C:\Users\pc\AppData\Local\Arduino15\packages\megaTinyCore\tools\python3\3.7.2-post1>python3 -u C:\Users\pc\AppData\Local\Arduino15\packages\megaTinyCore\hardware\megaavr\2.6.10/tools/prog.py -t uart -u COM9 -b 230400 -d attiny1616 --fuses 0:0b00000000 2:0x02 6:0x07 7:0x00 8:0x00 -fC:\fac22v3firmware.hex -a write -v

```
SerialUPDI
UPDI programming for Arduino using a serial adapter
Based on pymcuprog, with significant modifications
By Quentin Bolsee and Spence Konde
Version 1.2.3 - Jan 2022
Using serial port COM9 at 230400 baud.
Target: attiny1616
Set fuses: ['0:0b00000000', '2:0x02', '6:0x07', '7:0x00', '8:0x00']
Action: write
File: C:\fac22v3firmware.hex
pymcuprog.programmer - INFO - Setting up programming session for 'attiny1616'
pymcuprog.deviceinfo.deviceinfo - INFO - Looking for device attiny1616
pymcuprog.serialupdi.physical - INFO - Opening port 'COM9' at '115200' baud
pymcuprog.serialupdi.link - INFO - STCS 08 to 0x03
pymcuprog.serialupdi.link - INFO - STCS 06 to 0x02
pymcuprog.serialupdi.link - INFO - LDCS from 0x00
pymcuprog.serialupdi.link - WARNING - UPDI init failed: Can't read CS register.
pymcuprog.serialupdi.physical - INFO - Sending double break
pymcuprog.serialupdi.physical - INFO - Double-break sent. Retrying.
pymcuprog.serialupdi.physical - INFO - Opening port 'COM9' at '115200' baud
pymcuprog.serialupdi.link - INFO - STCS 08 to 0x03
pymcuprog.serialupdi.link - INFO - STCS 06 to 0x02
pymcuprog.serialupdi.link - INFO - LDCS from 0x00
pymcuprog.serialupdi.link - INFO - UPDI init OK
pymcuprog.serialupdi.link - INFO - STCS 06 to 0x02
pymcuprog.serialupdi.link - INFO - Setting UPDI clock to 8 MHz
pymcuprog.serialupdi.link - INFO - STCS 02 to 0x09
pymcuprog.serialupdi.physical - INFO - Switching to '230400' baud
pymcuprog.serialupdi.application - INFO - SIB: 'tinyAVR P:0D:0-3M2 (01.59B15.0)'
pymcuprog.serialupdi.application - INFO - Device family ID: 'tinyAVR'
pymcuprog.serialupdi.application - INFO - NVM interface: 'P:0'
pymcuprog.serialupdi.application - INFO - Debug interface: 'D:0'
pymcuprog.serialupdi.application - INFO - PDI oscillator: '3M2'
pymcuprog.serialupdi.application - INFO - Extra info: '(01.59B15.0)'
pymcuprog.serialupdi.application - INFO - Using 16-bit UPDI
pymcuprog.serialupdi.link - INFO - LDCS from 0x00
pymcuprog.serialupdi.application - INFO - PDI revision = 0x02
pymcuprog.serialupdi.link - INFO - LDCS from 0x0B
pymcuprog.serialupdi.application - INFO - Device ID from pyupdi = '1E9421' rev 'B'
pymcuprog.serialupdi.link - INFO - LDCS from 0x0B
pymcuprog.serialupdi.application - INFO - Already in NVM programming mode
pymcuprog.nvm - INFO - No specific initializer for this provider
Pinging device...
pymcuprog.programmer - INFO - Reading device ID...
pymcuprog.serialupdi.application - INFO - SIB: 'tinyAVR P:0D:0-3M2 (01.59B15.0)'
pymcuprog.serialupdi.application - INFO - Device family ID: 'tinyAVR'
pymcuprog.serialupdi.application - INFO - NVM interface: 'P:0'
pymcuprog.serialupdi.application - INFO - Debug interface: 'D:0'
pymcuprog.serialupdi.application - INFO - PDI oscillator: '3M2'
pymcuprog.serialupdi.application - INFO - Extra info: '(01.59B15.0)'
pymcuprog.serialupdi.application - INFO - Using 16-bit UPDI
pymcuprog.serialupdi.link - INFO - LDCS from 0x00
pymcuprog.serialupdi.application - INFO - PDI revision = 0x02
pymcuprog.serialupdi.link - INFO - LDCS from 0x0B
pymcuprog.serialupdi.application - INFO - Device ID from pyupdi = '1E9421' rev 'B'
pymcuprog.nvm - INFO - Device ID: '1E9421'
pymcuprog.nvm - INFO - Device revision: 'B'
pymcuprog.nvm - INFO - Device serial number: 'b'304e364d354d4ac9171f''
Ping response: 1E9421
Setting fuse 0x0=0x0
Writing literal values...
pymcuprog.programmer - INFO - Write...
pymcuprog.programmer - INFO - Writing 1 bytes of data to fuses...
pymcuprog.programmer - INFO - Write complete.
Verifying literal values...
pymcuprog.programmer - INFO - Reading 1 bytes from fuses...
pymcuprog.programmer - INFO - Verifying...
Action took 0.04s
Setting fuse 0x2=0x2
Writing literal values...
pymcuprog.programmer - INFO - Write...
pymcuprog.programmer - INFO - Writing 1 bytes of data to fuses...
pymcuprog.programmer - INFO - Write complete.
Verifying literal values...
pymcuprog.programmer - INFO - Reading 1 bytes from fuses...
pymcuprog.programmer - INFO - Verifying...
Action took 0.03s
Setting fuse 0x6=0x7
Writing literal values...
pymcuprog.programmer - INFO - Write...
pymcuprog.programmer - INFO - Writing 1 bytes of data to fuses...
pymcuprog.programmer - INFO - Write complete.
Verifying literal values...
pymcuprog.programmer - INFO - Reading 1 bytes from fuses...
pymcuprog.programmer - INFO - Verifying...
Action took 0.03s
Setting fuse 0x7=0x0
Writing literal values...
pymcuprog.programmer - INFO - Write...
pymcuprog.programmer - INFO - Writing 1 bytes of data to fuses...
pymcuprog.programmer - INFO - Write complete.
Verifying literal values...
pymcuprog.programmer - INFO - Reading 1 bytes from fuses...
pymcuprog.programmer - INFO - Verifying...
Action took 0.03s
Setting fuse 0x8=0x0
Writing literal values...
pymcuprog.programmer - INFO - Write...
pymcuprog.programmer - INFO - Writing 1 bytes of data to fuses...
pymcuprog.programmer - INFO - Write complete.
Verifying literal values...
pymcuprog.programmer - INFO - Reading 1 bytes from fuses...
pymcuprog.programmer - INFO - Verifying...
Action took 0.03s
Finished writing fuses.
Chip/Bulk erase,
Memory type eeprom is conditionally erased (depending upon EESAVE fuse setting)
Memory type flash is always erased
Memory type lockbits is always erased
...
pymcuprog.programmer - INFO - Erase...
pymcuprog.serialupdi.nvm - INFO - Chip erase using NVM CTRL
Erased.
Action took 0.02s
Writing from hex file...
Writing flash...
pymcuprog.programmer - INFO - Write...
pymcuprog.programmer - INFO - Writing 5533 bytes of data to flash...
[==================================================] 87/87
pymcuprog.programmer - INFO - Write complete.
Action took 1.09s
Verifying...
pymcuprog.programmer - INFO - Reading 5534 bytes from flash...
[==================================================] 11/11
pymcuprog.programmer - INFO - Verifying...
Verify successful. Data in flash matches data in specified hex-file
Action took 0.35s
pymcuprog.serialupdi.application - INFO - Leaving NVM programming mode
pymcuprog.serialupdi.application - INFO - Apply reset
pymcuprog.serialupdi.link - INFO - STCS 59 to 0x08
pymcuprog.serialupdi.application - INFO - Release reset
pymcuprog.serialupdi.link - INFO - STCS 00 to 0x08
pymcuprog.serialupdi.link - INFO - STCS 0C to 0x03
pymcuprog.serialupdi.physical - INFO - Closing port 'COM9'
```