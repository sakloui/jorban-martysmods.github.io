---
title: Using ReShade with Other Graphics Injection Tools
layout: page
nav_order: 99
parent: Special and Others
---

## **Using ReShade with Other Graphics Injection Tools**

Graphics injection tools are frequently used to make large modifications to games or applications, allowing users to customize the visual output of their experience. These tools typically come in the form of a `.dll` file and may conflict with each other if they lack proper naming conventions or graphics injection proxy systems.

The following guides will provide instructions on how to install and use ReShade in conjunction with graphics injection tools such as ENB and SpecialK.

---

<details markdown="block" class="details-tree">
<summary>ENBSeries</summary>

ENBSeries is a project developed by Boris Vorontsov that allows users to massively overhaul the visuals of games it is built for. It is a powerful graphics modification tool that can greatly enhance the visual quality of it's games. One of the key features of ENBSeries is its flexibility and customization options. Users can tweak various parameters and settings to achieve their desired visual style. This level of customization allows for a highly personalized gaming experience, tailored to individual preferences.

---

## Installing ENB alongside ReShade:

When multiple mods are combined in a single game, various issues can arise, such as conflicting file names or simultaneous access to internal game resources, that can result in glitches or crashes.

ENBSeries is commonly used in conjunction with ReShade to provide additional customization options for game visuals.

Unlike ReShade, ENBSeries is not a generic tool. Each game requires its own specific version of ENBSeries for compatibility. However, it offers access to a wider range of internal game resources that are tailored to that specific game, such as time of day, information about textures ingame, skin detection, and more.

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and ENB via ENBProxy</summary>

1. Download [ENBSeries](http://enbdev.com/download.html) for the game you want to use. It's recommended to look for websites that already provide ENB presets, as the default download only includes a few example shaders.

2. Extract the contents of the downloaded zip/rar file into the root folder of your game. If you're unsure about the location of the root folder, refer to [our guide on finding your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance.

3. Rename the ReShade `.dll` file to `reshade.dll`.

4. Open the `enbseries.ini` file and edit the following lines:
```
EnableProxyLibrary=true
InitProxyFunctions=false
ProxyLibrary=reshade.dll
```
5.  Save the edits you made.

{: .warning }
Make sure to follow the capitalization as shown in the guide, otherwise you will have problems loading ENB or ReShade.


</details>

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and ENB via Ultimate ASI Loader</summary>

For older DirectX 9 games we might need some other mods to make everything work together, one of those is [Ultimate ASI Loader](https://github.com/ThirteenAG/Ultimate-ASI-Loader).

1. Download the latest [ASI Loader](https://github.com/ThirteenAG/Ultimate-ASI-Loader/releases/) release.

2. Extract the contents of the downloaded zip/rar file into the root folder of your game. If you're unsure about the location of the root folder, refer to [this guide](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for assistance.

3. If there are conflicting file names for the ASI Loader file, you can use one of the examples listed below.

![ASI File names](../images/using-reshade-with-other-grapahics-injection-tools/ASI_filenames.png)

4. create a new folder called `plugins` in the root folder of the game.

5. Move the ReShade files to the plugins folder, these being:
```
reshade-shaders
ReShade.ini
ReshadePreset.ini
d3d9.dll
```
6. After moving the ReShade files to the plugins folder, change the extension on the ReShade file from `d3d9.dll` to `d3d9.asi`

7. Download and extract the ENBSeries files into the root folder of the game.

{: .important  }

The ReShade installation is now being loaded from the plugins folder, every new shader and texture added should go into ``GAME_FOLDER/plugins/reshade-shaders/`` and ReShade Addons should go into ``GAME_FOLDER/plugins/``

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>SpecialK</summary>

SpecialK is a project developed by Kaldaien that aims to improve game performance and provide additional features for PC games, such as fine tunning HDR settings and providing support for custom textures. It is a powerful tool that can help optimize games and enhance the overall gaming experience. 

---

## Installing ReShade alongside SpecialK

As with any combination of mods, installing SpecialK with ReShade may cause issues with games ranging from graphical glitches to stutters, bad performance and crashes.

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and SpecialK</summary>

1. Download and install [Special K Injection Frontend (SKIF)](https://www.special-k.info/).

2. The installer will create a shortcut on your desktop. Upon the first launch, it will automatically detect and list all the games installed on your PC.

3. Install ReShade following the usual installation process.

4. Double-click on the game in the SpecialK launcher, and it will launch with both SpecialK and ReShade.

5. To open the SpecialK GUI, press `Ctrl + Shift + Backspace`.

![SpecialK Shortcut](../images/using-reshade-with-other-grapahics-injection-tools/crtl_shift_backspace.png)

For more information check out he official SpecialK [wiki](https://wiki.special-k.info/en/SpecialK/ReShade) page for ReShade

{: .warning}

Do not use SpecialK in multiplayer games.

</details>

</details>
