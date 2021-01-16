# Mod:Smooth Doom

Smooth Doom is a spriting project/general enhacement that adds newly drawn
frames to all of DOOM's weapons and actors. It smoothes out animations and adds
additional visual effects to the following games:

- DOOM
- DOOM II: Hell on Earth
- Final DOOM

[Website][]

## Guide

1. Click the **DOWNLOAD ME** link on the mod website.
1. Download the mod archive (`SmoothDoom.pk3`) into `scoop\persist\_doom\mods`.
1. Open `scoop\persist\gzdoom\gzdoom_portable.ini` and paste in the following
   settings at the bottom of the file:

   ```ini
   [Doom.LocalServerInfo.Mod]
   bbtoggle=1
   catoggle=2
   dctoggle=1
   gbtoggle=1
   ggtoggle=1
   rmtoggle=1
   sawgibtoggle=1
   ```

1. Save the configuration file.

<!-- Reference Links -->

[website]: https://forum.zdoom.org/viewtopic.php?t=45550
