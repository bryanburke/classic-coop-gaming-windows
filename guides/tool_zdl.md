# Tool:ZDL

ZDL is a simple launcher for DOOM source ports. It supports profiles for quickly
switching between games and configurations.

[Website][] | [Repository][]

## Prerequisites

1. [Tool:Scoop](tool_scoop.md)
1. [Engine:GZDoom](engine_gzdoom.md)

## Guide

1. Update Scoop and install ZDL:

   ```powershell
   scoop update
   scoop install games/zdl
   ```

1. Launch ZDL.
1. Navigate to the **General settings** tab.
1. Below the **Source ports** box, click the plus button.
1. Select `scoop\apps\gzdoom\current\gzdoom.exe` to add the GZDoom source port.
1. Navigate to the **Launch config** tab.
1. Next to the **Launch** button, click the down arrow to show the rest of the
   options.

<!-- Reference Links -->

[Repository]: https://github.com/lcferrum/qzdl
[Website]: https://zdoom.org/wiki/ZDL
