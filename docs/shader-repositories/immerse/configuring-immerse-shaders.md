---
title: Configuring iMMERSE Shaders
layout: page
nav_order: 2
parent: iMMERSE
grand_parent: Shader Repositories
---

# Configuring iMMERSE Shaders

Below there will be drop downs for each tier level of the iMMERSE suite.

In each iMMERSE suite dropdown there are guides or explanations for each shader:

---

<details markdown="block" class="details-tree">
<summary>iMMERSE</summary>

This section will guide you through setting up and configuring shaders within the iMMERSE shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE: Launchpad</summary>

{: .warning}
None of the iMMERSE shaders will work properly without it, always have it enabled.

iMMERSE Launchpad is a helper shader, in so, there won't be a whole lot of changes you can see on screen, or require configuring from the user.

However, there are a few arguments that the user might want to enable, or disable.

Install the shader normally and then enable `iMMERSE Launchpad (enable and move to the top!) [MartysMods_LAUNCHPAD.fx]` in the `Home` tab of ReShade.

---

<details markdown="block" class="details-tree">
<summary>Smoothed Normals</summary>

"Smoothed Normals" configures the normals in a fasion that can provide a smoother normal map to shaders that require normals.

Simply, toggle on Smoothed Normals in Launchpad's avaliable arguments to enable it.

![Comparison](../images/configuring-immerse-shaders/launchpad_smoothed_normals.jpg){: style="max-width:85%" }

</details>

---

<details markdown="block" class="details-tree">
<summary>Textured Normals</summary>

![Texture Normals Preview](../images/configuring-immerse-shaders/texture_normals_preview.png)

Textured Normals allows you to bring more detail out into the normals, by estimating the surface relief through color information.

{: .note}
Textured Normals requires Smoothed Normals to be active beforehand.

---

## Arguments:

* Textured Normals Sample Radius:

    Value used to increase or decrease the sampling radius of added textured normals.

    You do not want this value to be too high, please use it with caution!
	
![Texture Normals Radius](../images/configuring-immerse-shaders/texture_normals_radius.png)

* Textured Normals Intensity

    Value used to increase or decrease the intensity of added textured normals.

    You do not want this value to be too high, please use it with caution!

![Texture Normals Intensity](../images/configuring-immerse-shaders/texture_normals_intensity.png)

* Textured Normals Quality

    Value ranging from 1 to 3 that allows the user to increase or decrease the quality of the textured normals on screen.
	
![Texture Normals Quality](../images/configuring-immerse-shaders/texture_normals_quality.png)	

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE: MXAO</summary>

iMMERSE MXAO is Marty's new iteration of MXAO, a robust ambient occlusion shader based off of GTAO and Irradiance Bitfields.
The difference from similar implementations of the same techniques is in the performance x quality ratio, which is always the ultimate goal on the iMMERSE suite.

---

<details markdown="block" class="details-tree">
<summary>Configuring the Shader</summary>

By default, MXAO should look on-par with most ambient occlusion solutions out of the box, but some users might like to tweak it a bit more for their needs.

The steps below will guide you through each function, and provide you with good practices to follow.

---

## **Step 1:** Enabling the Shader

Install the shader normally and then enable `iMMERSE MXAO [MartysMods_MXAO.fx]` in the `Home` tab of ReShade.

---

## **Step 2:** Find a testing area

While iMMERSE MXAO can be used anywhere, it's best to find a **static area with complex geometry** so that you can better configure the settings that you have avalible to you.

Also make sure to find one area with **foliage or flat geometry** to prevent haloing or shadows around them.

---

## **Step 3:** Enable "Show Raw AO" and configure "AO Type" preprocessor

Start off by enabling "Show Raw AO", this will allow you to better see what each AO type does on screen without the noise of textures and colors.

If you are on an area without geometry, the screen will just be white. So make sure you set it up before you started trying to configure it.

---

By default, MXAO will use GTAO, however, there are three others from you to choose from:

