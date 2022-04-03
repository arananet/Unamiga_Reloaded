### minimig RTG core

This folder contains the latest minimig core for Unamiga Reloaded/ITX. This new core has been completely re-build from the base sources of mininig and then adapted (ported) to use the Unamiga Reloaded features (i2s audio, 24 video dac). The sources of the original core shipped with the Unamiga Reloaded get lost, so we had to rebuilt it from the original sources again and in the meantime, issues with the has been fixed.

The base directory is the old core that was shipped with the Unamiga Reloaded.

The minimig_menu is just the english version of the minimig core menu.

### Instructions for the new core

Place the MINIMIG_b6.ua2 file into the cores (back SD) of your Unamiga Reloaded. Place or replace the file 832OSDAD.bin on the fpga SD.

Also this core requires or better works with Kickstart 3.2 (rename it as kick32.rom), for copyright restrictions we cannot share the kick32.rom here.

See the wiki for screen mode functional keys instructions.

### Special greetings

All the kudos to Ramón Martinez a.k.a Rampa069 who has ported the core from the latest sources of the mininig core( Alistair Robinson implementation) http://retroramblings.net/?page_id=1422. 

This new release fixes:
RTG on specific screen modes.
Fix the audio that has issues on a few games that were detected.
Speed up read and write access to the fpga SD.

We also like to thank Neuro (Aitor) who ported the original core of minimig included on the Unamiga Reloaded.


