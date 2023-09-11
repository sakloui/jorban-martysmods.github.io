---
title: Configuring RSRetroArch Shaders
layout: default
nav_order: 1
parent: RSRetroArch
grand_parent: Shader Repositories
---

# Configuring RSRetroArch Shaders

RSRetroArch shaders is a repository filled with powerful shaders that allow you to manipulate the visual output of your emulated games. 

This guide seeks to help you understand the processes for configuring the order and position of each shader within ReShade.

For detailed information about each individual shader, please refer to the [Emulators and Emulation wiki](https://emulation.gametechwiki.com/index.php/Shaders_and_filters).

## Understanding the Layers

To understand how shaders work, imagine your gaming setup as a series of layers. Each layer represents a different part of the gaming experience, from the game itself to the signal, the display, and the surrounding environment.

Each layer below is described for you to better visualize how these will work in terms of emulation:

* **Game/Medium Layer:**

  * This is the first layer and it represents the game or medium itself. Any shader that you apply at this layer will directly affect the game. This could include color correction, brightness adjustments, or other visual effects. Think of this layer as the 'base' of your gaming experience - everything starts here.

* **Image Signal:**

  * The next layer is the image signal. This represents the output from your game console or computer. Shaders applied at this layer will mimic the effects of different types of signals, such as NTSC or PAL. These shaders can introduce artifacts, blurring, and color changes that simulate the look of these signals. If you want to apply color correction at this layer, you should use a separate set of shaders to ensure that the effects are applied to the signal, not the game itself.

* **CRT/Output Display:**

  * The final layer is the CRT or output display. This layer represents the physical display and the surrounding environment. Shaders applied at this layer can simulate the look of different types of displays, such as a CRT monitor or an arcade cabinet. They can also create effects that appear outside the TV screen, such as reflections or ambient light.

Here's how a basic depth + signal + output should be ordered:

![Prefered / Correct Order](../images/configuring-rsretroarch-shaders/pref_order.png){: style="max-width:65%" }

Remember, the key to configuring RetroArch shaders is understanding these layers and how they interact. By carefully choosing and positioning your shaders, you can create a wide range of visual effects that enhance your gaming experience.

---

<details markdown="block" class="details-tree">
<summary>CRT Shaders</summary>

This section explains you some of the most used CRT-Shaders by preset makers and players. Describing more or less how they look and work.

---

<details markdown="block" class="details-tree">
<summary>CRT-Lottes</summary>

CRT-Lottes is a CRT shader made by Timothy Lottes (creator of FXAA) whose goal is to look convincing and not too heavy. It can simulate various types of CRTs and masks, with or without geometry distortions.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-Potato</summary>

CRT-Potato comes with 2 variants: Cool and Warm. Its meant to mimic a Trinitron display. Using a Lookup Table for the masks, it is super lightweight, however it doesn't have any fancy or "interesting" features. Should be good for super-weak setups or mobile machines.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-Hyllian</summary>
Hyllian's CRT shader aims to mimic an arcade display, but its also possible to mimic other domestic monitors and setups with it. Its a bit lighter than Lottes, but its also on the heavier side.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-NewPixie</summary>
Made by Mattias Gustaffson, CRT-NewPixie is one of the most popular choices for CRT Shaders. Made for emulators such as FS-UAE, it balances looks with a convincing look without being super focused on the specifics of a CRT.

</details>

---

<details markdown="block" class="details-tree">
<summary>CRT-Royale</summary>
Even though its not located in this repository per-se, CRT-Royale is the most-advanced CRT shader so far, and because of that, its more ideal to use it on 4K displays. It has all of the features from a CRT including multiple mask types, scanline options, interlacing, bloom and halation, phosphor and beam offsets and so on.
With that said, its the heaviest CRT shader, but also the most accurate and "pretty" looking one. Its recommended to have a dedicated GPU post-2010 to run this shader at an acceptable framerate.
</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Signal Shaders</summary>

This section explains some of the signal shaders (NTSC and PAL) that are available in the repository, along with their quirks.

---

<details markdown="block" class="details-tree">
<summary>Artifact Colors</summary>
This Shader mimics the output of a Apple II NTSC connection. While not close to the TV ones, those are very good for people looking for the signal/dot crawl effect (also known as "rainbow" effect). Due to how much it blurs its also good for 2D game sprite blending.
</details>

---

<details markdown="block" class="details-tree">
<summary>NTSC RetroArch</summary>
This is a NTSC shader made by trogglemonkey for RetroArch. Its one of the most common used ones due to its speed and ease of usage. It comes both with a version that has Scanlines and one that doesn't for users which plan on using a different Scanline method or do not want / need it.
</details>

---

<details markdown="block" class="details-tree">
<summary>GTUv50</summary>
A somewhat advanced NTSC-signal shader which focuses a lot on the blurring part of the signal. With options for scanlines, connection type, how much TV lines the signal has and the signal frequency on each layer, this one is tailored for people looking to replicate more specific setups.
</details>

---

<details markdown="block" class="details-tree">
<summary>MAME NTSC</summary>
This Shader is the standard NTSC integration as found in the MAME emulator. Not much to change here. It has a bit of the dot-crawl / signal artifacts, but its a lot more tame in comparison with the other shaders.
</details>

---

<details markdown="block" class="details-tree">
<summary>R57-PAL</summary>
While being the only PAL shader here, its quite a realistic one. This mimics the output of a NES PAL connection. It works great with the majority of console visuals and might mimic well enough how European countries had their setups. It also has a lot of the famous "dot-crawl" effects and other signal anomalies.
</details>

</details>

---

# Honorable Mentions

[CRT-Royale port by akgunter](https://github.com/akgunter/crt-royale-reshade) - As mentioned early in the guide, this is the most complex CRT shader out there. Mimicing various of the effects from an actual CRT. Best used in resolutions of 1080p and up.

[Sony Megatron for ReShade by MajorPainTheCactus](https://github.com/MajorPainTheCactus/SonyMegatron-ReShade) - A CRT shader that uses an HDR addon whose goal is to provide the most accurate monitor and mask simulation by using the monitor's resolution and brightness to calculate the phosphors iluminations and scanlines count. It looks very accurate, provided you have a high-end setup and a resolution of 4K.

[WinUAE Shaders by guest.r](https://github.com/guestrr/WinUAE-Shaders/tree/master/ReshadeShaders) - Creator of a few shaders for the RetroArch emulator frontend, those shaders were made for the UAE Amiga emulator, but were ported to ReShade for use in its x64 versions. While being a CRT shader suite, its most tailored at desktop stations / computer terminals rather than Television sets or Arcade CRTs.
