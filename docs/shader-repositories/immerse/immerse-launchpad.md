---
title: Launchpad
layout: page
nav_order: 1
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE Launchpad

iMMERSE Launchpad is a helper shader, in so, there won't be a whole lot of changes you can see on screen, or require configuring from the user.

However, there are a few arguments that the user might want to enable, or disable.

Install the shader normally and then enable `iMMERSE Launchpad (enable and move to the top!) [MartysMods_LAUNCHPAD.fx]` in the `Home` tab of ReShade.

## Smoothed Normals

"Smoothed Normals" configures the normals in a way that can provide a smoother normal map to shaders that require normals.

Simply, toggle on Smoothed Normals in Launchpad's avaliable arguments to enable it.

![Comparison](../images/launchpad_smoothed_normals.webp){: style="max-width:85%" }

![Texture Normals Preview](../images/texture_normals_preview.webp)

Textured Normals allows you to bring more detail out into the normals, by estimating the surface relief through color information.

{: .note}
Textured Normals requires Smoothed Normals to be active beforehand.

---

## Arguments:

* Textured Normals Sample Radius:

    Value used to increase or decrease the sampling radius of added textured normals.

    You do not want this value to be too high, please use it with caution!
	
![Texture Normals Radius](../images/texture_normals_radius.webp)

* Textured Normals Intensity

    Value used to increase or decrease the intensity of added textured normals.

    You do not want this value to be too high, please use it with caution!

![Texture Normals Intensity](../images/texture_normals_intensity.webp)

* Textured Normals Quality

    Value ranging from 1 to 3 that allows the user to increase or decrease the quality of the textured normals on screen.
	
![Texture Normals Quality](../images/texture_normals_quality.webp)	