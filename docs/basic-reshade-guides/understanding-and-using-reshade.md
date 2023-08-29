---
title: Understanding and Using ReShade
layout: default
nav_order: 2
parent: Basic ReShade Guides
---

# Understanding and Using ReShade

To make the most of ReShade, it's a good idea to get to know its UI. As understanding what ReShade has to offer, and how to navigate it's menu can help you down the line!

Press the `HOME` key (or `POS1` on some keyboards, depending on your locale) to bring up the on-screen tutorial. 

If you're new to ReShade, **stick with this tutorial** - it'll cover the basics and give you a solid foundation for what's next. **Don't skip it!**

If you've already skipped the tutorial, don't worry - we'll go through each feature and menu in this guide.

---

<details markdown="block" class="details-tree">
<summary>Exploring the Home Tab</summary>

The `Home` tab in ReShade is where all the shaders, and their configurations, are located.

With that in mind, it is one of the most important tabs of ReShade, but it can be complex.

Below will be a breakdown of each part of the `Home` tab to help guide you into understanding what is offered:

---

<details markdown="block" class="details-tree">
<summary>Current Preset</summary>

Let's start by identifying the active preset in ReShade, as shown in the highlighted section below:

![Current Preset](../images/understanding-and-using-reshade/rsui_preset.png){: style="max-width:65%" }

To the right of the current preset dropdown, you'll find a `+` button. Use this to create a new preset. Next to it, the diskette icon serves to save your preset.

To the left of the current preset dropdown, you'll find `<` and `>` buttons. These buttons switch the current preset to the next avaliable one in the same directory. ReShade will smartly identifie which `.ini` files in your game directory are presets!

When saving your preset, ReShade by default will save presets in the game directory, in a file named `ReShadePreset.ini` unless renamed.

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding the Technique List</summary>

The highlighted area below shows ReShade's `Technique List` within the `Home` tab:

![Technique List](../images/understanding-and-using-reshade/rsui_effectlist.png){: style="max-width:65%" }

This section lists all the shaders installed by you or the ReShade Installer. 

It is worth noting that your `Technique List` will likely not look like the image above, as its size can vary depending on the chosen preset and the shader repositories you've installed.

</details>

---

<details markdown="block" class="details-tree">
<summary>Global Pre-processor Definitions</summary>

The `Edit Global Preprocessor Definitions` button, highlighted in the image below, is your gateway to controlling the behavior of effects before they load. Definitions that you set here will act like switches, guiding how shaders function:

![Global Pre-processor Definitions](../images/understanding-and-using-reshade/rsui_globalpreprocessors.png){: style="max-width:65%" }

Clicking this button above will open a window with two tabs:

* `Global`:

  * Global will be where you can add or edit definitions that apply to all presets.

    ![Global Pre-processor Window](../images/understanding-and-using-reshade/rsui_globalpreprocessors_window.png)

* `Current Preset`:

  * Current Preset will likely not have any definitions by default, however, you can add and remove to apply these to your current preset!

    ![Global Pre-processor Current Preset](../images/understanding-and-using-reshade/rsui_globalpreprocessors_current_preset.png)

