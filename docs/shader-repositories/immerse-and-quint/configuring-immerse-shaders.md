---
title: Configuring iMMERSE Shaders
layout: page
nav_order: 2
parent: iMMERSE & qUINT
grand_parent: Shader Repositories
---

# Configuring iMMERSE Shaders

Welcome to the configuration guide for iMMERSE Shaders. 

This guide will walk you through each step of configuring the shaders under the entire iMMERSE suite.

Click the suite you'd like to start configuring below:

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Shader Guides</summary>

This section will guide you through setting up and configuring specific shaders within the standard iMMERSE shader suite!

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Anti Aliasing</summary>

iMMERSE Anti-Aliasing is a robust iteration of SMAA offering up to twice the performance of the original shader depending on your settings!

---

## Understanding the Basic Parameters of iMMERSE Anti Aliasing:

* `Edge Detection Type`: 

    * This parameter provides different options to the user for customizing the type of edge detection used. The best option for most scenarios is `Color edge detection (max)`.

* `Enable Predicated Thresholding`:

    * This feature allows iMMERSE Anti Aliasing to utilize the depth buffer to better calculate edges that often get missed by the edge detection methods. It is recommended to enable this feature.

* `SMAA_USE_EXTENDED_EDGE_DETECTION`

    * This preprocessor for iMMERSE Anti Aliasing extends the color detection range of SMAA, allowing for increased detection of edges. The usable values are 0 and 1.

---

<details markdown="block" class="details-tree">
<summary>Configuring iMMERSE Anti Aliasing with Depth (Best Output)</summary>

# Configuring iMMERSE Anti Aliasing for Best Output with Depth

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
<summary>Configuring iMMERSE Anti Aliasing without Depth</summary>

# Configuring iMMERSE Anti Aliasing for Best Output Without Depth

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

<details markdown="block" class="details-tree">
<summary>iMMERSE Pro Clarity</summary>

Clarity is a shader that allows you to enhance texture and image details by adjusting the image's local contrast.

This allows you to add a soft glow or sharp, gritty textures to your game without the standard issues of haloing or noise.

Below is our guide on how to utilize Clarity to your advantage, and what you should look out for in order to get the best image possible!

<details markdown="block" class="details-tree">
<summary>Adding Details | No Depth Separation</summary>

Since Clarity is a local contrasting sharpener, you can easily get more perceived quality or "Clarity" out of your game's textures. 

This guide will go over how to do so without destroying your image altogether without using depth separation!

---

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

</details>

---

<details markdown="block" class="details-tree">
<summary>iMMERSE Ultimate Shader Guides</summary>

Stay tuned for iMMERSE Ultimate Shaders - coming soon!

</details>
