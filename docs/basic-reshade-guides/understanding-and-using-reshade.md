---
title: Understanding and Using ReShade
layout: default
nav_order: 2
parent: Basic ReShade Guides
---

# Mastering ReShade

Understanding the ReShade UI is key to using it effectively. Knowing what it offers and how to navigate its menu is beneficial!

Press `HOME` (or `POS1` in some locales) to start the on-screen tutorial.

If you're new to ReShade, follow this tutorial - it covers the basics and sets a solid foundation. **Don't skip it!**

Skipped the tutorial already? No worries - we'll cover each feature and menu in this guide.

---

<details markdown="block" class="details-tree">
<summary>Exploring the Home Tab</summary>

The `Home` tab in ReShade houses all shaders and their configurations.

Being one of the most crucial tabs in ReShade, it can be a bit intricate.

Below, we'll dissect each part of the `Home` tab to help you grasp its offerings:

---

<details markdown="block" class="details-tree">
<summary>Current Preset</summary>

First, identify the active preset in ReShade, as shown below:

![Current Preset](../images/understanding-and-using-reshade/rsui_preset.png){: style="max-width:65%" }

On the right of the preset dropdown, there's a `+` button for creating new presets. The diskette icon next to it is for saving your preset.

On the left, `<` and `>` buttons switch to the next available preset in the same directory. ReShade will smartly identify which `.ini` files in your game directory are presets!

By default, ReShade saves presets in the game directory, in a file called `ReShadePreset.ini` unless you rename it.

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding the Technique List</summary>

The highlighted area below shows ReShade's `Technique List` within the `Home` tab:

![Technique List](../images/understanding-and-using-reshade/rsui_effectlist.png){: style="max-width:65%" }

This section lists all the shaders installed by you or the ReShade Installer. 

Keep in mind, that your `Technique List` may not match the image above. Its size can change based on the preset you choose and the shader repositories you install.

</details>

---

<details markdown="block" class="details-tree">
<summary>Global Pre-processor Definitions</summary>

The `Edit Global Preprocessor Definitions` button, shown below, lets you control effects before they load. Definitions set here act like switches, directing how shaders work:

![Global Pre-processor Definitions](../images/understanding-and-using-reshade/rsui_globalpreprocessors.png){: style="max-width:65%" }

Clicking this button above will open a window with two tabs:

* `Global`:

  * Global will be where you can add or edit definitions that apply to all presets.

    ![Global Pre-processor Window](../images/understanding-and-using-reshade/rsui_globalpreprocessors_window.png)

* `Current Preset`:

  * Current Preset will likely not have any definitions by default, however, you can add and remove to apply these to your current preset!

    ![Global Pre-processor Current Preset](../images/understanding-and-using-reshade/rsui_globalpreprocessors_current_preset.png)

{: .note }
When adjusting these options, you need to know the pre-processor definition's name and range. This info is usually in the shader comments. To look at FX files and their contents, try using advanced text editors like [Notepad++](https://notepad-plus-plus.org/) or [Visual Studio Code](https://code.visualstudio.com/).

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding Effect Parameters</summary>

The image below shows the shader's effect parameters:

![Effect Parameters](../images/understanding-and-using-reshade/rsui_effect_params.png){: style="max-width:65%" }

When you turn on a shader in ReShade, you'll see its options and parameters in the highlighted section.

Changes to Shader parameters happen in realtime. So, any changes you make show up right away, letting you see the effect of your changes instantly.

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding the Reload Button</summary>

The `Reload` button, shown in the image below, tells ReShade to look again at the files in the Shaders and Textures folders:

![Reload Button](../images/understanding-and-using-reshade/rsui_reload.png){: style="max-width:65%" }

Clicking the `Reload` button lets you add new effects without restarting the game. It also shows any changes you make to the shader code while you're working on it, so it's a useful tool for making real-time changes to the shader's code!

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding Performance Mode</summary>

The `Performance Mode` setting, shown in the image below, boosts the speed of compilation processes and ReShade's memory operations, cutting down on performance overhead:

![Performance Mode](../images/understanding-and-using-reshade/rsui_performance_mode.png){: style="max-width:65%" }

`Performance Mode` will limit changes to a shader's parameters.

If you notice anything odd while using Performance Mode, **always** let the shader developer know.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding the Add-ons Tab</summary>

