---
title: FiveM
layout: page
nav_order: 1
parent: Special Games
grand_parent: Special & Others
---

{: .highlight-title}
> **IMPORTANT:**
> 
>As of Aug. 06.2023, FiveM has released an update to their client in order to block version 5.9 and above. Unfortunately this had also blocked the hotfix specifically for the crashing that they are trying to prevent.
>
>At the current time of Aug 08.2023 - this blocking still has not been removed. However, they have pushed an update to the beta and latest Release Channel in order to remove the blocking for 5.9.1 users.
>
>Meaning that you should switch your FiveM Release Channel over to Beta, or Latest, and then install the latest version of ReShade on [ReShade's website](https://reshade.me). - Jordan Brady Aug.08.2023
><div>
><img src="./images/fivem/fivem_release_channel.png" height="120px"/>
></div>
>Installing the latest update is the same process as previous, see below.

----------------

# Installing ReShade to FiveM:
While FiveM is a modification platform for Grand Theft Auto V, it requires it's own special proceedures in order to inject ReShade into FiveM itself.

Unfortunately, this is the way that the developers of FiveM have set up their client, and there is nothing that we can realistically can do about it.

In order to install ReShade properly to FiveM, you can proceed with the following step based guide!

----------------

### Step 1.
Start by installing ReShade to GTAV.<br>
You will likely want the addon-support build of ReShade from the [ReShade website](https://reshade.me).

{: .warning}
You must install ReShade to `GTA5.exe`<br>
Installing ReShade to the launcher will give you the wrong binary, and won't allow ReShade to inject properly.

----------------

### Step 2.
Once ReShade is installed to GTAV, navigate to your GTAV folder.<br>
You should see:

* `dxgi.dll` - ReShade Binary File
* `reshade.ini` - ReShade Settings File
* `ReShade-Shaders` - ReShade Shaders & Textures Folder

{: .note}
These files belong to ReShade, and are **needed** for Step 5.<br>
Do not close this folder!


----------------

### Step 3.
Navigate to the location of your FiveM install.

{: .note}
The **default** is `C:\Users\{USERNAME}\AppData\Local\FiveM`.<br>
The location of your install of FiveM **might** slightly differ.


----------------

### Step 4.
**Create** a `plugins` folder in the `FiveM Application Data` folder.

{: note}
Skip if this step is already there


----------------

### Step 5.
Cut or move the ReShade files and singular folder from your Grand Theft Auto V game folder, into your FiveM `plugins` folder.

These files and singular folder are: 
* `dxgi.dll` - ReShade Binary File
* `reshade.ini` - ReShade Settings File
* `ReShade-Shaders` - ReShade Shaders & Textures Folder

{: .warning}
Do not copy and paste these files over, as it will cause issues.

----------------

### Step 6.
Boot up FiveM up and check the console for errors using the F8 key.

If the ReShade installer cannot detect the install location of FiveM, or your ReShade ID has changed, you can get the error:

`Blocked load of ReShade Version 5 or higher - it has a bug that will lead to game crashes in GPU drivers or d3d11.dll.` <br>
`If you want to force it to load anyway, add the following section to {location of CitizenFX.ini file.}`<br>

`[Addons]`<br>
`ReShade5=ID:XXXXXXX acknowledged that ReShade 5.x has a bug that will lead to game crashes.`<br>
<div>
<img src="./images/fivem/fivem_reshade5_bs.png" height="120px"/>
</div>

In order to fix this, go to the same location that is in that error, and add the proper ID shown in your F8 console error to the `CitizenFX.ini` file.

{: .note}
If your game launches with ReShade, you are finished with the install.

----------------

## Possible errors if done wrong:
* `Ignored graphics mod \Grand Theft Auto V\dxgi.dll - these should go in plugins/ now!`<br>
    If this error occurs - you likely have not dropped ReShade into the `plugins` folder of your FiveM install directory - or you still have existing mod injections in your GTAV folder.<br> <br>


* `Blocked load of ReShade Version 5 or higher - it has a bug that will lead to game crashes in GPU drivers or d3d11.dll.` <br>
    `If you want to force it to load anyway, add the following section to {location of CitizenFX.ini file.}`<br>

    `[Addons]`<br>
    `ReShade5=ID:XXXXXXX acknowledged that ReShade 5.x has a bug that will lead to game crashes.`<br>
    If you get this error, please follow the steps in Step 6.

{: .warning}
If you get any errors relating to using 5.9 or above, you likely have not switched your FiveM Release Channel over to Beta, or Latest, or you are not using the latest version of ReShade!
