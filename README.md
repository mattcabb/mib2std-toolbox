# MIB2Std-toolbox
Attempt to access VW, Seat, Skoda MIB2Std Infotainment filesystem to run some scripts and customize few things.

## Supported devices (soon to be)
* VW Discover Media MIB2 Delphi
* VW Discover Media MIB2 Technisat

## Unsuported devices
* all MIB1 infotainment units
* VW Composition Media MIB2 (no navi, no Personal POI, no attack vector)
* VW Discover Pro MIB2 (go to https://github.com/jilleb/mib2-toolbox for a great tool)

## Risks
* Loosing warranty
* Messing up the system
* Bricking the headunit
* Makine the car inoperable
* 🔥🔥🔥

## Requirements
1. Supported infotainment unit
1. Enabled developer mode
1. Empty, FAT32 formatted SD card 

## Enabling developer mode
### with OBDeleven
https://www.youtube.com/watch?v=R9WlrkBioi8
1. Connect with module 5F.
1. Select `Change service` and select `Developemnt mode`.
1. Select `Adaptation`.
1. Select channel `Developer mode`.
1. Set it to `Activated`
1. Save new setting.

### with VCDS
1. Connect with module 5F.
1. Select `Security Access` and enter code `S12345`.
1. Select `Adaptation`.
1. Select channel `Developer mode`.
1. Set it to `Activated`
1. Save new setting.

## MIB2Std-toolbox Installation
1. Place all files in root directory of the SD card.
1. Turn the ignition on
1. Wait about 1 minute for the infotainment to fully boot up.
1. Insert card to the SD1 port in the glovebox.
1. Wait for `SD card 1: Software update` notification.
1. Go to `NAV` > `Setup` > `Manage Memory` > `Update my POIs` > `Update` > `Next`.
1. Wait for `Software update complete` notification and press `OK`.
1. Reboot the infotainment unit by pressing and holding volume control knob for about 10 seconds.
1. Wait about 1 minute for the infotainment to fully boot up.
1. Press and hold `MENU` button for 10 seconds unit the `Testmode menue` appears.
1. Go to `Green Engeneering Menu` > `mib2std-toolbox`.

## Known issues
* Well, it doesn't work yet!

## TODO
* Preatty much everything right now...
* VW Composition Media MIB2 - one could use radiostation logo DB update vector.
* Dumping interesing files to SD card
* Replacing system UI elements
* Replacing system SFX

## How it works
1. Infotainment unit recognizes content of the SD card as Personal-POI update
1. `./metainfo2.txt` file contains list of Variants that the update applyies to and paths for files specific for each variant (for example `./PersonalPOI/MIB2TSD`).
1. Next `./PersonalPOI/MIB2DE/metainfo2.txt` file is processed. Again it contains list of variants but also files&directories to copy, destination paths, checksums. Altering destination path will force custom `.esd` file to be coppied to the infotainment file system.
1. `mib2std-toolbox.esd` file is an additional green engeneering menu screen which gives you access to running custom scripts.

## Research files
1. `Research/variants.csv` - list of variants with carmaker, hardware producer, and other details.
