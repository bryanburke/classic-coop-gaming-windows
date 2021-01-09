# Engine: GZDoom

GZDoom is a 3D-accelerated Doom source port. It makes playing and modding Doom
engine games on modern PCs much easier.

[Supported Games][]

[Website][] | [Repository][] | [Documentation][]

## Prerequisites

- [Tool: Scoop](tool_scoop.md)

## Guide

1. Update Scoop and install GZDoom:

   ```powershell
   scoop update
   scoop install gzdoom
   ```

   The GZDoom package creates the following two directories:

   - `scoop\persist\gzdoom` contains the GZDoom configuration file,
     `gzdoom_portable.ini`.
   - `scoop\persist\_doom` provides a place to store game files.
1. Create the following subdirectories in the `_doom` directory to organize game
   files into categories:

   - `iwads` to store IWADs, bundles that contain full game data.
   - `pwads` to store PWADs, bundles that contain partial game data.
   - `mods` to store mods, typically PK3 or ZIP archives.
   - `zdl` to store profiles for the ZDL launcher.
1. Open the configuration file and paste in the following settings:

   ```ini
   [GlobalSettings]
   cl_run=true
   gl_texture_filter=0
   save_dir=$PROGDIR/../../../persist/gzdoom/saves
   vid_maxfps=60
   vid_vsync=false

   [Doom.Player]
   autoaim=0
   name=Doomguy
   team=6

   [Doom.ConsoleVariables]
   am_showitems=true
   am_showtotaltime=true
   crosshair=7
   crosshaircolor=ff ff ff
   crosshairhealth=0
   crosshairscale=0.5
   gl_weaponlight=32
   m_quickexit=true
   vid_cursor=cursor
   ```

   Replace *Doomguy* with your name. If your monitor's refresh rate is higher
   than 60 Hz, replace *60* for `vid_maxfps` with the correct number.
1. Save the configuration file and open GZDoom with any IWAD to customize the
   remaining settings to your liking.

<!-- Reference Links -->

[Documentation]: https://zdoom.org/wiki/Main_Page
[Repository]: https://github.com/coelckers/gzdoom
[Supported Games]: https://zdoom.org/wiki/IWAD#Supported_IWADs
[Website]: https://www.zdoom.org/
