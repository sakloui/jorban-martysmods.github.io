---
title: "LUT Manager (Addon)"
layout: page
nav_order: 11
parent: "iMMERSE Ultimate"
grand_parent: Shader Repositories
---

# iMMERSE Ultimate: Lut Manager

LUT Manager combines a LUT application shader with an addon to manage LUT textures on the fly. This can allow users to easily switch between different LUTs without having to create or utilize a shader for each individual LUT file.

---

## Installing the Addon and the Shader

Without the addon support build of ReShade, LUT Manager's addon and shader **WILL NOT** work. 

Install the shader as normal, but for the Addon, you must place it close to the ReShade DLL and game's EXE, like this:

![Example Addon Installation](../images/regradep_addon_installation.webp)

---

## Downloading and Installing LUTs

Look-Up-Tables, commonly refered to as LUTs, are a format of predefined color grades. In ReShade, they're often in the format of a LUT atlas PNG file. You can browse common LUT repositories [such as MLUT](https://github.com/TheGordinho/MLUT) in order to view, find, and download LUTs at your pleasure.

Once you have the LUTs that you desire, create a folder named "LUTs" in the game directory and place the LUT textures that you've aquired inside.

---

## Enabling the Shader

To enable LUT Manager, simply enable the shader `iMMERSE Ultimate LUT Manager [MartysMods_LUTMANAGER.fx]`, after that, go to the "Add-Ons" tab, and in it, you should see MartysMods LUT Manager. There you'll see the names of all the LUTs you have installed and you can click the files to open the LUT list.

After that, pick one from the list and, if the shader is enabled, the colors will change right away!

![Pic of the LUT manager Window](../images/lutmanager-window.webp)

The shader iteself has 2 toggles, one named "Enhanced LUT Quality," which upsamples the LUTs using a expensive method. This is best used with small 16x16x16 LUT textures. And another named "Show all LUTs in its current atlas side-by-side," this will show all LUTs in the current png side-by-side.

You can also right-click any of the LUTs you like the most and add them to a favorites list for easy-finding later.

![LUT Manager Favorites Window](../images/lutmanager-favs.webp)