![MXAO Modes Comparison](../images/configuring-immerse-shaders/mxao_comparison_numbered.png)

* **0**: Ground Truth Ambient Occlusion (high contrast, fast)

* **1**: Solid Angle (smoother, fastest)

* **2**: Visibility Bitmask (DX11+ only, highest quality, slower)

* **3**: Visibility Bitmask w/ Solid Angle (like 2, only smoother)

AO type 3 will often be the best looking, but will only work in DX11 and above, alongside it will also be the harshest to performance.

---

## **Step 3:** Configure "Sample Quality and Shading Rate" Arguments

![MXAO Quality Comparison](../images/configuring-immerse-shaders/mxao_quality_comparison.png)

"Sample Quality" configures how many times geometry will be taken to generate the ambient occlusion. While this raises the quality and how detailed and dark the geometry is, it will also be harsher on performance the higher it is.

Often, you will not have to go past very high, however, large radius setups might require a higher "Sample Quality" configuration.

"Shading Rate" allows the user to configure the size of the processed frame slices for the ambient occlusion. The larger, the better the quality will be, but also the bigger the performance hit.

---

## **Step 4:** Configure "Sample Radius" Argument

![MXAO Sample Radius Comparison](../images/configuring-immerse-shaders/mxao_sampleradius_comparison_numbered.png)

"Sample Radius" defines how far MXAO will reach out and spread it's shading. The lower this argue is set the closer the shading will be concentrated.

"Increase Radius with Distance" is a toggle that configures MXAO's radius so that it scales the shading based around how far away the object is from the screen. This is good for games with an extremely huge horizon, but might look wrong for buildings far-away or massively detailed objects.

Keep in mind that you should configure "Sample Radius" in MXAO so that it is not producing halos in its shading that "spread" in the environment. Below are examples of a correct configuration, and a wrong configuration.

![MXAO Bad Example](../images/configuring-immerse-shaders/mxao_excessive_sample_radius_example.png)

---

## **Step 5:** Configure "Ambient Occlusion Amount, Fade-Out Distance, and Filter Quality" arguments

![MXAO Amount Comparison](../images/configuring-immerse-shaders/mxao_amount_comparison.png)

"Ambient Occlusion Amount" allows you to configure how strong the shadows are. Larger and close together objects should be dark, but, you want to avoid excessive shading on leaves and tiny objects.

"Fade-Out Distance" defines how far the AO will be processed until it disappears completely. With 1.0 being the horizon, and 0.1 being the most-valid closer value to the screen. It is recommended to change the Radius according to how intense and "correct" the scene looks with that.

"Filter Quality" is an option to provide better filtering and blending to the scene by reducing MXAO's banding and noise. Higher values will look better, but they will also lower performance.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE: Sharpen</summary>

iMMERSE Sharpen is Marty's new iteration of DELC, a local contrast sharpener.

Being a simple Sharpen shader, it doesn't have much control over over-sharpening or ringing, so everything should be tweaked with care. It is however, more effective than others at working with low values.

---

<details markdown="block" class="details-tree">
<summary>Configuring the Shader</summary>

## **Step 1:** Installing the shader
Install the shader and then enable `iMMERSE Sharpen [MartysMods_SHARPEN.fx]` in the `Home` tab of ReShade.

---

## **Step 2:** Finding a testing area

While iMMERSE Sharpen can be used anywhere, it's best to find a **static area with complex texturing** so that you can better configure the settings that you have avalible to you.

---

## **Step 3:** Configuring Sharpen Intensity

iMMERSE Sharpen has a single slider. Sharpen Intensity. This means that it takes very little in order to properly sharpen the scene.

You want to manage this argument where there is a noticble increase in game details, but not overly sharpening what there is to offer.

Start at the value of `0.000` and work your way up until you're able to find details being presnted more in the scene you've chosen.

![Comparison](../images/configuring-immerse-shaders/sharpned_image.jpg)

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE: Anti Aliasing</summary>

iMMERSE Anti-Aliasing is Marty's itteration of SMAA.

