---
layout: page
nav_order: 2
parent: iMMERSE
---

# Configuring iMMERSE Shaders

Below there will be drop downs for each tier level of the iMMERSE suite.

In each iMMERSE suite dropdown there are guides or explanations for each shader:

---

<details markdown="block" class="details-tree">
<summary>iMMERSE</summary>

This section will guide you through setting up and configuring shaders within the iMMERSE shader suite!

---


---

<details markdown="block" class="details-tree">
<summary>iMMERSE: Anti Aliasing</summary>

iMMERSE Anti-Aliasing is Marty's itteration of SMAA.

SMAA is a method of anti-aliasing which is both fast and effective. It has became an industry standard since, leaving behind other performance-heavy shaders with the same goal.

Install the shader and then enable `iMMERSE Anti Aliasing [MartysMods_SMAA.fx]` in the `Home` tab of ReShade.

---

<details markdown="block" class="details-tree">
<summary>General Parameters</summary>

* `Edge Detection Type` 

    * This parameter provides different options to the user for customizing the type of edge detection used. The best option for most scenarios is `Color edge detection (max)`.

* `Enable Predicated Thresholding`

    * This feature allows iMMERSE Anti Aliasing to utilize the depth buffer to better calculate edges that often get missed by the edge detection methods. It is recommended to enable this feature.

* `SMAA_USE_EXTENDED_EDGE_DETECTION`

    * This preprocessor for iMMERSE Anti Aliasing extends the color detection range of SMAA, allowing for increased detection of edges. The usable values are 0 and 1.

</details>

---





</details>

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro Shader Guides</summary>

This section will guide you through setting up and configuring specific shaders within the iMMERSE Pro shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: RTGI</summary>

RTGI is iMMERSE's flagship shader. It is a screen-space raytraced global-illumination solution. RTGI brings realistic lighting to scenes, while not being too taxing on the performance, especially against other solutions of its class. Ultimately, bringing the best on quality to performance ratio.

RTGI is capable of highlighting details or adding details that are otherwise hidden to the scenes via Global-Illumination and Ambient Occlusion with Raytracing. It can also highlight textures via its recently added Specular GGX reflections.

Our guide below will make sure you'll be familiarized with it and will allow you to learn how to make the most usage out of it.

---

<details markdown="block" class="details-tree">
<summary>Initial Configuration</summary>

