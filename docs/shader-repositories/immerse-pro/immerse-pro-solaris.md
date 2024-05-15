---
title: "Solaris"
layout: page
nav_order: 7
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: Solaris

Solaris is IMMERSE's main implementation of a Bloom shader. Bloom shaders are meant to mimic light bleeding from very bright surfaces, similar to how a camera lens act when looking at very bright reflective objects.

It's differential is ease of usage, and quality x speed relation. It is a very fast shader with very high quality results.

To configure it, follow the below steps. In this guide, there is no "best" or "worst" option, its all up to personal preference.

---

## Configuring the Scene

The first two options, "Log Exposure Bias" and "Log HDR Whitepoint" are responsible for telling how much light the "camera" is absorbing and how bright the white is. The more exposure bias, the more bloom, and the higher the Whitepoint, the more intense the bright parts will glow.

The last 3 parameters are the more "artistic" side of the bloom:

* **Bloom Intensity:** Changes the overall intensity of the bloom. Independent of what area is considered light or dark.

* **Bloom Radius:** How large are the light glows / ranges.

* **Bloom Hazyness:** Changes how much of the colors the bloom washes-away. With 0 being no color changes, and 1 being a full bleached look.

---

## Technical Parameters

Those parameters are more techincal and won't change much of the final look, they are made for more specific changes or user needs.

* **High Resolution Input:** Changes the resolution the Bloom should sample the scene. Useful if you need to grab more detailed objects which should glow.

* **Mask by Depth:** Made as a way to prevent HUD elements from glowing. Enabling this will make it so the depth controls what will emit bloom or not.

* **Depth Mask Strength:** The higher the value, the further away the bloom will apply, with 0 being the same as having depth masking disabled.

The last 2 pre-processor parameters will also depend on your usage.

* `ENABLE_SOLARIS_REGRADE_PARITY`: This will make it so Solaris will work together with ReGrade, using its exposure parameters and levels to define the bloom on the scene.

* `SOLARIS_PERF_MODE`: Enables a higher-performance mode for Solaris, changing how it works internally to tax less of the computer. Not generally necessary, but low-performance setups might benefit from having it on.