SMAA is a method of anti-aliasing which is both fast and effective. It has become an industry standard since, leaving behind other performance-heavy shaders with the same goal.

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



<details markdown="block" class="details-tree">
<summary>With Depth</summary>

{: .note}
The parameters below requires explanation from the previous section. Make sure to read it!

## **Step 1:** Select the option `View edges` for the parameter `Debug Output`:

* This will allow you to see all of the edges that iMMERSE Anti Aliasing is able to detect, and will allow us to better see the changes that the shader is able to make!

    ![Debug Output Preview](../images/configuring-immerse-shaders/smaa_debug_edges_preview.png)

---

## **Step 2:** Select the option `Color edge detection (max)` for `Edge Detection Type`:

* This option is the best soltuion for getting the most amount of edges within iMMERSE Anti Aliasing.
        
    * However, other options can be chosen if desired.

        ![Color Edge Detection(Max) Preview](../images/configuring-immerse-shaders/smaa_color_edge_detection_max_argument.png)

---

## **Step 3:** Check the option for `Enable Predicated Thresholding`:

* With this selected, you should notice a large decrease of edges that are being detected, this is normal, do not panic, as we will be configuring other parameters in order to get more of those edges back into view!

    ![Enable Predicated Thresholding Debug Output Preview](../images/configuring-immerse-shaders/smaa_debug_edges_depth_preview.png)

---

## **Step 4:** Reduce `Edge Detection Threshold` and `Depth Edge Detection Threshold` parameters to the lowest value that they can go:

* This will increase the amount of edges that you see, other parameters will be configured in order to detect more edges later on.

    ![Reducing Edge Detection Threshold and Depth Edge Detection Threshold Parameter Preview](../images/configuring-immerse-shaders/smaa_reduce_edt_and_dedt.png)

---

## **Step 5:** Reduce `Predication Threshold` as low as it can go:

* If you already have this set to default values, the parameter will likely not change much within your scene.

    * Keep in mind that this parameter will not do anything if you do not have depth access within your game!

    ![Reducing Predication Threshold Parameter Preview](../images/configuring-immerse-shaders/smaa_reduce_pt.png)

---

## **Step 6:** Increase `Predication Strength` just enough to the point where you notice no extra changes within the scene:

* This will increase the depth predication strength in order to grab more edges that are noticble in depth, but not by the edge detection method.

* Keep in mind that this parameter also will not do anything if you do not have depth access within your game!

    * Good `Predication Strength` value debug output:

        ![Good](../images/configuring-immerse-shaders/smaa_debug_edge_prediction_good_strength_preview.png)

    * Poor `Predication Strength` value debug output:

        ![Not Good](../images/configuring-immerse-shaders/smaa_debug_edge_prediction_bad_strength_preview.png)

---

## **Step 7:** Reduce `Predication Scale` as far as you can go without picking up noise from textures.

* Good `Predication Scale` value debug output:

    ![Good](../images/configuring-immerse-shaders/smaa_debug_edge_pred_scale_good.png)

* Poor `Predication Scale` value debug output:
  
    ![Not Good](../images/configuring-immerse-shaders/smaa_debug_edge_pred_scale_bad.png)

---

## **Step 8:** Increase or Decrease Settings Based on Desired Performance:

* If performance is permitting in your game and system, max out:

* `Max Search Steps`

* `Max Search Steps Diagonal`

* `Corner Rounding`

    * If performance is an issue, you can reduce these down to whatever value pleases your framerate choice.

---

From this point forward you should notice a decrease in shimmer and bright aliasing within your game. 

Please know that this will not take away all of your aliasing issues, but it can be enough to give you that extra smoothing to edges!

  * SMAA Enabled:

    ![Enabled](../images/configuring-immerse-shaders/smaa_enabled_preview.png)

  * SMAA Disabled:

    ![Disabled](../images/configuring-immerse-shaders/smaa_disabled_preview.png)


