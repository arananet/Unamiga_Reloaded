### Usb controller firmware instructions

This folder contains the binary file required for the STM32 that manage the USB devices. The current firmware is the first release but there might be further versions that will include support for more usb devices.

The current firmware controls USB keyboards, USB mouses, and SNES usb joypads (clones). 

On the test bench we use the Logitech K120 kit (with usb mouse), also the LogiLink ID0063 mouse and the SNES controller available on aliexpress. The SNES controller has also mapped some keyboards keys in order
to use them on different cores. The default mapping of buttons is based on the minimig one, by this I refer to the two buttons of the minimig core.

### Here are the links.

Logitech K120 https://www.amazon.es/Logitech-MK120-teclado-QWERTY-Espa%C3%B1ol/dp/B00564GWEI/ref=sr_1_3?__mk_es_ES=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=logitech+k120&qid=1623917142&sr=8-3

LogiLink ID0063 Mouse https://www.amazon.es/LogiLink-ID0063-Rat%C3%B3n-%C3%B3ptico-1000dpi/dp/B005OEKOIA/ref=sr_1_2?__mk_es_ES=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=logilink+raton&qid=1623917038&sr=8-2

SNES usb controller https://es.aliexpress.com/item/1005001698443179.html?spm=a2g0o.productlist.0.0.673647degorWWd&algo_pvid=f51eed73-a110-45a3-bc51-b151cfd9a4f1&algo_exp_id=f51eed73-a110-45a3-bc51-b151cfd9a4f1-4 

### Upgrading the STM32 firmware

In order to upgrade the STM32 USB stack you will requiere a STLINK programmer like this one: https://es.aliexpress.com/item/32887597480.html?spm=a2g0o.productlist.0.0.69b5eb2faM0ocV&algo_pvid=5b086bf2-98c3-4f10-b786-5ff86031ccb3&algo_exp_id=5b086bf2-98c3-4f10-b786-5ff86031ccb3-0

Also you will require the STM32Cubeprogrammer https://www.st.com/en/development-tools/stm32cubeprog.html or another compatible with STM32F105 series.

### Steps to upgrade the firmware

Download the last version of the firmware from the files directory on this repository (check the last version on the next table).

| Name                       | Version                   |
| -------------------------- | ------------------------- |
| unamiga_stm32f105.hex      | 0.2                       |
| unamiga_stm32f105_ori.hex  | 0.1 Init version          |

1-Open the stm32cubeprog and click from the top  Open File tab, then choose the bin file that you already downloaded.

2-Connect the STM32 STLINK programmer to the usb port of your computer.

3-Connect the programming pins following the next image (you will need to hold the four pins to complete the next step).

<img src="https://github.com/arananet/Unamiga_Reloaded/blob/main/images/programming.png?raw=true" width="400"/>

4-On the stm32cubeprog hit the Green CONNECT button from the right.

5-If the stm32 is detected, you will see that the main log is updated. If not you will receive an error.

6-If connection has been stablished with the STM32 controller the next step is to hit the Download button.

7-Once the programming is complete you can unplug the programming pins, and try the new firmware by power up the Unamiga Reloaded.

8-You could revert to the original firmware by doing the step 1-7 again.

### Copyright notice

Firmware completely developed by Miguel Fides and tested by Edu Arana. The use of this firmware is prohibited in another platforms. The only device compatible with this firmware is the Unamiga Reloaded and Unamiga MiniITX.
