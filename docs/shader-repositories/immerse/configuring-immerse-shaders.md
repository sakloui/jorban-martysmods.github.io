---
title: Configuring iMMERSE Shaders
layout: page
nav_order: 2
parent: iMMERSE
grand_parent: Shader Repositories
---

# Configuring iMMERSE Shaders

Below will be drop downs for each iMMERSE suite.

In each iMMERSE suite dropdown there are guides or explanations for each shader:

---

<details markdown="block" class="details-tree">
<summary>iMMERSE</summary>

This section will guide you through setting up and configuring shaders within the iMMERSE shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Launchpad</summary>

iMMERSE Launchpad is a helper shader, in so, there won't be a whole lot of changes you can see on screen, or require configuring from the user.

However, there are a few arguments that the user might want to enable, or disable.

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

Textured Normals allows you to bring more detail out into the normals, by estimating the surface relief through color information.

{: .note}
Textured Normals requires Smoothed Normals to be active beforehand.

---

## Arguments:

* Textured Normals Sample Radius:

    Value used to increase or decrease the sampling radius of added textured normals.

    You do not want this value to be too high, please use it with caution!

* Textured Normals Intensity

    Value used to increase or decrease the intensity of added textured normals.

    You do not want this value to be too high, please use it with caution!

* Textured Normals Quality

    Value ranging from 1 to 3 that allows the user to increase or decrease the quality of the textured normals on screen.

</details>

---

<details markdown="block" class="details-tree">
<summary>Optical Flow</summary>

Optical Flow is a process that estimates movement within the screen space. This allows shaders to more acurately account for the motion of your game camera and objects in motion.

Shaders, like iMMERSE Pro RTGI require Optical Flow in order to work properly.

---

## Arguments

* Optical Flow Filter Smoothness

    Allows the user to change the value of smoothness in the optical flow estimation.

    Too high and you will lose finer details.

    Too low, and you will enable the estimation to allow for artifacts.

---

## Preprocessors

* OPTICAL_FLOW_MATCHING_LAYERS

    Alows for three options from the user in order to increase or decrease the accuracy of the optical flow estimation:
    
     * 0: Luma (fastest)

     * 1: Luma + Depth (more accurate, slower, recommended)

     * 2: Circular Harmonics (most accurate, slowest)

* OPTICAL_FLOW_RESOLUTION
    
    Allows three options from the user in relation to increasing or decreasing the resolution of the optical flow estimation:

     * 0: Full Resolution (slowest)

     * 1: Half Resolution (faster, recommended)

     * 2: Quarter Resolution (fastest)

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE MXAO</summary>

iMMERSE MXAO is Marty's new iteration of MXAO, a robust ambient occlusion shader based off of GTAO and Irradiance Bitfields.

---

<details markdown="block" class="details-tree">
<summary>Configuring iMMERSE MXAO</summary>

By default, MXAO should look on-par with most ambient occlusion solutions out of the box, but some users might like to tweak it a bit more for their needs.

The steps below will guide you through each function, and provide you with good practices to follow.

---

## **Step 1:** Find a testing area

While iMMERSE MXAO can be used anywhere, it's best to find a **static area with complex geometry** so that you can better configure the settings that you have avalible to you.

Also make sure to find one area with **foliage or flat geometry** to prevent haloing or shadows around them.

---

## **Step 2:** Enable "Show Raw AO" and configure "AO Type" preprocessor

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
<summary>iMMERSE Sharpen</summary>

iMMERSE Sharpen is Marty's new iteration of DELC, a local contrast sharpener.

---

<details markdown="block" class="details-tree">
<summary>Configuring iMMERSE Sharpen</summary>

## **Step 1:** Finding a testing area:

While iMMERSE Sharpen can be used anywhere, it's best to find a **static area with complex texturing** so that you can better configure the settings that you have avalible to you.

---

## **Step 2:** Configuring Sharpen Intensity

iMMERSE Sharpen has a single slider. Sharpen Intensity. This means that it takes very little in order to properly sharpen the scene.

You want to manage this argument where there is a noticble increase in game details, but not overly sharpening what there is to offer.

