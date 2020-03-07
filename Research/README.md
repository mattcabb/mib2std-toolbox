# Research

## Variants
`Research/variants.csv` - list of variants with carmaker, hardware producer, and other details.

## SD card root paths
`/media/mp000`<br>
`/media/mp001`.

## GEM
`.esd` files path: `/tsd/etc/persistence/esd`.

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
which indicates that there's a flag to ignore SWaP codes for development purposes when running the software on virtual machine.
