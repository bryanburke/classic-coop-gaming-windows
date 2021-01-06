# Scoop

Scoop is a command-line installer for Windows. It simplifies installing and
updating some of the tools and engines that enable classic co-op gaming.

Website: <https://scoop.sh/>

Source code: <https://github.com/lukesampson/scoop>

## Guide

1. Open a Windows PowerShell console as your normal, non-Administrator user.
1. Allow PowerShell to execute scripts downloaded from the Internet if they are
   digitally signed by a trusted publisher:

   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

   This command allows executing remote signed scripts for your current user
   only and thus does not make any system-wide changes.
1. Download and execute the Scoop install script:

   ```powershell
   Invoke-WebRequest -UseBasicParsing https://get.scoop.sh/ | Invoke-Expression
   ```

   This script installs Scoop to the `scoop` subdirectory of your home
   directory.
1. Install [MinGit][], a minimal distribution of [Git for Windows][], so Scoop
   can check for and apply updates:

   ```powershell
   scoop install mingit-busybox
   ```

   This command installs the MinGit package with the BusyBox shell for the
   smallest footprint possible.
1. Add the [games bucket][], which contains manifests for some of the tools and
   engines in the guides:

   ```powershell
   scoop bucket add games
   ```

<!-- Reference Links -->

[games bucket]: https://github.com/Calinou/scoop-games
[Git for Windows]: https://gitforwindows.org/
[MinGit]: https://github.com/git-for-windows/git/wiki/MinGit
