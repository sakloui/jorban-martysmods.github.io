---
title: ReShade GUI & Depth Buffer
layout: default
nav_order: 2
parent: ReShade Guides
---

# ReShade GUI

Learning how to navigate through ReShade is key to being able to utilize it effectively. Being able to navigate it with ease and configure specifically what you are looking for allows the user to create whatever their imagination allows for.

So, this guide will walk you through all the basics of what ReShade has to offer in it's UI. Please do not skip this portion as it provides tons of valuable information that you could use to better your experience with ReShade!

---

<details markdown="block" class="details-tree">
<summary>Home Tab</summary>

The `Home` tab in ReShade houses several buttons and menus that you can interact with in order to change the way your game looks, as well as configure specific shaders.

As the `Home` tab is one of the most crucial tabs in ReShade for the end user, it can be a bit intricate, but everything that you will need to better utilize each function.

Below will be a dropdown that provides a disection of each part of the `Home` tab to help you become more familiar with it!

---

<details markdown="block" class="details-tree">
<summary>Preset Selection Bar</summary>

At the top of the ReShade `Home` menu will be preset selection section bar:

![Current Preset](../images/reshades-ui-and-depth-buffer/rsui_preset.png){: style="max-width:65%" }

This bar allows the user to select, create, save manually, or configure their preset to auto save once changes are made.

By default, ReShade saves presets in the game directory, in a file called `ReShadePreset.ini`.

</details>

---

<details markdown="block" class="details-tree">
<summary>Shader List</summary>

The area below the preset selection bar is ReShade's shader list:
![Technique List](../images/reshades-ui-and-depth-buffer/rsui_effectlist.png){: style="max-width:65%" }

This list will provide the user with all of the shaders that is installed for ReShade. If a shader is disabled, there will be a blank square to the left of the shader, and if it's enabled, there will be a check to the left of the shader.

</details>

---

<details markdown="block" class="details-tree">
<summary>Edit Pre-processor Definitions Button</summary>

Below the shader list will be the `Edit Global Preprocessor Definitions`. This button allows you to control aspects of shaders and depth before they are loaded by ReShade:

![Global Pre-processor Definitions](../images/reshades-ui-and-depth-buffer/rsui_globalpreprocessors.png){: style="max-width:65%" }

</details>

---

<details markdown="block" class="details-tree">
<summary>Shader Parameters List</summary>

The area below the shader list and edit pre-processor definitions button is the shader parameter list;

![Effect Parameters](../images/reshades-ui-and-depth-buffer/rsui_effect_params.png){: style="max-width:65%" }

When you turn on a shader in ReShade, you will be able to see it's exposed parameters to the user here. Any changes to these parameters happen in realtime. So, any changes you make show up right away, letting you see the effect of your changes instantly.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Add-ons Tab</summary>

The `Add-ons Tab` is for managing ReShade Add-ons:

![Add-ons Tab](../images/reshades-ui-and-depth-buffer/rsui_addons_tab.png){: style="max-width:65%" }

Each `Add-on` adds extra features or improvements to your ReShade shaders. They can offer new effects or tools for tweaking existing ones. `Generic Depth` comes with the ReShade Installer, but you can add many more.