You can now disable `Debug Output` and continue to the game as usual!

</details>

---

<details markdown="block" class="details-tree">
<summary>Without Depth</summary>

## **Step 1:** Select the option `View edges` for the parameter `Debug Output`:

* This will allow you to see all of the edges that iMMERSE Anti Aliasing is able to detect, and will allow us to better see the changes that the shader is able to make!

    ![Debug Output Preview](../images/configuring-immerse-shaders/smaa_debug_edges_preview.png)

---

## **Step 2:** Select the option `Color edge detection (max)` for `Edge Detection Type`:

* This option is the best soltuion for getting the most amount of edges within iMMERSE Anti Aliasing.

    * However, other options can be chosen if desired.

        ![Color Edge Detection(Max) Preview](../images/configuring-immerse-shaders/smaa_color_edge_detection_max_argument.png)

---

## **Step 3:** Reduce `Edge Detection Threshold` as far as you can go without picking up too many edges within textures:

* Some are fine, but you do not want a whole lot:

    * Good `Predication Scale` value debug output:

        ![Good](../images/configuring-immerse-shaders/smaa_debug_edge_detect_thresh_good.png)

    * Poor `Predication Scale` value debug output:
        
        ![Not Good](../images/configuring-immerse-shaders/smaa_debug_edge_detect_thresh_bad.png)

---

## **Step 4:** Enable `SMAA_USE_EXTENDED_EDGE_DETECTION` if desired:

* In theory this should allow iMMERSE Anti Aliasisng to provide better results for edges - however, in practice, the change is not always visable off the bat.

    ![SMAA USE EXTENDED EDGE DETECTION Argument Preview](../images/configuring-immerse-shaders/smaa_use_edge_extended_preview.png)

---

## **Step 5:** Increase or Decrease Settings Based on Desired Performance:

* If performance is permitting in your game and system, max out:

    * `Max Search Steps`

    * `Max Search Steps Diagonal`

    * `Corner Rounding`

        * If performance is an issue, you can reduce these down to whatever value pleases your framerate choice.

---

From this point forward you should notice a decrease in shimmer and bright aliasing within your game. 

Please know that this method is not as good as the method with depth detection - however, it might be enough to satisfy your desire to elimite those shimmers!

  * SMAA Enabled:

  ![Enabled](../images/configuring-immerse-shaders/smaa_no_depth_enabled.png)

  * SMAA Disabled:

  ![Disabled](../images/configuring-immerse-shaders/smaa_no_depth_disabled.png)

---

You can now disable `Debug Output` and continue to the game as usual!

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

RTGI is iMMERSE's flagship shader. It is a raytraced global-illumination solution. RTGI brings realistic lighting to scenes, while not being too taxing on the performance, especially against other solutions of its class. Ultimately, bringing the best on quality to performance ratio.

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

## **Step 1:** Enabling RTGI and Launchpad

* Enable the shader `iMMERSE Launchpad [MartysMods_LAUNCHPAD.fx]` in the "Home" tab of ReShade.

* Drag andd drop `iMMERSE Launchpad [MartysMods_Launchpad.fx]` to the top of the ReShade "Home" tab to ensure that it's the first in the shader load order.

* Enable the shader `iMMERSE Pro RTGI [MartysMods_RTGI.fx]` in the `Home` tab of ReShade.

---

## **Step 2:** Configuring the Scene lighting using the `Ambient Light` slider.

As of RTGI version 0.50 (released on 12/31/2023), RTGI now has an option to darken the overall scene to allow for the games to take more advantage of the Diffuse and Specular Global-Illumination introduced by RTGI. At first, your scene might look too dark for your liking, but that's what this function is here for.

The Ambient Lighta argument allows you to configure it from 0.0 to 1.0. Where 0.0 will be little to no original game scene lighting, and 1.0 will be fully lit by the game, with GI overlaying it. There isn't a value that fits all scenes, so it is all up to the user's preference.

A good strategy is to use these for close-up pictures or to give your scene more of a studio-lighting look by having only the parts you want lit illuminated.

