---
title: Installing ReShade Alongside Other Mods
layout: page
nav_order: 3
parent: Advanced ReShade Guides
---

# **Installing ReShade alongside other mods**
In this guide we will learn how to install ReShade alongside other mods that also require the mod `.dll` file to be named `d3d9.dll` or `dxgi.dll`.

ReShade and other graphical mods need their file name to be named like this so they can load together with the application they intend to hook to.

Other alternative file names for mods can be for example `dinput.dll` or `dinput8.dll`, if you ever tried to mod old DirectX 9 games you probably came across said files before, they can be used as loaders for other mods or one single standalone mod.

Today we will learn how to inject ReShade using [ENB Series](http://enbdev.com/download.html) and [SpecialK](https://github.com/SpecialKO/SpecialK)


<details markdown="block" class="details-tree">
<summary>Installing ENB Series</summary>

---

ENBSeries is the project of graphic modifications for games. The main idea is to allow every gamer to configure how game looks like for their own taste, so every player could share settings with others. Many games may look much better and ENBSeries is the easiest way to improve them.


---

1. [Download](https://github.com/ThirteenAG/Ultimate-ASI-Loader/releases/tag/v5.4) the ASI Loader version that matches the game architecture (32 or 64 bits) from the releases page on github.
    > You can check the application architecture by opening the task manager while it is open and looking for the (32 bits) flag.
   
    > If there is not (32 bits) flag then the application is 64 bits
    
    ![App Architecture](../images/installing-reshade-alongside-other-mods/application_architecture.png)

2. Extract the file to the root folder of the game you want to use ReShade on.

    <details markdown="block" class="details-tree">
    <summary> if your game already has a dinput8.dll file you can use one of the following file names for the ASI Loader .dll file.</summary>
    
    ![ASI filenames](../images/installing-reshade-alongside-other-mods/ASI_filenames.png)
    </details>

3. We are done with ASI Loader for now
</details>

---

 <details markdown="block" class="details-tree">
[comment]: <>  <summary>Installing ReShade with ASI Loader</summary>


Now we need to install ReShade and get all the files created after the installation .

`dxgi.dll` or `d3d9.dll` for DirectX 9 games.

`ReShade.ini` containing most of the ReShade settings.

`ReShadePreset.ini` with the default blank preset.

and the `reshade-shaders` folder.

![ReShade files](../images/installing-reshade-alongside-other-mods/reshade_files.png)

After the installation we are going to create a new folder inside the root folder of the game called `plugins`.
 
After creating said folder we need to move all the ReShade files and folders listed above to the `plugins`folder we just created.

After moving the files we need to change the file extension of the ReShade `.dll` file to `.asi`.

The file name before the extension doesn't matter to ASI Loader as long as the extension is `.asi`, so we can rename our ReShade dll to `ReShade.asi` just to keep things organized.

![Plugins folder](../images/installing-reshade-alongside-other-mods/reshade-plugins-folder.png)

All ReShade shaders files (the ones that have an `.fx`extension) and textures should go in their respective folders inside the `[GAME_FOLDER]/plugins/reshade-shaders/...` folder 


Now here comes the fun part, if we have another mod (for ex ENB or a trainer) that needs to have the file name `dxgi.dll` or `d3d9.dll`.

We can just rename it and change its file extension `ENB.asi` and move the `plugins` folder we just created.

Remember that all other `.ini` files that are use for mods configurations should also go inside the `plugins` folder otherwise some mods will break when trying to find said files.


Launch the game and hope for the best :thumbsup:

</details>
 