Start at the value of `0.000` and work your way up until you're able to find details being presnted more in the scene you've chosen.

![Comparison](../images/configuring-immerse-shaders/sharpened_image.jpg)

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Anti Aliasing</summary>

iMMERSE Anti-Aliasing is Marty's itteration of SMAA.

---

<details markdown="block" class="details-tree">
<summary>General Parameters</summary>

* `Edge Detection Type`: 

    * This parameter provides different options to the user for customizing the type of edge detection used. The best option for most scenarios is `Color edge detection (max)`.

* `Enable Predicated Thresholding`:

    * This feature allows iMMERSE Anti Aliasing to utilize the depth buffer to better calculate edges that often get missed by the edge detection methods. It is recommended to enable this feature.

* `SMAA_USE_EXTENDED_EDGE_DETECTION`

    * This preprocessor for iMMERSE Anti Aliasing extends the color detection range of SMAA, allowing for increased detection of edges. The usable values are 0 and 1.

</details>

---

<details markdown="block" class="details-tree">
<summary>With Depth</summary>

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
<summary>iMMERSE Pro RTGI</summary>

RTGI is iMMERSE's flagship shader. It is a raytraced global-lighting solution. It brings realistic lighting to scenes using ReShade, while not being too taxing on the performance, especially against other solutions of its class. Ultimately, bringing the best on quality x performance ratio.

RTGI is capable of highlighting details or adding details that are otherwise hidden to the scenes via Global Illumination and Ambient Occlusion with Raytracing. It can also highlight textures via its recently added Specular GGX reflections.

Our guide below will make sure you'll be familiarized with it and will allow you to learn how to make the most usage out of it.

---

<details markdown="block" class="details-tree">
<summary>Initial Configuration</summary>
Before starting, make sure Launchpad is properly set-up. After that, find a place you want to try the shader in a game or application and get to tweaking it.
RTGI is also made to take advantage of specific Launchpad features, such as Texture Normals, Smooth Normals and whatnot, so make sure to re-read the guide if you ever get lost or feel like something could look better.

---

</details>

---

<details markdown="block" class="details-tree">
<summary>Configuring the Shader</summary>
## **Step 1:** Enable the Shader
* Simply check the shader `iMMERSE Pro RTGI [MartysMods_RTGI.fx]` in the `Home` tab of ReShade.
* This will activate RTGI and will give you the arguments at the bottom to change.

---

## **Step 2:** Configuring the Scene lighting using the `Ambient Light` slider.

As of RTGI version 0.50 (Released in 2023/12/31), RTGI now has an option to darken the overall scene to allow for the games to take more advantage of the Dynamic Lighting introduced by RTGI. At first, your scene might look too dark for your liking, but that's what this function is here for.
It goes from 0.0 to 1.0, 0.0 being little to no original game scene lighting, and 1.0 being fully lit by the game, with GI over the top. There isn't a value that fits all scenes, so its all up to preference.
A good strategy is to use these for close-up pictures or to give it more of a studio-lighting look by having only the parts you want lit illuminated.

![Comparison between none to full Ambient Lighting](../images/configuring-immerse-shaders/rtgi_ambient_lighting_comparison.png)

---
	
## **Step 3:** Restoring and configuring the scene lighting.

With the above said, we'll start by tweaking the scene lighting again in a case which the ambient lighting is really low, allowing effectively for RTGI to replace the game's lighting.
First, we'll start up by changing the quality of the RTGI by going on the `Diffuse GI Quality` setting. It has a few presets, with "Low" being the lowest but fastest, and "Ultra" being the highest but the most performance-consuming one.
The higher the quality, the larger the GI will bleed and the less noise it will have in the final result.

![Comparison of Quality Levels](../images/configuring-immerse-shaders/rtgi_quality_comparison.png)

Second option we'll have to tweak is the `Diffuse GI Radius`, this tells how far the Global Illumination will go in the scene. The larger this is, the more the bright elements will spread on the scene. With 1 being little to no light bleeding and 20 being the farthest it can reach.

