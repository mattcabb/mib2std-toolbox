# Research

## Headunit variants
`Research/variants.csv` - list of variants with carmaker, hardware producer, and other details.

## SD card root paths
(found in update files)<br>
`/media/mp000`<br>
`/media/mp001`

## GEM - Green Engineering Menu
(found in update files)<br>
`.esd` files path: `/tsd/etc/persistence/esd`

## System sounds
(found in update files)<br>
`/tsd/etc/waveplayer/sound/*.wav` - TOUCHSCREEN2.wav, NAVPOI.wav, WARNING1.wav<br>
`/tsd/etc/speech/tts/tones/Tones22kHz16Bitmono/tone_error.wav`

## File structure
(without `tree` commnad)<br>
`find / | sed -e "s/[^-][^\/]*\// |/g" -e "s/|\([^ ]\)/|-\1/" > /media/mp000/tree.txt`

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

## Override SWaP
File `tmp/hmi/runHMI.sh` contains lines<br>
`# Override SWaP`<br>
`# VMOPTIONS="$VMOPTIONS -Dde.vw.mib.asl.internal.exlap.overrideSWaP"`<br>
which indicates that there's a flag that might ignore FEC/SWaP codes for development purposes when running the software on virtual machine. Can it also be triggered when the HU is runnig?
