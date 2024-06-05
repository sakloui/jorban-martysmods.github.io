---
title: MXAO
layout: page
nav_order: 2
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE MXAO

![MXAO Comparison](../images/mxao_main.png)

iMMERSE: MXAO is Marty's new iteration of MXAO, a robust ambient occlusion shader based off of GTAO and Irradiance Bitfields. The difference from similar implementations of the same techniques is in the performance to quality ratio, which is always the ultimate goal on the iMMERSE suite.

---

## Debug parameters

* **Show Raw AO** is the debug mode of MXAO. This will allow you to better see what each ambient occlusion type does on screen without the noise of textures and colors.

    ![Raw AO Debug](../images/mxao_raw_output.jpg)

---

## AO Modes

By default, MXAO will be set up to use GTAO, however, there are three others from you to choose from:

* **0**: Ground Truth Ambient Occlusion (high contrast, fast)

* **1**: Solid Angle (smoother, fastest)

* **2**: Visibility Bitmask (DX11+ only, highest quality, slower)

* **3**: Visibility Bitmask w/ Solid Angle (like 2, only smoother)

    ![MXAO Modes Comparison](../images/mxao_comparison_numbered.webp)

---

## Quality Arguments

* **Sample Quality** will configure how many times geometry will be taken into account in order to generate ambient occlusion on-screen. While this raises the quality and how detailed and dark the geometry is, it will also be harsher on performance the higher it is. Often, you will not have to go past "very high," however, larger radius setups will often require a higher "**Sample Quality**."

    ![MXAO Quality Comparison](../images/mxao_quality_comparison.webp)

* **Shading Rate** will configure the size of the processed frame slices for ambient occlusion. The larger, the better the quality will be, but also the bigger the performance hit.

---

## Radius Arguments

* **Sample Radius** defines how far MXAO will reach out and spread it's shading. The lower this argue is set the closer the shading will be concentrated.

    ![MXAO Sample Radius Comparison](../images/mxao_sampleradius_comparison_numbered.webp)

* **Increase Radius with Distance** is a toggle that configures MXAO's radius so that it scales the shading based around how far away the object is from the screen. This is good for games with an extremely huge horizon, but might look wrong for buildings far-away or massively detailed objects.

---

## Strength Arguments

* **Ambient Occlusion Amount** allows you to configure how strong the shadows are. Larger and close together objects should be dark, but, you want to avoid excessive shading on leaves and tiny objects.

    ![MXAO Amount Comparison](../images/mxao_amount_comparison.webp)

* **Fade-Out Distance** defines how far the AO will be processed until it disappears completely. With 1.0 being the horizon, and 0.1 being the most-valid closer value to the screen. It is recommended to change the Radius according to how intense and "correct" the scene looks with that.

* **Filter Quality** is an option to provide better filtering and blending to the scene by reducing MXAO's banding and noise. Higher values will look better, but they will also lower performance.