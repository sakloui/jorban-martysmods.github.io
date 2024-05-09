---
title: Sharpen
layout: page
nav_order: 3
parent: iMMERSE
grand_parent: Shader Repositories
---

# iMMERSE Sharpen

iMMERSE Sharpen is Marty's new iteration of DELC, a local contrast sharpener.

Being a simple Sharpen shader, it doesn't have much control over over-sharpening or ringing, so everything should be tweaked with care. It is however, more effective than others at working with low values.

## Enabling the shader

Enable `iMMERSE Sharpen [MartysMods_SHARPEN.fx]` in the "Home" tab of ReShade.

---

## Find a testing area

While iMMERSE Sharpen can be used anywhere, it's best to find a **static area with complex texturing** so that you can better configure the settings that you have avalible to you.

---

## "Sharpen Intensity" argument

iMMERSE Sharpen has a single slider. Sharpen Intensity. This means that it takes very little in order to properly sharpen the scene.

You want to manage this argument where there is a noticble increase in game details, but not overly sharpening what there is to offer.

Start at the value of `0.000` and work your way up until you're able to find details being presnted more in the scene you've chosen.

![Comparison](../images/configuring-immerse-shaders/sharpned_image.jpg)

JORDAN, REMOVE IMAGE AS ITS NOT NEEDED.