![Comparison of GI Radius](../images/configuring-immerse-shaders/rtgi_radius_comparison.png)

Last, is the `Diffuse Bounce Lighting Intensity` slider, this used to be configured via a pre-processor definition, but as of the latest version, it is computed along with the base RTGI. This is responsible for telling how bright later bounces of lighting are.
This helps maintain the scene lit while not making light sources reach too far or overbright the entire scene.

![Comparison of Bounce Lighting Values](../images/configuring-immerse-shaders/rtgi_bouncelighting_comparison.png)
	
Now, to fine-tune it, change the `Fade-Out Range` so what you want covered from the scene gets covered up and `Z-Thickness` to change how thin or thick the objects on the scene are to add shadows. This is also useful to avoid halos around objects which shouldn't have them.

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

---

</details>

---

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro Clarity</summary>

Clarity is a shader that allows you to enhance texture and image details by adjusting the image's local contrast.

This allows you to add a soft glow or sharp, gritty textures to your game without the standard issues of haloing or noise.

Below is our guide on how to utilize Clarity to your advantage, and what you should look out for in order to get the best image possible!

<details markdown="block" class="details-tree">
<summary>Without Depth</summary>

## **Step 1:** Enable the Shader

* Simply check the shader `iMMERSE Pro Clarity [MartysMods_CLARITY.fx]` in the `Home` tab of ReShade.

    ![Check Clarity Shader](../images/configuring-immerse-shaders/immerse_clarity_enable.png)

* This will activate Clarity and give you the arguments at the bottom to change.

    ![Show User Clarity Options with Defaults](../images/configuring-immerse-shaders/show_user_clarity_arguments.png)

---

## **Step 2:** Configure `Texture Intensity` for Increased Perception and Clarity: 

To configure `Texture Intensity` for increased perception and clarity in the scene, move the slider to the right.

This does not take much.<br>
You will notice that textures end up popping out more, and the contrast of the overall scene will increase.

However, do not go extremely overboard with this effect, as it can damage the game author's original envision for the game!

* Example of the base game:

    ![Clarity Texture Intensity Base Game Image](../images/configuring-immerse-shaders/clarity_base_game_image.png)

* Example of a properly configured `Texture Intensity`:

    ![Clarity Texture Intensity Properly Configured](../images/configuring-immerse-shaders/clarity_properly_configured.png)

* Example of a poorly configured `Texture Intensity`:

    ![Clarity Texture Intensity Poorly Configured](../images/configuring-immerse-shaders/clarity_poorly_configured.png)

Once you have configured this argument to your liking, you might notice that the scene is slightly darker than it should be - this is where `Local Contrast Intensity` will come into play!

---

## **Step 3:** Configure `Local Contrast Intensity` to Remove Some Contrast

In order to remove some contrast from the image, while still keeping the benefits that iMMERSE Pro Clarity has to offer, you can configure the `Local Contrast Intensity` argument!

This argument is touchy, so it only needs a little bit.

You are going to want to match the original game world's contrast with this, so that when you flick iMMERSE Pro Clarty on and off, you would see no difference in the white and black points!

Moving this slider to the right, will increase the local contrast intensity giving the image a brighter feeling, while moving it to the left and give you a darker feel.

* Example of the base game:

    ![Clarity Local Contrast Base Game Image](../images/configuring-immerse-shaders/clarity_base_game_image.png)

* Example of a properly configured `Local Contrast Intensity`:

    ![Clarity Local Contrast Properly Configured](../images/configuring-immerse-shaders/clarity_properly_configured.png)

* Example of a poorly configured `Local Contrast Intensity`:

    ![Clarity Local Contrast Poorly Configured](../images/configuring-immerse-shaders/clarity_local_contrast_poorly_configured.png)

If you get results that are close to the original game, with the added benefits of increased texture resolve/quality - you have set up Clarity without any depth separation properly!

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro Depth of Field</summary>

WIP

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro ReGrade</summary>

WIP

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro Solaris</summary>

Solaris is IMMERSE's main implementation of a Bloom shader. Bloom shaders are meant to mimic light bleeding from very bright surfaces, similar to how a camera lens act when looking at very bright reflective objects.

