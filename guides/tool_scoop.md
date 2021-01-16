# Tool:Scoop

Scoop is a portable software manager that simplifies installing and updating
some of the packages for the guides.

[Website][] | [Repository][] | [Documentation][]

## Guide

1. Open a Windows PowerShell console as your normal, non-Administrator user.
1. Allow PowerShell to execute scripts downloaded from the Internet if they are
   digitally signed by trusted publishers:

   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

   This command allows executing remote signed scripts for your current user
   only and thus does not make any system-wide changes.

1. Download and execute the Scoop install script:

   ```powershell
   Invoke-WebRequest -UseBasicParsing https://get.scoop.sh/ | Invoke-Expression
   ```

   This script installs Scoop to the `scoop` subdirectory of your home directory
   unless you [change the install directory][]. Regardless of where you install
   Scoop, the other guides simply refer to the install directory as `scoop`.

1. Install [MinGit][], a minimal distribution of [Git for Windows][], so Scoop
   can check for and apply updates:

   ```powershell
   scoop install mingit-busybox
   ```

   This command installs the MinGit package with the BusyBox shell for the
   smallest footprint possible.

1. Add the [games bucket][], which contains manifests for some of the software
   in other guides:

   ```powershell
   scoop bucket add games
   ```

<!-- Reference Links -->

[change the install directory]:
  https://github.com/lukesampson/scoop#install-scoop-to-a-custom-directory-by-changing-scoop
[documentation]: https://github.com/lukesampson/scoop/wiki
[games bucket]: https://github.com/Calinou/scoop-games
[git for windows]: https://gitforwindows.org/
[mingit]: https://github.com/git-for-windows/git/wiki/MinGit
[repository]: https://github.com/lukesampson/scoop
[website]: https://scoop.sh/
