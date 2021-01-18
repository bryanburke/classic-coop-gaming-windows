# Game:DOOM

DOOM is the first game in the DOOM series and one of the most iconic and
important first-person shooters in history.

[Website][] | [Store Page][]

## Prerequisites

Before continuing, if you have not done so already, complete these guides in
order and then return here:

1. [Tool:GOG Galaxy](tool_gog-galaxy.md)
1. [Tool:Scoop](tool_scoop.md)
1. [Engine:GZDoom](engine_gzdoom.md)
1. [Mod:Smooth Doom](mod_smooth-doom.md)
1. [Tool:ZDL](tool_zdl.md)

## Caveats

- All players must be using the EXACT same GZDoom version, IWAD, PWADs, mods,
  file load order, and save file for co-op to work properly.

## Guide

### Game

1. Install _The Ultimate DOOM_ in GOG Galaxy.
1. Right click on the game in your library.
1. Within **Manage installation**, click **Configure...**
1. Next to **Launch parameters**, check **Custom executables / arguments**.
1. Scroll down and click **Add another executable / arguments**.
1. Select `scoop\apps\zdl\current\ZDL.exe` to add the ZDL launcher.
1. Enter _ZDL_ for **My label**.
1. Below the ZDL entry, select **Default executable**.
1. Click **OK** to save the configuration.
1. Launch the game in GOG Galaxy to open ZDL.
1. Navigate to the **General settings** tab.
1. Below the **IWADs** box, click the **plus** button.
1. Select `GOG Galaxy\Games\DOOM\DOOM.WAD` to add the DOOM IWAD.
1. Navigate to the **Launch config** tab.
1. For **Source port**, select _GZDoom_.
1. For **IWAD**, click _The Ultimate Doom v1.9_ to select it.

### Addons

1. Download [SIGIL][] and unpack the PWAD (`SIGIL_v1_21.wad`) into
   `scoop\persist\_doom\pwads`.

   SIGIL is a free PWAD by [John Romero][] that adds a fifth campaign episode.

1. Download the [Roland SC-55 music pack][] and place the ZIP archive in
   `scoop\persist\_doom\mods`. Choose the **FLAC Pack** below **Doom/Ultimate
   Doom (Boosted)** (`doom_sc55_flac.zip`) for the best experience.

   This pack contains high quality recordings of the DOOM soundtrack MIDIs on
   the Roland SC-55.

1. Below the **External files** box in ZDL, click the **plus** button.
1. Select the files for the above addons (`SIGIL_v1_21.wad` and
   `doom_sc55_flac.zip`) to add them.
1. Add the Smooth Doom mod (`SmoothDoom.pk3`) in the same way.
1. Use the **up** and **down** arrow buttons to reorder the files like this:

   1. `SIGIL_v1_21.wad`
   1. `SmoothDoom.pk3`
   1. `doom_sc55_flac.zip`

### Co-op

1. In ZDL, select _Co-op_ for **Game mode**.
1. Follow the appropriate instructions below depending on whether you are
   joining or hosting the game.
1. Once the game is set up and working, in the **ZDL** drop-down menu click
   **Save .zdl**.
1. Name the file `doom1_join.zdl` or `doom1_host.zdl` as appropriate.
1. Save the profile to `scoop\persist\_doom\zdl`.

#### Joining

1. Select _Joining_ for **Players**.
1. Enter the **Hostname/IP** and **Port** values you receive from the person
   hosting the game.
1. If you are resuming from a save game:
   1. Select _(Browse...)_ for **Savegame**.
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
   +alwaysapplydmflags 1 +sv_allowfreelook 1 +sv_cooploseammo 1 +sv_cooplosearmor 1 +sv_cooplosepowerups 1 +sv_forcerespawn 1 +sv_killallmonsters 1 +sv_noautoaim 1 +sv_nocrouch 1 +sv_nojump 1 +sv_weapondrop 1 +teamplay 1
   ```

   Reference [Multiplayer and bot settings][] for these and other multiplayer
   settings.

1. If you are resuming from a save game:
   1. Select _(Browse...)_ for **Savegame**.
   1. Choose the desired file in `scoop\persist\gzdoom\saves`.
   1. Reset **Map** back to _(Default)_.
1. Click **Host**.

<!-- Reference Links -->

[john romero]: https://doomwiki.org/wiki/John_Romero
[roland sc-55 music pack]: https://sc55.duke4.net/games.php#doom
[multiplayer and bot settings]:
  https://zdoom.org/wiki/CVARs:Configuration#Multiplayer_and_bot_settings
[sigil]: https://romero.com/sigil
[store page]: https://www.gog.com/game/the_ultimate_doom
[website]: https://doomwiki.org/wiki/DOOM