![Comparison between none to full Ambient Lighting](../images/configuring-immerse-shaders/rtgi_ambient_lighting_comparison.png)

---
	
## **Step 3:** Restoring and configuring the scene lighting.

With the above said, we'll start by tweaking the scene lighting again in a case which the Ambient Lighting argument is really low, allowing RTGI to effectively replace the game's lighting.

First, we'll start up by changing the quality of the RTGI by going on the `Diffuse GI Quality` setting. It has a few presets, with "Low" being the lowest but fastest, and "Ultra" being the highest but the most performance-consuming one.

The higher the quality, the larger the GI will bleed and the less noise it will have in the final result.

![Comparison of Quality Levels](../images/configuring-immerse-shaders/rtgi_quality_comparison.png)

Second option that will need to be tweaked is `Diffuse GI Radius`. This option tells RTGI how far you want the global-illumination to go in the scene. The larger this is, the more the bright elements will spread on the scene. With 1 being little to no light bleeding and 20 being the farthest it can reach.

![Comparison of GI Radius](../images/configuring-immerse-shaders/rtgi_radius_comparison.png)

The last option is `Diffuse Bounce Lighting Intensity`. This option tells RTGI how much Diffuse lighting you want within the scene. You want to configure this option to provide as much bounce lighting you want, while not making light sources overbrighten the entire scene.

![Comparison of Bounce Lighting Values](../images/configuring-immerse-shaders/rtgi_bouncelighting_comparison.png)
	
Now, to fine-tune it, change the `Fade-Out Range` so what you want covered from the scene gets covered up and `Z-Thickness` to change how thin or thick the objects on the scene are to add shadows.

In `Z-Thickness`, always try to keep a balance of how dark the objects look around. A lower value will make little to no AO (no shadows), and a higher value will cause shadows to be disproportionate.

This is also useful to avoid halos around objects which shouldn't have them.

---

## **Step 4:** Tweaking Surfaces and Reflections.

As of 0.50, the PBR GGX Specular Reflection feature has been re-introduced. This feature allows RTGI to "guess" reflective surfaces and how rough or smooth they are. Combined with Launchpad's Texture Normals, it allows for a "wet-floors" while not looking out of place, or to give extra depth to scenes.

Please note that this feature `only works on DirectX 10 and up, OpenGL and Vulkan`, it does not work with DirectX 9 given its age and limitations. So, moving those sliders in a DX9 application will result in no changes.

Make sure to also check Launchpad, as it has special integration with `Texture Normals` to keep details and highlights of the scene textures intact, while adding reflections. If there is too much noise on them, tweak the `Texture Normals Sample Radius` and `Texture Normals Intensity` on Launchpad until it looks correct to your tastes.

Observations out of the way, lets learn about its parameters.

Starting with `Specular GI Quality`, this works the same as the `Diffuse GI Quality` parameter, except it will only affect the reflections part, you can keep that on "Low" if you're not planning on having them enabled to save computational power and framerate.

Then, the second parameter: `Specular Lighting Intensity`. This tells RTGI how much the surfaces reflect on the scene. With 0 disabling the reflections fully. 

If you don't want to cause a "wet-world" effect, tweak those until they just show a bit of the geometry above them.

![Specular Lighting Preview](../images/configuring-immerse-shaders/rtgi_specular_comparison.png)
	
At last, we have `Surface Roughness`, this tells how Defined the reflections are, since RTGI doesn't know how rough surfaces are, it guesses and blurs the reflections as a mean to make it more rough and less defined. 0 makes the reflections super-shiny and defined, while 1.0 makes them super-blurry and hard to see.
	
![Reflection Roughness Comparison](../images/configuring-immerse-shaders/rtgi_reflection_comparison.png)
	
---

## **Step 5:** Experimental section.

It only has one option, which is `Assume sRGB Input`, with games that has flat and simple lighting, this will prevent washing the scene's colors or making them too bright. For games with more detailed lighting, having this disabled will help highlight the scenes details.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: Clarity</summary>

