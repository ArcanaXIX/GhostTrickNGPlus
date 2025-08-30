VERSION 1.0.0 released 08/29/2025
Hack by Leo ArcanaXIX
Patch created with Delta Patcher for use with Ghost Trick - Phantom Detective (USA) (En,Fr,De,Es,It).nds ROM file.

WARNING: Spoilers for the original game follow.

~*~*~ ABOUT ~*~*~

Do you want to play Ghost Trick as a cat the whole time? This patch is for you.

I made this hack because after beating the game I wanted to do just that. It ended up taking about 4 years to reverse-engineer enough of the game's code to implement it, but it's now in a baseline fully-playable state!

Implemented Changes:
  * Every portrait sprite for Sissel in gameplay and menus has been replaced with the cat.
  * ...For the ENGLISH language only. The portrait sprites are defined per-localization and I only modified the English files.
  * Yomiel's body has been replaced with an animation of the cat in the "People" directory.

For more information on how this was accomplished and a roadmap of possible future additions:
  * https://www.romhacking.net/forum/index.php?topic=32844
  * https://github.com/ArcanaXIX/GhostTrickNGPlus

~*~*~ INSTALL ~*~*~

NOTE: This patch entirely replacees Sissel's portraits with the cat in all gameplay scenarios in English. I highly recommend keeping a backup copy of the original ROM before applying if you would like to play the game normally again in the future. It is not reversible.

I recommend using Delta Patcher to apply this patch to a copy of the original game ROM.

Get Delta Patcher on RHDN: https://www.romhacking.net/utilities/704/
Or their GitHub page: https://github.com/marco-calautti/DeltaPatcher/releases/

It's a very easy tool to use!
  1. Launch DeltaPatcher.exe
  2. Drag your unmodified ROM file into the top bar
  3. Drag the GhostTrick_NGPlus_1.0.0.xdelta patch into the bottom bar
  4. Click "Apply Patch" (a pop-up will display a description of the patch contents)
  5. You're done!

Once the patch is applied, load it in your emulator of choice and play the game as normal. Sissel will now be a cat!

~*~*~ CREDITS ~*~*~

Team:
This was mostly a one-person project. Hacking, reverse-engineering, testing, etc by Leo ArcanaXIX.
  * http://arcanaxix.com/Romhacking/
  * play my indie game!! https://linktr.ee/amadeusgame

However, it would not have been completed without the help of MLC, who did a ton of research on the save files and has been working on their own GT hacking tool.
  * https://github.com/CrazyMLC/ghost-treader

Tools used:
  * CrystalTile2 by angel-team
  * DeSmuME by YopYop156 and the DeSmuME team
  * XVI32 by Christian Maas
  * BatchLZ77 by DarthNemesis
  * DeltaPatcher by Marco Calautti

~*~*~ CONTACT ~*~*~

Please let me know if you encounter any bugs or issues. I believe I caught all the cases where Yomiel accidentally got cat-ified and reverted them, but if you find any (or any missed Sissel sprites) let me know so I can fix them.

leo_arcanaxix@protonmail.com
