---
title: Grand Theft Auto V
layout: page
nav_order: 3
parent: Special Games
---

## Installing ReShade to Grand Theft Auto V

Grand Theft Auto: V is tricky to get ReShade properly installed for.

In a recent update, Grand Theft Auto: V developers decided to block certain graphics injections, and this has caused ReShade and other graphics injections to stop working properly.

Below will be several guides that you can follow in order to get ReShade working in Grand Theft Auto: V.

---

<details markdown="block" class="details-tree">
<summary>Just ReShade</summary>

This guide will go over how to install ReShade specifically for Grand Theft Auto: V and assumes that you have no other graphics injections installed.

---

## **Step 1:** Install ReShade through the ReShade Installer

Install ReShade to Grand Theft Auto: V through the ReShade Installer. If you need help with the ReShade installation, please refer to [our guide on downloading and installing ReShade.](https://guides.martysmods.com/docs/reshade-guides/downloading-and-installing-reshade/)

Make sure that you are selecting the "GTAV.exe" exectuable when installing ReShade through the ReShade Installer. If you select the wrong exectuable, the ReShade Installer will install the improper ReShade binary to your game directory.

---

## **Step 2:** Change the ReShade DLL name from "dxgi.dll" to "d3d12.dll"

Navigate to your Grand Theft Auto: V folder using our guide for [locating your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/) and rename the file "dxgi.dll" to "d3d12.dll".

</details>

---

<details markdown="block" class="details-tree">
<summary>ReShade with ENB</summary>

This guide will go over how to install ReShade alongside ENB in Grand Theft Auto: V.

---

## **Step 1:** Download ENB for Grand Theft Auto: V - Ignore if you already have ENB Installed

Navigate to the ENB page for Grand Theft Auto: V [http://enbdev.com/download_mod_gta5.htm](http://enbdev.com/download_mod_gta5.htm)

The ENB page for Grand Theft Auto: V will provide you with the latest version of ENB for Grand Theft Auto: V.

At the bottom of the page, click the latest version to go to it's change-log page.

![ENB Version Select Highlight](../images/gtav/enb-version-select.png)

Then click the download icon at the bottom of the change-log page.

![ENB Download Button Highlight](../images/gtav/enb-download-button.png)

---

## **Step 2:** Install ENB for Grand Theft Auto: V - Ignore if you already have ENB Installed

Open the archive that you have downloaded from the ENB page for Grand Theft Auto: V.

![ENB Archive Image](../images/gtav/open-enb-archive.png)

Then enter the "WrapperVersion" directory.

![ENB Wrapper Version Directory](../images/gtav/enter-wrapperversion-directory.png)

Once there you will be greated with a plethora of files:

![ENB WrapperVersion Files Image](../images/gtav/wrapperversion-files.png)

The files shown above are files are needed for ENB. 

Copy each of these files over to the Grand Theft Auto: V base directory. 

If you need help finding your Grand Theft Auto: V base directory, you can [follow our guide for finding your game's executable and directory](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

![Move ENB files to GTAV Directory](../images/gtav/enb-to-gtav-move.png)

---

## **Step 3:** Make a copy of ENB's "d3d11.dll" and rename it to "d3d12.dll"

This step has to be done because the latest version of Grand Theft Auto: V refuses to inject via the "d3d11.dll" injection name.

However, ENB does not like to inject via the "d3d12.dll" so this is the compromise.

You should have a two files that look identical to the image below.


![Renamed ENB DLL](../images/gtav/enb-dll-rename.png)

---

## **Step 4:** Install ReShade normally

Install ReShade as you normally would.

Make sure that you target the executable called "GTAV.exe" otherwise, the ReShade Installer will not copy over the proper binary file, and ReShade will not work.

</details>
