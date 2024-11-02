## How to run v83 cosmic on linux

So after a few days i managed to get [v83 cosmic](https://github.com/P0nk/Cosmic) running under linux.

I wanted to share my process with any one also looking to run under linux for testing

Some assumption before we start.

   * I assume you know how to install the game using lutris

   * I assume you know how to use lutris

Thats all :)

Install the game using this preset  
![Windows 98 + 3DFX 32-bit](/docs/assets/guide1.png)

After the game is installed follow the steps on the [github page](https://github.com/P0nk/Cosmic) to complete the install (mainly dropping files into maplestory directory)

Lutris settings

a working directory need to be set
![Pic](/docs/assets/guide2.png)

Runner options need to be set as follows

Enable DXVK and D3D Extras, Disable system winetricks, VKD3D, dgvoodoo2
![Pic](/docs/assets/guide3.png)

System options

Disable lutris runtime and prefer system libraries
![Pic](/docs/assets/guide4.png)

So far so good we are done with lutris settings now we are going to install all the libs we need and dlls

In winetricks, install windows dll and choose the following

d3dcompiler_43

d3dx10_43

dotnet20sp2

dinput8

vcrun2003

make sure you install either corefonts or allfonts using winetricks

Ok almost done we just need 2 dlls [ws2_32.dll](/docs/assets/ws2_32.dll) and [ws2help.dll](/docs/assets/ws2help.dll) , I found them after a quick google search for maplelegends linux just make sure you place them into $WINEPREFIX/drive_c/windows/system32 and system

After all this the game should open for a few seconds then freeze

To fix this I am using [MapleEzorsia-V2](https://github.com/444Ro666/MapleEzorsia-v2) HD client

Installation is real simple go to releases, grab the [dll](/docs/assets/dinput8.dll), [config](/docs/assets/config.ini), [wz file](/docs/assets/EzorsiaV2_UI.wz) and drop them into maplestory folder

Now to fix the crash that the client cause we need to regedit 1 thing

wine regedit
![Pic](/docs/assets/guide5.png)

Under HKEY_CURRENT_USER\Software\Wine\Direct3D

Add a DWord MaxShaderModelVS and set it to 3

I really hope it helps people running that version of the game under linux
