---
title: MXAO
layout: page
nav_order: 2
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE MXAO

iMMERSE MXAO is Marty's new iteration of MXAO, a robust ambient occlusion shader based off of GTAO and Irradiance Bitfields.

The difference from similar implementations of the same techniques is in the performance x quality ratio, which is always the ultimate goal on the iMMERSE suite.

By default, MXAO should look on-par with most ambient occlusion solutions out of the box, but some users might like to tweak it a bit more for their needs.

The steps below will guide you through each function, and provide you with good practices to follow.

---

## "Show Raw AO" and configure "AO Type" preprocessor

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

## "Sample Quality and Shading Rate" arguments

![MXAO Quality Comparison](../images/configuring-immerse-shaders/mxao_quality_comparison.png)

"Sample Quality" configures how many times geometry will be taken to generate the ambient occlusion. While this raises the quality and how detailed and dark the geometry is, it will also be harsher on performance the higher it is.

Often, you will not have to go past very high, however, large radius setups might require a higher "Sample Quality" configuration.

"Shading Rate" allows the user to configure the size of the processed frame slices for the ambient occlusion. The larger, the better the quality will be, but also the bigger the performance hit.

---

## "Sample Radius" argument

![MXAO Sample Radius Comparison](../images/configuring-immerse-shaders/mxao_sampleradius_comparison_numbered.png)

"Sample Radius" defines how far MXAO will reach out and spread it's shading. The lower this argue is set the closer the shading will be concentrated.

"Increase Radius with Distance" is a toggle that configures MXAO's radius so that it scales the shading based around how far away the object is from the screen. This is good for games with an extremely huge horizon, but might look wrong for buildings far-away or massively detailed objects.

Keep in mind that you should configure "Sample Radius" in MXAO so that it is not producing halos in its shading that "spread" in the environment. Below are examples of a correct configuration, and a wrong configuration.

![MXAO Bad Example](../images/configuring-immerse-shaders/mxao_excessive_sample_radius_example.png)

---

## "Ambient Occlusion Amount, Fade-Out Distance, and Filter Quality" arguments

![MXAO Amount Comparison](../images/configuring-immerse-shaders/mxao_amount_comparison.png)

"Ambient Occlusion Amount" allows you to configure how strong the shadows are. Larger and close together objects should be dark, but, you want to avoid excessive shading on leaves and tiny objects.

"Fade-Out Distance" defines how far the AO will be processed until it disappears completely. With 1.0 being the horizon, and 0.1 being the most-valid closer value to the screen. It is recommended to change the Radius according to how intense and "correct" the scene looks with that.

"Filter Quality" is an option to provide better filtering and blending to the scene by reducing MXAO's banding and noise. Higher values will look better, but they will also lower performance.