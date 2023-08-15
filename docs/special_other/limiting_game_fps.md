---
title: Limiting Your Game Framerate
layout: page
nav_order: 11
parent: Special & Others
---

# Limiting your game's framerate.

While having the highest FPS can be seen as a good thing, it often comes with the side effect of not allowing shaders breathing room in ReShade.

The guides listed below will guide you through several different methods on how to limit your framerate!

------

<details markdown="block">

<summary>AMD Adrenalin (Driver Based, AMD GPU Only, All Games)</summary>

This guide will provide you with the basics to limit your framerate using AMD Adrenalin's `Frame rate target control` function.

Keep in mind that this works globally, so it will force the framerate to what you set for ALL games on your system.

<h3>Step 1. - Open Adrenalin:</h3>

* __Easiest Method__ - Right click your desktop wallpaper, and click `AMD Software꞉ Adrenalin Edition`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/amd_desktop_context_menu.jpg"/>
* Alternative Method - Search `Adrenalin` in the Windows Search Bar.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/amd_start_search_software.jpg"/>

<h3>Step 2. - Enabling "Frame rate target control":</h3>

1. Click `Gaming` on the top most bar of the `Adrenaline` software, and then click `Graphics` in the second bar that has now appeared.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/amd_graphics_gaming_highlight.jpg"/>
2. Scroll down to the `Advanced` portion of the `Graphics` tab and enable `Frame rate target control`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/amd_enable_frtc.jpg"/>
3. Tune `Frame rate target control` to have the desired `Max FPS`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/amd_frtc_tune.jpg"/>
</details>

------

<details markdown="block">
<summary>NVIDIA Control Panel (Driver Based, NVIDIA GPU Only, All Games)</summary>

This guide will provide you with the basics to limit your framerate using NVIDIA's Control Panel `3D Settings` options for `Max Frame Rate`.

Keep in mind that this works globally, so it will force the framerate to what you set for ALL games on your system.

<h3>Step 1. - Open NVIDIA Control Panel:</h3>

* __Easiest Method__ - Right click your desktop wallpaper, and click `NVIDIA Control Panel`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_desktop_context_menu.jpg"/>
* Alternative Method - Search `NVIDIA Control Panel` in the Windows Search Bar.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_start_search_software.jpg"/>

<h3>Step 2. - Adjust the 3D Global Settings:</h3>

1. On the left hand corner, click `Manage 3D Settings`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_manage_3d_settings.jpg"/>
2. Ensure that you are within the `Global Settings` tab.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_global_settings_tab.jpg"/>
3. Enable `Max Frame Rate` and set the desired framerate between values 20 and 1000.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_max_frame_rate.jpg"/>

</details>

------

<details markdown="block">
<summary>NVIDIA Control Panel (Driver Based, NVIDIA GPU Only, Specific Games)</summary>

This guide will provide you with the basics to limit your framerate using NVIDIA's Control Panel `3D Settings` options for `Max Frame Rate`.

Keep in mind that this works for only the game you set, so it will force the framerate to what you set for just the game you select.

<h3>Step 1. - Open NVIDIA Control Panel:</h3>

* __Easiest Method__ - Right click your desktop wallpaper, and click `NVIDIA Control Panel`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_desktop_context_menu.jpg"/>
* Alternative Method - Search `NVIDIA Control Panel` in the Windows Search Bar.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_start_search_software.jpg"/>

<h3>Step 2. - Adjust the 3D Global Settings:</h3>

1. On the left hand corner, click `Manage 3D Settings`.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_manage_3d_settings.jpg"/>
2. Ensure that you are within the `Program Settings` tab.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_perapp_settings_tab.jpg"/>
3. Click the option on the right of the `Program to customize:` tab that says `Add`
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_perapp_settings_tab_add.jpg"/>
4. Find the program that you are wanting to cap the framerate of.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_perapp_settings_tab_app.jpg"/>
5. Enable `Max Frame Rate` and set the desired framerate between values 20 and 1000.
    <div class="figure">
    <img style="max-width: 100%; display: block; padding-block: 1rem" src="./images/limiting_game_fps/nvidia_max_frame_rate_per_app.jpg"/>

</details>