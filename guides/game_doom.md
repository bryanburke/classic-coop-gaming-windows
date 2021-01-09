# Game:DOOM

DOOM is the first release of the DOOM series and one of the games that
consolidated the first-person shooter genre.

[Store Page][]

[Website][]

## Prerequisites

1. [Engine:GZDoom](engine_gzdoom.md)
1. [Tool:ZDL](tool_zdl.md)

## Caveats

- All players must be using the EXACT same GZDoom version, IWAD, PWADs, mods,
  and save file for co-op to work properly.

## Guide

### Game

1. Install *The Ultimate DOOM* in GOG Galaxy.
1. Right click on the game in your library.
1. Under **Manage installation**, click **Configure...**
1. Check **Custom executables / arguments**.
1. Scroll down and click **Add another executable / arguments**.
1. Select `scoop\apps\zdl\current\ZDL.exe` to add the ZDL launcher.
1. Enter *ZDL* for **My label**.
1. Below the ZDL entry, select **Default executable**.
1. Click **OK** to save the configuration.
1. Launch the game in GOG Galaxy to open ZDL.
1. Navigate to the **General settings** tab.
1. Below the **IWADs** box, click the plus button.
1. Select `GOG Galaxy\Games\DOOM\DOOM.WAD` to add the DOOM IWAD.
1. Navigate to the **Launch config** tab.
1. For **Source port**, select *GZDoom*.
1. For **IWAD**, select *The Ultimate Doom v1.9*.

### Addons

* TODO: Move Smooth Doom mod to own guide and cut down settings to only customizations

1. Download [SIGIL][] and unpack `SIGIL_v1_21.wad` into
   `scoop\persist\_doom\pwads`.

   SIGIL is a free PWAD by [John Romero][] that adds a fifth campaign episode.
1. Download [Smooth Doom][] (`SmoothDoom.pk3`) into `scoop\persist\_doom\mods`.

   Smooth Doom is a mod that adds smoother animations and various new visual
   effects to the game.
1. Download the [Roland SC-55 music pack][] (`doom_sc55_flac.zip` for the
   boosted FLAC version) into `scoop\persist\_doom\mods`.

   This pack contains high quality recordings of the DOOM soundtrack MIDIs on
   the Roland SC-55.
1. Below the **External files** box in ZDL, click the plus button.
1. Select the files for the above addons to add them.
1. If necessary, use the up and down arrow buttons to reorder the files like
   this:

   1. `SIGIL_v1_21.wad`
   1. `SmoothDoom.pk3`
   1. `doom_sc55_flac.zip`

1. Open `scoop\persist\gzdoom\gzdoom_portable.ini` and paste in the following
   settings at the bottom of the file:

   ```ini
   [Doom.LocalServerInfo.Mod]
   bbtoggle=1
   botoggle=0
   bstoggle=0
   catoggle=2
   dctoggle=1
   dutoggle=0
   gbtoggle=1
   ggtoggle=1
   gotoggle=0
   mdtoggle=1
   pftoggle=1
   pitoggle=0
   putoggle=0
   retoggle=0
   ritoggle=0
   rmtoggle=1
   rotoggle=0
   sawgibtoggle=1
   totoggle=0
   vatoggle=0
   wetoggle=0
   ```

1. Save the configuration file.

### Co-op

1. In ZDL, select *Co-op* for **Game mode**.
1. Follow the appropriate instructions below depending on whether you are
   joining or hosting the game.
1. Once the game is set up and working, in the **ZDL** drop-down menu click
   **Save .zdl**.
1. Name the file `doom1_join.zdl` or `doom1_host.zdl` as appropriate.
1. Save the profile to `scoop\persist\_doom\zdl`.

#### Joining

1. Select *Joining* for **Players**.
1. Enter the **Hostname/IP** and **Port** values you receive from the person
   hosting the game.
1. If you are resuming from a save game:
   1. Select *(Browse...)* for **Savegame**.
   1. Coordinate with the host to choose the correct file in
      `scoop\persist\gzdoom\saves`.
1. When the host is ready, click **Join**.

#### Hosting

1. Select the desired number of **Players**.
1. Enter the desired **Port** for hosting the game.
1. Select the desired **Map** and **Skill** level.
1. Enter the following for **Extra command line arguments** and tweak as
   desired:

   ```text
   +set sv_allowfreelook true +set sv_cooploseammo true +set sv_cooplosearmor true +set sv_cooplosepowerups true +set sv_killallmonsters true +set sv_noautoaim true +set sv_nocrouch true +set sv_nojump true +set sv_weapondrop true +set teamplay true
   ```

   Reference [Multiplayer and bot settings][] for these and other multiplayer
   settings.
1. If you are resuming from a save game:
   1. Select *(Browse...)* for **Savegame**.
   1. Choose the desired file in `scoop\persist\gzdoom\saves`.
   1. Reset **Map** back to *(Default)*.
1. Click **Host**.

<!-- Reference Links -->

[John Romero]: https://doomwiki.org/wiki/John_Romero
[Roland SC-55 music pack]: https://sc55.duke4.net/games.php#doom
[Multiplayer and bot settings]: https://zdoom.org/wiki/CVARs:Configuration#Multiplayer_and_bot_settings
[SIGIL]: https://romero.com/sigil
[Smooth Doom]: https://forum.zdoom.org/viewtopic.php?t=45550
[Store Page]: https://www.gog.com/game/the_ultimate_doom
[Website]: https://doomwiki.org/wiki/DOOM