It's differential is ease of usage, and quality x speed relation. It is a very fast shader with very high quality results.

To configure it, follow the below steps. In this guide, there is no "best" or "worst" option, its all up to personal preference.

---

## **Step 1:** Enable the Shader

Click on the IMMERSE Pro Solaris shader and enable it. Once you do, there will be some options, first, lets start by setting up the scene settings.

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

---

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Shader Guides</summary>

This section will guide you through setting up and configuring specific shaders within the iMMERSE Ultimate shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Convolution Bloom</summary>

Convolution Bloom (or FFT Bloom) is a more-advanced and high-end bloom based on Fast-Fourier Transform with a different end-effect. The way it works allows for bloom to have different shapes and sizes, instead of being just huge glowing light sources. Those being "Spikes", which simulates blades from a camera, and "Inverse Square Glow", which is similar to traditional bloom methods, but with a much higher range.
More about those will be shown later down the guide, meanwhile, we'll focus on the shared options.

---

## **Step 1:** Enabling the shader
Click on the IMMERSE Ultimate ConvolutionBloom shader and enable it. Most of the parameters are the same as Solaris, with only one new option shared between the (later) pre-processor options.

* `Bloom Padding`: Due to the way FFT works, the bloom will usually go beyond the screen resolution and boundaries and "leak" to the top or bottom of the image, causing weird / innacurate results. This parameter creates a black border to mitigate this, but will also reduce how far the bloom goes.
* `Log Exposure Bias` and `Log HDR Whitepoint` are responsible for telling how much light the "camera" is absorbing and how bright the "White" is. The more exposure bias, the more bloom, and the higher the Whitepoint, the more intense the bright parts will glow.
* `Bloom Intensity`: Changes the overall intensity of the bloom. Independent of what area is considered white or "dark".
* `Bloom Radius`: How large are the light glows / ranges.
* `Bloom Hazyness`: Changes how much of the colors the bloom washes-away. With 0 being no color changes, and 1 being a full bleached look.
* `Enable Debug View`: Shows multiple debug outputs to help see how the shader is working, with the first option showing only the output of the bloom (how the bright areas look without taking the general image into consideration) and the second showing the Fourier texture of the bloom (more dev-oriented).

---

## **Step 2:** Pre-Processor options
Before talking about the other options, we must talk about the Pre-Processor ones since those interfere on what options you'll have at your disposure, the Pre-Processor settings are:

* `CONVOLUTION_BLOOM_QUALITY`: Changes the resolution of the Fourier kernel, higher values (from 0 to 2) will produce better results, but also require more resources.
* `CONVOLUTION_BLOOM_MASK_PRESET`: The default option is "Diffraction Spikes", which will create blades of light from glowing / bright sources, similar to the blades of a camera. The second one is "Inverse Square Glow", which will create a more traditional bloom (as in, light sources will spread lights to its surroundings).

---

## *Step 3:* Individual options
The options of the First method, `Diffraction Spikes`, are:

* `Diffraction Spike Amount`: How many "Spikes" the bloom has, basically working as how many blades the "camera" has.
* `Diffraction Spike Rotation`: The rotation of the blades, as in, if they are coming straight from vertical, or tilted. 
* `Diffraction Spike Radius`: How far the "spikes" of light go through the image. The higher the value, the further they'll reach.
* `Diffraction Spike Blurryness`: How blurry the spikes are. The lower the value, the more evident the spike shapes are.
* `Diffraction Spike Phase Amount`: How bright the spikes (blades) are, not the light sources. The higher, the brighter / more visible the spikes will appear.

The options for the Second method, `Inverse Square Glow`, are:

* `Glow Intensity`: How far the bloom goes and how intense it is, higher values means further and brighter.
* `Glare Amount`: How far the "dark" part of the bloom goes, the higher, the darker it is at the edges of the bloom sources.

---

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Addon Guides</summary>

This section will guide you through setting up and configuring specific shaders within the iMMERSE Ultimate Addon suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate ReGrade +</summary>

WIP

</details>

</details>