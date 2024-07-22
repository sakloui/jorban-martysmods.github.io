---
title: "RTGI"
layout: page
nav_order: 5
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: RTGI

{% slider auto %}
 ![image #1](../images/rtgi_header.png)
 ![image #2](../images/rtgi_header2.png)
{% endslider %}

{: .highlight-title }
>IMPORTANT
>
>RTGI **REQUIRES** iMMERSE: Launchpad in order to function.

Raytraced Global Illumination (RTGI) is a shader within iMMERSE Pro that brings realistic lighting to your games. By using ray tracing, RTGI is able to physically simulate how light interacts with objects in order to enhance details and provide more accurate screen spaced bounce lighting through the means of global illumination and ambient occlusion.

---

## Diffuse RTGI

* **Quality:** Configures the quality of RTGI's diffuse global illumination. Higher settings cast more rays per pixel and provide more samples per ray, resulting in more stable and detailed lighting. 

{% comment %}
Once a new image is provided, add the statement below to the quality portion.
The image below shows the difference between Low and Ultra settings.
![RTGI Low/Ultra Quality](../images/diffuse_rtgi_quality.png) 
{% endcomment %}

* **Ambient Occlusion Intensity:** Adjusts the strength of the ambient occlusion, which enhances the perception of depth and shadows in crevices and corners.

* **Bounce Lighting Intensity:** Controls the intensity of the diffuse global illumination, affecting how much indirect light bounces off surfaces and illuminates the scene.

* **Z-Thickness:** Defines the perceived thickness of objects in the scene. Setting this too high can cause visual artifacts, while too low a setting can impair shading, shadowing, and global illumination propagation.

{% comment %}
Once a new image is provided, add the statement below to the z-thickness portion.
The image below shows the difference between a z-thickness that is too low, just right, and too high.
![RTGI ZThickness Low/Right/High](../images/rtgi_z_thickness.png)
{% endcomment %}

---

## Specular RTGI

* **Quality:** Adjusts the quality of RTGI's specular global illumination. Higher settings increase the number of rays cast per pixel and the samples per ray, enhancing light reflections and stability.

{% comment %}
Once a new image is provided, add the statement below to the quality portion.
The image below shows the difference between Low and Ultra settings.
![RTGI Low/Ultra Quality](../images/specular_rtgi_quality.png) 
{% endcomment %}

* **Surface Roughness:** Adjusts the roughness value for materials in the scene, with rougher surfaces diffusing more light based reflections while smoother surfaces will reflect more sharper lighting based reflections.

{% comment %}
Once a new image is provided, add the statement below to the surface roughness portion.
The image below shows the difference between a low and high surface roughness.
![RTGI Low/High Surface Roughness](../images/rtgi_surface_roughness.png)
{% endcomment %}

* **Specular Lighting Intensity:** Sets the strength of the specular global illumination, impacting clarity of reflected light on shiny surfaces.

---

## Blending Arguments

* **Ambient Level:** Modifies the overall amount of ambient light in the scene, influencing the general brightness and visibility of details. However, this will allow RTGI to increasingly add more raytraced global illumination back into the scene.

* **Ambient Sky Intensity:** Regulates the intensity of ambient light coming from the sky, contributing to the natural illumination of the scene.

* **Fade Out Range:** Determines the distance over which RTGI propagates light, affecting how far lighting effects extend within the scene.

---

## Experimental Arguments

* **Assume sRGB Input:** Specifies whether the input to RTGI is in sRGB color space. This setting is particularly useful when playing a game in HDR or providing RTGI with HDR buffers, ensuring accurate color representation and lighting effects.

---

## Debug Arguments

* **Enable Debug View:** Provides the user with two debug views.
 * **Validation Layer:** Debug providing visual output of Depth, Lighting, Normal Vectors, and Optical Flow
{% comment %}
Once a new image is provided, add the image below to the validation layer portion.
![RTGI Low/High Surface Roughness](../images/rtgi_vl_debug.png)
{% endcomment %}
 * **Lighting only:** Standard Lighting Channel Debug
{% comment %}
Once a new image is provided, add the image below to the Lighting only portion.
![RTGI Low/High Surface Roughness](../images/rtgi_lc_debug.png)
{% endcomment %}