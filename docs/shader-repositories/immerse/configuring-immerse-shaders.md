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

However, there are neat things you can do with it listed below:

---

<details markdown="block" class="details-tree">
<summary>Smoothed Normals</summary>

Smoothed Normals allows you to better smooth over the normals that are given to shaders from ReShade.

Simply, toggle on Smoothed Normals in Launchpad's avaliable arguments to enable it.

---

* Smoothed Normals
    ![Smoothed Normals](../images/configuring-immerse-shaders/launchpad_smoothed_normals.png)

* Original Normals
    ![Original Normals](../images/configuring-immerse-shaders/launchpad_original_normals.png)

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

    Too low, and you will end up embedding the estimated texturing into the normals.

    To high, and you will end up embossing the estimated texturing into the normals.

* Textured Normals Intensity

    Value used to increase or decrease the intensity of added textured normals.

    You do not want this value to be too high, please use it with caution!

* Textured Normals Quality

    Value ranging from 1 to 3 that allows the user to increase or decrease the quality of the textured normals on screen.

</details>

---

<details markdown="block" class="details-tree">
<summary>Optical Flow</summary>

Optical Flow is a simulation of movement within the screen space. This allows shaders to more acurately account for the motion of your game camera and objects in motion.

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

iMMERSE MXAO is Marty's new iteration of qUINT MXAO, a robust ambient occlusion shader based off of GTAO and Irradiance Bitfields.

---

<details markdown="block" class="details-tree">
<summary>Configuring iMMERSE MXAO</summary>

MXAO should look on-pair with most AO solutions out of the box, but some users might like to tweak it a bit more for their needs.

The information below will explain what each function does, along with good practices and what should or should not be done with it.

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

## **Step 3:** Configure "Sample Quality" and "Shading Rate" Arguments

![MXAO Quality Comparison](../images/configuring-immerse-shaders/mxao_quality_comparison.png)

Sample Quality defines how many times the geometry will be taken to generate the AO, while this raises the quality and how detailed and dark the geometry is, it will also take more performance the higher it is.

Generally, you do not have to go past very high, however, large radius setups might require a higher Sample Quality configuration.

Shading Rate defines the size of the processed frame slices for the AO computing. The larger, the better the quality will be, but also the bigger the performance hit. Usually half-rate balances quality and performance.

---

## **Step 4:** Configure "Sample Radius" Argument

![MXAO Sample Radius Comparison](../images/configuring-immerse-shaders/mxao_sampleradius_comparison_numbered.png)

Sample Radius defines how far the AO will be spread, the lower, the closer the shadows will be concentrated.

The other option also makes it so the radius is scaled up according to the distance from the screen. This is good for games with an extremely huge horizon, but might look wrong for buildings far-away or too-detailed horizons.

You should define it in a way that it doesn't cause halos or shadows that "spread" in the environment. Below is examples of something that looks correct vs something that looks wrong.

![MXAO Bad Example](../images/configuring-immerse-shaders/mxao_excessive_sample_radius_example.png)

---

## **Step 5:** Configure "Amount and Fade-Out Range" arguments

![MXAO Amount Comparison](../images/configuring-immerse-shaders/mxao_amount_comparison.png)

Amount defines how strong the shadows are. Since those are for close range objects, they should be dark, but remember to not make them too dark to avoid excessive shadows on leaves and tiny objects, or halos.

Fade-Out distance defines how far the AO will be processed until it disappears completely. With 1.0 being the horizon, and 0.1 being the most-valid closer value to the screen. It is recommended to change the Radius according to how intense and "correct" the scene looks with that.

Filter Quality aims to reduce the banding and blending of the dither and noise. Higher values mitigate this better, but also lowers performance. Usually 1 is fine.

---

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

---

* Base Image:
    ![Base Image](../images/configuring-immerse-shaders/sharpen_no_sharpen.png)

* Properly Sharpened Image:
    ![Sharpened Image](../images/configuring-immerse-shaders/sharpen_properly_sharpened.png)

* Badly Sharpened Image:
    ![Badly Sharpened Image](../images/configuring-immerse-shaders/sharpen_badly_sharpened.png)

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

WIP

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

WIP

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Shader Guides</summary>

This section will guide you through setting up and configuring specific shaders within the iMMERSE Ultimate shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Convolution Bloom</summary>

WIP

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