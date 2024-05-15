---
title: "ReLight"
layout: page
nav_order: 13
parent: "iMMERSE Ultimate"
grand_parent: Shader Repositories
---

# iMMERSE Ultimate: ReLight

ReLight is a point-lighting solution for ReShade. Similar to Studio Lights in photographs, and point lighting in games and photomodes, it allows to change the lighting of a scene. Allowing for more granular changes in the mood and details of the scenes.

While you can use it for any sort of scene, use-cases prove that close-ups or photos of humanoid models are the best cases for using it. However, you're allowed to see as you fit, below is how to install and use it.

---

## iMMERSE: Launchpad

Before starting, make sure Launchpad is properly set-up. After that, find a place you want to try the shader in a game or application and get to tweaking it. If you do not have the iMMERSE: Launchpad shader, you can grab it from the ReShade installer or by manually installing it from the [iMMERSE GitHub](https://github.com/martymcmodding/iMMERSE)

If you want to manually install the iMMERSE GitHub repository for Launchpad, make sure to follow [our guide on manually installing shaders for ReShade](https://guides.martysmods.com/docs/reshade-guides/manual-reshade-installs/#step-1-create-a-reshade-shaders-folder)!

ReLight is made to take advantage of specific Launchpad features, such as Smoothed and Textured Normals, so make sure to read the guide specific to [iMMERSE: Launchpad]() if you ever get lost or feel like something could look better.

---

## Enable iMMERSE Ultimate: ReLight and iMMERSE: Launchpad

Enable the shader `iMMERSE: Launchpad [MartysMods_LAUNCHPAD.fx]` in the "Home" tab of ReShade. Launchpad needs to be above ReShade

Enable the shader `iMMERSE Ultimate: ReLight [MartysMods_RELIGHT.fx]` from the "Home" tab of ReShade.

---

## ReLight's Debug

After enabling, you might not notice too much difference, but its enabled, however, to better visualize it, we gotta first go through the Debug modes.

The shader has a debug section and under exists the option "Debug outputs." Changing this to "Lighting will allow you to instantly see the scene with a very faint light.

![Debug output preview](../images/relight-debug-out.png)

---

## General Shader Arguments

Similar to RTGI, in the "Global" section, you can tweak how much light from the original scene is kept and the overall parameters for the lighting and shadows, here, the options are the following:

* **Ambient Light:** How much of the original scene lighting is kept

* **Trace Shadows:** If the light will cast shadows. The two parameters below are directly related to that.

* **Shadow Penumbra:** Penumbra is the effect of the shadow when its leaking outside from being partially hit by light. This defines how wide it is, and consequently, how intense it / dark it will look.

* **Z-Thickness:** Like in RTGI, it defines how thick or thin the objects are. Thicker objects will cast darker shadows, while thinner ones might cast lighter and wider shadows.

* **Shadow Trace Quality:** How defined and how many tracces the ReSTIR casted shadows have. The higher the quality, the sharper the shadows but also the higher the performance consumption.

---

## Light Sources and Parameters

Each light source will have its category identified as "Light #." The number of light sources can be changed by going at the bottom of the shader's parameter list and selecting the `AMOUNT_OF_LIGHTS` preprocessor definition. By default, it comes with 2 lights and at most can go up to 4.

With that out of the way, you can tweak the following about the light sources:

* **Active:** If the light source is active or not.

* **Position:** The light source position on the screen. First is Horizontally, Second is Vertically and the Last one is the depth.

* **Tint:** Sets the color of the selected light source.

* **Intensity:** How bright the light is.

---

## Humans and Sub-Surface Scattering

Sub-Surface Scattering (SSS) is the term for the light which bounces from inside the skin or from inside translucent surfaces. It is very common with humans and other organic matter, such as plants.

The shader also has a quite good simulation for that effect, despite not knowing what is organic and what isn't.

Below are the parameters related to that:

* **Enable Sub-Surface Scattering:** Enables the SSS function in the shader. Not all scenes require it, so having a toggle is very helpful and saves on performance.

* **Subsurface Scattering Quality:** Changes the quality of the effect. Higher quality will have better light traversal on those areas, however, with a bigger performance hit.

* **SSS Translucency Radius:** Defines how deep or thick the "translucent" surfaces are. With higher values bringing more brigther and colorful light inside those areas.

* **SSS Saturation:** How saturated the colors in those areas are.

* **SSS Diffusion Radius:** How farther the sub-surface lighting will bleed onto the nearby surfaces.

* **SSS Skin Hue:** In the color wheel, defines what color / hue should be used to detect what is a fitting area for the Subsurface Scattering to consider as a skin.

* **SSS Skin Hue Tolerance:** Defines how strict the color has to be to be considered as a skin part. The higher the value, the closer to that absolute color.