---
title: Grand Theft Auto V
layout: page
nav_order: 3
parent: Special Games
grand_parent: Special and Others
---

## Installing ReShade to Grand Theft Auto V

Grand Theft Auto V unfortunately blocks `dxgi` and `d3d11` graphics injections now. 

With this in mind, you have to change the graphics injection point of ReShade to `d3d12`.

Below are steps on how to properly do this:

---

## **Step 1:** Install ReShade

Install ReShade to Grand Theft Auto V normally.

Ensure that you are selecting the `GTAV.exe` exectuable when installing ReShade, otherwise you will be installing ReShade improperly.

If you need help with the ReShade installation, refer to [our guide on downloading and installing ReShade.](https://guides.martysmods.com/docs/basic-reshade-guides/downloading-and-installing-reshade/)

---

## **Step 2:** Change `dxgi.dll` to `d3d12.dll`

Navigate to your Grand Theft Auto V folder and rename the file `dxgi.dll` to `d3d12.dll`.

If you need help finding the folder for Grand Theft Auto V, please follow our guide on [locating your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance!

---

## **Step 3:** Verify everything is working

Launch your game and verify that Grand Theft Auto V has launched properly and ReShade is installed!