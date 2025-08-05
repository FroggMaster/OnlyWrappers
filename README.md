# OnlyLaunchers
A collection of Windows batch scripts designed to wrap game launchers, automating tasks before launch or during cleanup after the game has closed.

## Scripts

### BorderlessGaming Wrapper

This script automates the process of running a game in a borderless window using the [Borderless Gaming](https://github.com/Codeusa/Borderless-Gaming) application. It launches Borderless Gaming, starts your game, waits for the game to close, and then automatically terminates the Borderless Gaming process.

#### Setup

1.  Place the `BorderlessGaming Wrapper` batch file in the same directory as your game's executable.
2.  Open the script in a text editor.
3.  Modify the variables in the `Configuration Settings` section to match your setup.

#### Configuration

-   `BLGInstallPath`: The full installation path for Borderless Gaming.
-   `GameEXE`: The filename of your game's executable.
-   `MinimizeModeChoice`: Controls how the command window is minimized while monitoring the game. Set to `1` or `2`.

```batch
:: Configuration Settings
:: The install path for BorderlessGaming
set "BLGInstallPath=C:\Program Files (x86)\Borderless Gaming\10.1.2 (Premium)\steamapps\common\Borderless Gaming"
:: Your games executable name
set "GameEXE=deadrising3.exe"
:: Minimize mode, controls how the CMD window is minimzed while monitoring for the game. 
:: Valid options: 1 or 2
set "MinimizeModeChoice=2"
```

To launch your game, run the `BorderlessGaming Wrapper` script instead of the game's executable.

---

### EA Launcher Wrapper

This script is a wrapper for games that use the EA App. It performs two main functions:
1.  **Pre-launch**: Terminates the `DS4Windows.exe` process.
2.  **Post-game**: Waits for the game process to close and then terminates background EA services (`EADesktop.exe`, `EABackgroundService.exe`) to free up system resources.

#### Setup

1.  Place the `EA Launcher Wrapper` batch file in the same directory as your game's executable.
2.  Open the script in a text editor.
3.  Modify the variables in the `Configuration Settings` section.

#### Configuration

-   `GameEXE`: The filename of your game's executable.
-   `MinimizeModeChoice`: Controls how the command window is minimized while monitoring the game. Set to `1` or `2`.
-   `EAServices`: A space-separated list of EA service executables to terminate after the game closes.

```batch
:: Configuration Settings
:: Your games executable name
set "GameEXE=BF2042.exe"
:: Minimize mode, controls how the CMD window is minimzed while monitoring for the game. 
:: Valid options: 1 or 2
set "MinimizeModeChoice=2"
:: EA Services executables
set "EAServices=EADesktop.exe EABackgroundService.exe"
```

To launch your game, run the `EA Launcher Wrapper` script. You can create a shortcut to this script for convenience.

## License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.
