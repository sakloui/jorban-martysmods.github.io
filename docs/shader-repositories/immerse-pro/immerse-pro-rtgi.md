---
title: "RTGI"
layout: page
nav_order: 5
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: RTGI

RTGI is iMMERSE's flagship shader. It is a screen-space raytraced global-illumination solution. RTGI brings realistic lighting to scenes, while not being too taxing on the performance, especially against other solutions of its class. Ultimately, bringing the best on quality to performance ratio.

RTGI is capable of highlighting details or adding details that are otherwise hidden to the scenes via Global-Illumination and Ambient Occlusion with Raytracing. It can also highlight textures via its recently added Specular GGX reflections.

Our guide below will make sure you'll be familiarized with it and will allow you to learn how to make the most usage out of it.

---

## iMMERSE: Launchpad

Before starting, make sure Launchpad is properly set-up. After that, find a place you want to try the shader in a game or application and get to tweaking it. If you do not have the iMMERSE Launchpad shader, you can grab it from the ReShade installer or by manually installing it from the [iMMERSE GitHub](https://github.com/martymcmodding/iMMERSE)

If you want to manually install the iMMERSE GitHub repository for Launchpad, make sure to follow [our guide on manually installing shaders for ReShade](https://guides.martysmods.com/docs/reshade-guides/manual-reshade-installs/#step-1-create-a-reshade-shaders-folder)!

RTGI is made to take advantage of specific Launchpad features, such as Smoothed and Textured Normals, so make sure to read the guide specific to iMMERSE Launchpad if you ever get lost or feel like something could look better.

---

## Enable iMMERSE Pro: RTGI and iMMERSE: Launchpad

Enable the shader `iMMERSE: Launchpad [MartysMods_LAUNCHPAD.fx]` in the "Home" tab of ReShade.

Drag and drop `iMMERSE: Launchpad [MartysMods_Launchpad.fx]` to the top of the ReShade "Home" tab to ensure that it's the first in the shader load order.

Enable the shader `iMMERSE Pro: RTGI [MartysMods_RTGI.fx]` in the "Home" tab of ReShade.

---

## "Ambient Light" argument

As of RTGI version 0.50 (released on 12/31/2023), RTGI now has an option to darken the overall scene to allow for the games to take more advantage of the Diffuse and Specular Global-Illumination introduced by RTGI. At first, your scene might look too dark for your liking, but that's what this function is here for.

The Ambient Light argument allows you to configure it from 0.0 to 1.0. Where 0.0 will be little to no original game scene lighting, and 1.0 will be fully lit by the game, with GI overlaying it. There isn't a value that fits all scenes, so it is all up to the user's preference.

A good strategy is to use these for close-up pictures or to give your scene more of a studio-lighting look by having only the parts you want lit illuminated.

![Comparison between none to full Ambient Lighting](../images/rtgi_ambient_lighting_comparison.webp)

Another tool to aid with ambient light in general is the new "Ambient Lighting Sky Intensity" feature, added in 0.51 (released 21/08/2024) to replace the old "Skycolor" feature, working together with Ambient Lighting to help the scenes have a more accurate light tone, this new revision allows it to work better with indoors, which might contribute for more moody scenes of indoors.

The value goes from 0.0 to 1.0, with 0 being none, and 1 being the max. Please take note that in dark scenes, it will darken the environment, so have that in mind.

![Comparison between none to full Sky Intensity](../images/rtgi_sky_lighting_comparison.webp)

---
	
## Configuring Scene lighting

With the above said, we'll start by tweaking the scene lighting again in a case which the Ambient Lighting argument is really low, allowing RTGI to effectively replace the game's lighting.

First, we'll start up by changing the quality of the RTGI by going on the "Diffuse GI Quality" setting. It has a few presets, with "Low" being the lowest but fastest, and "Ultra" being the highest but the most performance-consuming one.

The higher the quality, the larger the GI will bleed and the less noise it will have in the final result.

![Comparison of Quality Levels](../images/rtgi_quality_comparison.webp)

Second option that will need to be tweaked is "Diffuse GI Radius." This option tells RTGI how far you want the global-illumination to go in the scene. 

The larger this is, the more the bright elements will spread on the scene. With 1 being little to no light bleeding and 20 being the farthest it can reach.

![Comparison of GI Radius](../images/rtgi_radius_comparison.webp)

The last option is "Diffuse Bounce Lighting Intensity." This option tells RTGI how much Diffuse lighting you want within the scene. 

You want to configure this option to provide as much bounce lighting you want, while not making light sources overbrighten the entire scene.

![Comparison of Bounce Lighting Values](../images/rtgi_bouncelighting_comparison.webp)
	
Now, to fine-tune it, change the "Fade-Out Range" so what you want covered from the scene gets covered up and "Z-Thickness" to change how thin or thick the objects on the scene are to add shadows.

In "Z-Thickness," always try to keep a balance of how dark the objects look around. A lower value will make little to no AO (no shadows), and a higher value will cause shadows to be disproportionate.

This is also useful to avoid halos around objects which shouldn't have them.

---

## Tweaking textured normals and specular reflections

As of 0.50, the PBR GGX Specular Reflection feature has been re-introduced. This feature allows RTGI to "guess" reflective surfaces and how rough or smooth they are. Combined with Launchpad's Texture Normals, it allows for a "wet-floors" while not looking out of place, or to give extra depth to scenes.

Please note that this feature "only works on DirectX 10 and up, OpenGL and Vulkan", it does not work with DirectX 9 given its age and limitations. So, moving those sliders in a DX9 application will result in no changes.

Make sure to also check Launchpad, as it has special integration with "Texture Normals" to keep details and highlights of the scene textures intact, while adding reflections. If there is too much noise on them, tweak the "Texture Normals Sample Radius" and "Texture Normals Intensity" on Launchpad until it looks correct to your tastes.

Observations out of the way, lets learn about its parameters.

Starting with "Specular GI Quality," this works the same as the "Diffuse GI Quality" parameter, except it will only affect the reflections part, you can keep that on "Low" if you're not planning on having them enabled to save computational power and framerate.

Then, the second parameter: "Specular Lighting Intensity". This tells RTGI how much the surfaces reflect on the scene. With 0 disabling the reflections fully. 

If you don't want to cause a "wet-world" effect, tweak those until they just show a bit of the geometry above them.

![Specular Lighting Preview](../images/rtgi_specular_comparison.webp)
	
At last, we have "Surface Roughness," this tells how Defined the reflections are, since RTGI doesn't know how rough surfaces are, it guesses and blurs the reflections as a mean to make it more rough and less defined. 0 makes the reflections super-shiny and defined, while 1.0 makes them super-blurry and hard to see.
	
![Reflection Roughness Comparison](../images/rtgi_reflection_comparison.webp)
	
---

## Experimental section

It only has one option, which is "Assume sRGB Input," with games that has flat and simple lighting, this will prevent washing the scene's colors or making them too bright. For games with more detailed lighting, having this disabled will help highlight the scenes details.