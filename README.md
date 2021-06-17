# Unamiga Reloaded
This main repo contains the lastest binary cores available in UA2 format and usb controller firmware for the Unamiga Reloaded.

The USB controller firmware has his own custom readme for upgrade instructions.

### About cores

Some cores requires another SD card because their special filesystem, for example the MSX and the SPECCY (next) cores. The MINIMIG (AMIGA) SD could coexist with others like NES or C64. So make sure you put the correct SD card on the FPGA socket (the one on the front) with the required files for the choosen core and the back SD that will contain all the UA2 core files.

By default all the Unamiga Reloaded are shipped with two SD cards completely free without extra charge.

### SD cards distribution

### Amstrad core:
You can use the MINIMIG core SD, just create a new folder on the root called AMSTRAD and put all the roms.

### Atari800 core:
You can use the MINIMIG core SD, just create a new folder on the root called ATARI and put all the roms.

### MINIMIG:
Requires custom SD card filesystem for the Minimig core. The SD card included as a gift already has the minimig required filesystem.

### C64 core:
You can use the MINIMIG core SD, just create a new folder on the root called C64 and put all the prg or taps inside.

### NES core:
You can use the MINIMIG core SD, just create a new folder on the root called NES and put all the roms.

### SNES core:
You can use the MINIMIG core SD, just create a new folder on the root called SNES and put all the roms.

### VideoPac core:
You can use the MINIMIG core SD, just create a new folder on the root called VIDEOPAC and put all the roms.

### MSX core:
Requires a custom SD card because his partitions configurations. The SD image required for the core can be downloaded from here: https://www.zxuno.com/forum/viewtopic.php?t=3976.

### ZXNEXT core:
Requires a custom SD card because his partitions configurations. The SD image required for the core can be download from the original project, here: https://www.specnext.com/latestdistro/

### KypZX48:
You can use the MINIMIG core SD, just create a new folder on the root called ZX48 and put all the roms.

### Usb controller programming

On the cores/USB controller there are instructions on how to flash/upgrade the STM32 USB controller.

https://github.com/arananet/Unamiga_Reloaded/tree/main/cores/USB%20Controller

### Special thanks and Kudos

Thanks to @benitoss, Neuro (aka neurorulez), Rampa, Kypp among others for porting the cores to the Unamiga Reloaded.

Thanks to Miguel Fides for the STM32 USB stack specially made for the Unamiga Reloaded.

Thanks to Victor Trucco for create the multicore system.

Thanks to the Unamiga Reloaded users for the patience and the huge support to keep this project alive.

### Cores source code

These cores are ports made for the FPGA Team, there are some sources on the repo: https://github.com/UnAmigaReloaded-fpga

The FPGA team are the ones that have the last additions. This repo is only for binary cores.
