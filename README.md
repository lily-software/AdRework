# AdRework
Remove spotify ads by seamlessly and automatically muting and skipping them!
## [download latest version here](https://github.com/uDMBK/AdRework/releases/latest)

## Features
* Seamless, Automatic Ad Muting and Skipping
* Starts with Windows Automatically
* Extremely Small File Size (~2mb Total)
* Configurable Settings

## Troubleshooting
### I can't hear normal songs in Spotify!
as of version 0.2.0, this should **NEVER** occur unless you have set the fallbackvolume in the configuration to 0!

~this is a very rare bug that may occur where AdRework never unmutes the program after an ad, to fix this just go to the volume mixer and turn it back up again. If it is happening consistently then change the Mute Ads setting in the config file to false.~

### It's not starting up with Windows!
AdRework adds a registry key to startup with windows as well as a shortcut in the shell:startup folder. If it isn't starting up with windows check if the shortcut is there in shell:startup. If it isn't there, then add it manually, alternatively run AdRework as an administrator in case this process requires elevated permissions on your system.

### In my config file, it says 'CONFIG RESET DUE TO LOADING ERROR' - why?
if you are seeing this in your config file, then shockingly, your configuration file was reset due to, you guessed it, a loading error. if you set an invalid value for any config option or update to a newer version with changes to the configuration this will be added to the start of the file. it wont break AdRework or anything, its only there to inform you in case you had a custom config that it was reset.

### There is one particular song that is always muted and skipped by AdRework!
this shouldn't occur however as there are countless songs on spotify i cannot possibly test them all, if this occurs please contact me on discord (@dmbk#0255) with the song name and artist or (preferably) with a link to the song

### AdRework isn't in my task manager / AdRework is giving me a crash message whenever started
in either of these circumstances, AdRework has crashed! make sure you check your background processes first just in case (unless you are literally getting a crash message) this should never occur. if it is happening i genuinely have no clue whats happening. the only possible scenario i can think of is if the FallbackVolume config setting is set beyond 100 or less than 0, or if an anti-virus is for some reason interfering with the program being falsely detected as a virus (it's not - the releases are not obfuscated and can be reversed with dnSpy to prove this as well as AdRework literally being open source)

## Configuration Editing
AdRework creates a folder within your user's Roaming AppData folder (%AppData%\dmbk\AdRework) upon first startup.
In this folder you will find config.ini containing the following settings:
> SkipAds='True'
> MuteAds='True'
> BypassAds='True'
> ImmediateSkip='True'
> RegistryStartup='True'
> FallbackVolume='50'
You can modify these values to either true or false (except FallbackVolume requiring an integer value between 0 - 100), disabling SkipAds, MuteAds and AdBypass will cause the program to almost instantly terminate whenever started.

### Skip Ads / Mute Ads
specifies if AdRework should skip/mute ads respectively

### Bypass Ads
if spotify should be muted when no song name is returned (results in spotify also being muted whenever paused but this is not noticable as well,, there isnt any music playing)

### Immediate Skip
disabling this will result in AdRework waiting 5 seconds to skip all and any ads. not recommended, but if you want the multimedia popup to show up for less time or have an absolute hate-fueled rage for the 'wait to skip ads' banner in spotify then this option is for you

### Registry Startup
some people dont like AdRework touching the registry. this is understandable and disabling this will disable AdRework attempting to run at startup through the registry (doesn't remove any existing keys created though)

### Fallback Volume
this setting is to fix the previously extremely rare bug that would case spotify to be muted during actual music, setting the volume back to a 'fallback' volume instead of being muted. setting this to 0 will disable it however is not recommended to be used with BypassAds on as it will result in spotify being almost always muted