Clarity is a shader based on the feature of similar name in Adobe's software suites. It has the objective of highlighting and reviving otherwise hidden details by changing the image contrast locally.

The main difference of Clarity when compared to other shaders is that it has lots of features to avoid haloing or other artifacts.

Below is a guide to help with the tweaking of the shader and its values.

---

<details markdown="block" class="details-tree">
<summary>Without Depth</summary>

## **Step 1:** Enable the Shader

* Simply check the shader `iMMERSE Pro Clarity [MartysMods_CLARITY.fx]` in the `Home` tab of ReShade.

    ![Check Clarity Shader](../images/configuring-immerse-shaders/immerse_clarity_enable.png)

* This will activate Clarity and give you the arguments at the bottom to change.

    ![Show User Clarity Options with Defaults](../images/configuring-immerse-shaders/show_user_clarity_arguments.png)

---

## **Step 2:** Configuring the values in `Blending` Section

The `Blending` section is where most of the shaders' changes happens. We have 2 values here worth noting

First one is *Texture Intensity*, this one is responsible for how strong the sharpening / highlighting of the details are. While the shader tries to take measures against it, high values might still cause a tiny bit of haloing and overall noise. So its recommended to change this slowly.

Below you can see examples (close-ups) of correct and wrong results.

* Example of correctly and incorrectly configured Texture Intensity values. Notice the black haloing around object corners:
	
	![Clarity Texture Intensity comparison](../images/configuring-immerse-shaders/clarity_textureintensity_comparison.png)
	
The second one is the *Local Contrast Intensity* slider. This allows you to remove or add the image's contrast to combat haloing and artifacts while still keeping Clarity's highlight effect on.
Once again, its recommended to take it easy and slowly tweak that until it looks easy on the eyes and correct. The goal while using clarity is to have more details while not steering away from the game's base look.

* Example of correctly and incorrectly configured Local Contrast values. Notice how depth details are lost when it is incorrectly tweaked:

	![Clarity Local Contrast comparison](../images/configuring-immerse-shaders/clarity_localcontrast_comparison.png)
	
This section finishes and summarizes the main settings of the Clarity shader. In the next section we will detail how the depth settings work.
	
---

</details>

<details markdown="block" class="details-tree">
<summary>With Depth</summary>

{: .note}
The parameters below requires explanation from the previous section. Make sure to read it!

Taking into consideration the values from the previous section (`Without Depth`), here we will detail only the values used and relevant to the depth separation section of clarity, those being.

* `Use Depth Separation` is the main toggle. It is responsible for telling if the Depth separation is on or off.
* `Show Depth Separation` will show a white background for far elements, while keeping the image intact for near elements. It is a visual way of seeing where the separation between Background and Foreground is.
* `Texture Intensity FG` is responsible for the Texture Intensity value at Foreground level. As in, elements in front of the background.
* `Local Contrast Intensity FG` is responsible for the Contrast value at Foreground level. As in, elements in front of the background.
* `Texture Intensity BG` is responsible for the Texture Intensity value at Background level.
* `Local Contrast Intensity BG` is responsible for the Contrast value at Background level.

While separating them into depth, take note that due to background having smaller details, its smart to keep those values lower than the background ones. As to avoid noise and artifact in details.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: Depth of Field</summary>

iMMERSE Depth of Field is a shader which adds, as the name says, depth of field to a scene. It is also physically-based, which means that all the parameters and features work just like a real-life camera would.
It allows for total control for focusing on specific points of interest or objects on a scene, be it a macro-object or micro, it has enough parameters that will certainly fit your virtual photography needs.

Below, we will present all of the parameters, what they do and how they work so you can get used to the shader.

## **Step 1:** Enabling the shader and initial setup

Before we start, make sure Launchpad is correctly set-up and that your scene is organized and ready to start the photography work, just like in a real-life studio. With that done, enable the shader `iMMERSE Pro Depth of Field [MartysMods_DEPTHOFFIELD.fx]` and the options should appear on the bottom.