{: .note }
When tinkering with these options, it's crucial to know the pre-processor definition's name and range. You can often find this information in the comments of the shaders. To inspect FX files and their contents, consider using advanced text editors like [Notepad++](https://notepad-plus-plus.org/) or [Visual Studio Code](https://code.visualstudio.com/).

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding Effect Parameters</summary>

The image below shows the effect parameters of shaders:

![Effect Parameters](../images/understanding-and-using-reshade/rsui_effect_params.png){: style="max-width:65%" }

When you enable a shader in ReShade, its options and parameters appear in the highlighted section above.

Shader parameters are dynamic, meaning that any modifications you make are reflected in real-time, allowing you to see the impact of your changes immediately.

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding the Reload Button</summary>

The `Reload` button, as highlighted in the image below, instructs ReShade to re-examine the files in the Shaders and Textures folders:

![Reload Button](../images/understanding-and-using-reshade/rsui_reload.png){: style="max-width:65%" }

By clicking the `Reload` button, you can integrate newly installed effects without needing to restart the game. This feature also reflects any changes made to the shader code during development, making it a handy tool for real-time adjustments of the shader's code!

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding Performance Mode</summary>

The `Performance Mode` setting, as highlighted in the image below, enhances the efficiency of compilation processes and ReShade's memory operations, reducing performance overhead:

![Performance Mode](../images/understanding-and-using-reshade/rsui_performance_mode.png){: style="max-width:65%" }

`Performance Mode` will restrict changes made to a shader's parameters.

If you encounter any inconsistencies while using Performance Mode, **always** report them to the shader creator.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Understanding the Add-ons Tab</summary>

The `Add-ons Tab`, as shown in the image below, manages each ReShade Add-on:

![Add-ons Tab](../images/understanding-and-using-reshade/rsui_addons_tab.png){: style="max-width:65%" }

The `Add-ons` Tab serves as a control panel for managing Add-ons. Each `Add-on` provides additional functionality or enhancements to your installed ReShade shaders. Some `Add-ons` may offer new effects, while others provide tools for fine-tuning existing effects!

The `Add-ons` Tab also allows you to enable or disable individual add-ons and control their arguments.

By default, `Generic Depth` is the only add-on included with the ReShade Installer. However, you can install many other ReShade Add-ons.

In addition to `Generic Depth`, other popular Add-ons include [ShaderToggler - FransBouma](https://github.com/FransBouma/ShaderToggler), [ReShade Effect Shader Toggler - 4lex4nder](https://github.com/4lex4nder/ReshadeEffectShaderToggler), and [AutoHDR - MajorPainTheCactus](https://github.com/MajorPainTheCactus/AutoHDR-ReShade).

We'll explore `Generic Depth` and other add-ons in more detail later, as these complex Add-ons can significantly alter the behavior of each ReShade shader and game they are applied to - they are powerful tools that can inject any developer's code into the game!

</details>

---

<details markdown="block" class="details-tree">
<summary>Discovering the Settings Tab</summary>

The `Settings` tab, depicted in the image below, allows you to adjust variousReShade settings — such as directories for Shaders, keys for menu access, FPS meter configurations, theme settings, and more:

![Settings Tab](../images/understanding-and-using-reshade/rsui_settings_tab.png){: style="max-width:65%" }

Below are dropdowns that provide information about the key settings, per dropdown in ReShade, you can adjust within the ReShade `Settings` Tab:

---

<details markdown="block" class="details-tree">
<summary>General Menu</summary>

1. `Keybindings`: 

    * Here, you can set the keybindings for various actions in ReShade, allowing you to customize the controls:

      * `Overlay key`:

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

The `Statistics Tab`, as shown in the image, is a powerful tool for monitoring and optimizing the performance of ReShade. It provides detailed information about various aspects of ReShade's operation:

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

![Log Tab](../images/understanding-and-using-reshade/rsui_log_tab.png){: style="max-width:65%" }

The `Log Tab`, as shown in the image above, is a crucial tool for monitoring ReShade's operations and troubleshooting issues. It provides a detailed log of ReShade's activities that should be able to help you decipher where your issues lie!

If anything in ReShade reports a warning or error, they'll appear in the Log Tab in different colors:

  * YELLOW: Indicates a warning. This usually means that an effect has loaded, but there might be potential for optimization or the effect experienced alterations during the load process.

  * RED: Signals an error. This is typically accompanied by an explanatory note detailing the nature of the error.

If something seems off, it's recommended to share the error text or the entire log file, which is stored in the game directory as `ReShade.log`. However, logs are reset each time the game is restarted. So, be sure to share or save logs before rebooting your game!

</details>

---

<details markdown="block" class="details-tree">
<summary>Appreciating the About Tab</summary>

![About Tab](../images/understanding-and-using-reshade/rsui_about_tab.png){: style="max-width:65%" }

The `About Tab`, as shown in the image, serves several important functions related to the acknowledgement and recognition of the work behind ReShade:

* ReShade Version

* Contributor Credits

* License Acknowledgements

The `About Tab` is a formal acknowledgment of the collective effort that goes into creating, maintaining, and improving ReShade. It serves as a reminder of the collaborative nature of software development and the importance of giving credit where it's due.

</details>

---

# Understanding ReShade's Depth Buffer

The depth buffer in a game tells what in the game has “depth”, as in, what is actually 3D, and what is just a plane. 

It is the basis for effects such as Ambient Occlusion to detect what occludes and what doesn’t, and for Depth of Field to detect what is close to the camera and what isn’t. Without that, those effects don’t know what is close and far, and can’t work. 

In the next few steps, you will learn how to identify a depth buffer, how to see if it works, common issues which makes the detection not possible, and so on.

{: .warning}
> Make sure you correctly set-up ReShade and followed the previous steps on the other pages! 
> 
> This guide will be made on the basis that you followed all of the instructions there and got ReShade set-up and running correctly.

---

<details markdown="block" class="details-tree">
<summary>Understanding Depth Buffer Basics</summary>

Before diving in, it's crucial to understand what each part and color of the Depth Buffer signifies. 

This section will explain each component, what to look out for, and how to handle each case.

---

{: .warning}
> IMPORTANT: BEFORE PROCEEDING, GO TO YOUR GAME GRAPHICS SETTINGS, AND DISABLE THE FOLLOWING:
>
> * MSAA ANTIALIASING
>
> * SSAA ANTIALIASING
>
> FXAA or TXAA is acceptable, as they don’t erase the depth-buffer information by doing multiple samples

![Depth Buffer Reversed](../images/understanding-and-using-reshade/depth_buffer_reversed_example.png)

If your screen resembles the image above, the shader has loaded correctly and is functioning as expected. 

However, note that we're not quite finished, as there are still some inaccuracies in the displayed details.

{: .important }
> If your shader resembles the images below, it lacks data. You should revisit the previous warning and carefully read about what to disable.
> 
> ![Depth Buffer No Data](../images/understanding-and-using-reshade/depth_buffer_no_data_example.png)
> 
> This image shows what the depth buffer shader looks like without data.
> 
> ![Depth Buffer No Data - Reversed](../images/understanding-and-using-reshade/depth_buffer_no_data_reversed_example.png)
> 
> This image shows what the shader looks like when it lacks data and is reversed.

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
