---
title: "RTGI"
layout: page
nav_order: 5
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: RTGI

![RTGI Header Image](../images/rtgi_header.png)

{: .highlight-title }
>IMPORTANT
>
>RTGI **REQUIRES** iMMERSE: Launchpad in order to function.

Raytraced Global Illumination (RTGI) is a shader within iMMERSE Pro that brings realistic lighting to your games. By using ray tracing, RTGI physically simulates how light interacts with objects, enhancing details, providing accurate lighting, and enhancing physical lighting details through the means of global illumination and ambient occlusion.

---

## Raytracing Arguments

* **Diffuse GI Quality:** Configures the quality of RTGI's diffuse global illumination. Higher settings cast more rays per pixel and provide more samples per ray, resulting in more stable and detailed lighting. The image below shows the difference between Low and Ultra settings.

    ![RTGI Low/Ultra Quality](../images/rtgi_quality.png) 

* **Specular GI Quality:** Adjusts the quality of RTGI's specular global illumination. Higher settings increase the number of rays cast per pixel and the samples per ray, enhancing light reflections and stability.

* **Diffuse GI Radius:** Sets the coverage area for RTGI's diffuse global illumination. A larger radius requires higher quality settings to maintain detail and stability. The image below shows the difference between a short and long diffuse radius.

    ![RTGI Short/Long Diffuse Radius](../images/rtgi_diffuse_radius.png)

* **Surface Roughness:** Adjusts the roughness value for materials in the scene, with rougher surfaces diffusing more light based reflections while smoother surfaces will reflect more sharper lighting based reflections. The image below shows the difference between a low and high surface roughness.

    ![RTGI Low/High Surface Roughness](../images/rtgi_surface_roughness.png)

* **Z-Thickness:** Defines the perceived thickness of objects in the scene. Setting this too high can cause visual artifacts, while too low a setting can impair shading, shadowing, and global illumination propagation. The imabe below shows the difference between a z-thickness that is too low, just right, and too high.

    ![RTGI ZThickness Low/Right/High](../images/rtgi_z_thickness.png)

---

## Blending Arguments

* **Ambient Occlusion Intensity:** Adjusts the strength of the ambient occlusion, which enhances the perception of depth and shadows in crevices and corners.

* **Diffuse Bounce Lighting Intensity:** Controls the intensity of the diffuse global illumination, affecting how much indirect light bounces off surfaces and illuminates the scene.

* **Specular Lighting Intensity:** Sets the strength of the specular global illumination, impacting clarity of reflected light on shiny surfaces.

* **Ambient Lighting Level:** Modifies the overall amount of ambient light in the scene, influencing the general brightness and visibility of details. However, this will allow RTGI to increasingly add more raytraced global illumination back into the scene.

* **Ambient Lighting Sky Intensity:** Regulates the intensity of ambient light coming from the sky, contributing to the natural illumination of the scene.

* **Fade Out Range:** Determines the distance over which RTGI propagates light, affecting how far lighting effects extend within the scene.


---

## Experimental Arguments

* **Assume sRGB Input:** Specifies whether the input to RTGI is in sRGB color space. This setting is particularly useful when playing a game in HDR or providing RTGI with HDR buffers, ensuring accurate color representation and lighting effects.

---

## Debug Arguments

* **Enable Debug View:** Activates the lighting channel debug mode for RTGI, allowing users to visualize and fine-tune the settings under the raytracing arguments.