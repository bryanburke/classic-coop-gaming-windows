# Engine:GZDoom

GZDoom is a DOOM engine source port with 3D acceleration and tons of features
that streamlines playing and modding DOOM engine games on modern PCs.

[Website][] | [Repository][] | [Supported Games][] | [Documentation][]

## Guide

1. Update Scoop and install GZDoom:

   ```powershell
   scoop update
   scoop install games/gzdoom
   ```

   The GZDoom package creates the following two directories:

   - `scoop\persist\gzdoom` contains the GZDoom configuration file,
     `gzdoom_portable.ini`.
   - `scoop\persist\_doom` provides a place to store game files.

1. Create the following subdirectories in the `_doom` directory to organize game
   files into categories:

   - `iwads` to store IWADs, bundles that contain full game data.
   - `pwads` to store PWADs, bundles that contain addon game data.
   - `mods` to store mods, typically PK3 or ZIP archives.
   - `zdl` to store profiles for the ZDL launcher.

1. Open `scoop\persist\gzdoom\gzdoom_portable.ini` and paste in the following
   settings:

   ```ini
   [GlobalSettings]
   cl_run=true
   gl_texture_filter=0
   save_dir=$PROGDIR/../../../persist/gzdoom/saves
   snd_channels=256
   vid_maxfps=60
   vid_preferbackend=1
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

1. Replace _Doomguy_ with your name.
1. If your monitor's refresh rate is higher than 60 Hz, replace _60_ for
   `vid_maxfps` with the correct number.
1. Save the configuration file.
1. If you need a free IWAD to launch GZDoom for the first time, download the
   [DOOM shareware episode][] and unpack `DOOM1.WAD` into `scoop\persist\_doom`.
1. Launch GZDoom with any IWAD to customize the remaining settings to your
   liking.
1. After tweaking your settings in-game, close GZDoom.

<!-- Reference Links -->

[documentation]: https://zdoom.org/wiki/Main_Page
[doom shareware episode]:
  http://www.doomworld.com/3ddownloads/ports/shareware_doom_iwad.zip
[repository]: https://github.com/coelckers/gzdoom
[supported games]: https://zdoom.org/wiki/IWAD#Supported_IWADs
[website]: https://www.zdoom.org/
