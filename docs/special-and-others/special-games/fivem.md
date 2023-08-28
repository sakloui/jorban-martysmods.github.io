---
title: FiveM
layout: page
nav_order: 1
parent: Special Games
grand_parent: Special and Others
---

{: .warning-title }
> IMPORTANT NOTICE:
> 
> As of Aug. 06.2023, FiveM released an update to their client, blocking version 5.9 and above. This also blocked the hotfix designed to prevent crashes.
>
> As of Aug 08.2023, this block remains in place. However, an update to the beta and the latest `Update channel` has been pushed to unblock version 5.9.1 users.
>
> Therefore, **switch your FiveM `Update channel` to `Beta` or `Latest`**, and **install the latest version of ReShade** from [ReShade's website](https://reshade.me). - Jordan Brady Aug.08.2023
>
> ![FiveM Release Channel](../images/fivem/fivem_release_channel.png)

The installation process remains the same as before.

---

# FiveM

FiveM, a modification platform for Grand Theft Auto V typically used for PVP and roleplay servers, demands specific procedures to integrate ReShade with the client properly.

Unfortunately, this design choice stems from the FiveM developers and there is nothing that the ReShade community can do to circumvent this! 

To install ReShade to FiveM, please follow the step-by-step guide below:

---

## Step 1: Install ReShade to GTAV

Begin by installing ReShade to GTAV from the [ReShade website](https://reshade.me).

* If you're unsure on how to install ReShade to GTAV, you can follow our guide for [installing ReShade](https://guides.martysmods.com/docs/basic-reshade-guides/downloading-and-installing-reshade/)!

* Please ensure that you are using the latest version of ReShade!

{: .warning }
> Ensure ReShade is installed to `GTA5.exe`. 
> 
> Installing to the launcher provides an incorrect binary, preventing proper ReShade injection.

---

## Step 2: Ensure ReShade Files are Installed

After installing ReShade to GTAV, open your GTAV folder. 

You should notice the files:

* `dxgi.dll` - ReShade Binary File

* `reshade.ini` - ReShade Settings File

* `ReShade-Shaders` - ReShade Shaders & Textures Folder

    * If you're unsure where your game directory is located, please see our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance!

    * Ensure that you also have file extensions enabled in Windows in order to properly see these files and their extensions.<br> We have a guide here on [how to enable file extensions in Windows](https://guides.martysmods.com/docs/special-and-others/enabling-windows-file-extensions/)!

{: .note }
> These files are essential for Step 5. 
>
> **Do not close the folder until the end of the procedure!**

---

## Step 3: Locate your FiveM Installation

Open your FiveM install location.
    
- If you're unsure where your game directory is located, please see our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance!

{: .note }
Typically, this is `C:\Users\YOUR_USERNAME_HERE\AppData\Local\FiveM`. Replace `YOUR_USERNAME_HERE` with your actual username. Your install location might vary slightly.

---


## Step 4: Create or Navigate to the Plugins Directory

In the `FiveM Application Data` folder, create a `plugins` directory.

{: .note}
If the folder already exists, skip this step.

---

## Step 5: Transfer ReShade Files to the FiveM Plugins Directory

Transfer the ReShade files and the single folder from your GTAV directory into the FiveM `plugins` folder:

 * `dxgi.dll` - ReShade Binary File

 * `reshade.ini` - ReShade Settings File

 * `ReShade-Shaders` - ReShade Shaders & Textures Folder

{: .warning }
Avoid copying and pasting these files, as it can cause complications, instead cut and paste, or move the files.

---

## Step 6: Check for FiveM Errors using the Console

Launch FiveM and inspect the console for issues using the **F8 key**.

If the ReShade installer can't pinpoint the FiveM install location, or if your ReShade ID has been altered, the following error might arise:

`Blocked load of ReShade Version 5 or higher - it has a bug that will lead to game crashes in GPU drivers or d3d11.dll.`<br>
    `If you want to force it to load anyway, add the following section to {location of CitizenFX.ini file.}`<br>
    `[Addons]`<br>
    `ReShade5=ID:XXXXXXX acknowledged that ReShade 5.x has a bug that will lead to game crashes`

![Error Screenshot](../images/fivem/fivem_reshade5_bs.png)

To remedy this, visit the location mentioned in the error and incorporate the specified ID from your F8 console error into the `CitizenFX.ini` file located in the directory in the error. The directory where `CitizenFX.ini` may change per user, but is noted in green.

{: .note }
If ReShade successfully launches with your game, the installation is complete.

---

## Potential Errors:

- `Ignored graphics mod \Grand Theft Auto V\dxgi.dll - these should go in plugins/ now!`<br><br>
    If this pops up, you might have neglected to place ReShade in the `plugins` directory of your FiveM installation, or other mod injections persist in your GTAV folder.

{: .warning }
Errors related to using version 5.9 or above suggest that you haven't transitioned your FiveM Release Channel to Beta or Latest, or that you're not using the latest ReShade version.

