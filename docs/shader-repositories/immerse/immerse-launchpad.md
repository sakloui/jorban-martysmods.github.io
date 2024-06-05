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

iMMERSE: Launchpad is a helper shader for other Marty's Mods shaders like RTGI, MXAO, and ReLight. With that in mind, there won't be a whole lot of changes that you can see on screen.

## Smoothed Normals

* **Smoothed Normals** is a configuration option within iMMERSE Launchpad to allow you to smoothed the normals that get pulled into ReShade.

    ![Comparison](../images/launchpad_smoothed_normals.png)

---

## Textured Normals

* **Textured Normals Sample Radius:** Value used to increase or decrease the sampling radius of added textured normals. If this value is set too high, you will lose lots of detail or have the normals be misrepresented within MXAO, RTGI, or ReLight.

* **Textured Normals Intensity:** Value used to increase or decrease the intensity of added textured normals. If the value is set too high, you will end up creating massive normals in places normals should not exist.

    ![Texture Normals Intensity](../images/launchpad_textured_normals.png)

* **Textured Normals Quality:** Value ranging from 1 to 3 that allows the user to increase or decrease the quality of the textured normals on screen. Typically you want the quality value to be set to 3 unless you're within a large performance constraint.