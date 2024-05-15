---
title: "ReGrade+ (Addon)"
layout: page
nav_order: 10
parent: "iMMERSE Ultimate"
grand_parent: Shader Repositories
---

# iMMERSE Ultimate: ReGrade +

ReGrade+ is a commercial-level color-correction suite for ReShade. Taking inspiration and trying to mimic the featureset of industry-standard and professional tools, this version of ReGrade aims to take way the middleman step of having to leave the game to make more granular and intuitive changes on an external software. Effectively turning color-correction into a single experience.

The advantage to this from the other implementations is that not only it offers that sort of featureset, but also makes it so the changes can be seen in real-time and with graphical interfaces similar to those tools thanks to its addon.

While everyone can use the tool and its capabilities, users with more knowledge on Color Theory, Photography and Image Post-Processing areas might take the most advantage of this shaders' features.

On the next set of instructions, we'll guide you through the installation of it along with the featureset it offers.

---

## Installing the ReGrade + Shader and Addon

Without the addon support build of ReShade, ReGrade +'s addon and shader **WILL NOT** work. 

Install the shader as normal, but for the Addon, you must place it close to the ReShade DLL and game's EXE, like this:

![ReGradePlus Addon Installation](../images/regradep_addon_installation.png)

If you want to test if everything was correctly installed, you can open your game, if it was, you'll have a new tab in ReShade's menu, named "ReGrade +."

![ReGradePlus ReShade Window Tab](../images/regradep_addon_tab.png)

With that done, the shader can be enabled by going to the "Home" tab and enabling `iMMERSE Ultimate: ReGrade+ [MartysMods_REGRADE+.fx]` and `iMMERSE Ultimate: ReGrade+ Histogram [MartysMods_REGRADE+.fx]`. The latter shader is so the addon's histogram widgets work and display the correct values.

---

## Using the Shader

Before explaining its parameters, we recommend you move the "ReGrade +" tab to a separate window in the ReShade / Game UI since that controls the entire shader. This will also allow you to tweak your other effects along with the color correction and visualize the results better without having to jump between windows.

Remember, enabling the Shader itself won't do anything, and if one of the components are not running, the Addon / Shader Window will tell, like so:

![ReGradePlus ReShade Window Alerts - All OFF](../images/regradep_shaders_off.png)

If everything is correct, it should look like this:

![ReGradePlus ReShade Window Alerts - All ON](../images/regradep_shaders_ok.png)

Now, with those ready, you can start tweaking the parameters, please note that different from the usual ReShade shaders, this one works differently and closer than professional industry tools, so its alright if you get confused at first.
This guide will do its best to help you with questions and whatever you might need to use this shader correctly.

---

## Scopes Window

The "Scopes" area of the window is an easy way to see graphics of various colour statistics and balances of the image. By default, it is configured to "Histogram RGB", which is supposed to show the exposure and color values on the current scene.

By clicking on the Drop-Down box, you can choose between different options, such as:

* **Histogram Y:** shows the Luma levels of the images.

* **Histogram RGB:** shows the color levels of the images.

* **Waveform Y:** shows the Luma levels of the image in a nice Waveform / Spectral visualization.

* **Waveform RGB:** shows the color levels of the image in the same Waveform / Spectral visualization.

You can also click the "Undock" button to have those working separated from the ReGrade+ window. Allowing for better organization of the workspace.

![ReGradePlus Scopes Window](../images/regradep_scopes_widget.png)

---

## Tweaks

The "Tweaks" section of the shader is dedicated for general tweaking of the images' brightness, saturation and whatnot. It is the region with less granularity and meant for quick-tweaks and changes without going deep into the image formatting.

The options we can see here are divided in Categories, and each one of those has lots of sub-categories, such as:

* **White Balance** which changes the colors and image tones related to the temperature and bright points of the images, the options available are:

    * **Temperature:** Changes the color temperature of the image.

    * **Lab Offset A:** Changes the level of Green and Magenta of the image.

    * **Lab Offset B:** Changes the level of Orange and Blue of the image.

* **Exposure** is all related directly to the image illumination, lighting and exposure, with a few color options aswell, those are:

    * **Exposure:** Changes the image exposure, which is how much light the lenses are absorbing. Lower values means a darker image, higher values means a brighter image.

    * **Contrast:** Changes the entire image's contrast levels.

    * **Gamma:** Changes the image's brightness.

    * **Filmic Gamma:** Changes the image's brightness on the dark and mid-points.

    * **Saturation:** Changes the image's color saturation. The higher the value, the more colorful the image is, the less, the more saturated.

    * **Vibrance:** Changes how vibrant the colors are. The higher tha value, the more vibrant.

* **High Dynamic Range** is all related to the image's lighting tweaks. This allows you to change anything inbetween all the brightness levels. The options are:

    * **Shadows:** Controls the brightness of the grey points of the image.

    * **Darks:** Controls the brightness of the darkest points of the image.

    * **Lights:** Controls how bright is the highest point of the image.

    * **Highlights:** Controls how bright are the highest light points of the image. It is recommended to always have the Lights level below this.

---

## Tone Curves

"Tone Curves" is one of the various interactive widgets available for the user in ReGrade+ , with this, you can make your own tonemap, which means you can choose how bright and dark each color or even the luminance levels are in a curve, essentially change the image lighting level even further to suit your needs.

By default, it comes enabled in the "RGB" mode, which tweaks all of the 3 main colors (Red, Green and Blue) toning and brightness, however, you can change to a per-channel mode by clicking the coloured squares in the lower part of the Graph.

![ReGradePlus Tone Curve Modes](../images/regradep_curves_mode.png)

To start using it, click on a point in the graph and move it to start changing the tone curve. To plot a new point, click somewhere else and move that point. The changes, along with the graphic, will all update in real-time.

![ReGradePlus Tone Curve Points Example](../images/regradep_curves_points.png)

You cannot delete per-point, so any time you need to revert the changes, you can right click and select "Reset to Default" to have all the curve changes and points undone.

---

## Color Correction

The "Color Correction" section is subdivided in two: "Split Tuning" and a "Color Wheel".

"Split Toning" allows you to change the colors in a per-light level basis. It has 3 wheels: "Shadows," "Midtones," and "Highlights."

There are two ways you can edit those values, you can either click on the point on the center of color wheel and move it on where you want it to be, or you can drag the gauges left and right for more granular and fine-tuning of the values.

![ReGradePlus Split Toning Wheel Example](../images/regradep_colorwheel_toning.png)

The second wheel allows you to change the color values of Red, Orange, Yellow, Green, Aqua, Purple and Magenta by Luma (brightness) and also Saturation (Amount of Color).

By default, the Color Wheel comes configured to change the color values based on Luma ("Hue vs Luma"), but you can change the values you're choosing by clicking on the small wheel. This allows you to change between the first mode and the "Hue vs Saturation" mode.

To tweak the values, click on the color you wanna change it and move it with the Mouse, by holding the "Shift" key, you can linearly move it in the vertical/diagonal axis, preventing mistakes when you wanna change its saturation or brightness without changing the color tone.

To reset the values of a changed color, right click on the point you wanna reset. 

While this part of the shader doesn't allow you to drag any sort of gauges, it allows you to see how much of the values are changed in each section of the spectrum.

![ReGradePlus Color Wheel Example](../images/regradep_colorwheel_example.png)