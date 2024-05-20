---
title: "ReLight"
layout: page
nav_order: 13
parent: "iMMERSE Ultimate"
grand_parent: Shader Repositories
---

# iMMERSE Ultimate: ReLight

![ReLight Main Image](../images/relight-main.png)

ReLight is a point-lighting solution for ReShade. Similar to studio lights in photography, ReLight allows you to change the lighting, and adjust for more granular changes in the mood and details of the scenes.

While you can use it for any sort of scene, use-cases prove that close-ups or photos of humanoid models are the best cases for using ReLight. However, you're allowed to see as you fit.

---

## iMMERSE: Launchpad
Before starting, make sure Launchpad is properly installed and enabled within ReShade as it's a requirement for ReLight to work properly. Launchpad is included with the latest version of the iMMERSE Ultimate archive. Afterwards, find a location in-game and start tweaking ReLight.

ReLight is made to take advantage of specific Launchpad features, such as Smoothed and Textured Normals, so make sure to read the guide specific to [iMMERSE: Launchpad](https://guides.martysmods.com/docs/shader-repositories/immerse/immerse-launchpad/) if you ever get lost or feel like something could look better.

---

## ReLight's Debug

Upon enabling ReLight, you might not notice too much of a difference within your scene, In order to better visualize what ReLight is providing to the scene you can use the debug modes that are provided in the shader's arguments.

![Debug output preview](../images/relight-debug-output.webp)

---

## General Shader Arguments

Similar to RTGI, in the "Global" section of ReLight, you can tweak how much light from the original scene is kept and the overall parameters for the lighting and shadows.

The options for you to configure are:

* **Ambient Light:** How much of the original scene lighting is kept. `1` being all of the ambient light from the scene, `0` being no ambient light from the scene.

![Ambient Light Argument 1-0](../images/ambient-light-slider.webp)

* **Shadow Tracing:** This argument will control if and how the lights placed in ReLight will end up casting shadows. The options to choose from are "Off," "Visability Test," and "Recursive Path Tracing."

![Ambient Light Argument 1-0](../images/relight-shadow-tracing-type.webp)

* **Shadow Trace Quality:** Shadow Trace Quality will define the quality of the shadows that are being traced. The higher the quality, the more samples per ray are being accounted for, and therefore the sharper the shadows end up being.

![Shadow Trace Quality Low - Maximum](../images/relight-shadow-quality.png)

* **Z-Thickness:** Like in RTGI, "Z-Thickness" will define how thick or thin the objects are within the scene. Thicker objects will cast darker and more prominent shadows, while thinner ones will often cast lighter and less prominent shadows.

![Z-Thickness 0-2](../images/relight-z-thickness.png)

---

## Light Sources and Parameters

Each light source will have its category identified as "Light #." The number of light sources can be changed by going to the bottom of the shader's parameter list and selecting the `AMOUNT_OF_LIGHTS` preprocessor definition. By default, it comes with 2 lights and at most can go up to 4.

* **Active:** If the light source is active or not.

* **Type:** This will control what type of light that you are using for the specific light source you're configuring. You can choose between Point or Infinite.

* **Temp / Tint:** This argument allows the user to set the tint and tint control of the particular light source.

* **Intensity:** How bright and large the light source is within the screen space.

* **Shadow Penumbra:** Penumbra is the effect of the shadow when its leaking outside from being partially hit by light. Changing the argument for "Shadow Penumbra" will allow you to adjust how soft the shading cast from your ReLight probes will be in the final image.

* **Infinite Light: Azimuth/Elevation:** This will end up controling how the Infinite Light mode will end up casting light into the scene based on Azimuth and Elevation

* **Point Light: Position:** This argument will control where the light source is positioned within the screen space. First is horizontal (X), second is vertical (Y), and the third is the depth (Z).

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