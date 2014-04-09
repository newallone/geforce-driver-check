Geforce Driver Check (GDC)
==========================
### Checks for new Nvidia Display Drivers then does an automated unattended install, or with many more options.
Copyright (c) 2014 Jon Retting

- [GDC Github repo](https://github.com/jonretting/geforce-driver-check)
- [GDC on SourceForge](https://sourceforge.net/projects/geforce-driver-check/)

### [Latest v1.082](https://sourceforge.net/projects/geforce-driver-check/files/latest/download)

#### [v1.078](http://sourceforge.net/projects/geforce-driver-check/files/geforce-driver-check-1.078.zip/download)
#### [v1.076-1](http://sourceforge.net/projects/geforce-driver-check/files/geforce-driver-check-1.076-1.zip/download)

### Release Notes:

#### 1.082 :
- bug fix filename validation per extraction error
- include 7za as valid 7z binary dependency
- add 337.50 Desktop Devices hwid list
- use double underscore for function names
- switch all variables to lowercase
- add additional recursive mkdir error handling

#### 1.078 :
- improve naming conventions
- replace all echo's with printf
- remove eronious unimplemented vars and conditions
- improve excluded package array handling for 7z extraction
- add more return code handling for fallback cd
- drop pointless cat commands
- drop sed for substring match replacement
- add quoting to prevent some word splitting where possible

#### 1.076-1 :
- fix wget bad var name for url
- fix installer exit code issue
- all function names changed for better readability, and follows common naming conventions
- tab character indents replaced with four spaces per indent
- all vars renamed for better readability, and given GDC_ prefix to avoid any shell  confusion
- better Win OS architecture detection (no sub-shell), and more descriptive error
- better Win OS version detection (no-sub-shell), and more descriptive error

INFO:
-----
- Requires CYGWIN
- Currently supports: Windows 7 x64, Server 2008 r2, Windows 8/8.1 x64, (Server 2012 Untested)
- Works with Desktop and Notebook Graphics adapters
- No configuration needed to run, simply bash the slut
- Compares your current version with latest available from Nvidias website
- Downloads latest version if current version is older
- Option to Force-Reinstall latest version will verify integrity of downloaded archive, and act accordingly
- Will search your Program Files (x86/x64) for 7-Zip (7z.exe) will prompt for optional creation of symlink'
- If 7zip is not found, GDC will prompt to download x64 msi, then prompt to attended or unattended install
- Supports the international driver package version when "-i" is invoked
- Only installs Display Driver, HD Audio, and PshyX
- User interaction required before download/install procedure (unless [-s] or [-y] is invoked)
- Displays Nvidia installation progress box
- Runs driver setup with all driver packages when [-A] is invoked enables [-a] as well
- You can check and see if a new version is available with [-C] won't prompt to download and continue
- Extracts new display driver by default to /cygdrive/c/NVIDIA/GDC-"driver-ver#"
- The -r option will enable Nvidia driver installer to prompt user to reboot if needed (untested)

DEPENDENCIES:
-------------
wget, 7-Zip (prompts to download/install 7-Zip if not found)

OPTIONS:
--------
	geforce.sh [-asycCAirVh] [-d=/download/path]
	-a    Attended install (user must traverse Nvidia setup GUI)
	-s    Silent install (don’t show Nvidia progress bar)
	-y    Answer 'yes' to all prompts
	-c    Clean install (removes all saved profiles and settings)
	-d    Specify download location
	-C    Only check for new version (returns version#, 0=update available, 1=no update)
    -R    Force Reinstalls latest driver version (integrity checks on current installer package)
	-A    Enable all Nvidia packages (GFExperience, NV3DVision, etc) uses attended install
	-i    Download international driver package (driver package for non-English installs)
	-r    Don't disable reboot prompt when reboot is needed (could be bugged)
	-V    Displays version info
	-h    this crupt

	See INFO for more information

EXAMPLES:
---------
- Run default
	`./geforce.sh`

- Run with International (driver package for non English installs)
	`./geforce.sh -i`

- Run with all packages enabled (GFexperience, Geforce Vission, etc) fully attended install
	`./geforce.sh -A`

- Run with fully attended install enabled, will requires user to progress through Nvidia setup GUI
	`./geforce.sh -a`

- Run completely silent answers "yes" to all prompts, doesn't display any Nvidia GUI (no driver install progress window)
	`./geforce.sh -s`

- Run and only see if you need an update and exit
	`./geforce.sh -C`

- Run with Download path specified, yes to all prompts, and silent driver install (no Nvidia GUI)
	`./geforce.sh -d "/home/me/Downloads" -s -y`

### TODO:
- * add re-install option of any previously GDC installed driver package, and just rollback
- *! trap ctrl-c/z and kill anything and everything script executed
- *use logger instead of tee, use custom logit to windows events
- *make compatible with multiple installed nvidia card environments
- remove .sh suffix for release candidate
- correct handling of assorted nvidia graphics hardware
- create windows shortcuts to geforce.sh option
- add notification email switch when update is available
- make crontab friendly
- add long format options --re-install
- allow for other types ex: x86 version, only whql
- add geforce inspector tool install options
- add ntune o/c settings option show oc pane
- add driver purge style installation, complete graphics driver removal
