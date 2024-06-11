---
title: SMAA
layout: page
nav_order: 4
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE: SMAA

![iMMERSE SMAA Main Image](../images/smaa_main.png)

iMMERSE: Anti-Aliasing is Marty's iteration of SMAA. SMAA is a fast and effective method of anti-aliasing, becoming an industry standard since its initial release. It outperforms other performance-heavy shaders with the same goal. iMMERSE: Anti-Aliasing is best used where games only offer solutions such as FXAA or when no anti-aliasing solution is provided at all.

---

## SMAA's Debug

To better see what SMAA is doing, use its debug function. You can find these debug functions at the bottom of the shader arguments.

![SMAA Debug View](../images/smaa_debug_ui.png)

---

## General Shader Arguments

* **Edge Detection Type:** Defines the type of edge detection used in SMAA. Options include:
   * Luminance edge detection
   * Color edge detection (max)
   * Color edge detection (weighted)
   * Depth edge detection

* **Edge Detection Threshold:** Sets how many edges are detected based on the edge detection type.

* **Depth Edge Detection Threshold:** Sets how many depth edges are detected. (Works only if "Predicated Thresholding" is enabled.)

* **Max Search Steps:** Sets how many steps SMAA uses to effectively anti-alias the scene.

* **Max Search Steps Diagonal:** Sets how many steps SMAA uses to find diagonal aliasing in the scene.

* **Corner Rounding:** Sets how much anti-aliasing is applied to the scene.