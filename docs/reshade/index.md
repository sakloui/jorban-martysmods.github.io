---
title: ReShade Guides
layout: default
nav_order: 3
---

# Installing ReShade 

<img style="max-width: 15%" src="./images/installing_reshade/rs_gradiant.png"/>

ReShade is a shader-injection tool for all games and applications under the DirectX 9-12, OpenGL, and Vulkan graphics rendering APIs.

Similar to ENB, DXVK, or ASILoader, ReShade injects into your game in order to allow for unlimited creativity from its users so they can create the image that they desire.

This guide has been written in order to help guide you through the install process for ReShade so that you can utilize it in all of your games, and progress your knowledge for the fundamentals and advanced features of ReShade!

------

<details markdown="block">
<summary>Downloading the ReShade Installer</summary>

To start, download the latest version of ReShade by navigating to the [homepage for ReShade](https://reshade.me/#download).<br>Once there, you need to scroll all the way down to the latest available versions to download.<br>There will be two builds of ReShade that are avaliable for the latest install of ReShade.

{: .warning}
Do not download ReShade Installers or DLLs from unofficial sources outside of the official ReShade website: [https://reshade.me](https://reshade.me)<br>Downloading and utilizing unofficial binaries can lead to various issues, including viruses.<br>**Be Cautious!**

<img src="./images/installing_reshade/rs_scroll.gif"/>
Once you are at the bottom of the site, you will be presented with two variations of the ReShade Installer.

There are large differences between these builds, and it is very important to understand what each build has to offer.

------

### Standard ReShade Build (Download ReShade x.x.x)

<img src="./images/installing_reshade/rs_standard_button.png"/>
The first build option for you to choose is ReShade's standard build. 

This build is specificially to be used in games that endorse online play and have implemented anti-cheat or anti-tamper systems. These security measures, prevalent in many MMO and modern FPS games, help maintain an even playing field by preventing it's players from cheating. Some game developers have even created sophisticated driver-level anti-cheat systems to deploy in popular games.The Standard Build of ReShade is suited for gamers who frequent multiplayer games or games fortified with such security measures. 

Some online games, including Dead by Daylight, PlayerUnknown's Battlegrounds, and Apex Legends, permit this build of ReShade to inject while having an anti-cheat system - this is due to ReShade cutting access to the add-ons, when an online connection in the game is present. 

This add-on functionality is what powers depth-based shaders like iMMERSE MXAO, iMMERSE Pro RTGI, and CinematicDOF - and without the add-on functionality, these shaders do not work properly.

Although this provides a secure gaming experience, it can easily restrict the capabilities of shaders and hamper the full extent of users attainable visual enhancements.

------

### Full Add-On Support ReShade Build (Download ReShade x.x.x with full add-on support)

<img src="./images/installing_reshade/rs_addon_button.png"/>
The second build option for you to choose is ReShade's full add-on support version. 

This build was designed primarily for single player games or games that don't use anti-cheat mechanisms. 

While it can be used in older games with less robust anti-cheats (for example: older Valve games using VAC or older idTech shooters using PunkBuster), you can still be putting yourself at risk of a ban. Therefore, we advise users to **be careful** and only inject this version in known games that do not list bans for ReShade or other graphics injections.

The largest difference in this version is the ability to use ReShade's add-on features. This version allows for ReShade users to utilize Add-ons (outside of Generic Depth) developed by community members. This version also allows you to utilize these Add-ons within a game that has a network connection. 

Add-ons are ReShade extensions that developers can code to maximize ReShade's potential. For reference, they can detect buffers in different ways or utilize various effects that tie deeply into your game. Addons other than Generic Depth are allowed in this version, but not the standard build of ReShade.

{: .warning }
The majority of the effects and add-ons are harmless, but if you deliberately use them for unfair advantages in games, you should expect a ban. There won't be any right to appeal since this is a clear violation - as ReShade modifies the game during runtime.

</details>

------

<details markdown="block">
<summary>Utilizing the ReShade Installer</summary>

Once launched, the installer will prompt you to select a game or application that you want to inject ReShade to. It's recommended to explore the additional options offered by the installer!
<img src="./images/installing_reshade/rs_game_list.png"/>
Beneath the game selection box, you'll notice a search bar and a "Browse..." button. These features allow you to locate the game's executable directly. Clicking on "Browse..." opens the File Explorer, where you can pick the exact executable file for your game. Keep in mind that Desktop shortcuts are not the same as the game's executable file.
<img src="./images/installing_reshade/rs_browse.png"/>
This method is particularly helpful if you're installing ReShade to a game downloaded from platforms like itch.io, older games without setup processes, or emulators such as DOSBox or Dolphin.

Once your game is selected properly, click the button labeled "Next..."

------

<details markdown="block">
<summary>Selecting the Rendering API in the ReShade Installer</summary>

Upon clicking next, you will be greeted with a new page that hosts a selection of renderer names. This part is very important in the install process as you will need to pick the correct one.

Below is general information in order to take a best guess - however, we recommend using websites like Steam and PCGamingWiki in order to search for your title and make the appropriate selection.

{: .important }
Please remember, if you choose the wrong rendering API, ReShade will not inject properly!

<img src="./images/installing_reshade/rs_dx9.png"/>
DirectX 9 was widely used from early 2005 to late 2012. Most modern titles will opt to use newer DirectX versions or other rendering APIs. However, some games can also use DirectX 9 as a legacy or fallback renderer.

------

<img src="./images/installing_reshade/rs_dx10_11_12.png"/>
DirectX 10 to DirectX 12 is widely used for most industry-standard engines, such as Unity or Unreal Engine, and modern AAA games. When in doubt, select this option, as it should work. If not, the rendering API of the game will be one of the latter options. It is very rare for a game post-2012 to not utilize one of the renderers below.

------

<img src="./images/installing_reshade/rs_ogl.png"/>
OpenGL is still used today; especially to a few game engines (Like Unity and Godot), applications (Such as emulators, video players) and a few old games, especially old idTech / id Software titles (Quake Series, DOOM, sourceports of games, a few tools), if DirectX didn’t work and the title doesn’t use any “legacy” rendering options (Such as Direct3D, Glide or anything pre-2000), this is the renderer you want.
------

<img src="./images/installing_reshade/rs_vk.png"/>
Vulkan is used as the main renderer for modern emulators (such as PS3, Switch, Xbox 360), and any recently released Bethesda / idSoftware titles (DOOM Eternal, DOOM 2016, Wolfenstein series.) Vulkan will be mandatory if used on Linux (via Wine) or with similar interfaces such as Steam’s Proton.

{: .important }
Installing ReShade using the Vulkan rendering API will require the ReShade installer to prompt the user for admin rights. This is due to the ReShade Installer needing to create a few files in the “ProgramData” folder of the PC and changes a few values in the registry. If you deny admin rights to the ReShade installer, installing ReShade for Vulkan will not work properly!

</details>

------

<details markdown="block">
<summary>Installing Presets with the ReShade Installer</summary>

Installing presets has been made miles easier with the ReShade installer! No longer will you have to worry about finding the specific shaders that are used in presets. When selecting the preset file in the ReShade installer under the preset install section, the ReShade installer will automatically select the proper shaders and repos that you need for it to work properly! Please keep in mind that this method will not work properly for your preset if the preset requires unique shaders and textures that come with the preset archive!
<img src="./images/installing_reshade/rs_preset.png"/>
In order to select the preset you want to install with ReShade, simply click the "Browse..." button on the bottom right hand corner of the ReShade installer.
<img src="./images/installing_reshade/rs_preset_browse.png"/>

{: .note }
ReShade presets will be in the form of {PresetName}.ini files.

</details>

------

<details markdown="block">
<summary>Installing Shaders with the ReShade Installer</summary>

Shaders are what makes ReShade so valuable to it's users. They're the effects that you can toggle on and configure to get the specific look you want per game!

That being said, finding shader collections can be difficult, as each Shader Developer has their own methods of storing and updating shaders - however, the ReShade installer has made this much easier for users wanting to utilize shaders made by Shader Developers. 

If you installed a preset, there will already be marks set in this portion of the installer - if not, it should be blank other than "Standard Effects."
<img src="./images/installing_reshade/rs_shader.png"/>

Each repository has two options for the user to select:
On the left hand side of the shader install portion of the ReShade installer window, you will notice a square tick, and a check tick. These two have different meanings. A square tick means that you are selectively installing the shaders from that repository, while a check tick means that you are getting all the shaders in the whole repository.

If you want to know more about the developer of each shader repository, you can also click the blue highlighted text where the repository name and author's name is, and it will open a page in your browser to their repository! Generally shader repositories have more information to each shader, and descriptions that might be valuable to a user.

Once you have the shaders selected that you want, simply click "Next"
<img src="./images/installing_reshade//rs_shader_select.png"/>
If you have selected the square tick for any shader repositories, you will be greeted with a "Select {shader repository name} files to install screen. Simply select the shaders that you want from that repository and click next!

</details>

------

<details markdown="block">
<summary>Finishing Up the Installation Process</summary>

When you are completely done with installing ReShade through the ReShade installer, you will be greeted with a screen saying that ReShade has installed successfully. Simply click "Finish" and launch your game!
<img src="./images/installing_reshade/rs_complete.png"/>
If you've done everything properly, ReShade will present a banner in game:
<img src="./images/installing_reshade/rs_game_banner.png"/>

</details>
</details>

------

# Understanding ReShade's UI

So, after getting ReShade installed, the next step is to run the game and see if the ReShade popup appears on the top of the screen, if it does, congratulations! You have 70% of the work done. If not, try fiddling with the renderer settings again. 

A crucial step to start playing around with ReShade though, is getting acquainted with the UI, for this, press “HOME” on the Keyboard (or POS1 in a few other languages, this changes per Keyboard or locale) you can then follow the in-screen tutorial. (Make sure to follow it if you are a first-time user, reading does pay-off) However, if you skipped through it (pressed “Skip Tutorial” instead of “Continue”), we will assist you on what each part and button does. Make sure to follow and learn this properly so you have to worry less when our adventure with the Depth Buffer starts.

------

<details markdown="block">
<summary>The Home Tab</summary>

The Home tab of ReShade is a critical section that houses many benifitial configuration items for the end user to discover.

<details markdown="block">
<summary>Current Preset</summary>

<img src="./images/understanding_reshade_ui/rsui_preset.png"/>
The highlighted portion in the image above shows what preset is currently active within ReShade. Presets are saved in the game directory by default, and the default name for them is always ReShadePreset.ini, you can create a new one by clicking on the “+” button, save it by clicking on the Diskette-icon button and switch between them using the arrow buttons. ReShade tries to automatically detect which ini is a Preset, so you won’t have problems with ReShade picking up the wrong ini as a preset.

</details>

------

<details markdown="block">
<summary>Effect List</summary>

<img src="./images/understanding_reshade_ui/rsui_effectlist.png"/>
The highlighted portion in the image above shows the effect list within ReShade's "Home" tab. This portion of the "Home" tab is where all of your installed shaders live within the ReShade UI. Your list may be bigger or smaller depending on the effects the preset you downloaded uses, or the effect packs you installed back at the ReShade setup.

</details>

------

<details markdown="block">
<summary>Global Pre-processor Definitions</summary>

<img src="./images/understanding_reshade_ui/rsui_globalpreprocessors.png"/>
The highlighted portion ion the image above shows the "Edit Global Preprocessor Definitions" button within the ReShade "Home" tab. Pre-Processor definitions are “flags” or toggles which define how an effect should behave before it gets loaded. It's often used to change various shader behaviors or compatibility. This is important. Once you click it, it should open a small window:
<img src="./images/understanding_reshade_ui/rsui_globalpreprocessors_window.png"/>
The first tab shows which defines are “Global”, which means that they will get applied to every preset. By default, ReShade leaves those configured to its own effects, but you might add, edit or remove by clicking on the “Plus” and “Minus” signs. Make sure to always know the name of the pre-processor definition you need to change, and its min and max values. Shaders usually have those in comments. So, you will need to open the FX files with a advanced text editor to help with reading (Such as Notepad++).
<img src="./images/understanding_reshade_ui/rsui_globalpreprocessors_current_preset.png"/>
The second tab shows which defines are valid for the “Current Preset”, which means they will change or reset to what is the shader’s default or the Global value for them when the preset is changed. This is useful if different presets use different pre-load values.

{: .note}
With a default ReShade preset, this tab will be blank

</details>

------

<details markdown="block">
<summary>Effect Parameters</summary>

<img src="./images/understanding_reshade_ui/rsui_effect_params.png"/>

The image above shows you the location of shader's effect parameters. When you enable a shader within ReShade, its options and parameters will appear there. Changes made here are changed in real-time, so you can always have the window a bit to the side to see what exactly is being altered on the image.

</details>

----------------

<details markdown="block">
<summary>Reload Button</summary>

<img src="./images/understanding_reshade_ui/rsui_reload.png"/>

This button, highlighted within the image above, forces ReShade to re-read the files on the Shaders and Textures folder, and add / include newly installed effects there, without having to quit and open the game again. This is also useful to see changes made to the shader code while programming.

</details>

----------------

<details markdown="block">
<summary>Performance Mode</summary>

<img src="./images/understanding_reshade_ui/rsui_performance_mode.png"/>

This setting, highlighted within the image shown above, optimizes the compilation functions and how ReShade runs in the memory, making it less impactful on performance. Note that this will prevent edits to be made on the shaders and that some effects might not work well with it. In this case, you should always let the shader author know if there are any issues with the Performance Mode.

</details>
</details>

------

<details markdown="block">
<summary>Add-ons Tab</summary>

<img src="./images/understanding_reshade_ui/rsui_addons_tab.png"/>

This tab, highlighted in the image above, controls how each installed ReShade “Addon” works, by default, only “Generic Depth” is installed. Which is responsible on getting the depth buffer and selecting the correct one, we’ll look deeper into it later, for now, just know that this exists and can be used to control how each ReShade extension behaves.

</details>

-----

<details markdown="block">
<summary>Settings Tab</summary>

<img src="./images/understanding_reshade_ui/rsui_settings_tab.png"/>

This tab, highlighted in the image above, controls various important ReShade options, such as where the directories for Shaders are, the keys to open the menu, change between effects, FPS meter options , window theme and etcetera. Make sure to read through them all and experiment to make yourself more comfortable with the UI.

</details>

-----

<details markdown="block">
<summary>Statistics Tab</summary>

<img src="./images/understanding_reshade_ui/rsui_stats_tab.png"/>

This tab, highlighted in the image above, shows performance metrics, what the effects are using, how much they are consuming, how they are looking on each pass, how they work… Usually, you won’t need to look there much unless you are developing or measuring a shader’s performance.

</details>

-----

<details markdown="block">
<summary>Log Tab</summary>

<img src="./images/understanding_reshade_ui/rsui_log_tab.png"/>

This tab, highlighted in the image above, shows ReShade’s “Log”, which writes how loading the shaders and ReShade itself went. If there are any errors or problems with a shader, they will be shown here, with YELLOW being a warning (incase an effect loaded, but certain functions and code could be better written or was changed during load), and RED being a error (Critical, prevented an effect from loading, usually followed by a description of the error), this is a very important tool for developers when they make their shaders, so if you see anything wrong, and you think a error or warning might be relevant, make sure to send them the resulting text, or sending the log file (all LOGs get saved on the game directory as ReShade.log, please note that the logs will be cleaned up once you leave and start the game again, so make sure to leave the game, send the log, and then send again to prevent loss of information).

</details>

-----


<details markdown="block">
<summary>About Tab</summary>

<img src="./images/understanding_reshade_ui/rsui_about_tab.png"/>

This tab, highlighted in the image above, shows the credits of who worked / works in the development of ReShade, licenses, other code it used for its development and such. Mostly a formality.

</details>

-----

# Understanding ReShade's Depth Buffer

The depth buffer in a game tells what in the game has “depth”, as in, what is actually 3D, and what is just a plane. It is the basis for effects such as Ambient Occlusion to detect what occludes and what doesn’t, and for Depth of Field to detect what is close to the camera and what isn’t. Without that, those effects don’t know what is close and far, and can’t work. In the next few steps, you will learn how to identify a depth buffer, how to see if it works, common issues which makes the detection not possible, and so on.

{: .warning}
Make sure you correctly set-up ReShade and followed the previous steps on the other pages! This guide will be made on the basis that you followed all of the instructions there and got ReShade set-up and running correctly.

------

<details markdown="block">
<summary>Depth Buffer Basics</summary>

First of all, what you need to do before anything is to know what each part and color of the Depth Buffer means, this will explain what each means, what to notice and what to do with each case.

{: .warning}
>BEFORE DOING ANYTHING THOUGH, GO TO YOUR GAME GRAPHICS SETTINGS, AND DISABLE THE FOLLOWING:
>
> * MSAA ANTIALIASING - (FXAA or TXAA is fine though, since it doesn’t erase the depth-buffer information by doing multiple samples)
> * SSAA ANTIALIASING

<img src="./images/understanding_reshade_depth_buffer/depth_buffer_reversed_example.png"/>

If it looks like the image above, the shader has loaded and is working properly, but please notice that we’re not yet done, since there are still some details wrong about what has been shown above.

{: .important}
> If your shader looks like the images below, it has no data, and you should go back a few steps and read what you should disable, carefully.
> 
> <img src="./images/understanding_reshade_depth_buffer/depth_buffer_no_data_example.png"/>
> 
> This is what the depth buffer shader looks like with no data.
> 
> <img src="./images/understanding_reshade_depth_buffer/depth_buffer_no_data_reversed_example.png"/>
> 
This is what the shader looks like when it has no data, and is reversed.

</details>

------

<details markdown="block">
<summary>Global Preprocessor Basic Arguments</summary>

------

### RESHADE_DEPTH_INPUT_IS_REVERSED
Used when you can see the normals, but can’t see the depth image itself (The first result image should represent this perfectly), usually starts at 1 so set it to 0 to fix it, it can also be the other way around.

------

### RESHADE_DEPTH_INPUT_IS _UPSIDE_DOWN
As the name says, when the image shown by the DisplayDepth shader is upside down, setting it to 1 should fix the issue.

------

### RESHADE_DEPTH_INPUT_IS_LOGARITHMIC
Used when the depth buffer has lots of waves or “stripes”. Very FEW games actually do use this, so you rarely will have to switch or change that.

</details>

------

<details markdown="block">
<summary>Global Preprocessor Advanced Arguments</summary>
These more advanced options here will rarely need to be changed, but for old games or emulators, you might have to fiddle around with them.

Here you can find a generalized description of them.

------

### RESHADE_DEPTH_INPUT_X_SCALE | RESHADE_DEPTH_INPUT_Y_SCALE
Changes the depth buffer size (multiplier, so 1 = original size, 2 = double and so on) on the horizontal (X) and vertical (Y) axis.

------

### RESHADE_DEPTH_LINEARIZATION_FAR_PLANE
How far is the “infinite” defined in the depth buffer. Values can either be really low or really high, so you will have to experiment to see which fits best on your case.

------

### RESHADE_DEPTH_MULTIPLIER
Multiplies the far plane for easy visualization of really low or really high far plane values.

</details>
