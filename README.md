# FrontBench
Using Frontier: Elite 2 as benchmarking software for the Atari ST line of computers

This Python 3 script will patch the Shareware version of the Atari ST version of Frontier: Elite 2 to count frames between two specific places in the intro sequence. A faster computer/memory combination should be able to draw more frames between these two points and thus appear smoother.

It's not a rigorous benchmark, but it's a decent representation of an AltRAM-supporting game that is heavy on memory access and CPU load. It provides a good visual feedback too. Frontier does not use an FPU.

*Please note*, Frontier uses the vertical blank to time the intro sequence. The sequence is therefore shorter on 60Hz machines. This will give a frame count ~17% lower than on an otherwise identical configuration running at 50Hz. This needs to be taken into account when comparing results.

Frontier (and FrontBench) requires a 1MB machine.

# Results

Some examples I've collected:


#### PAL (50Hz VBL)

Stock 8MHz PAL STE: ~880 frames [various].  
8MHz PAL ST with 68010: ~890 frames [exxos].  

8MHz PAL ST + STORM AltRAM: frames ~905 [czietz].  
8MHz PAL Mega ST4 with 68010 + AltRAM: frames ~930 [frank.lukas].  

16MHz PAL STE: ~940 frames.  
32MHz PAL STE: ~1100 frames [exxos].  
64MHz PAL H4 ST: ~1155 frames [exxos].  

16MHz PAL STE + 7MB/s AltRAM: ~1320 frames.  

16MHz PAL(?) MegaSTE (L2 cache): ~1480 frames [rubber_johnnie].  

16MHz PAL Mega ST + Hypercache: ~1505 frames [czietz].  

50MHz PAL Mega ST4, PAK68/3-030 (no Fastram no L2 cache): ~1500 frames [frank.lukas].  

Stock Falcon @50Hz 50Hz RGB mode: ~2070 frames.  

50MHz PAL Mega ST+TF536 (TTRAM): ~2440 frames [coonsgm].  
50MHz PAL H5[STF]+TF536 (TTRAM): ~2700 frames [davec].  
50MHz PAL STFM+ST536(Exxos) (TTRAM): ~2940 frames [elethiomel].  

50MHz PAL H5 + TF536-ST: ~2930 frames [exxos].  

40MHz PAL Mega ST4, PAK68/3-030 (L2 cache, no FASTRAM): ~3100 frames [frank.lukas].  

50MHz PAL H5+TF536-ST w/cache enabled with MAPROM_C: ~3210 frames [steve].  

50MHz DFB1 Falcon + 33MB/s AltRAM @50Hz RGB mode: ~4160 frames.  


#### NTSC/VGA (60Hz VBL)
##### Game time runs faster in the 60Hz mode therefore there are ~16% fewer frames on average on 60Hz machines

Stock NTSC Atari Mega STe (L2 cache): ~1227 frames [darklord].  

Stock Falcon @60Hz 60Hz VGA mode: ~1650 frames.  

32MHz TT (Stock + TTRAM) 60Hz VGA mode: ~2875 frames [stephen_usher, susher].  

40MHz NTSC STacy + Pak 68/3 (L2 cache, no FASTRAM): ~3160 frames [darklord].  

48MHz TT + EDO TTRAM 60Hz VGA: ~3420 frames [czietz].  

48MHz TT (SpeedyTT + SuperStorm TT-RAM 60Hz VGA: ~3660 frames [steve].  


# Use

1) Download the shareware version of Frontier from (for example) https://www.frontierastro.co.uk/Files/files.html

2) Extract frontier.bin from the ST disc image (use mtools or an emulator) and place it in the directory with this script. Rename it to lower case if necessary.

3) Run this script: "python3 frntbnch_patcher.py"

4) If you get no errors, you should have a working program called 'frntbnch.prg' in the same directory as this script.


# Caveats

This script may work, but as not been tested, with an originally owned copy of FRONTIER.PRG. Rename it to 'frontier.bin' (lower case) before trying. It won't work with compressed versions (eg. cracked copies from menus). File size should be 587798 bytes.

There is no error checking here. Work in a temporary directory. Don't lose your original program because of my shitty script!

This script is provided as is for personal educational gratification.
