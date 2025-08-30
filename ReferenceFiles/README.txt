This directory contains scripts and modified files that can be used to recreate or analyze my work, if anyone wants to try a similar hack or to modify the other language files in the game. It also includes this document as a changelog of all the work I did before 1.0.0 release.

Included here:
  - System files or other files with special manual edits
  - Scripts to run on individual localized stage files to replace sprite pointers
    (".xsc" files are scripts for use with XVI32 for mass find+replace-ing sprite pointers.)
  - Instructions to replicate my work (in this readme.txt file)

Not included here:
  - All the edited localized stage files
  - The rest of the ROM

The version number (e.g. "0.2.0") indicates what work-in-progress version the file was created at - see below.

VERSION 1.0.0

Further modifications to arm9.bin. The only difference between 1.0.0 and 0.2.3 is the hex at 0.3B830 has been modified to read "3C" rather than "31" so it points to the cat portrait instead of the ghost.

With this, bare minimum requirements for v1.0.0 are achieved.

VERSION 0.2.3

Modified arm9.bin so that it will always pull up Ghost Sissel in the Rollback Menu. This is achieved by modifying the hex at 0x3B82E to read "606A," which prevents the branching code from doing anything.

It still does not display a cat, but there are no more known instances of Sissel using Yomiel's sprite.

VERSION 0.2.2

Modified overlay9_0006.bin such that the 2 sprites corresponding to Sissel's entries in the directory have been updated with the cat, and the bottom screen sprite has been updated to always show a ghost.

This just comes down to replacing the code at 72BC and 72FC to read "D7."

The bottom screen sprite cannot be easily replaced with the cat, but it CAN be replaced with the ghost. Editing memory address 7794 to "9C" achieves this.

Only remaining known case where Sissel is still using Yomiel's sprite: "Rewind Time" scene.

VERSION 0.2.1

Known cases where Sissel is still using Yomiel's sprite:
  - "Rewind Time" scene
  - "People" database

Changes:

Sprite swap script to replace all (used in version 0.2.0, see below) run on "system_0000.en.msg.xml.bin" which appears to have updated the "phone line down" scene.

database_0000_Expand.en.xml.bin has been overwritten with the following changes:

- "Me, the Mystery" text replaced with "Me, a Meowstery"
- Yomiel sprite replaced with cat animation

Process:

Find + replace ALL of:

37002b002800ff0016003c003600370028003500
("the Myster")

replace with

2400FF001600280032003a003600370028003500
("a Meowster")

In addition, update hex code from address 34 to the following:
FDFF780E0100FCFF50FFD9FF50FFD9FFF4FF50FFD9FF09100A100B100C100D100E100F1010101110121013101410151016101710181019101A101A10

To update the animation for Sissel's entry.

VERSION 0.2.0

Re-pointed all of Sissel's talk sprites for every line of dialogue to be pointed to the cat instead. Because talk sprites appear to indicated per line of dialogue per language, this has only modified the English language version. Currently untested.

Files up through st05 were edited manually. Files from st06 onward were automated.

Mistakes found in manual files and rectified:

st01_game021
st03_demo010

Process:

1. Export .en.xml file(s) using CrystalTile2
2. Decompress using BatchLZ77
3. Replace the hex codes for Sissel's sprites. Script below. Used XVI32's scripting function to automate.
4. Compress edited file with BatchLZ77
5. Import the edited file using CrystalTile2

In most cases this replaces only Sissel but not Yomiel as some early testing indicated their codes are different. However, some endgame scenes did in fact modify Yomiel as well. These files have been overwritten with a separate script that only re-points the ghost with sunglasses. The following files were modified and re-inserted:

st14_game060
st14_game061
st14_game050*
st14_demo060
st14_game022
st13_game020
st13_game021

*This scene also features human Sissel at the start, so after scripting to replace the ghost, additionally ran the replace-all one more time and re-inserted.

The following scene was reverted to its original state as the script falsely replaced Yomiel with Sissel and has no ghost Sissel present:

st13_game022

Needs to be fully playtested to search for other false positives or mishaps.

Script to replace all in XVI32:

ADR 0
REPLACEALL 08 FF 27 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 29 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 2B 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 2D 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 2F 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 31 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 34 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 36 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 38 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 3A 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 28 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 2A 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 2C 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 2E 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 30 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 32 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 35 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 37 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 39 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 08 FF 3B 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 19 FF 27 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 29 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 2B 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 2D 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 2F 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 31 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 34 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 36 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 38 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 3A 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 28 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 2A 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 2C 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 2E 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 30 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 32 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 35 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 37 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 39 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 19 FF 3B 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 1B FF 01 00 BY 1B FF 08 00

Script to replace only ghost in XVI32:

ADR 0
REPLACEALL 08 FF 31 00 BY 08 FF 3C 00
ADR 0
REPLACEALL 08 FF 32 00 BY 08 FF 3D 00
ADR 0
REPLACEALL 19 FF 31 00 BY 19 FF 3C 00
ADR 0
REPLACEALL 19 FF 32 00 BY 19 FF 3D 00
ADR 0
REPLACEALL 1B FF 0D 00 BY 1B FF 08 00
