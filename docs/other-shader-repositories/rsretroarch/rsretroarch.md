---
title: RSRetroArch
layout: default
nav_order: 2
parent: Other Shader Repositories
---

# RSRetroArch Shaders

RSRetroArch shaders is a repository filled with powerful shaders that allow you to manipulate the visual output of your emulated or retro games.

This guide will help you understand the processes for configuring the order and position of each shader within ReShade.

For detailed information about each individual shader, please refer to the [Emulators and Emulation wiki](https://emulation.gametechwiki.com/index.php/Shaders_and_filters).

Due to ReShade not having access to internal resolutions or other features specific of the emulators, results might differ from Emulators which has those shaders when in comparison to ReShade.

---

## Understanding the Layers

To understand how shaders work, imagine your gaming setup as a series of layers. Each layer represents a different part of the gaming experience, from the game itself to the signal, the display, and the surrounding environment.

Each layer below is described for you to better visualize how these will work in terms of emulation:

---

### **Game/Medium Layer:**

  * This is the first layer and it represents the game or medium itself. Any shader that you apply at this layer will directly affect the game. This could include color correction, brightness adjustments, or other visual effects. Think of this layer as the 'base' of your gaming experience - everything starts here.

---

### **Image Signal:**

  * The next layer is the image signal. This represents the output from your game console or computer. Shaders applied at this layer will mimic the effects of different types of signals, such as NTSC or PAL. These shaders can introduce artifacts, blurring, and color changes that simulate the look of these signals. If you want to apply color correction at this layer, you should use a separate set of shaders to ensure that the effects are applied to the signal, not the game itself.

---

### **CRT/Output Display:**

  * The final layer is the CRT or output display. This layer represents the physical display and the surrounding environment. Shaders applied at this layer can simulate the look of different types of displays, such as a CRT monitor or an arcade cabinet. They can also create effects that appear outside the TV screen, such as reflections or ambient light.

---

Generally, this is the correct order for your configuration within ReShade:

![Prefered / Correct Order](../images/configuring-rsretroarch-shaders/pref_order.png){: style="max-width:65%" }

Remember, the key to configuring RetroArch shaders is understanding these layers and how they interact. By carefully choosing and positioning your shaders, you can create a wide range of visual effects that enhance your gaming experience.

---

<details markdown="block" class="details-tree">
<summary>CRT Shaders</summary>

This section introduces some of the most commonly used CRT-Shaders. Each shader has unique features and performance impacts.

---

<details markdown="block" class="details-tree">
<summary>CRT-Lottes</summary>

CRT-Lottes, created by Timothy Lottes, is designed to convincingly simulate various types of CRTs and masks. It's not too resource-intensive, making it a good choice for most systems.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-Potato</summary>

CRT-Potato is a lightweight shader that comes in two variants: Cool and Warm. It's designed to mimic a Trinitron display and is ideal for less powerful systems or mobile devices.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-Hyllian</summary>

CRT-Hyllian is designed to mimic an arcade display, but can also simulate other types of monitors. It's a bit more resource-intensive than Lottes, but still manageable for most systems.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-NewPixie</summary>

CRT-NewPixie, created by Mattias Gustaffson, is a popular choice for CRT Shaders. It strikes a balance between visual fidelity and performance, making it a good all-around choice.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-Royale</summary>

CRT-Royale is the most advanced CRT shader currently available. It's designed for 4K displays and includes a wide range of features, including multiple mask types, scanline options, interlacing, bloom and halation, phosphor and beam offsets, and more. However, it's also the most resource-intensive shader, so a dedicated GPU from 2010 or later is recommended.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Signal Shaders</summary>

This section introduces some of the signal shaders (NTSC and PAL) available in the repository, highlighting their unique features and performance impacts.

---

<details markdown="block" class="details-tree">
<summary>Artifact Colors</summary>

Artifact Colors shader mimics the output of an Apple II NTSC connection. It's great for those seeking the signal/dot crawl effect (also known as "rainbow" effect). Its blurring effect is also useful for 2D game sprite blending.

</details>

---

<details markdown="block" class="details-tree">
<summary>NTSC RetroArch</summary>

NTSC RetroArch, created by trogglemonkey, is a widely used NTSC shader due to its speed and ease of use. It comes in two versions: one with scanlines and one without, catering to different user preferences.

</details>

---

<details markdown="block" class="details-tree">
<summary>GTUv50</summary>

GTUv50 is an advanced NTSC-signal shader that emphasizes on signal blurring. It offers options for scanlines, connection type, TV line count, and signal frequency on each layer, making it ideal for replicating specific setups.

</details>

---

<details markdown="block" class="details-tree">
<summary>MAME NTSC</summary>

MAME NTSC is the standard NTSC shader found in the MAME emulator. It offers some dot-crawl / signal artifacts, but is more subdued compared to other shaders.

</details>

---

<details markdown="block" class="details-tree">
<summary>R57-PAL</summary>

R57-PAL is a realistic PAL shader that mimics the output of a NES PAL connection. It works well with most console visuals and effectively replicates the setups common in European countries. It also includes the notable "dot-crawl" effects and other signal anomalies.

</details>

</details>

---

# Honorable Mentions:

These shaders will exist outside of the RSRetroArch Repository, but are worth mentioning since they are similar to the ones here.

---

## [CRT-Royale port by akgunter](https://github.com/akgunter/crt-royale-reshade):

* This is the most complex CRT shader available, replicating various effects from an actual CRT.
* Best used in resolutions of 1080p and up.
* Presets are available here (https://github.com/Matsilagi/CRT-Royale-ReShade-Presets), made by Matsilagi.

---

## [Sony Megatron for ReShade by MajorPainTheCactus](https://github.com/MajorPainTheCactus/SonyMegatron-ReShade):

* This CRT shader uses an HDR addon to simulate a monitor and mask accurately, a SDR version is also available, but it might darken the image too much. 
* It calculates phosphors illuminations and scanlines count based on the monitor's resolution and brightness. It's highly accurate, but requires a high-end setup and a resolution of 4K.

---

## [WinUAE Shaders by guest.r](https://github.com/guestrr/WinUAE-Shaders/tree/master/ReshadeShaders):

* These shaders were originally created for the UAE Amiga emulator and later ported to ReShade for use in its x64 versions. 
* While it's a CRT shader suite, it's more tailored for desktop stations/computer terminals than Television sets or Arcade CRTs.

---

## [RSJankShaders by matsilagi](https://github.com/Matsilagi/RSJankShaders)

* A series of random small Shadertoy ports and other Shader experiments. Has some shaders which might fit the retro-gaming criteria.
* Shaders here are largely untested and might break / will break.