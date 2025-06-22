If you have a flipper zero you can simply download this app: https://lab.flipper.net/apps/avr_isp
Then drop in your SD card into folder: apps_data/avr_isp
- Phasor_pcb.avr
- phasor_pcb_eeprom.hex
- phasor_pcb_flash.hex

Connect your flipper zero gpio to the SPI bus on the PCB and flash the ATMega88 using the app.



       FLIPPER ZERO --- PCB ---          --- PCB --- FLIPPER ZERO
                                 ______
         PIN 03  --  MISO --->  | x  x |  ----- VCC  -- PIN 09
         PIN 05  --  SCK <----  | x  x    ----> MOSI  -- PIN 02
         PIN 06  --  RST <----  | x  x |  ----- GND -- PIN 11
                                 ------