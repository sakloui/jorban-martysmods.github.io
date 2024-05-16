---
title: "LUT Manager (Addon)"
layout: page
nav_order: 11
parent: "iMMERSE Ultimate"
grand_parent: Shader Repositories
---

# iMMERSE Ultimate: Lut Manager

LUT Manager combines the MultiLUT shader with an addon to manage LUT textures on the fly. Its more of a tool rather than a shader by itself.

In this guide we will detail installation steps along with how to use it effectively and how to organize your files.

---

## **Step 1: Installing the Addon and the Shader**

Without the addon support build of ReShade, LUT Manager's addon and shader **WILL NOT** work. 

Install the shader as normal, but for the Addon, you must place it close to the ReShade DLL and game's EXE, like this:

![Example Addon Installation](../images/regradep_addon_installation.webp)

---

## Installing LUTs

Before starting the game and enabling the LUTs, create a folder named "LUTs" in the game directory and place the LUT files you need there. All of the main LUT formats used by ReShade shaders are supported. Those included the LUTs from the repositories in the ReShade setup.

After that is done, just start the game, you may add more LUTs later ingame by reloading ReShade.

---

## Enabling the Shader

First, enable the Shader `iMMERSE Ultimate LUT Manager [MartysMods_LUTMANAGER.fx]`, after that, go to the "Add-Ons" tab, and in it, you should see MartysMods LUT Manager. There you'll see the names of all the LUTs / PNGs you have installed. Click in one of them to open the LUT list.

After that, pick one from the list and, if the shader is enabled, the colors will change right away!

![Pic of the LUT manager Window](../images/lutmanager-window.webp)

The shader iteself has 2 toggles, one named "Enhanced LUT Quality," which upsamples the LUTs using a expensive method. This is best used with small 16x16x16 LUT textures. And another named "Show all LUTs in its current atlas side-by-side," this will show all LUTs in the current png side-by-side.

You can also right-click any of the LUTs you like the most and add them to a favorites list for easy-finding later.

![LUT Manager Favorites Window](../images/lutmanager-favs.webp)