Popular Add-ons include [ShaderToggler - FransBouma](https://github.com/FransBouma/ShaderToggler), [ReShade Effect Shader Toggler - 4lex4nder](https://github.com/4lex4nder/ReshadeEffectShaderToggler), and [AutoHDR - MajorPainTheCactus](https://github.com/MajorPainTheCactus/AutoHDR-ReShade).

</details>

---

<details markdown="block" class="details-tree">
<summary>Settings Tab</summary>

The `Settings` tab lets you tweak ReShade settings like shader directories, menu access keys, FPS meter configurations, theme settings:

![Settings Tab](../images/reshades-ui-and-depth-buffer/rsui_settings_tab.png){: style="max-width:65%" }

The dropdowns below detail commonly used options that you can adjust within the `Settings` tab:

---

<details markdown="block" class="details-tree">
<summary>General Menu</summary>

1. `Keybindings`: 

    * Here, you can set the keybindings for various actions in ReShade, allowing you to customize the controls:

      * `Overlay key`

      * `Effect toggle key`

      * `Effect reload key`

      * `Performance mode toggle key`

      * `Previous preset key`

      * `Next preset key`

2. `Input processing`:

    * This setting lets users change the default behavior of ReShade's input control:

      * `Pass on all input` - Allows your game to also receive inputs from your keyboard and mouse, regardless of where they are on the game window.

      * `Block input when cursor is on overlay` - Allows the game to receive inputs from your keyboard and mouse only when they are off of the ReShade UI.

      * `Block all input when overlay is visible` (default option) - Disallows the game to receive all inputs from your keyboard and mouse when the ReShade overlay is active.

3. `Start-up preset`:

    * This argument allows ReShade to utilize a preset to use once your game has started. By default, ReShade loads the last used preset from the user. You can change this behavior by defining a preset file path.

4. `Effect...` and `Texture search paths`: 

    * These settings allow you to specify where ReShade should look for shader files. You can add multiple directories, and ReShade will search all of them when looking for shaders.

    * The default options are:

      * `Effect search paths` - `.\ReShade-Shaders\Shaders\**`

      * `Texture search paths` - `.\ReShade-Shaders\Textures\**`

5. `Load only enabled effects`:

    * This option ensures that only the shaders enabled in your current ReShade preset are loaded. It can prevent issues with conflicting files/techniques from other shaders and reduce the compile time needed at the start of ReShade.

</details>

---

<details markdown="block" class="details-tree">
<summary>Screenshots Menu</summary>

1. `Screenshot key`

2. `Screenshot path`:

    * This option sets the location where ReShade saves screenshots. By default, it's set to `.\`, meaning ReShade will save screenshots in the directory where the ReShade binary `.dll` file is located.

3. `Screenshot name`:

    * This advanced option lets you specify the naming convention for screenshots. It uses macros to include real-time data in the screenshot name. The available macros are:

        * %AppName% - Current application name.

        * %PresetName% - Name of the applied preset at the moment of the screenshot.

        * %Date% - Current date (in '%s' or seconds format).

          * %DateYear%, %DateMonth%, %DateDay% - Year, month, and day components of the current date.

        * %Time% - Current time (in '%s' or seconds format).

          * %TimeHour%, %TimeMinute%, %TimeSecond%, %TimeMS% - Hour, minute, second, and millisecond components of the current time.

        * %Count% - Number of screenshots taken in the current session.

4. `Screenshot format`:

    * This option lets you change the file extension and compression processing for your screenshots. The available formats are:

      * `Bitmap (*.bmp)` - Choose this for a lossless file that's easy to edit but takes up more space. This format isn't ideal for online sharing. If selected, you can enable `Clear alpha channel` to remove the image's transparency layer if shaders support creating alpha channels.

      * `Portable Network Graphics (*.png)` - Choose this for a lossy file that's almost identical to the original and good for online sharing. This is the default option in ReShade. If selected, you can enable `Clear alpha channel`.

      * `JPEG (*.jpeg)` - Choose this for a compressed file that saves on storage and bandwidth but isn't as close to the original. If selected, you can adjust the compression quality.

5. `Save current preset file`:

    * This option lets you save the preset used when the screenshot is taken.

6. `Save before and after images`:

    * This option lets you take two screenshots of the same frame: one without ReShade and one with ReShade.

</details>

---

<details markdown="block" class="details-tree">
<summary>Overlay & Styling</summary>

1. `Show screenshot message`:

    * This toggle enables or disables the screenshot notification message.

2. `Group effect files with tabs instead of a tree`:

    * This toggle lets you choose between a tree structure or a grouped structure for shader configuration arguments. While a grouped structure can be more organized, the choice is purely preference-based. By default, this option is off, and the tree structure is used.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Statistics Tab</summary>

![Statistics Tab](../images/reshades-ui-and-depth-buffer/rsui_stats_tab.png){: style="max-width:65%" }

The `Statistics Tab`, shown in the image, is a great tool for tracking and improving ReShade's performance. It gives detailed info on various aspects of ReShade's operation. All of the data provided for it is invaluable to those developing shaders, and those attempting to help troubleshoot other's issues.

</details>

---

<details markdown="block" class="details-tree">
<summary>Log Tab</summary>

The `Log Tab` is a key tool for monitoring ReShade's operations and troubleshooting issues. It provides a detailed log of ReShade's activities to help you identify where your issues are.

If something seems wrong, it's recommended to share the error text or the entire log file, which is stored in the game directory as `ReShade.log`. However, logs are reset each time the game is restarted. So, remember to share or save logs before restarting your game!

</details>

---

<details markdown="block" class="details-tree">
<summary>About Tab</summary>

The `About Tab`, as shown in the image above, acknowledges and recognizes the work behind ReShade as well as the current version that you are running!

</details>

---

# Depth Buffer

The depth buffer is a crucial part of any 3D game. It is a single channel image buffer which contains information about the distance of the scene to the camera, per pixel. Many ReShade effects depend on it and will not work correctly. 

ReShade's builtin `Generic Depth` Add-on scans the game data for the (likely) correct depth buffer and forwards it to the shaders.

In the following sections, you'll learn how to verify the depth settings are correct and how to fix common issues.

{: .warning}
Ensure you've correctly set up ReShade and followed the previous steps on the other pages! This guide assumes you've followed all instructions and have ReShade set up and running correctly.

---

<details markdown="block" class="details-tree">
<summary>Understanding Depth Buffer Basics</summary>

To start, enable the shader `DisplayDepth`. This shader is included with all ReShade installs through the ReShade Installer. If you do not have it, you can manually install it from [Crosire's ReShade-Shaders repository](https://github.com/crosire/reshade-shaders/tree/slim/Shaders).

The image below shows what the output **should** look like. The depth buffer is on the right side, the normal buffer (generated from depth) on the left side.

![Depth Buffer Reversed](../images/reshades-ui-and-depth-buffer/working_depth_output.jpg)

If it looks like above, you're good to go. Otherwise look below for the most common issues and solutions:

---

<details markdown="block" class="details-tree">
<summary>Reversed Depth Buffer</summary>

The image below shows that the `DisplayDepth` shader has loaded correctly, however, the depth is reversed. 

![Depth Buffer Reversed](../images/reshades-ui-and-depth-buffer/depth_buffer_reversed_example.png)

---

You can solve this issue by inverting the `RESHADE_DEPTH_INPUT_IS_REVERSED` argument within the `Global Preprocessor Definitions` under the `Home` tab of ReShade. If it is set to 1, set it to 0 and vice versa.

</details>

---

<details markdown="block" class="details-tree">
<summary>Upside Down Depth Buffer</summary>

The image below shows that the `DisplayDepth` shader has loaded correctly, however, the depth output is upside down:

![Depth Buffer Upside Down](../images/reshades-ui-and-depth-buffer/upside_down_normals.jpg)

You can solve this issue by simply inverting the `RESHADE_DEPTH_INPUT_IS_UPSIDE_DOWN` argument within the `Global Preprocessor Definitions` under the `Home` tab of ReShade. If it is set to 1, set it to 0 and vice versa.

</details>

---

<details markdown="block" class="details-tree">
<summary>Empty Depth Buffer</summary>

If your output resembles **either** of the images below, it lacks data from the `Generic Depth` Add-on:

![Depth Buffer No Data](../images/reshades-ui-and-depth-buffer/depth_buffer_no_data_example.png)
![Depth Buffer No Data - Reversed](../images/reshades-ui-and-depth-buffer/depth_buffer_no_data_reversed_example.png)

  * Before proceeding any further, ensure that these anti-aliasing options are disable within your game:

    * MSAA ANTIALIASING

    * SSAA ANTIALIASING

  FXAA or TXAA are acceptable, as they usually do not clear the depth-buffer information. Note that some games do not mention which AA method they use.

The image shown above is the output of `DisplayDepth` showing no data from `Generic Depth`. This means that:

* Your game is not presenting a depth buffer 

* You have the wrong options configured for `Generic Depth`

* You have the wrong arguments chosen for your `global preprocessor definitions`

* Your depth buffer choice is wrong.

---

You can absolve this issue simply by toying around with `Generic Depth` in order to get the proper depth buffer active:

  * Try toggling on and off `Copy depth buffer before clear operations` and `Copy depth buffer before fullscreen draw calls`

  * Try selecting the depth buffer with the closest resolution to your game resolution

  * Try selecting the depth buffer with the highest amount of draw calls and verticies.

If at any point you start to see any features in the output that match the scene, re-check the preprocessor definitions.

</details>

---

</details>

---

<details markdown="block" class="details-tree">
<summary>Global Preprocessor Arguments</summary>

This section will provide you with the `Global Preprocessor Definitions` that can be utilized with the ReShade Depth Buffer.

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_IS_REVERSED</summary>

This preprocessor is used when you can see the normals, but the depth image itself is not visible.

The argument can only be `1` or `0`, so flipping the value for it should solve the problem.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_IS_UPSIDE_DOWN</summary>

This preprocessor is used when the image displayed by the DisplayDepth shader is upside down.

The argument can only be `1` or `0`, so flipping the value for it should solve the problem.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_IS_LOGARITHMIC</summary>

This argument is used when the depth buffer displays numerous waves or "stripes".

Very FEW games actually utilize this, so it's rare that you'll need to toggle or modify this setting.

The argument can only be `1` or `0`, so flipping the value for it should solve the problem.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_X_SCALE | RESHADE_DEPTH_INPUT_Y_SCALE</summary>

These two preprocessors modify the depth buffer size along the `X` and `Y` axes.

They work in multiplcations and you can test them in the `DisplayDepth` shader before applying them to the `Global Preprocessors`.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_LINEARIZATION_FAR_PLANE</summary>

This preprocessor will adjust the value of the depth range.

If the depth range is too narrow or wide, based on the visible black to white (close to far) gradient given from the depth in `DisplayDepth`, shaders that utilize the depth buffer will not be able to properly account for depth.

The values can be either extremely low or high, so you'll need to experiment to determine the best fit for your specific case.

</details>

</details>