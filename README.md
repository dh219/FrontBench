# FrontBench
Using Frontier: Elite 2 as benchmarking software for the Atari ST line of computers

This Python 3 script will patch the Shareware version of the Atari ST version of Frontier: Elite 2 to count frames between two specific places in the intro sequence. A faster computer/memory combination should be able to draw more frames between these two points and thus appear smoother.

It's not a rigorous benchmark, but it's a decent representation of an AltRAM-supporting game that is heavy on memory access and CPU load. It provides a good visual feedback too. Frontier does not use an FPU.

*Please note*, Frontier uses the vertical blank to time the intro sequence. The sequence is therefore shorter on 60Hz machines. This will give a frame count ~17% lower than on an otherwise identical configuration running at 50Hz. This needs to be taken into account when comparing results.

Frontier (and FrontBench) requires a 1MB machine.

# Results

Some examples I've collected:

Stock 8MHz PAL STE: ~850 frames.

16MHz PAL STE: ~940 frames.
16MHz PAL STE + 7MB/s AltRAM: ~1320 frames.

Stock Falcon @60Hz VGA mode: ~1650 frames

50MHz PAL H5[STF]+TF536: ~2700 frames.


# Use

1) Download the shareware version of Frontier from (for example) https://www.frontierastro.co.uk/Files/files.html

2) Extract frontier.bin from the ST disc image (use mtools or an emulator) and place it in the directory with this script. Rename it to lower case if necessary.

3) Run this script: "python3 frntbnch_patcher.py"

4) If you get no errors, you should have a working program called 'frntbnch.prg' in the same directory as this script.


# Caveats

This script may work, but as not been tested, with an originally owned copy of FRONTIER.PRG. Rename it to 'frontier.bin' (lower case) before trying. It won't work with compressed versions (eg. cracked copies from menus). File size should be 587798 bytes.

There is no error checking here. Work in a temporary directory. Don't lose your original program because of my shitty script!

This script is provided as is for personal educational gratification.
