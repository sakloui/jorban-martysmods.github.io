---
title: FiveM
layout: page
nav_order: 1
parent: Special Games
---

# FiveM

FiveM is a modification platform for Grand Theft Auto V, typically used for PVP and roleplay servers. Unfortunately, FiveM requires procedures from the end user in order to properlly allow ReShade to be installed to their client. This design choice stems from the FiveM developers and there is nothing that the ReShade community can do to circumvent this. 

{: .warning }
Do not ask for additional help in relation to getting FiveM to work in accordance of the ReShade Discord, as all of the information you need to get ReShade running in FiveM is in this guide.

---

## Housekeeping

For this guide to be followed through step-by-step, you will have to first set up Windows file extenions to be properly viewed. You can get the information for setting up Windows file extensions to be viewed by following this our guide for [enabling Windows file extensions](https://guides.martysmods.com/docs/additional-guides/enabling-windows-file-extensions/)!

---

## Install ReShade to GTAV

Start by downloading the latest version of the Add-on Support Build of ReShade. Make sure to not install ANY add-ons in this process. If you are struggling to install ReShade to GTAV, please [follow our guide for installing ReShade](https://guides.martysmods.com/docs/reshade/downloading-and-installing/).

---

## Navigate to Your GTAV Folder

Navigate to your GTAV folder by using our [guide for locating your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/)! Once there, look specifically for these two files, and singular folder and keep a mental note of where they are located:

| File or Folder | Description |
| dxgi.dll | ReShade Binary File |
| reshade.ini | ReShade Settings File| 
| reshade-shaders | ReShade Shaders & Textures Folder |

![GTAV ReShade Install Files](../images/fivem/gtav-reshade-install-files.webp)

---

## Locate your FiveM Installation

In order to locate your FiveM location, please utilize our [guide for locating your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/)!

![FiveM File Location](../images/fivem/fivem-file-location.webp)

---

## Navigate to FiveM's Plugins Directory

Once you have located your FiveM Installation folder, enter the `FiveM Application Data` folder, and then into your `plugins` directory.

![FiveM appdata Location](../images/fivem/fivem-appdata-location.webp)

![FiveM plugins Location](../images/fivem/fivem-plugins-location.webp)

---

## Transfer ReShade Files from GTAV to the FiveM Plugins Directory

Cut and paste ReShade's files and `ReShade-Shaders` folder from your GTAV directory into the FiveM `plugins` folder:

| File or Folder | Description |
| dxgi.dll | ReShade Binary File |
| reshade.ini | ReShade Settings File| 
| reshade-shaders | ReShade Shaders & Textures Folder |

![FiveM reshade install Location](../images/fivem/fivem-reshade-install-location.webp)

---

## Press F8 and Check Your FiveM Log

Launch FiveM and press F8 on your keyboard to read the message in your log. FiveM should present you with the error:

![Error Screenshot](../images/fivem/fivem_reshade5_bs.webp)

This error holds all of the steps needed in order to fix the issue that you are facing. In Green text will be the location of your "CitizenFX.ini" file. You will need to open this file and copy the entire error from "[Addons]" downards in order to solve the issue. If this is not copied exactly how it is written in your console, then you will not be able to fix the issue. You can copy and paste these two lines into your "CitizenFX.ini" file, however, you MUST use your own ID instead of the dummy ID given:

```
[Addons]
ReShade5=ID:XXXXXX acknowledged that ReShade 5.x has a bug that will lead to game crashes
```

---

## Restart FiveM and enable "Fix UI Lag"

Restart the FiveM client and then go into your FiveM settings in order to enable FiveM's "Fix UI Lag" option. Afterwards, restart your game a final time.