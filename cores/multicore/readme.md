On this folder you will find the BIN file to flash the STM32 that controls the multicore and the JIC multicore for the FPGA.

Follow the next instructions to flash the multicore on the onboard STM32 and the multicore on the FPGA.

### Required parts

USB BLASTER programmer (recommended for both, fixed and multicore support):

https://es.aliexpress.com/item/4000428690459.html?spm=a2g0o.productlist.0.0.56eeaa6csAYyPO&algo_pvid=6985defa-48ba-4692-abb4-307d74d6e8df&algo_expid=6985defa-48ba-4692-abb4-307d74d6e8df-11&btsid=0b0a182b16038866260806565e01e2&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_

STLINK programmer

https://es.aliexpress.com/item/1005002543516185.html?spm=a2g0o.productlist.0.0.77d8eb2faFbAfb&algo_pvid=207c1be0-d542-4d51-a298-2e5d1481f97e&aem_p4p_detail=20211008121043127481405555100042292587&algo_exp_id=207c1be0-d542-4d51-a298-2e5d1481f97e-4&pdp_ext_f=%7B%22sku_id%22%3A%2212000021074140345%22%7D

On the ITX version, in order to connect the stm32 on the FPGA you will require a little IDC 2x5 female to female cable link this one:

https://es.aliexpress.com/item/32700048506.html?spm=a2g0o.productlist.0.0.310b601fW3osbp&algo_pvid=af77932d-76d4-4b9a-b921-a23483ff0068&algo_expid=af77932d-76d4-4b9a-b921-a23483ff0068-8&btsid=0bb0623e16038875348986088ed701&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_

The female to female IDC cable is required because the onboard STM32 on the Unamiga ITX act as a USB BLASTER. So you need this physical connection to allow the STM32 to temporary flash the cores into the FPGA.

Connect the IDC cable like this image.

<img src="https://github.com/arananet/Unamiga_Reloaded/blob/main/images/multicoreitx.jpg?raw=true" width="400"/>

### How the Multicore works?

The Unamiga Reloaded and ITX uses a STM32 onboard to provide the multicore support. The Multicore works as other fpga solutions, by showing a MENU, blue on this case, at the power up. Each time you power off the machine and start over, the same blue menu will appear on screen.

In order to use the multicore support among the required steps detailed here, you will require an additional SD card to store each core in UA2 format. You just download each core in UA2 format from the CORES folder and drop them on the root of the multicore sd card. 

The multicore supports needs two steps, one is flashing the stm32 firmware made by Victor Trucco and flashing the multicore menu on the FPGA. On the CORES/MULTICORE folder there is a JIC file that's the one we need to flash on the FPGA and a BIN file that is required to burn on the STM32.

#### Note: By replacing the initial core, on the ITX for example, you will lost the original core, on this case the minimig and will be replaced by the multicore menu. Is the multicore menu, when you select the core that you want to load, the one in charge of temporary flash the selected core into the FPGA. As we mentioned before, Each time you power off the machine and start over, the same blue menu will appear on screen.

### Flashing the STM32

In order to flash the multicore firmware from Victor Trucco on the unamiga, you will need to download the STM32Cubeprogrammer (requires the STLINK usb). There is also another software from STLINK, here is the alternative https://www.st.com/en/development-tools/stsw-link004.html.

https://www.st.com/en/development-tools/stm32cubeprog.html

1-Install the Cubeprogrammer software.

2-Download the multicore bin file from the CORES/MULTICORE folder.

3-Connect the STLINK to the required pins. The pins are marked on the pcb silkcreen, each pin must go the the respective one on the STLINK.

VCC > VCC

GND > GND

SWIO > SWIO

SWCLK > CLK OR SWCLK

Find the required pins on the Reloaded and ITX using the next images.

#### Unamiga Reloaded:

<img src="https://github.com/arananet/Unamiga_Reloaded/blob/main/images/multicorereloaded.png?raw=true" width="400"/>

#### Unamiga ITX:

<img src="https://github.com/arananet/Unamiga_Reloaded/blob/main/images/multicoreitx.png?raw=true" width="400"/>

##### Important note (only for Unamiga ITX version):
In order to program the stm32 for multicore, you will need to remove the FPGA module from the board and then follow the next procedure.

4-Connect to your computer and open the Cube programmer software.

5-Click on the CONNECT buttom from the right panel. If everything goes OK it will connect and you will see a log update on the main screen. Select the Open File TAB and choose the BIN file downloaded from this github. Then hit the DOWNLOAD button and the STLINK will start programming the core.

Note: Since we are using the STLINK we don't need to change the JUMPERS from the STM32.

Once it finish, you will see a DOWNLOAD COMPLETE on the main log screen.

If everything goes OK, you have succefully flashed the firmware on the STM32 bluepill board.

### Flashing the multicore core.

In order to flash the multicore core on the FPGA we will need the USB BLASTER and the QUARTUS PROGRAMMING SOFTWARE. Follow the next instructions to properly setup it.

1-Download and install the Altera Quartus 13.1:

https://fpgasoftware.intel.com/13.1/

2-Download the multicore core JIC file from the CORES/MULTICORE folder.

3-Connect the USB BLASTER on your computer, now each version of the board has his own method for core programming.

For Unamiga Reloaded use these pins:

<img src="https://github.com/arananet/Unamiga_Reloaded/blob/main/images/fpgapinsreloaded.png?raw=true" width="400"/>

Note: You will need to connect to the USB BLASTER with duponds cables in order to establish the connection.

For the Itx version, connect the USB BLASTER using the IDC connector on the FPGA of the UNAMIGA (the black board) make sure you connect it properly (check the image below). Power-up the UNAMIGA. 

<img src="https://github.com/arananet/Unamiga_A500_multicore/blob/master/images/flashing.png?raw=true" width="400"/>

4-Open the QUARTUS program, make clic on the ADD FILE button, browse to the folder where you you download the JIC file and choose it. Select the two check box button (marked on the image).

5-Finally hit the START button to start flashing the new core. You will see that the progress bar will start increasing. Once it's at the 100% you will have the new core burned permatelly on the FPGA. Finally if it hits the 100%, disconnect the USB blaster from the UNAMIGA header and  connect the IDC from the HEADER to the FPGA.

<img src="https://github.com/arananet/Unamiga_A500_multicore/blob/master/images/quartus.png?raw=true" width="400"/>

If all goes OK turn on the UNAMIGA and you will see a blue little window with the cores that you have downloaded from the step before.

<img src="https://github.com/arananet/Unamiga_A500_multicore/blob/master/images/multicoremenu.png?raw=true" width="350"/>

Once we got all setted up, with the stm32 flashed, the fpga with the multicore flashed, the sd card on the multicore socket, the IDC little cable connected, powerup the unamiga header and you will see the cores in a list. To select the required core to start using that machine/console, use the ARROW keys and ENTER to choose the selected core one.
