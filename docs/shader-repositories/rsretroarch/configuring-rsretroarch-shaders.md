---
title: Configuring RSRetroArch Shaders
layout: default
nav_order: 1
parent: RSRetroArch
grand_parent: Shader Repositories
---

# Configuring RSRetroArch Shaders
First of all, this will only cover the order and more or less how and where to position each shader. Which means individual informations about each shader will have to be looked on the wiki dedicated for the Emulators and Emulation itself. You can find those [here](https://emulation.gametechwiki.com/index.php/Shaders_and_filters). The emulators part ain't too important, but the individual shaders are.
The basic grasp to have is the following: 

> Imagine you have a console setup in a room. The way you think of it, there is the game / medium itself, the signal, your TV apparel (hypotetically if its a CRT), the cables you use to connect to your said hypotetical display, and everything else after is the world around you / the place you are.

That said, you'll always have those layers, without considering the ReShade ordering (classic depth shaders first, 2D-shaders later):

 - The Medium/Game layer. Everything that should affect only the game itself goes here. Doesn't matter if its color-correction and whatnot, so whatever you want to affect the game, goes always on the top-ish.
 - The Signal of the image. If you use a shader such as NTSC or PAL signal shaders, here, you'll alter the "signal" output, this brings artifacts, blurring and other color/visual modifying shaders that aren't from the game, but from the cable/apparel/physical part of the image itself. If you need color-correction here aswell, have a separate set of shaders for it (Incase you want the game to look like something and then tune-up the signal to give a specific TV-look) so it applies to your taste.
 - The CRT/Output display. This is all that comes on the Physical side. This will be responsible on replicating the ambient around your display, either an overlay, an Arcade Cabinet, you get the point. This also would be responsible for any other effect which is **outside** the TV screen.

Here's how a basic depth + signal + output should be ordered
![Prefered / Correct Order](../images/configuring-rsretroarch-shaders/pref_order.png){: style="max-width:65%" }

However, even with the link above, this guide will now try to explain the most popular shaders from that repository to not make for a full/messy installation.

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
