---
title: FiveM
layout: page
nav_order: 1
parent: Special Games
---

# FiveM

FiveM is a modification platform for Grand Theft Auto V, typically used for PVP and roleplay servers. 

Unfortunately, FiveM requires procedures from the end user in order to properlly allow ReShade to be installed to their client.

This design choice stems from the FiveM developers and there is nothing that the ReShade community can do to circumvent this. 

Please do not ask for additional help in relation to getting FiveM to work in accordance of the ReShade Discord, as all of the information you need to get ReShade running in FiveM is in this guide.

---

## **Step 0:** Housekeeping:

For this guide to be followed through step-by-step, you will have to first step up Windows file extenions to be properly viewed.

You can get the information for setting up Windows file extensions to be viewed by following this our guide for [enabling Windows file extensions](https://guides.martysmods.com/docs/additional-guides/enabling-windows-file-extensions/)!

---

## **Step 1:** Install ReShade to GTAV

Begin by downloading the latest version of ReShade from the [ReShade website](https://reshade.me).

**DO NOT use older builds of ReShade** as it will only cause issues for you in the future.

If you are struggling to install ReShade ot GTAV, please [follow our guide for installing ReShade](https://guides.martysmods.com/docs/reshade-guides/downloading-and-installing-reshade/).

---

## **Step 2:** Ensure ReShade Files are Installed

Navigate to your GTAV folder by using our [guide for locating your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/)!

Once there, look specifically for these two files, and singular folder and keep a mental note of where they are located:

* `dxgi.dll` - ReShade Binary File

* `reshade.ini` - ReShade Settings File

* `reshade-shaders` - ReShade Shaders & Textures Folder

![GTAV ReShade Install Files](../images/fivem/gtav-reshade-install-files.png)

---

## **Step 3:** Set FiveM to update using the **Beta Channel**

Open FiveM and then navigate to the settings menu, and go to the `Game` tab.

There you will find an option specifically for `Update Channel`.

Click on the `Beta` option and then close your game.

![Release Channel Screenshot](../images/fivem/fivem-release-channel.png)

---

## **Step 4:** Locate your FiveM Installation

In order to locate your FiveM location, please utilize our [guide for locating your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/)!

![FiveM File Location](../images/fivem/fivem-file-location.png)

---

## **Step 5:** Create or Navigate to the Plugins Directory

Once you have located your FiveM Installation folder, enter the `FiveM Application Data` folder, and create a `plugins` directory, then enter it.

![FiveM appdata Location](../images/fivem/fivem-appdata-location.png)

![FiveM plugins Location](../images/fivem/fivem-plugins-location.png)

---

## **Step 6:** Transfer ReShade Files to the FiveM Plugins Directory

Transfer the ReShade files and the single folder from your GTAV directory into the FiveM `plugins` folder:

* `dxgi.dll` - ReShade Binary File

* `reshade.ini` - ReShade Settings File

* `reshade-shaders` - ReShade Shaders & Textures Folder

![FiveM reshade install Location](../images/fivem/fivem-reshade-install-location.png)

{: .note}

Avoid copying and pasting these files, as it can cause complications, instead cut and paste, or move the files.

---

## Step 7: Check for FiveM Errors using the Console

Launch FiveM and inspect the **entire** console for issues. You can open the console by tapping the **F8 Key** on your keyboard.

In the console, you are looking for the error below, please read it fully:

![Error Screenshot](../images/fivem/fivem_reshade5_bs.png)

This error holds all of the steps needed in order to fix the issue that you are facing. In Green text will be the location of your `CitizenFX.ini` file. You will need to open this file and copy the entire error from `[Addons]` downards in order to solve the issue. If this is not copied exactly how it is written in your console, then you will not be able to fix the issue.