## **Step 2:** Preparing to focus on the subject / Focusing Section of the Shader
Before we start, lets take a look at the base options, first one and most-important is `Focusing Mode`, it has 3 options, each one worth taking note.

* Manual Focus is first and most advanced one, but also the hardest to use. It allows you to have full control of the "camera" lens for focusing.

* Autofocus is the second, its the most limited, and will not fit all cases, but might be useful for gameplay. It always focuses on the closest object inside the area of interest / focus area parameter (more on that later).

* Autofocus (Point and Click with MMB [Middle Mouse Button]) is the third one. It works like the autofocus function in most mobile phones, you point to the subject you want using the mouse and press the middle mouse button to focus on it. Easy to use and quite controllable, this should be the best and easiest option for amateur photographers.

To help you with those, a parameter named `Enable Focus Helper` is available. Enabling it will show a few pointers on the screen, changing according to the mode. It consists of:
- A small/darker box, which is the focus subject of the lens.
- The bigger, outer box, which is responsible for highlighting the background range.
- A white stripe / line, which is used to represent the focal point transition from near to far.
- A blue overlay, which is used to represent the furthest / infinity focal point of the camera.

![Example of the debug output in `Manual Focus` mode](../images/configuring-immerse-shaders/dof_debug_output.png)

With those 2 explained, we can start going on and actually preparing the focus.

`Autofocus Center` is responsible for defining where the camera will be focusing on the scene. Despite its name, it is also where the manual focus will be focusing. Change that if you need to focus on something that isn't on the center of the scene.

`Autofocus Detection Range` is responsible for expanding or narrowing the range of focusing. This is useful for precisely narrowing what you want / need to be the focal subject.

`Autofocus Adjustment Speed` determines how responsive the lens/camera is on focus changes. The bigger the number, the faster the camera will react to changes. If you are only using it for gameplay which requires fast movement, its recommended to be kept at the highest value so it doesn't distract from action.

## **Step 3:** Tweaking the focus and lens parameters.

The section dedicated to the lense is separated on 2 subcategories: `Simple` and `Advanced`, with one fine tuning even more the focus, exposure, how many aperture blades the camera has and the blur, and the latter one manipulating the bokeh shapes themselves and lens distortion of the camera.

In the `Simple` section, we have:

* `Focal Length`, which is how far the camera will focus. Lower values will produce less blur and have a smaller depth of field, while larger ones will allow the camera to focus more and further.
* `Aperture F-Stops` tells how open or closed the camera blades are. The higher that number is, the more light "goes through" the camera lens, which means more blur and less-defined shapes.

![Aperture F-Stops Example](../images/configuring-immerse-shaders/dof_fstop_preview.png)

* `Foreground \ Background Blur` tells how much the close and far points of the camera are blurred. While in real life it is always dependant on where and what you're focusing, here, for artistic liberty, the shader allows you to tweak how blurry objects closer or farther from the camera gets blurred.
* `Aperture Blade Count` determines how many blades the camera shutter has, directly influentiating on how the bokeh shapes are defined and visualized.

![Aperture Blade Count Example](../images/configuring-immerse-shaders/dof_blade_preview.png)

* `Aperture Roundness` defines how sharp or rounded the shapes are. In real life, the blades determine how rounded or not the shapes are, but here, for artistic liberty and freedom, you can tweak on how rounded you want the blades to be;

![Blade Roundness Example](../images/configuring-immerse-shaders/dof_roundness_preview.png)

In the `Advanced` section, we have:

* `Bokeh Rotation` defines how angled the bokeh shapes are. Best used when `Bokeh Roundness` parameter is set to 0.0

![Example of different bokeh rotations](../images/configuring-immerse-shaders/dof_rotation_preview.png)

* `Tangential Bokeh Scale` defines how distorted the bokeh shapes are tangentially (from center to outside, in a circular-manner).