Before starting, make sure Launchpad is properly set-up. After that, find a place you want to try the shader in a game or application and get to tweaking it. If you do not have the iMMERSE Launchpad shader, you can grab it from the ReShade installer or by manually installing it from the [iMMERSE GitHub](https://github.com/martymcmodding/iMMERSE)

If you want to manually install the iMMERSE GitHub repository for Launchpad, make sure to follow [our guide on manually installing shaders for ReShade](https://guides.martysmods.com/docs/reshade-guides/manual-reshade-installs/#step-1-create-a-reshade-shaders-folder)!

RTGI is made to take advantage of specific Launchpad features, such as Smoothed and Textured Normals, so make sure to read the guide specific to iMMERSE Launchpad if you ever get lost or feel like something could look better.

</details>

---

<details markdown="block" class="details-tree">
<summary>Configuring the Shader</summary>



</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: Clarity</summary>



</details>

---

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: Depth of Field</summary>



---

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: ReGrade</summary>

ReGrade is a color-correction suite designed to be feature-packed enough to be close to commercial tools. With all of its available options, it has the power to bring the usability and versatility of even commercial-level tools to games. Effectively removing the step of toggling between a color-correction software and the game to finish editing, making it all real-time and hassle-free.

While there is no correct values and usage of this shader, people familiarized with Photography, color theory and related areas will make the best usage. However, even people with no experience can get great results by looking at the changes made being shown instantly.

---

## **Step 1: Installing the Shader**

Click on the `iMMERSE Pro ReGrade [MartysMods_REGRADE.fx]` shader and enable it. Once you do, all of its options will appear. 

The following steps will show each parameter and what they do.

---

## **Step 2: Color Operations and Slots**

At first, you should notice lots of drop-down boxes in the section "Color Operations", this tells the shader what color operation is applied on each step. Think of it like building blocks, with the first being the bottom layer, and the last being the top layer.
You have 9 slots available, and the following options, they can be applied in any order as the user desires or needs:

* `The parameters for each option is explained further down the guide, so if you wanna know the values for each function, keep reading.`

`Levels` will change the black and white levels of the image.

`Adjustments` is for general color and overall image changes without much granularity

`Lift Gamma Gain` allows you to tweak the "Lift", "Gamma" and "Gain" levels of the image.

`Calibration` allows you modify the default values for the Color Hues and Layers.

`Color Remapping` allows you to directly change the colors of the image.

`Tone Curves` allows you to change the tones of the exposed and unexposed (bright and dark) parts of the image.

`Split Toning` allows you to change the values and colors of the tones (exposed and unexposed) parts of the image separately. Effectively having even more granularity over "Tone Curves".

`Color Balance` allows for changing the colors on the Shadows, Midtones and Highlighs of the image, offering granularity beyond just the exposure of the shadows.

`Special Transforms` allows for more "artistic" changes on the scene brightness and light levels.

![ReGrade Slots](../images/configuring-immerse-shaders/regrade_slots_preview.png)

Now that you know each of the functions, lets get deeper and start doing some modifications.

---

## **Step 3: Levels Function**

Levels changes the black and white levels of a picture. On a bare explanation: It means it changes what is considered completely back and completely white on the image.
The parameters are:

`Bypass Levels` effectively disables the changes made in that layer.

`Black Level In` changes where the black levels start.

`White Level In` changes where the white levels start.

`Black Level Out` changes where the black levels end.

`White Level Out` changes the white levels end.

---

## **Step 4: Adjustments Function**

Adjustments are for overall global / wide adjustments of a picture. Its made to have less granularity and serve as quick tweaks to change and stabilize colors and scene without needing to fiddle with settings much.
The parameters for those are:

`Bypass Adjustements` disables the changes made in that layer.

`Contrast` changes the entire image's contrast.

`Exposure` changes the entire image exposure. Exposure is how much light the lens is absorbing. With higher values making the image brighter, and lower values making the image darker.

`Gamma` changes the brightness of the image.

`Filmic Gamma` changes the brightness of the dark points of the image.

`Saturation` changes how much the colors are saturated in the image.

`Vibrance` changes how vibrant and colorful the colors are in the image.

---

## **Step 5: Lift, Gamma and Gain functions**

Lift,Gamma and Gain changes separate the bright parts of the image in 3 layers - Dark, Midtones and Bright. Not only that, but it allows to change the colors of each one of them.
The parameters are:

`Bypass Lift Gamma Gain` disables the changes made in that layer.

`Lift Gamma Gain Mode` changes the way the calculations for it works, with 2 standards available, "American Society of Cinematographers" and "DaVinci Resolve", with the latter mimicing how the software works.

`Lift` changes the White levels of the image. If set to non-grey values, it will change the color aswell.

`Gamma` changes the midtones of the image. If set to non-grey values, it will change the overall temperature of the image.

`Gain` changes the dark levels of the image. If set to non-grey values, it will change the color of dark parts of the image.

---

## **Step 6: Calibration function**

This adjust overall color and temperature calibrations of the image. Again, for general changes without much need for granularity.
The parameters are:

`Bypass Calibration` disables the changes made in that layer.

`Color Temperature` changes the white / temperature of the entire image.

`Lab A Offset` changes the Magenta / Green balance of the image colors.

`Lab B Offset` changes the Orange / Blue balance of the image colors.

`R|G|B Primary Mode` changes how the color changing behaviour works, with 3 methods available: "ReGrade Legacy" mimicing the old ReGrade shader version, "Barycentric" and "Hue Based".

`R|G|B Primary Hue` changes the hue offset of each color channel (Red, Green and Blue)

`R|G|B Primary Saturation` changes the hue saturation value of each color channel (Red, Green and Blue)

---

## **Step 7: Color Remapping function**

Color remapping allows the user to change the color values of each one of the colors in the image, this allows them to have more control over the colors of the image.

The parameters dictate changes to each one of the colors (Red, Orange, Yellow, Green, Aqua, Blue and Magenta) , separating it by Hue (First Value), Saturation (Second Value) and Color Value (Third Value)

---

## **Step 8: Tone Curve function**

Tone curve allows the user to change the brightness of the 3 light values of the image per-tone, which means it can use this to make certain gradients within those areas brighter or darker.

The parameters for those are:

`Shadows` changes the images Shadow brightness.

`Darks` changes the images Dark points brightness.

`Lights` changes the images Bright points brightness.

`Highlights` changes the images brigthest points brightness.

`Dark Wash Range` changes how much dark points washes / bleaches the colours.

`Dark Wash Intensity` changes how intense the bleaching of the colors are.

---

## **Step 9: Split Toning function**

Split toning allows the user to change the tint of 2 of the image's tone properties in a curve.

The parameters are:

`Split Mode` changes which parts of the image's curve will be changed, being able to pick between Shadows / Highlights and Grey / Saturated Colors.

`Tint A` changes the tint / grey value of the first parameter.

`Tint B` changes the tint / grey value of the second parameter.

`Balance` changes which side will be more intense / prevalent, the lower the value, the more it will prioritize the first value, and the higher the value, the more the second value is prioritize.

`Blend Mode` changes how these changes are mixed in the image. With the option being "Soft Light" and "Overlay".

---

## **Step 10: Color Balance function**

Color balance changes the color Brightness and saturation of the image's lighting.

They are split in Dark, Hightlights and Midtones.

---

## **Step 11: Special Transforms**

Special transforms are more artistic changes for the image. 

There are 2 options here skipping the bypass one, which is `Bleach Bypass (Gamma Corrected)`, which bleaches taking Gamma into consideration, and `Gamma on Luma | Chroma`, which changes the gamma level on the colors and luminosity.

---

## **Step 12: Vignette and Utility**

Vignette applies a camera vignette effect, which darkens the image around. It doesn't depend on any of the layer slots since its always applied over all of them, but the difference between this and others is the fact it is deeply integrated into ReGrade, so it takes all the color and image changes into account when applying it.

The parameters for the Vignette are:

`Mechanical Vignette: Radius` changes the Vignette radius on the image.

`Mechanical Vignette: Blurryness` changes how out-of-focus the outer-part of the vignette is on the image.

`Mechanical Vignette: Shape` changes the shape of the vignette, with 0 being circular and higher values aiming for more anamorphic-looking ones.

`Sensor Vignette: Scale` changes how much of the vignette is visible on the image.

`Vignette Blending Mode` changes how the Vignette will be blended on the image. With "HDR simulation" focusing on the brightness and color levels and blending with those, with an option to preserve tones, and Standard just placing it over the image. 

---

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: Solaris</summary>

Solaris is IMMERSE's main implementation of a Bloom shader. Bloom shaders are meant to mimic light bleeding from very bright surfaces, similar to how a camera lens act when looking at very bright reflective objects.

It's differential is ease of usage, and quality x speed relation. It is a very fast shader with very high quality results.

To configure it, follow the below steps. In this guide, there is no "best" or "worst" option, its all up to personal preference.

---

## **Step 1:** Enable the Shader

Click on the `iMMERSE Pro Solaris [MartysMods_SOLARIS.fx]` shader and enable it. Once you do, there will be some options, first, lets start by setting up the scene settings.

---

## **Step 2:** Configure overall Scene Look

The first two options, `Log Exposure Bias` and `Log HDR Whitepoint` are responsible for telling how much light the "camera" is absorbing and how bright the "White" is. The more exposure bias, the more bloom, and the higher the Whitepoint, the more intense the bright parts will glow.

The last 3 parameters are the more "artistic" side of the bloom, those are:

* `Bloom Intensity`: Changes the overall intensity of the bloom. Independent of what area is considered white or "dark".
* `Bloom Radius`: How large are the light glows / ranges.
* `Bloom Hazyness`: Changes how much of the colors the bloom washes-away. With 0 being no color changes, and 1 being a full bleached look.

---

## **Step 3:** Technical Parameters

Those parameters are more techincal and won't change much of the final look, they are made for more specific changes or user needs.

* `High Resolution Input`: Changes the resolution the Bloom should sample the scene. Useful if you need to grab more detailed objects which should glow.
* `Mask by Depth`: Made as a way to prevent HUD elements from glowing. Enabling this will make it so the depth controls what will emit bloom or not.
* `Depth Mask Strength`: The higher it is, the far away the bloom will apply, with 0 being the same as having depth masking disabled.

The last 2 post-process parameters will also depend on your usage.

* `ENABLE_SOLARIS_REGRADE_PARITY`: This will make it so Solaris will work together with ReGrade, using its exposure parameters and levels to define the bloom on the scene.
* `SOLARIS_PERF_MODE`: Enables a higher-performance mode for Solaris, changing how it works internally to tax less of the computer. Not generally necessary, but low-performance setups might benefit from having it on.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Shader Guides</summary>

This section will guide you through setting up and configuring specific shaders within the iMMERSE Ultimate shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate: Convolution Bloom</summary>

Convolution Bloom (or FFT Bloom) is a more-advanced and high-end bloom based on Fast-Fourier Transform with a different end-effect. The way it works allows for bloom to have different shapes and sizes, instead of being just huge glowing light sources. Those being "Spikes", which simulates blades from a camera, and "Inverse Square Glow", which is similar to traditional bloom methods, but with a much higher range.

More about those will be shown later down the guide, meanwhile, we'll focus on the shared options.

---

## **Step 1:** Enabling the Shader

Click on the `iMMERSE Ultimate ConvolutionBloom [MartysMods_FFTBLOOM.fx]` shader and enable it. Most of the parameters are the same as Solaris, with only one new option shared between the (later) pre-processor options.

* `Bloom Padding`: Due to the way FFT works, the bloom will usually go beyond the screen resolution and boundaries and "leak" to the top or bottom of the image, causing weird / innacurate results. This parameter creates a black border to mitigate this, but will also reduce how far the bloom goes.
* `Log Exposure Bias` and `Log HDR Whitepoint` are responsible for telling how much light the "camera" is absorbing and how bright the "White" is. The more exposure bias, the more bloom, and the higher the Whitepoint, the more intense the bright parts will glow.
* `Bloom Intensity`: Changes the overall intensity of the bloom. Independent of what area is considered white or "dark".
* `Bloom Radius`: How large are the light glows / ranges.
* `Bloom Hazyness`: Changes how much of the colors the bloom washes-away. With 0 being no color changes, and 1 being a full bleached look.
* `Enable Debug View`: Shows multiple debug outputs to help see how the shader is working, with the first option showing only the output of the bloom (how the bright areas look without taking the general image into consideration) and the second showing the Fourier texture of the bloom (more dev-oriented).

---

## **Step 2:** Pre-Processor Options

Before talking about the other options, we must talk about the Pre-Processor ones since those interfere on what options you'll have at your disposure, the Pre-Processor settings are:

* `CONVOLUTION_BLOOM_QUALITY`: Changes the resolution of the Fourier kernel, higher values (from 0 to 2) will produce better results, but also require more resources.
* `CONVOLUTION_BLOOM_MASK_PRESET`: The default option is "Diffraction Spikes", which will create blades of light from glowing / bright sources, similar to the blades of a camera. The second one is "Inverse Square Glow", which will create a more traditional bloom (as in, light sources will spread lights to its surroundings).

---

## *Step 3:* Individual Options

The options of the First method, `Diffraction Spikes`, are:

* `Diffraction Spike Amount`: How many "Spikes" the bloom has, basically working as how many blades the "camera" has.
* `Diffraction Spike Rotation`: The rotation of the blades, as in, if they are coming straight from vertical, or tilted. 
* `Diffraction Spike Radius`: How far the "spikes" of light go through the image. The higher the value, the further they'll reach.
* `Diffraction Spike Blurryness`: How blurry the spikes are. The lower the value, the more evident the spike shapes are.
* `Diffraction Spike Phase Amount`: How bright the spikes (blades) are, not the light sources. The higher, the brighter / more visible the spikes will appear.

The options for the Second method, `Inverse Square Glow`, are:

* `Glow Intensity`: How far the bloom goes and how intense it is, higher values means further and brighter.
* `Glare Amount`: How far the "dark" part of the bloom goes, the higher, the darker it is at the edges of the bloom sources.

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate: ReLight</summary>

ReLight is a point-lighting solution for ReShade. Similar to Studio Lights in photographs, and point lighting in games and photomodes, it allows to change the lighting of a scene. Allowing for more granular changes in the mood and details of the scenes.

While you can use it for any sort of scene, use-cases prove that close-ups or photos of humanoid models are the best cases for using it. However, you're allowed to see as you fit, below is how to install and use it.

{: .note}
It doesn't require iMMERSE RTGI, however, using it together with it might result in even better screenshots.

---

## **Step 1: Installing the Shader and enabling it**

To install the shader, simply copy the shader file to the Shaders folder and enable `MartysMods_RELIGHT [MartysMods_RELIGHT.fx]` from the "Home" tab of ReShade, in the shaders list. It should now be enabled.

---

## **Step 2: Enabling the debug mode and starting to tweak**

After enabling, you might not notice too much difference, but its enabled, however, to better visualize it, we gotta first go through the Debug modes.
The shader has a "Debug" section with a `Debug outputs` option, change that to "Lighting" and you should instantly see the scene with a very faint light.
There is also a second option called `Hide Light Sources`, this will hide the Light icon from the sources.

![Debug output preview](../images/configuring-immerse-shaders/relight-debug-out.png)

With that explained, we can finally start to explain what each parameter does and how it works.

---

## **Step 3: Tweaking the Scene for the Light Sources**

Similar to RTGI, in the `Global` section, you can tweak how much light from the original scene is kept and the overall parameters for the lighting and shadows, here, the options are the following:

* `Ambient Light`: How much of the original scene lighting is kept
* `Trace Shadows`: If the light will cast shadows. The two parameters below are directly related to that.
* `Shadow Penumbra`: Penumbra is the effect of the shadow when its leaking outside from being partially hit by light. This defines how wide it is, and consequently, how intense it / dark it will look.
* `Z-Thickness`: Like in RTGI, it defines how thick or thin the objects are. Thicker objects will cast darker shadows, while thinner ones might cast lighter and wider shadows.
* `Shadow Trace Quality`: How defined and how many tracces the ReSTIR casted shadows have. The higher the quality, the sharper the shadows but also the higher the performance consumption.

---

## **Step 4: Light Sources and Parameters**

Each light source will have its category identified as Light #, the number of light sources can be changed by going at the bottom of the shader and selecting the `AMOUNT_OF_LIGHTS` preprocessor definition. By default, it comes with 2 lights.

With that out of the way, you can tweak the following about the light sources:

* `Active`: If the light source is active or not.
* `Position:` The light source position on the screen. First is Horizontally, Second is Vertically and the Last one is the depth.
* `Tint:` Sets the color of the selected light source.
* `Intensity:` How bright the light is.

---

## **Step 5: Humans and Sub-Surface Scattering**

Sub-Surface Scattering (SSS) is the term for the light which bounces from inside the skin or from inside translucent surfaces. It is very common with humans and other organic matter, such as plants.

The shader also has a quite good simulation for that effect, despite not knowing what is organic and what isn't.

Below are the parameters related to that:

* `Enable Sub-Surface Scattering`: Enables the SSS function in the shader. Not all scenes require it, so having a toggle is very helpful and saves on performance.
* `Subsurface Scattering Quality`: Changes the quality of the effect. Higher quality will have better light traversal on those areas, however, with a bigger performance hit.
* `SSS Translucency Radius`: Defines how deep or thick the "translucent" surfaces are. With higher values bringing more brigther and colorful light inside those areas.
* `SSS Saturation`: How saturated the colors in those areas are.
* `SSS Diffusion Radius`: How farther the sub-surface lighting will bleed onto the nearby surfaces.
* `SSS Skin Hue`: In the color wheel, defines what color / hue should be used to detect what is a fitting area for the Subsurface Scattering to consider as a skin.
* `SSS Skin Hue Tolerance:` Defines how strict the color has to be to be considered as a skin part. The higher the value, the closer to that absolute color.

---

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Addon Guides</summary>

{: .warning}
This shaders on this section depends on both the Shader files and Addon files, trying to use one without the other will NOT work.

This section will guide you through setting up and configuring specific shaders within the iMMERSE Ultimate Addon suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate: ReGrade +</summary>

ReGrade+ is a commercial-level color-correction suite for ReShade. Taking inspiration and trying to mimic the featureset of industry-standard and professional tools, this version of ReGrade aims to take way the middleman step of having to leave the game to make more granular and intuitive changes on an external software. Effectively turning color-correction into a single experience.

The advantage to this from the other implementations is that not only it offers that sort of featureset, but also makes it so the changes can be seen in real-time and with graphical interfaces similar to those tools thanks to its addon.

While everyone can use the tool and its capabilities, users with more knowledge on Color Theory, Photography and Image Post-Processing areas might take the most advantage of this shaders' features.

On the next set of instructions, we'll guide you through the installation of it along with the featureset it offers.

---

## **Step 1: Installing the Shader and the Addon**

For this version, we recommmend using the `ADDON` version of ReShade's binaries, while the normal version might work, your mileage may vary and you might face some bugs.

Install the shader as normal, but for the Addon, you must place it close to the ReShade DLL and game's EXE, like this:

![ReGradePlus Addon Installation](../images/configuring-immerse-shaders/regradep_addon_installation.png)

If you want to test if everything was correctly installed, you can open your game, if it was, you'll have a new tab in ReShade's menu, named "ReGrade+", right next to "About"

![ReGradePlus ReShade Window Tab](../images/configuring-immerse-shaders/regradep_addon_tab.png)

With that done, the shader can be enabled by going to the "Home" tab and enabling `iMMERSE Ultimate: ReGrade+ [MartysMods_REGRADE+.fx]` and `iMMERSE Ultimate: ReGrade+ Histogram [MartysMods_REGRADE+.fx]`. The latter shader is so the addon's histogram widgets work and display the correct values.

---

## **Step 2: Preparing to use the Shader**

Before explaining its parameters, we recommend you move the "ReGrade+" tab to a separate window in the ReShade / Game UI since that controls the entire shader. This will also allow you to tweak your other effects along with the color correction and visualize the results better without having to jump between windows.

Remember, enabling the Shader itself won't do anything, and if one of the components are not running, the Addon / Shader Window will tell, like so:

![ReGradePlus ReShade Window Alerts - All OFF](../images/configuring-immerse-shaders/regradep_shaders_off.png)

If everything is correct, it should look like this:

![ReGradePlus ReShade Window Alerts - All ON](../images/configuring-immerse-shaders/regradep_shaders_ok.png)

Now, with those ready, you can start tweaking the parameters, please note that different from the usual ReShade shaders, this one works differently and closer than professional industry tools, so its alright if you get confused at first.
This guide will do its best to help you with questions and whatever you might need to use this shader correctly.

---

## **Step 3: Scopes Window**

The "Scopes" area of the window is an easy way to see graphics of various colour statistics and balances of the image. By default, it is configured to "Histogram RGB", which is supposed to show the exposure and color values on the current scene.

By clicking on the Drop-Down box, you can choose between different options, such as:

`Histogram Y` shows the Luma levels of the images.

`Histogram RGB` shows the color levels of the images.

`Waveform Y` shows the Luma levels of the image in a nice Waveform / Spectral visualization.

`Waveform RGB` shows the color levels of the image in the same Waveform / Spectral visualization.

You can also click the `Undock` button to have those working separated from the ReGrade+ window. Allowing for better organization of the workspace.

![ReGradePlus Scopes Window](../images/configuring-immerse-shaders/regradep_scopes_widget.png)

---

## **Step 4: Tweaks**

The "Tweaks" section of the shader is dedicated for general tweaking of the images' brightness, saturation and whatnot. It is the region with less granularity and meant for quick-tweaks and changes without going deep into the image formatting.

The options we can see here are divided in Categories, and each one of those has lots of sub-categories, such as:

`White Balance` which changes the colors and image tones related to the temperature and bright points of the images, the options available are:

* `Temperature`: Changes the color temperature of the image.
* `Lab Offset A`: Changes the level of Green and Magenta of the image.
* `Lab Offset B`: Changes the level of Orange and Blue of the image.

`Exposure` is all related directly to the image illumination, lighting and exposure, with a few color options aswell, those are:

* `Exposure`: Changes the image exposure, which is how much light the lenses are absorbing. Lower values means a darker image, higher values means a brighter image.
* Contrast`: Changes the entire image's contrast levels.
* `Gamma`: Changes the image's brightness.
* `Filmic Gamma`: Changes the image's brightness on the dark and mid-points.
* `Saturation`: Changes the image's color saturation. The higher the value, the more colorful the image is, the less, the more saturated.
* `Vibrance`: Changes how vibrant the colors are. The higher tha value, the more vibrant.

`High Dynamic Range` is all related to the image's lighting tweaks. This allows you to change anything inbetween all the brightness levels. The options are:

* `Shadows`: Controls the brightness of the grey points of the image.
* `Darks`: Controls the brightness of the darkest points of the image.
* `Lights`: Controls how bright is the highest point of the image.
* `Highlights`: Controls how bright are the highest light points of the image. It is recommended to always have the Lights level below this.

---

## **Step 5: Tone Curves**

"Tone Curves" is one of the various interactive widgets available for the user in ReGrade+ , with this, you can make your own tonemap, which means you can choose how bright and dark each color or even the luminance levels are in a curve, essentially change the image lighting level even further to suit your needs.

By default, it comes enabled in the `RGB` mode, which tweaks all of the 3 main colors (Red, Green and Blue) toning and brightness, however, you can change to a per-channel mode by clicking the coloured squares in the lower part of the Graph.

![ReGradePlus Tone Curve Modes](../images/configuring-immerse-shaders/regradep_curves_mode.png)

To start using it, click on a point in the graph and move it to start changing the tone curve. To plot a new point, click somewhere else and move that point. The changes, along with the graphic, will all update in real-time.

![ReGradePlus Tone Curve Points Example](../images/configuring-immerse-shaders/regradep_curves_points.png)

You cannot delete per-point, so any time you need to revert the changes, you can right click and select "Reset to Default" to have all the curve changes and points undone.

---

## **Step 6: Color Correction**

The "Color Correction" section is subdivided in two: "Split Tuning" and a "Color Wheel".

`Split Toning` allows you to change the colors in a per-light level basis. It has 3 wheels: "Shadows", "Midtones" and "Highlights".

There are two ways you can edit those values, you can either click on the point on the center of color wheel and move it on where you want it to be, or you can drag the gauges left and right for more granular and fine-tuning of the values.

![ReGradePlus Split Toning Wheel Example](../images/configuring-immerse-shaders/regradep_colorwheel_toning.png)

The second wheel allows you to change the color values of Red, Orange, Yellow, Green, Aqua, Purple and Magenta by Luma (brightness) and also Saturation (Amount of Color).

By default, the Color Wheel comes configured to change the color values based on Luma (`Hue vs Luma`), but you can change the values you're choosing by clicking on the small wheel. This allows you to change between the first mode and the `Hue vs Saturation` mode.

To tweak the values, click on the color you wanna change it and move it with the Mouse, by holding the "Shift" key, you can linearly move it in the vertical/diagonal axis, preventing mistakes when you wanna change its saturation or brightness without changing the color tone.

To reset the values of a changed color, right click on the point you wanna reset. 

While this part of the shader doesn't allow you to drag any sort of gauges, it allows you to see how much of the values are changed in each section of the spectrum.

![ReGradePlus Color Wheel Example](../images/configuring-immerse-shaders/regradep_colorwheel_example.png)

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate: Lut Manager</summary>

LUT Manager combines the MultiLUT shader with an addon to manage LUT textures on the fly. Its more of a tool rather than a shader by itself.

In this guide we will detail installation steps along with how to use it effectively and how to organize your files.

---

## **Step 1: Installing the Addon and the Shader**

`This shader depends on both the Shader files and Addon, trying to use one without the other will NOT work.`

For this shader, we recommmend using the `ADDON` version of ReShade's binaries, while the normal version might work, your mileage may vary and you might face some bugs.
Install the shader as normal, but for the Addon, you must place it close to the ReShade DLL and game's EXE, like this:

![Example Addon Installation](../images/configuring-immerse-shaders/regradep_addon_installation.png)

---

## **Step 2: Installing the LUTs**

Before starting the game and enabling the LUTs, create a folder named "LUTs" in the game directory and place the LUT files you need there. All of the main LUT formats used by ReShade shaders are supported. Those included the LUTs from the repositories in the ReShade setup.

After that is done, just start the game, you may add more LUTs later ingame by reloading ReShade.

---

## **Step 3: Enabling the Shader**

First, enable the Shader `iMMERSE Ultimate LUT Manager [MartysMods_LUTMANAGER.fx]`, after that, go to the "Add-Ons" tab, and in it, you should see MartysMods LUT Manager. There you'll see the names of all the LUTs / PNGs you have installed. Click in one of them to open the LUT list.

After that, pick one from the list and, if the shader is enabled, the colors will change right away!

![Pic of the LUT manager Window](../images/configuring-immerse-shaders/lutmanager-window.png)

The shader iteself has 2 toggles, one named *Enhanced LUT Quality*, which upsamples the LUTs using a expensive method. This is best used with small 16x16x16 LUT textures. And another named *Show all LUTs in its current atlas side-by-side*, this will show all LUTs in the current png side-by-side.

You can also right-click any of the LUTs you like the most and add them to a favorites list for easy-finding later.

![LUT Manager Favorites Window](../images/configuring-immerse-shaders/lutmanager-favs.png)

---

</details>

</details>