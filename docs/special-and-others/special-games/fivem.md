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
> As of Sep 01.2023, this block remains in place. However, an update to the beta and the latest `Update channel` has been pushed to unblock version 5.9.1 users.
>
> Therefore, **switch your FiveM `Update channel` to `Beta` or `Latest`**, and **install the latest version of ReShade** from [ReShade's website](https://reshade.me).
>
> ![FiveM Release Channel](../images/fivem/fivem_release_channel.png)
>
> Passing up this notice will not allow ReShade to work properly in your game. Do not utilize older builds of ReShade. - Jordan Oct. 10th, 2023

---

## FiveM

FiveM is a modification platform for Grand Theft Auto V, typically used for PVP and roleplay servers. 

Unfortunately, FiveM requires procedures from the end user in order to properlly allow ReShade to be installed to their client.

This design choice stems from the FiveM developers and there is nothing that the ReShade community can do to circumvent this. 

Please do not ask for additional help in relation to getting FiveM to work in accordance of the ReShade Discord, as all of the information you need to get ReShade running in FiveM is in this guide.

---

## **Step 1:** Install ReShade to GTAV

Begin by installing ReShade to GTAV from the [ReShade website](https://reshade.me). Always install the latest version of ReShade. Using older builds of ReShade will only cause issues for you in the future.

If you're unsure on how to install ReShade to GTAV, you can follow our guide for [installing ReShade](https://guides.martysmods.com/docs/reshade-guides/downloading-and-installing-reshade/)!

**When installing ReShade, make sure that you are installing ReShade to the `GTA5.exe` executable file. Installing to the launcher will provide you with an incorrect ReShade install, and will not work for you.**

---

## **Step 2:** Ensure ReShade Files are Installed

After installing ReShade to GTAV, open your GTAV folder. 

If you're unsure where your game directory is located, please follow our guide on [locating your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance!

Once in your GTAV folder, you will see the files:

* `dxgi.dll` - ReShade Binary File

* `reshade.ini` - ReShade Settings File

* `ReShade-Shaders` - ReShade Shaders & Textures Folder

If you cannot find the files, please follow the guide here on [enabling file extensions in Windows](https://guides.martysmods.com/docs/special-and-others/enabling-windows-file-extensions/)!

---

## **Step 3:** Locate your FiveM Installation

Open your FiveM install location.

Typically, this is `C:\Users\YOUR_USERNAME_HERE\AppData\Local\FiveM`. Replace `YOUR_USERNAME_HERE` with your actual username. Your install location might vary slightly.

If you're unable to find your FiveM install location, please follow our guide on [locating your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance!

---


## **Step 4:** Create or Navigate to the Plugins Directory

In the `FiveM Application Data` folder, create a `plugins` directory, then enter it.

If the `plugins` directory already exists, just enter it.

---

## **Step 5:** Transfer ReShade Files to the FiveM Plugins Directory

Transfer the ReShade files and the single folder from your GTAV directory into the FiveM `plugins` folder:

* `dxgi.dll` - ReShade Binary File

* `reshade.ini` - ReShade Settings File

* `ReShade-Shaders` - ReShade Shaders & Textures Folder

Avoid copying and pasting these files, as it can cause complications, instead cut and paste, or move the files.

---

## Step 6: Check for FiveM Errors using the Console

Launch FiveM and inspect the **entire** console for issues using the **F8 key**.

You are looking for the error below, please read it:

`Blocked load of ReShade Version 5 or higher - it has a bug that will lead to game crashes in GPU drivers or d3d11.dll.`<br>
    `If you want to force it to load anyway, add the following section to {location of CitizenFX.ini file.}`<br>
    `[Addons]`<br>
    `ReShade5=ID:XXXXXXX acknowledged that ReShade 5.x has a bug that will lead to game crashes`

![Error Screenshot](../images/fivem/fivem_reshade5_bs.png)

The location of your `CitizenFX.ini` file will be noted in green in your game console.

Visit the location of your `CitizenFX.ini` file, and open it.

Then copy the entire error from `[Addons]` downward into your CitizenFX.ini file.

The error you are copying has to be exactly as it was seen in the game console, otherwise it will not work.

Additionally, keep in mind that on the `Beta` or `Latest (Unstable)` clients of FiveM, your console will have lots to unpack. The error discussed above will likely require the user to check the actual FiveM log file, or scroll up to find it.