![Tangential bokeh scale results](../images/configuring-immerse-shaders/dof_tangential_preview.png)

* `Sagittal Bokeh Scale` defines how distorted the bokeh shapes are sagittally (outer-lense, in a circular offset).

![Sagittal bokeh scale results](../images/configuring-immerse-shaders/dof_sagittal_preview.png)

* `Anamorph Bokeh Ratio` defines how distorted the shapes are horizontally. The higher the value, the more "squished" the shapes will appear.

![Anamorph bokeh scale results](../images/configuring-immerse-shaders/dof_anamorph_preview.png)

* `Spherical Aberration` defines how sharp the inner shapes of the DoF are. The lower the value, the more filled the shapes are, with the higher values focusing the color to the outer-ring of the shape.

* `Spherical Aberration Mode` allows to switch to how many lens the camera has for focusing. With Single being one, and doublet being two. Those change how the aberration distribution on the shapes work.

![Spherical Aberration Mode results](../images/configuring-immerse-shaders/dof_aberration_mode_preview.png)

## **Step 4:** Tweaking the blur and quality of the effect

This part of the shader is more related to the quality and performance than the looks themselves, even though a few of its elements change the overall look, most users won't need to touch that part.

`Bokeh Quality` is self-explainatory. It changes how much points are used to sample / draw the bokeh shape. With higher values improving the quality of the blur and the shapes, but costing more to render.

![Bokeh Quality preview](../images/configuring-immerse-shaders/dof_bokeh_quality.png)

`Bokeh Highlight Intensity`, `Bokeh Highlight Gamma` and `Bokeh Color Intensity` all changes how brighter, darker or saturated the shapes are. The images below shows how those look, in order.

![Bokeh Highlight Intensity](../images/configuring-immerse-shaders/dof_highlight_intensity_preview.png)

![Bokeh Highlight Gamma](../images/configuring-immerse-shaders/dof_highlight_gamma_preview.png)

![Bokeh Color Intensity](../images/configuring-immerse-shaders/dof_color_intensity_preview.png)

`Bokeh Smoothness` blurs the sample circles, eventually filling the shapes if they are separated, may be useful as a counter for raising the sample quality, at the cost of sharpness.

`Enable Undersampling Protection` makes it so all areas are sampled equally, preventing areas from being ignored by the blurring or shape sampling algorithms. It improves the quality of the blur, but has a very high performance cost.

`Enable Bokeh Sprites` and `Sprite Bokeh Percentage` tells the shader how much of the disc-sampled shapes to replace with procedural generated ones. The higher the value, the more will be replaces. This allows for even more defined and sharp shapes, at the cost of performance.

The last few are optional, with them being:

* `Bokeh Shape Helper` which will forcefully draw the bokeh shapes on the screen to allow to preview how they will look.

* `DOF_FULL_RESOLUTION`, which is a pre-processor toggle, will render the DoF at the screen resolution. It improves the quality but is overkill and should not ever be necessary. It is there however if someone wants to experiment with it.

---

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro: ReGrade</summary>

ReGrade is a color-correction suite designed to be feature-packed enough to be close to commercial tools. With all of its available options, it has the power to bring the usability and versatility of even commercial-level tools to games. Effectively removing the step of toggling between a color-correction software and the game to finish editing, making it all real-time and hassle-free.
While there is no correct values and usage of this shader, people familiarized with Photography, color theory and related areas will make the best usage. However, even people with no experience can get great results by looking at the changes made being shown instantly.

---

## **Step 1: Installing the Shader**

Click on the `iMMERSE Pro ReGrade [MartysMods_REGRADE.fx]` shader and enable it. Once you do, all of its options will appear. The following steps will show each parameter and what they do.

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

Special transforms are more artistic changes for the image. There are 2 options here skipping the bypass one, which is `Bleach Bypass (Gamma Corrected)`, which bleaches taking Gamma into consideration, and `Gamma on Luma | Chroma`, which changes the gamma level on the colors and luminosity.

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