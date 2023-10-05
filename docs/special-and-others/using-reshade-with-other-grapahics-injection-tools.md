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

1. Download [ENBSeries](http://enbdev.com/download.html) for the game you want to use (it's recommended to look for sites that already pack some ENB presets since the default download only comes with a few example shaders)

2. extract the contents of the zip/rar file inside the root folder of the game (check [this guide](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) to find out where the root folder is)



</details>

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and ENB via Ultimate ASI Loader</summary>
[comment:] prob not need asi



</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>SpecialK</summary>

SpecialK is a project developed by Kaldaien that aims to improve game performance and provide additional features for PC gamers. It is a powerful tool that can help optimize games and enhance the overall gaming experience. 

While it's not specifically a graphics injection that can allow for large customizations to the visual output of your game, it does use the same injection front to allow for it's quality of life tools.

---

## Installing ReShade alongside SpecialK

[comment :] Information for why SpecialK is an issue alongside ReShade just like in the ENB section

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and SpecialK using SKIF</summary>



</details>

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and SpecialK using ASI Loader</summary>



</details>

---

<details markdown="block" class="details-tree">
<summary>Loading ReShade and SpecialK using SpecialK's Injection Proxy</summary>



</details>

</details>
