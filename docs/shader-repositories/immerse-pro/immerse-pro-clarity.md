---
title: "Clarity"
layout: page
nav_order: 9
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: Clarity

![Clarity Header Image](../images/clarity_main.png)

iMMERSE Pro: Clarity is a shader based on the sharpening technique used in Photoshop's Clarity tool. Its main goal is to highlight and restore details that are either already in the image or hidden. Unlike other shaders, Clarity has features to avoid haloing and other artifacts.

---

## Basic Arguments

* **Effect Radius:** Defines the area around each pixel that Clarity affects. A larger radius affects more surrounding pixels, creating a broader effect.

---

## Blending Arguments

* **Texture Intensity:** Controls how strong the sharpening and highlighting of details are. Increase this to make details more pronounced.

* **Local Contrast Intensity:** Adjusts the image's contrast to combat haloing and artifacts while maintaining Clarity's highlighting effect. Higher values increase contrast, which can help in reducing unwanted halos and enhancing overall detail.


---

## Depth Separation Arguments

* **Use Depth Separation:** Toggles the use of depth separation. This allows Clarity to treat the foreground and background differently, improving visual depth.

* **Show Depth Separation:** Toggles the depth separation debug mode. This helps you see and configure the separation between foreground and background more effectively.

* **Foreground/Background Balance:** Configures the balance between foreground and background separation. Adjust this to control how much emphasis is placed on the foreground versus the background.

* **Texture Intensity FG:** Configures the texture intensity for the foreground. Use this to sharpen and highlight details in the foreground independently of the background.

* **Local Contrast Intensity FG:** Configures the local contrast intensity for the foreground. Adjust this to manage the contrast in the foreground, helping to reduce artifacts and enhance detail.

* **Texture Intensity BG:** Configures the texture intensity for the background. Similar to the foreground setting, but applies to the background, allowing for independent control.

* **Local Contrast Intensity BG:** Configures the local contrast intensity for the background. This setting helps manage contrast in the background, ensuring that it complements the foreground without introducing unwanted artifacts.