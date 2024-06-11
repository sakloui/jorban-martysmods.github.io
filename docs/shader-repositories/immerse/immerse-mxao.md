---
title: MXAO
layout: page
nav_order: 2
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE MXAO

![MXAO Comparison](../images/mxao_main.png)

iMMERSE: MXAO is Marty's new iteration of MXAO, a robust ambient occlusion shader based on GTAO and Irradiance Bitfields. The difference from similar implementations is the performance to quality ratio, which is always the ultimate goal of the iMMERSE suite.

---

## Debug parameters

* **Show Raw AO** is the debug mode of MXAO. This lets you see what each ambient occlusion type does on screen without the distraction of textures and colors.

    ![Raw AO Debug](../images/mxao_raw_output.jpg)

---

## AO Modes

By default, MXAO uses GTAO, but you can choose from three other modes:

* **0**: Ground Truth Ambient Occlusion (high contrast, fast)
* **1**: Solid Angle (smoother, fastest)
* **2**: Visibility Bitmask (DX11+ only, highest quality, slower)
* **3**: Visibility Bitmask w/ Solid Angle (like 2, only smoother)

    ![MXAO Modes Comparison](../images/mxao_comparison_numbered.webp)

---

## Quality Arguments

* **Sample Quality:** Configures how many times geometry is considered to generate ambient occlusion. Higher values increase quality and detail but reduce performance. Generally, you won't need to go past "very high," but larger radius setups might require higher values.

    ![MXAO Quality Comparison](../images/mxao_quality_comparison.webp)

* **Shading Rate:** Configures the size of the processed frame slices for ambient occlusion. Larger sizes improve quality but also increase the performance hit.

---

## Radius Arguments

* **Sample Radius:** Defines how far MXAO reaches and spreads its shading. Lower values concentrate the shading closer.

    ![MXAO Sample Radius Comparison](../images/mxao_sampleradius_comparison_numbered.webp)

* **Increase Radius with Distance** Toggles MXAO's radius scaling based on how far the object is from the screen. Useful for games with a large horizon, but might look odd for far-away buildings or detailed objects.

---

## Strength Arguments

* **Ambient Occlusion Amount:** Configures the strength of the shadows. Large, close objects should be dark, but avoid excessive shading on leaves and small objects.

    ![MXAO Amount Comparison](../images/mxao_amount_comparison.webp)

* **Fade-Out Distance:** Defines how far the AO is processed before disappearing. 1.0 is the horizon, and 0.1 is a closer value to the screen. Adjust the Radius to make the scene look correct.

* **Filter Quality:** Configures the quality of MXAO's filter. Increasing the filter quality will reduce MXAO's banding and noise, providing better filtering and blending. The higher the value, the harsher the performance hit.
