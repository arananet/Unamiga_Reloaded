# Unamiga_Reloaded
This main repo contains the lastest cores available and usb controller firmware for the Unamiga Reloaded.

The USB controller firmware has his own custom readme for upgrade instructions.

### About cores

Some cores requires another SD card because their special filesystem, for example the MSX and the SPECCY (next) cores. The MINIMIG (AMIGA) SD could coexist with others like NES or C64. So make sure you put the correct SD card on the FPGA socket (the one on the front) with the required files for the choosen core and the back SD that will contain all the UA2 core files.

By default all the Unamiga Reloaded are shipped with two SD cards completely free without extra charge.

### SD cards distribution: 

### MINIMIG:
Requires custom SD card filesystem for the Minimig core. The SD card included as a gift already has the minimig required filesystem.

### C64 core:
You can use the MINIMIG core SD, just create a new folder on the root called C64 and put all the prg or taps inside.

### NES core:
You can use the MINIMIG core SD, just create a new folder on the root called NES and put all the roms.

### MSX core:
Requires a custom SD card because his partitions configurations. The SD image required for the core can be downloaded from here: https://www.zxuno.com/forum/viewtopic.php?t=3976.

### ZXNEXT core:
Requires a custom SD card because his partitions configurations. The SD image required for the core can be download from the original project, here: https://www.specnext.com/latestdistro/

# Special thanks and Kudos

Thanks to @benitoss, Neuro (aka neurorulez), Rampa, Kypp among others for porting the cores to the Unamiga Reloaded.

Thanks to Miguel Fides for the STM32 USB stack specially made for the Unamiga Reloaded.

Thanks to Victor Trucco for create the multicore system.

Thanks to the Unamiga Reloaded users for the patience and the huge support to keep this project alive.

2021 - @edu_arana
