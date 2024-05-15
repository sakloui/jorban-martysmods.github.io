---
title: "Convolution Bloom"
layout: page
nav_order: 12
parent: "iMMERSE Ultimate"
grand_parent: Shader Repositories
---

# iMMERSE Ultimate: Convolution Bloom

Convolution Bloom (or FFT Bloom) is a more-advanced and high-end bloom based on Fast-Fourier Transform with a different end-effect. The way it works allows for bloom to have different shapes and sizes, instead of being just huge glowing light sources. Those being "Spikes", which simulates blades from a camera, and "Inverse Square Glow", which is similar to traditional bloom methods, but with a much higher range.

More about those will be shown later down the guide, meanwhile, we'll focus on the shared options.

---

## Shader Arguments

* **Bloom Padding:** Due to the way FFT works, the bloom will usually go beyond the screen resolution and boundaries and "leak" to the top or bottom of the image, causing weird / innacurate results. This parameter creates a black border to mitigate this, but will also reduce how far the bloom goes.

* **Log Exposure Bias and Log HDR Whitepoint:** are responsible for telling how much light the "camera" is absorbing and how bright the "White" is. The more exposure bias, the more bloom, and the higher the Whitepoint, the more intense the bright parts will glow.

* **Bloom Intensity:** Changes the overall intensity of the bloom. Independent of what area is considered white or "dark".

* **Bloom Radius:** How large are the light glows / ranges.

* **Bloom Hazyness:** Changes how much of the colors the bloom washes-away. With 0 being no color changes, and 1 being a full bleached look.

* **Enable Debug View:** Shows multiple debug outputs to help see how the shader is working, with the first option showing only the output of the bloom (how the bright areas look without taking the general image into consideration) and the second showing the Fourier texture of the bloom (more dev-oriented).

---

## Pre-Processor Options

Before talking about the other options, we must talk about the Pre-Processor ones since those interfere on what options you'll have at your disposure, the Pre-Processor settings are:

* `CONVOLUTION_BLOOM_QUALITY`: Changes the resolution of the Fourier kernel, higher values (from 0 to 2) will produce better results, but also require more resources.

* `CONVOLUTION_BLOOM_MASK_PRESET`: The default option is "Diffraction Spikes", which will create blades of light from glowing / bright sources, similar to the blades of a camera. The second one is "Inverse Square Glow", which will create a more traditional bloom (as in, light sources will spread lights to its surroundings).

---

## Diffraction Spikes

* **Diffraction Spike Amount:** How many spikes the bloom has, basically working as how many blades the camera has.

* **Diffraction Spike Rotation:** The rotation of the blades, as in, if they are coming straight from vertical, or tilted. 

* **Diffraction Spike Radius:** How far the spikes of light go through the image. The higher the value, the further they'll reach.

* **Diffraction Spike Blurryness:** How blurry the spikes are. The lower the value, the more evident the spike shapes are.

* **Diffraction Spike Phase Amount:** How bright the spikes are, not the light sources. The higher the values are, the brighter and more visible the spikes will appear.

## Inverse Square Glow

* **Glow Intensity:** How far the bloom goes and how intense it is, the higher the values is, the further and brighter the bloom will end up being.

* **Glare Amount:** How far the dark part of the bloom goes, the higher, the darker it is at the edges of the bloom sources.