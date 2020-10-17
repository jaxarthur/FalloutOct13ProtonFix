# FalloutOct13ProtonFix

I have figured out how to fix the issue with Fallout 76 crashing on startup after the October 13, 2020 update so I have decided to document it here.

For some reason Fallout76 dosen't like the curent version of dbghelp.dll that ships with proton the solution is to get a new version of the file and tell proton to use it.

To start you can get the dll here by going to:
https://github.com/jaxarthur/FalloutOct13ProtonFix/raw/main/dbghelp.dll
Or get it from dll-files.com
I have run it through virustotal.com and it is clean you can do the same if you want

Once you have the file put it here <SteamFolder>/steamapps/compatdata/1151340/pfx/drive_c/windows/system32/dbghelp.dll
This will require you to replace the file that is already there

Once this is done add the following to your steam launch options:
WINEDLLOVERRIDES="dbghelp=n,b"

Do Not use this and WINEDLLOVERIDES=winedbg.exe=d, which is used to prevent a crash on character creation.  You must combine them like so:
WINEDLLOVERRIDES="dbghelp=n,b;winedbg.exe=d"

And if you dont already have it add this to the end of the launch options:
%command%

I have not tested this much and there may be other broken things with the update but it at least lets you launch the game properly.
Also the winetricks dbghelp dosn't work for this it seems to only suport 32bit.
