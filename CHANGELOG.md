Geforce Driver Check (GDC)
==========================
### CHANGE LOG NOTES:

#### 1.0921:
- added checks for 7za extracted windows ACLs
- fixed fixed not being able to execute installer

#### 1.0920:
- removed 7z auto download and symlink functionality
- added 7za to replace 7z
- added 7za binary to GDC
- added 7za dependency check
- beta -U arg to remove previous driver version using windows PnPUtil
- added ShieldWirelessController and GfExperienceService to excluxed list
- rename func.src to func.sh
- update wget Mozilla user agent rv to 34.0

#### 1.0915-1:
- fixed pathing issue

#### 1.0915 :
- posix compliancy
- removed bash arrays
- use command instead of hash
- source in functions (func.src)
- source in config (config.conf)
- removed superfluous files
- update README info

#### 1.09 :
- removed various bashisms

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
- drop sed for substring match replace
- add quoting to prevent some word splitting where possible

#### 1.076-1 :
- fix wget bad var name for url
- fix installer exit code issue
- all function names changed for better readability, and follows common naming conventions
- tab character indents replaced with four spaces per indent
- all vars renamed for better readability, and given GDC_ prefix to avoid any shell  confusion
- better Win OS architecture detection (no sub-shell), and more descriptive error
- better Win OS version detection (no-sub-shell), and more descriptive error

#### 1.06-BETA :
- add logger to deps list, and validate true
- add non functioning reminder options logger and verbose
- minify devices compat detect function
- prep adding log message output to windows event log
- remove hyphen from function names
- replace echo with printf where appropriate
- fix inf loop detect counter for source script path
- *remove/alter vast majority of bashisms

#### 1.051-BugFix :
- fix extract path
- fix international vars
- fix adapater type
- fix installed ver number
- fix install path
- add 7zip -y flag
- add Network.Service to do not install pkg array (is user editable array top of script)

#### 1.05 :
- fix check only exit condition
- use environments globals for defaults first, if exist and not empty
- use more bash builtins over sub shell executions
- various code cleanups
- allow data parse/store functions to call parent query function on demand
- add GDC icons arhive for future links/shortcuts

#### 1.049 :
- various function optimizations
- improve nvidia web query handling
- increased exception handling for root paths and downloads path
- added devices and notebook devices dbase files as tarball
- verify adapter description again devices dbase, instead of just notebook detection

#### 1.048-2 :
- proper detection of graphics card when non-nvidia card is present
- checks for compatabile NVIDIA card early on
- improved wmic installed driver information query
- updated notebook devices db to latest 332.21

#### 1.048-1 :
- better architecture and os version detection including fixes
- added user agent to web data queries huge increase in speed upwards of twice as fast
- fix non executable files having +x permissions

#### 1.048 RC3 :
- CYGWIN 32-bit and 64-bit support
- Force reinstall option [-R] with download validation checks
- Properly detects host architecture and Windows version
- Untested with multiple graphic adapter setups
- User is prompted before new driver download and setup.exe execution
- Supports non-admin account execution
- Most common bugs fixed
