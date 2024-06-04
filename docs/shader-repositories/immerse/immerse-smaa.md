---
title: SMAA
layout: page
nav_order: 4
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE SMAA

![iMMERSE SMAA Main Image](../images/smaa_main.png)

iMMERSE Anti-Aliasing is Marty's itteration of SMAA. SMAA is a method of anti-aliasing which is both fast and effective. It has became an industry standard since it's initial release, leaving behind other performance-heavy shaders with the same goal.

SMAA is best used where games only offer solutions such as FXAA or when no anti-aliasing solution is provided at all.

---

## SMAA's Debug

In order to better visualize what SMAA is doing, it's best to use it's debug function. You can find these debug functions at the bottom of the shader arguments.

![SMAA Debug View](../images/smaa_debug_ui.png)

---

## General Shader Arguments

* **Edge Detection Type:** Will define the type of edge detection used in SMAA. These options are:
   * Luminance edge detection
   * Color edge detection (max)
   * Color edge detection (weighted)
   * Depth edge detection

* **Edge Detection Threshold:** Will define how many edges will be detected from the edge detection type.

* **Depth Edge Detection Threshold:** Will define how much of the edges in depth are detected. (**Will only work if "Predicated Thresholding" is enabled.**)

* **Max Search Steps:** Will define how many steps are used within the SMAA construct in order to effectively anti-alias the scene.

* **Max Search Steps Diagonal:** Will define how many steps are used within the SMAA construct to find diagonal aliasing within the scene.

* **Corner Rounding:** Will define how much anti-aliasing will be applied to the scene