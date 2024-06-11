---
title: Launchpad
layout: page
nav_order: 1
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE: Launchpad

{: .highlight-title }
>IMPORTANT
>
>This shader is required to be used for Marty's Mods shaders RTGI and ReLight. It can also be optionally used with MXAO.

iMMERSE: Launchpad is a helper shader for other Marty's Mods shaders like RTGI, MXAO, and ReLight. Because of this, you won't see many visible changes on screen.

## Smoothed Normals

* **Smoothed Normals** Configures the normals to be smoothed or not. Smoothed normals allows for RTGI and ReLight to provide much better lighting than they could with the original normals.

    ![Comparison](../images/launchpad_smoothed_normals.png)

---

## Textured Normals

* **Textured Normals Sample Radius:** Adjusts how far the shader samples for textured normals. Setting this too high can reduce detail or distort normals in MXAO, RTGI, or ReLight.

* **Textured Normals Intensity:** Adjusts the strength of the textured normals. Setting this too high can create exaggerated normals where they shouldn't be.

    ![Texture Normals Intensity](../images/launchpad_textured_normals.png)

* **Textured Normals Quality:** Ranges from 1 to 3, allowing you to control the quality of the textured normals. It's best to set this to 3 unless you need better performance.