The `Add-ons Tab`, shown below, is your control center for managing ReShade Add-ons:

![Add-ons Tab](../images/understanding-and-using-reshade/rsui_addons_tab.png){: style="max-width:65%" }

Each `Add-on` adds extra features or improvements to your ReShade shaders. They can offer new effects or tools for tweaking existing ones. `Generic Depth` comes with the ReShade Installer, but you can add many more.

Popular Add-ons include [ShaderToggler - FransBouma](https://github.com/FransBouma/ShaderToggler), [ReShade Effect Shader Toggler - 4lex4nder](https://github.com/4lex4nder/ReshadeEffectShaderToggler), and [AutoHDR - MajorPainTheCactus](https://github.com/MajorPainTheCactus/AutoHDR-ReShade).

We'll dive deeper into `Generic Depth` and other add-ons later. They're powerful tools that can change how each ReShade shader and game works - they can even inject any developer's code into the game!

</details>

---

<details markdown="block" class="details-tree">
<summary>Discovering the Settings Tab</summary>

The `Settings` tab, shown below, lets you tweak ReShade settings like shader directories, menu access keys, FPS meter configurations, theme settings, and more:

![Settings Tab](../images/understanding-and-using-reshade/rsui_settings_tab.png){: style="max-width:65%" }

The dropdowns below detail the settings you can adjust within the ReShade `Settings` Tab:

{: .note }
The following dropdowns for ReShade's settings are verbose, and might not provide a ton of information you would find useful. Skip this part if uneeded.

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

2. `Preset transition duration`:

    * This setting allows you to change the transition between preset files, counted in milliseconds. Remember, 1 second equals 1000 milliseconds!

3. `Input processing`:

    * This setting lets users change the default behavior of ReShade's input control:

      * `Pass on all input` - Allows your game to also receive inputs from your keyboard and mouse, regardless of where they are on the game window.

      * `Block input when cursor is on overlay` - Allows the game to receive inputs from your keyboard and mouse only when they are off of the ReShade UI.

      * `Block all input when overlay is visible` (default option) - Disallows the game to receive all inputs from your keyboard and mouse when the ReShade overlay is active.

4. `Start-up preset`:

    * This argument allows ReShade to utilize a preset to use once your game has started. By default, ReShade loads the last used preset from the user. You can change this behavior by defining a preset file path.

5. `Effect...` and `Texture search paths`: 

    * These settings allow you to specify where ReShade should look for shader files. You can add multiple directories, and ReShade will search all of them when looking for shaders.

    * The default options are:

      * `Effect search paths` - `.\ReShade-Shaders\Shaders\**`

      * `Texture search paths` - `.\ReShade-Shaders\Textures\**`

6. `Load only enabled effects`:

    * This option ensures that only the shaders enabled in your current ReShade preset are loaded. It can prevent issues with conflicting files/techniques from other shaders and reduce the compile time needed at the start of ReShade.

7. `Clear effect cache`:

    * This option allows you to clear the cache for the compiled shaders in ReShade. It can be useful for resolving issues with shaders.

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

7. `Save separate image with the overlay visible`:

    * This option lets you save a separate image with the ReShade UI, useful for troubleshooting.

8. `Screenshot sound`:

    * This option lets you choose a `.wav` file to play when you take a screenshot.

9. `Post-save command`:

    * This option is highly advanced, and allows the users to port their screenshots into external software in order to edit upon saving.
    
      * The option is specifically for pointing to the executable that you will be utilizing.

10. `Post-save command arguments`:

    * This option lets you specify arguments for the executable provided in `Post-save command`. Supported macros include:

      * %AppName% - Current application name.

      * %PresetName% - Name of the preset applied when the screenshot was taken.

      * %Date% - Current date (in '%s' or seconds format).

        * %DateYear%, %DateMonth%, %DateDay% - Year, month, and day components of the current date.

      * %Time% - Current time (in '%s' or seconds format).

        * %TimeHour%, %TimeMinute%, %TimeSecond%, %TimeMS% - Hour, minute, second, and millisecond components of the current time.

      * %TargetPath% - Full path of the screenshot file.

      * %TargetDir% - Directory of the screenshot file.

      * %TargetFileName% - Full name of the screenshot file.

      * %TargetExt% - Extension of the screenshot file.

      * %TargetName% - Name of the screenshot file without the extension.

      * %Count% - Number of screenshots taken in the current session.

11. `Post-save command working directory`:

    * This option lets you define the directory for the Post-save processing software.

12. `Hide post-save command window`:

    * This toggle lets you choose whether to show or hide the window of the Post-save processing application. By default, this option is off, so the program window is visible.

</details>

---

<details markdown="block" class="details-tree">
<summary>Overlay & Styling</summary>

1. `Restart tutorial`:

    * This button restarts the ReShade tutorial that appears when you first launch a game with ReShade injected.

2. `Show screenshot message`:

    * This toggle enables or disables the screenshot notification message.

3. `Group effect files with tabs instead of a tree`:

    * This toggle lets you choose between a tree structure or a grouped structure for shader configuration arguments. While a grouped structure can be more organized, the choice is purely preference-based. By default, this option is off, and the tree structure is used.

4. `Global Style`:

    * This option lets you select from several distinct themes for ReShade. Here's what each preset looks like:

      * `Default`:

        ![Default Preset](../images/understanding-and-using-reshade/default.png){: style="max-width:20%" }
      
      * `Dark`:

        ![Dark Preset](../images/understanding-and-using-reshade/dark.png){: style="max-width:20%" }

      * `Light`:

        ![Light Preset](../images/understanding-and-using-reshade/light.png){: style="max-width:20%" }

      * `Solarized Dark`:

        ![Solarized Dark Preset](../images/understanding-and-using-reshade/solarized_dark.png){: style="max-width:20%" }

      * `Solarized Light`:

        ![Solarized Light Preset](../images/understanding-and-using-reshade/solarized_light.png){: style="max-width:20%" }

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Getting to Know the Statistics Tab</summary>

![Statistics Tab](../images/understanding-and-using-reshade/rsui_stats_tab.png){: style="max-width:65%" }

The `Statistics Tab`, shown in the image, is a great tool for tracking and improving ReShade's performance. It gives detailed info on various aspects of ReShade's operation:

---

* General: 

  * This section provides real-time data on the performance of ReShade and it's shaders - It includes the current frame rate, the time taken to render each frame, and the total number of frames rendered since ReShade was started.

---

* Techniques: 

  * This section shows how much each effect is being used. This can be useful for identifying effects that are consuming a disproportionate amount of resources.

---

* Render Targets & Textures

  * This section provides developers and users with information as to what shaders are doing, what textures they are using or creating, and information about the textures.

---

While the `Statistics Tab` is not typically a frequent stop for casual users, it is an invaluable resource for those creating or analyzing shaders. It provides the detailed performance data needed to optimize shaders and ensure they run smoothly.

</details>

---

<details markdown="block" class="details-tree">
<summary>Deciphering the Log Tab</summary>

![Log Tab](../images/understanding-and-using-reshade/rsui_log_tab.png)

The `Log Tab` is a key tool for monitoring ReShade's operations and troubleshooting issues. It provides a detailed log of ReShade's activities to help you identify where your issues are.

Warnings or errors in ReShade will appear in the Log Tab in different colors:

  * YELLOW: A warning. This usually means an effect has loaded, but there might be room for optimization or the effect was altered during the load process.

  * RED: An error. This is usually accompanied by a note explaining the error.

If something seems wrong, it's recommended to share the error text or the entire log file, which is stored in the game directory as `ReShade.log`. However, logs are reset each time the game is restarted. So, remember to share or save logs before restarting your game!

</details>

---

<details markdown="block" class="details-tree">
<summary>Appreciating the About Tab</summary>

![About Tab](../images/understanding-and-using-reshade/rsui_about_tab.png)

The `About Tab`, as shown in the image above, acknowledges and recognizes the work behind ReShade:

  * ReShade Version

  * Contributor Credits

  * License Acknowledgements

The `About Tab` is a formal acknowledgment of the collective effort that goes into creating, maintaining, and improving ReShade. It highlights the collaborative nature of software development and the importance of giving credit where it's due.


</details>

---

# Understanding ReShade's Depth Buffer

The depth buffer in a game tells what in the game has “depth”, as in, what is actually 3D, and what is just a plane. 

It's crucial for effects like Ambient Occlusion, which determines what occludes and what doesn't, and Depth of Field, which identifies what is close to the camera and what isn't. Without it, these effects can't distinguish between near and far objects. 

In the following sections, you'll learn how to identify a depth buffer, check if it's working, and troubleshoot common issues that prevent detection.

{: .warning}
Ensure you've correctly set up ReShade and followed the previous steps on the other pages! This guide assumes you've followed all instructions and have ReShade set up and running correctly.

---

<details markdown="block" class="details-tree">
<summary>Understanding Depth Buffer Basics</summary>

Before diving in, it's crucial to understand what each part and color of the Depth Buffer signifies.

This section will explain, what to look out for, and how to handle each case.

---

<details markdown="block" class="details-tree">
<summary>Reversed Depth Buffer</summary>

To start, enable the shader `DisplayDepth`. This shader is included with all ReShade installs through the ReShade Installer. If you do not have it, you can manually install it from [Crosire's ReShade-Shaders repository](https://github.com/crosire/reshade-shaders/tree/slim/Shaders).

The image below shows that the `DisplayDepth` shader has loaded correctly, however, there are issues with the example shown. 

![Depth Buffer Reversed](../images/understanding-and-using-reshade/depth_buffer_reversed_example.png)

This is unfortunately a case of the Depth Buffer being reversed, but it's an easy fix!

You can solve this issue by simply flipping the `RESHADE_DEPTH_INPUT_IS_REVERSED` argument within the `Global Preprocessor Definitions` under the `Home` tab of ReShade.

</details>

<details markdown="block" class="details-tree">
<summary>No Depth Buffer</summary>

To start, enable the shader `DisplayDepth`. This shader is included with all ReShade installs through the ReShade Installer. If you do not have it, you can manually install it from [Crosire's ReShade-Shaders repository](https://github.com/crosire/reshade-shaders/tree/slim/Shaders).

If your shader resembles the images below, it lacks data from the `Generic Depth` Add-on:

![Depth Buffer No Data](../images/understanding-and-using-reshade/depth_buffer_no_data_example.png)

  * Before proceeding any further, ensure that these anti-aliasing options are disable within your game:

    * MSAA ANTIALIASING

    * SSAA ANTIALIASING

  FXAA or TXAA are acceptable, as they don’t erase the depth-buffer information.

The image shown above is the output of `DisplayDepth` showing no data from `Generic Depth`.

This means that:

* Your game is not presenting a depth buffer 

* You have the wrong options configured for `Generic Depth`

* Your depth buffer choice is wrong.

---

You can absolve this issue simply by playing around with `Generic Depth` in order to 



![Depth Buffer No Data - Reversed](../images/understanding-and-using-reshade/depth_buffer_no_data_reversed_example.png)

This image shows what the shader looks like when it lacks data and is reversed.

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding Global Preprocessor Basic Arguments</summary>

This section will guide you through the basic arguments that are presented to the ReShade Depth Buffer.

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_IS_REVERSED</summary>

This argument is used when you can see the normals, but the depth image itself is not visible (The first result image should illustrate this perfectly). It usually starts at 1, so setting it to 0 should fix the issue. However, the solution could also be the reverse.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_IS_UPSIDE_DOWN</summary>

As the name suggests, this argument is used when the image displayed by the DisplayDepth shader is upside down. Setting it to 1 should rectify the problem.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_IS_LOGARITHMIC</summary>

This argument is used when the depth buffer displays numerous waves or "stripes". Very FEW games actually utilize this, so it's rare that you'll need to toggle or modify this setting.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding Global Preprocessor Advanced Arguments</summary>

These advanced options will seldom require modification. However, for older games or emulators, you might need to adjust them. Below, you'll find a general description of these arguments.

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_INPUT_X_SCALE | RESHADE_DEPTH_INPUT_Y_SCALE</summary>
These arguments modify the depth buffer size (with 1 representing the original size, 2 being double, and so forth) along the horizontal (X) and vertical (Y) axes.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_LINEARIZATION_FAR_PLANE</summary>
This argument defines the "infinite" distance in the depth buffer. 

The values can be either extremely low or high, so you'll need to experiment to determine the best fit for your specific case.

</details>

---

<details markdown="block" class="details-tree">
<summary>RESHADE_DEPTH_MULTIPLIER</summary>
This argument multiplies the far plane, facilitating the visualization of extremely low or high far plane values.

</details>
</details>
