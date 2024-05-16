---
title: SMAA
layout: page
nav_order: 4
parent: iMMERSE
grand_parent: Shader Repositories
---

JORDAN PROBABLY BEST TO REWORK WHOLE GUIDE. ITS A BIT HARD TO FOLLOW AND A LITTLE WACK.
ASK MARTY ABOUT HOW TO PROCEED

# iMMERSE SMAA

iMMERSE Anti-Aliasing is Marty's itteration of SMAA.

SMAA is a method of anti-aliasing which is both fast and effective. It has became an industry standard since, leaving behind other performance-heavy shaders with the same goal.

In order to use iMMERSE SMAA, enable `iMMERSE Anti Aliasing [MartysMods_SMAA.fx]` in the "Home" tab of ReShade.

---

## General arguments

* Edge Detection Type

    * This parameter provides different options to the user for customizing the type of edge detection used. The best option for most scenarios is "Color edge detection (max)."

* Enable Predicated Thresholding

    * This feature allows iMMERSE Anti Aliasing to utilize the depth buffer to better calculate edges that often get missed by the edge detection methods. It is recommended to enable this feature.

* SMAA_USE_EXTENDED_EDGE_DETECTION

    * This preprocessor for iMMERSE Anti Aliasing extends the color detection range of SMAA, allowing for increased detection of edges. The usable values are `0` and `1`.

<details markdown="block" class="details-tree">
<summary>With Depth</summary>

{: .note}
The parameters below requires explanation from the previous section. Make sure to read it!

## "View edges" for the parameter "Debug Output"

This will allow you to see all of the edges that iMMERSE Anti Aliasing is able to detect, and will allow us to better see the changes that the shader is able to make!

![Debug Output Preview](../images/configuring-immerse-shaders/smaa_debug_edges_preview.webp)

---

## "Color edge detection (max)" for "Edge Detection Type"

This option is the best soltuion for getting the most amount of edges within iMMERSE Anti Aliasing - However, other options can be chosen if desired.

![Color Edge Detection(Max) Preview](../images/configuring-immerse-shaders/smaa_color_edge_detection_max_argument.webp)

---

## Enable "Predicated Thresholding"

With this selected, you should notice a large decrease of edges that are being detected, this is normal, do not panic, as we will be configuring other parameters in order to get more of those edges back into view!

![Enable Predicated Thresholding Debug Output Preview](../images/configuring-immerse-shaders/smaa_debug_edges_depth_preview.webp)

---

## Reduce "Edge Detection Threshold" and "Depth Edge Detection Threshold" parameters

When reducing the arguments for "Edge Detection Threshold" and "Depth Edged Detection Threshold" you are allowing SMAA to detect more edges within the scene, and will greatly increase the amount of edges that you see.

![Reducing Edge Detection Threshold and Depth Edge Detection Threshold Parameter Preview](../images/configuring-immerse-shaders/smaa_reduce_edt_and_dedt.webp)

---

## Reduce "Predication Threshold"

If you already have this set to default values, the parameter will likely not change much within your scene, it's worth keeping in mind that this parameter will not do anything if you do not have depth access within your game!

![Reducing Predication Threshold Parameter Preview](../images/configuring-immerse-shaders/smaa_reduce_pt.webp)

---

## Increase "Predication Strength"

This will increase the depth predication strength in order to grab more edges that are noticble in depth, but not by the edge detection method.

Keep in mind that this parameter also will not do anything if you do not have depth access within your game!

* Good "Predication Strength" value debug output:

        ![Good](../images/configuring-immerse-shaders/smaa_debug_edge_prediction_good_strength_preview.webp)

* Poor "Predication Strength" value debug output:

        ![Not Good](../images/configuring-immerse-shaders/smaa_debug_edge_prediction_bad_strength_preview.webp)

---

## Reduce "Predication Scale"

You want to reduce "Predition Scale" down to the point where you are still picking up hard edges, but not detecting edges in texture work.

* Good "Predication Scale" value debug output:

    ![Good](../images/configuring-immerse-shaders/smaa_debug_edge_pred_scale_good.webp)

* Poor "Predication Scale" value debug output:
  
    ![Not Good](../images/configuring-immerse-shaders/smaa_debug_edge_pred_scale_bad.webp)

---

## Increase or Decrease Settings Based on Desired Performance:

If performance is permitting in your game and system, max out:

* "Max Search Steps"
* "Max Search Steps Diagonal"
* "Corner Rounding"

If performance is an issue, you can reduce these down to whatever value pleases your framerate choice.

---

From this point forward you should notice a decrease in shimmer and bright aliasing within your game. 

Please know that this will not take away all of your aliasing issues, but it can be enough to give you that extra smoothing to edges!

### SMAA Enabled:

![Enabled](../images/configuring-immerse-shaders/smaa_enabled_preview.webp)

### SMAA Disabled:

![Disabled](../images/configuring-immerse-shaders/smaa_disabled_preview.webp)


You can now disable "Debug Output" and continue to the game as usual!

</details>

---



JORDAN DO STUFF HERE FORWARD
JORDAN DO STUFF HERE FORWARD
JORDAN DO STUFF HERE FORWARD
JORDAN DO STUFF HERE FORWARD
JORDAN DO STUFF HERE FORWARD
JORDAN DO STUFF HERE FORWARD
JORDAN DO STUFF HERE FORWARD


danke

<details markdown="block" class="details-tree">
<summary>TO DO:::::::: Without Depth</summary>

## **Step 1:** Select the option `View edges` for the parameter `Debug Output`:

* This will allow you to see all of the edges that iMMERSE Anti Aliasing is able to detect, and will allow us to better see the changes that the shader is able to make!

    ![Debug Output Preview](../images/configuring-immerse-shaders/smaa_debug_edges_preview.webp)

---

## **Step 2:** Select the option `Color edge detection (max)` for `Edge Detection Type`:

* This option is the best soltuion for getting the most amount of edges within iMMERSE Anti Aliasing.

    * However, other options can be chosen if desired.

        ![Color Edge Detection(Max) Preview](../images/configuring-immerse-shaders/smaa_color_edge_detection_max_argument.webp)

---

## **Step 3:** Reduce `Edge Detection Threshold` as far as you can go without picking up too many edges within textures:

* Some are fine, but you do not want a whole lot:

    * Good `Predication Scale` value debug output:

        ![Good](../images/configuring-immerse-shaders/smaa_debug_edge_detect_thresh_good.webp)

    * Poor `Predication Scale` value debug output:
        
        ![Not Good](../images/configuring-immerse-shaders/smaa_debug_edge_detect_thresh_bad.webp)

---

## **Step 4:** Enable `SMAA_USE_EXTENDED_EDGE_DETECTION` if desired:

* In theory this should allow iMMERSE Anti Aliasisng to provide better results for edges - however, in practice, the change is not always visable off the bat.

    ![SMAA USE EXTENDED EDGE DETECTION Argument Preview](../images/configuring-immerse-shaders/smaa_use_edge_extended_preview.webp)

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

  ![Enabled](../images/configuring-immerse-shaders/smaa_no_depth_enabled.webp)

  * SMAA Disabled:

  ![Disabled](../images/configuring-immerse-shaders/smaa_no_depth_disabled.webp)

---

You can now disable `Debug Output` and continue to the game as usual!
