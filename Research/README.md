# Research

## Variants
`Research/variants.csv` - list of variants with carmaker, hardware producer, and other details.

## SD card root paths
`/media/mp000`<br>
`/media/mp001`.

## GEM
`.esd` files path: `/tsd/etc/persistence/esd`.

## Override SWaP
File `tmp/hmi/runHMI.sh` contains lines<br>
`# Override SWaP`<br>
`# VMOPTIONS="$VMOPTIONS -Dde.vw.mib.asl.internal.exlap.overrideSWaP"`<br>
which indicates that there's a flag to ignore SWaP codes for development purposes when running the software on virtual machine.
