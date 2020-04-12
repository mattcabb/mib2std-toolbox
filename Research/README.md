# Research

## Headunit variants
`Research/variants.csv` - list of variants with carmaker, vendor, options, P/Ns. Might not be 100% accurate!<BR>

As can be seen in `metainfo2.txt` there are two MIB2std vendors: TechniSat and Delphi. Each is making devices in different variants. Variant is 5 digit long number which most likely contains specification of the head unit (vendor, target car maker, GPS, DAB, Sirius, Speech recogn...).

```
???xx
172 = VW
372 = Skoda
472 = Seat
```
```
xxx?x
0, 1, 2 = TechniSat
4, 5, 6, 7 = Delphi (Delphi might be +4 to current value)
```

When trying to assign variants to head units, features, and P/Ns - there's a difficulty: P/N is not vendor exclusive. For example device `3Q0 035 846` is made by both vendors. Also I can not find any indication of the device variant in hidden menus. The only way that I saw so far is by placing unsupported update in the SD port and waiting for variant conflict message to pop up.

Why this is important?
TechniSat and Delphi are using different file structures, separate firmware updates, even PPOI db locations are different:<br>
TechniSat = `/tsd/var/nav/personalpoi/`<br>
Delphi = `/media/swdl/packages/PersonalPOI/Package`

## SD card root paths
(found in update files)<br>
TechniSat  - `/media/mp000`; `/media/mp001`<br>
Delphi - `/sdc1`; `/sdc2`

## GEM - Green Engineering Menu
(found in update files)<br>
TechniSat  - `/tsd/etc/persistence/esd/*.esd`<br>
Delphi - `/apps/GEM_PROD/*.esd`

## System sounds
(found in update files)<br>
TechniSat  - `/tsd/etc/waveplayer/sound/*.wav`; `/tsd/etc/speech/tts/tones/Tones22kHz16Bitmono/*.wav`<br>
Delphi - ???

## File structure
(without `tree` commnad)<br>
TechniSat  - `find / | sed -e "s/[^-][^\/]*\// |/g" -e "s/|\([^ ]\)/|-\1/" > /media/mp000/tree.txt`<br>
Delphi - ???

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
