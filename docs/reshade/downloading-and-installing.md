---
title: Downloading and Installing
layout: page
parent: ReShade
nav_order: 1
---

# Downloading and Installing ReShade

ReShade enhances your video game visuals by adding effects like improved color depth and sharper details. It's compatible with most games and works with graphics APIs including DirectX, OpenGL, and Vulkan.

This guide is here to help you quickly download and install ReShade, ensuring you can easily upgrade your gaming experience. Follow the steps below to get started.

---

<details markdown="block" class="details-tree">
<summary>Downloading ReShade</summary>

The latest version of ReShade will always be avaliable at [ReShade's Homepage](https://reshade.me/#download).

![ReShade Homepage](../images/downloading-and-installing/rs_homepage.webp){: style="max-width:90%" }

Avalible for download are two builds of ReShade that you can select. The Standard, and Full Add-on Support build. Below, you can find information specifically on what differientiates the two builds, and the common usecases for them.

![ReShade Download Options](../images/downloading-and-installing/rs_download.webp){: style="max-width:90%" }

## Standard ReShade Build (Download ReShade x.x.x)

The Standard Build of ReShade is the most common version. It is ideal for online games with strict anti-cheat mechanisms (e.g., Dead by Daylight, PUBG, Apex Legends.) This build is used for online games due to its limitations to features to prevent misuse and cheating in online games. 

If you are unsure of what build to pick, this is likely the best choice!

## Full Add-On Support ReShade Build (Download ReShade x.x.x with full add-on support)

The Full Add-On Support Build of ReShade is best for offline games or games without anti-cheat systems (e.g., Final Fantasy XXIV, World of Warcraft, Baldur's Gate 3.) This build will offer the full feature set and freedom for creating presets with various shaders and add-ons.

If your game is offline, it's best to choose this build to prevent issues down the line!

</details>

---

<details markdown="block" class="details-tree">
<summary>Installing ReShade with the ReShade Installer</summary>

## Selecting Your Game

When opening the ReShade Installer, you'll be greeted with the option to choose what application that you want to install ReShade to. This part is very important, as if the wrong application or executable is selected, ReShade will not launch when your game starts.

![Game List](../images/downloading-and-installing/rs_game_list.webp)

If your game does not appear in the listing, click the "Browse..." button at the bottom right of the ReShade Installer. This button will open up a "File Explorer" window that will allow you to manually find your game's executable. 

If you are unsure of where the executable is located, check our [guide on finding your game's executable and directory](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

![Browse](../images/downloading-and-installing/rs_browse.webp){: style="max-width:90%" }

---

## Selecting the Rendering API

In order for ReShade to properly be installed, the ReShade Installer needs to know what Rendering API your game utilizes. The Rendering API has to be selected properly for ReShade to successfully inject, so make sure that you are getting this option correct, otherwise ReShade will not launch with your game.

If unsure which API your game uses, check [PCGamingWiki](https://pcgamingwiki.com) for details.

![ReShade Rendering API Selection](../images/downloading-and-installing/rs_rendering_api_select.webp)

<details markdown="block" class="details-tree">
<summary>DirectX 9</summary>

DirectX 9 was common between 2005 and 2012. It's less likely for modern games, which often use newer APIs.

![DirectX 9 Example](../images/downloading-and-installing/rs_dx9.webp)

</details>

---

<details markdown="block" class="details-tree">
<summary>DirectX 10-12</summary>

These versions are widely used in modern games, particularly with Unity and Unreal Engine.

![DirectX 10-12 Example](../images/downloading-and-installing/rs_dx10_11_12.webp)

</details>

---

<details markdown="block" class="details-tree">
<summary>OpenGL</summary>

Chosen for certain engines and older games where DirectX is not used.

![OpenGL Example](../images/downloading-and-installing/rs_ogl.webp)

</details>

---

<details markdown="block" class="details-tree">
<summary>Vulkan</summary>

Favored in modern emulators and newer games, essential for Linux users via Wine or Proton. Note: Vulkan installations may require admin permissions.

![Vulkan Example](../images/downloading-and-installing/rs_vk.webp)

</details>

---

## Installing Presets

ReShade presets, stored in `.ini` files, allow you to apply someone else's visual customizations, including shader configurations and hotkeys.

The ReShade Installer simplifies preset installation: just select the desired `.ini` file, and the installer automatically handles shader downloads and installations required by the preset.

![Preset Selection](../images/downloading-and-installing/rs_preset.webp)

If you don't have a preset to install, you can bypass this step by clicking "Skip" in the preset installation window's bottom right corner.

---

## Installing Shaders

Shaders are essential for enhancing game visuals through ReShade, offering a range of looks tailored by users. The ReShade Installer facilitates easy discovery and installation of these shaders.

Shaders are organized into repositories, displayed during the installation process. You can learn more about each by clicking on the blue-highlighted repository or author names.

![Shader Repository Links](../images/downloading-and-installing/reshade_installer_shader_repo_link_highlight.webp)

To install shaders, simply select the desired repositories and click "Next".

![Shader Repositories Selection](../images/downloading-and-installing/rs_shader.webp)

<details markdown="block" class="details-tree">
<summary>Check Tick</summary>

Selecting a repository with a **check tick** installs all shaders from that repository. Click "Next" to proceed with automatic installation.

![Check Tick Example](../images/downloading-and-installing/reshade_installer_shader_repo_check_tick.webp)

</details>

---

<details markdown="block" class="details-tree">
<summary>Square Tick</summary>

Selecting a repository with a **square tick** lets you choose individual shaders within a repository. After selecting, click "Next" to install.

![Square Tick Selection](../images/downloading-and-installing/reshade_installer_shader_repo_square_tick.webp)

![Individual Shader Selection](../images/downloading-and-installing/rs_shader_select.webp)

</details>

---

## Installing Add-ons (Add-on Support Only)

Add-ons, introduced as a new feature in ReShade, expand customization through the ReShade Add-on API. They're primarily for users interested in exploring advanced features from both previous shader developers and current add-on creators.

Unless you're familiar with what an add-on does, it's recommended to avoid selecting any from the list to prevent potential game instability.

![Selecting Add-ons](../images/downloading-and-installing/rs_addon_select.webp)

---

## Finishing Up

Once the ReShade Installer completes, a confirmation screen will show up. Simply click the "Finish" button at the bottom right of the installer, then launch your game.

![Installation Complete](../images/downloading-and-installing/rs_complete.webp)

Upon successful installation, you'll see a ReShade banner in-game:

![ReShade In-Game Banner](../images/downloading-and-installing/rs_game_banner.webp)

If you don't see this banner, ReShade may not have been injected correctly. Try reinstalling, ensuring all steps are followed precisely.

---

<details markdown="block" class="details-tree">
<summary>Common Issues</summary>

The most frequent problem is selecting the wrong game executable during installation. If you encounter issues, revisit the "Selecting Your Game" section for guidance.

Incorrect Rendering API selection is another common hiccup. If unsure, review the "Selecting the Rendering API" section for more clarity.

Other potential issues include:

  * Game compatibility with ReShade.
  * Missing software dependencies, like the [.NET Framework](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net481-web-installer).
  * Conflicts with other game mods.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Manually Installing ReShade</summary>

## Identifying Game Architecture and Rendering API

If you already know your game's archtecture and Rendering API, you're more than welcome to skip this part of the guide. However, if you are unsure, make sure to navigate to the [PCGamingWiki website](https://www.pcgamingwiki.com/wiki/Home). This website is home to many wiki pages with just about every game that exists on PC.

---

Once at the PCGamingWiki site, use the search bar to navigate the page and find your game.

![Search Bar](../images/downloading-and-installing/pcgw_search.webp)

---

When you've found your specific game, scroll down and locate the API tab within the wiki.

![API Tab](../images/downloading-and-installing/pcgamingwiki_api.webp)

---
 
## Download the ReShade Installer

The next step will be to download the latest ReShade installer from the [official ReShade website](https://reshade.me). The installer holds the ReShade binaries required in order to manually install ReShade.

---

## Download and Install 7Zip

This guide uses 7Zip in order to extract the ReShade binaries from the ReShade Installer. You can download and install the latest `.msi` version from [7Zip's official website](https://www.7-zip.org/download.html).

Keep in mind, that WinRar can serve as an alternative, but this guide utilizes 7Zip for convienence.

---
 
## Extract the ReShade Binary

Once 7Zip is installed, Right-click the ReShade Installer `ReShade_Setup_x.x.x.exe`, and hover over 7Zip, the select the "Open Archive" option.

![Open with 7Zip](../images/downloading-and-installing/reshade_setup_open_with_7zip.webp)

Upon clicking "Open Archive," a new window will appear that holds the two ReShade binaries. One for games with a 32Bit architecture and one for games with a 64bit archtecture.

You can extract the DLL that relates to your game's architecture by draging the file out of the 7Zip window to your Desktop

Below are the two different files that are within hte ReShade Installer:

   * `ReShade64.dll` for 64-Bit

   * `ReShade32.dll` for 32-Bit

   ![Extract DLL](../images/downloading-and-installing/7zip_extract_reshade_binaries.webp)

---
 
## Rename the ReShade Binary

After you've extracted the right binary, right-click the `ReShadeXX.dll` and click "Rename." Afterwards you can rename the binary to the proper graphics injection name for the Rendering API that your game utilizes:

   * `dxgi.dll` - DirectX 10/11/12

   * `d3d12.dll` - DirectX 12

   * `d3d11.dll` - DirectX 11

   * `d3d10.dll` - DirectX 10

   * `d3d9.dll` - DirectX 9

   * `opengl32.dll` - OpenGL

   ![Rename DLL](../images/downloading-and-installing/extacted_reshade_binary_rename.webp)

Keep in mind that if you do not select this graphics injection name properly based off of your game's current Rendering API, ReShade will not inject properly.

---
 
## Move the ReShade Binary

Lastly, you will need to move the renamed DLL into the root folder of your game, the same directory where the game's executable is located.

If you're unsure of your game's executable location, follow [our guide on identifying your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

![Place in Game Folder](../images/downloading-and-installing/place_reshade_binary_game_folder.webp)

Upon completion, your game should launch with ReShade injected!

![Successful Installation](../images/downloading-and-installing/ultrakill_reshade_installed.webp)

</details>

---

<details markdown="block" class="details-tree">
<summary>Manually Injecting ReShade</summary>

Certain games do not support automatic ReShade injection during runtime.<br>This is especially common for UWP (Microsoft Store) games, which often disallow automatic injection. 

Thankfully, Crosire has developed a tool for manual DLL injection into games.

{: .note }
When manually injecting ReShade using Crosire's Inject Tool, you have to manually install shaders as well.

{: .warning} 
Crosire's Inject tool, being an external injector, is more likely to trigger anti-cheat systems. **Use with caution and at your own risk**.

---

## Step 1: Determine your game's architecture

1. Go to [PCGamingWiki](https://www.pcgamingwiki.com/wiki/Home).

2. Enter your game's name in the search bar.

   ![Search Bar](../images/downloading-and-installing/pcgw_search.webp)

3. Proceed to the API section on your game's page (usually located towards the end).

   ![API Section](../images/downloading-and-installing/pcgamingwiki_api.webp)

---

## Step 2: Download the right injector for your game's architexture

Choose the injector based on your game's architecture:

   * [64-bit Injector](https://reshade.me/downloads/inject64.exe)

   * [32-bit Injector](https://reshade.me/downloads/inject32.exe)

---

## Step 3: Download ReShade Installer

Acquire the latest ReShade Installer from the [ReShade website](https://www.reshade.me).

---

## Step 4: Download and install 7Zip

Download and install the latest `.msi` version from [7Zip's official website](https://www.7-zip.org/download.html).

WinRar can serve as an alternative, but this guide utilizes 7Zip.

---

## Step 5: Extract the ReShade binary

1. Right-click the ReShade Installer `ReShade_Setup_x.x.x.exe`, hover over 7Zip, and select "Open Archive."

   ![Open with 7Zip](../images/downloading-and-installing/reshade_setup_open_with_7zip.webp)

2. Extract the desired DLL:

   The DLL architecture should match the injector you've previously downloaded.

   * `ReShade64.dll` for 64-Bit

   * `ReShade32.dll` for 32-Bit

   ![Extract DLL](../images/downloading-and-installing/7zip_extract_reshade_binaries.webp)

---

## Step 6: Position the files properly in your game's folder

Move both the `injectXX.exe` and `ReShadeXX.dll` files to your game directory.

   If you're unsure of your game's executable location, follow [our guide on identifying your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

   ![File Placement](../images/downloading-and-installing/place_reshade_dll_and_inject_in_game_folder.webp)

---

## Step 7: Identify the game process name

1. Launch the desired game.

2. Open Task Manager and right-click on your game under the processes tab, then select "Go to Details."

   ![Go to Details](../images/downloading-and-installing/task_manager_go_to_details.webp)

3. The highlighted executable displays the game's process name.

   ![Executable Name](../images/downloading-and-installing/task_manager_details_view_exe.webp)

---

## Step 8: Inject ReShade

1. Close your game.

2. Navigate to your game's directory and open a command prompt by typing `cmd` into File Explorer's address bar.

   ![Open CMD](../images/downloading-and-installing/cmd_in_file_explorer.webp)

3. Input `inject[x32/x64].exe "name_of_the_process.exe"` and hit Enter.

   ![Inject Command](../images/downloading-and-installing/type_inject_params.webp)

4. Open your game.

   If executed correctly, ReShade should be active once the game begins.

   ![Successful Injection](../images/downloading-and-installing/ultrakill_reshade_installed.webp)

</details>

---

<details markdown="block" class="details-tree">
<summary>Manually Installing Shaders for ReShade</summary>

This guide will go over how to install ReShade shaders manually without having to run the ReShade Installer.

This guide assumes that you already have ReShade installed.

---

## Step 1: Create a reshade-shaders folder

1. Navigate to your game directory.

   If you're unsure of your game's executable location, follow [our guide on identifying your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

2. Create a `reshade-shaders` folder in the same location as your ReShade binary and enter the `reshade-shaders` folder.

   ![Newly Created reshade-shaders Folder](../images/downloading-and-installing/new_reshadeshader_folder.webp)

3. Create two new folders within `reshade-shaders` called:

   * `Shaders`

   * `Textures`

   ![Newly Created Shader and Texture Folders](../images/downloading-and-installing/new_shader_and_textures_folders.webp)

---

## Step 2: Download the shader repository(s) required

This guide will be utilizing the iMMERSE repository on GitHub, however, you can utilize any shader repository for this guide. 

Skip this portion of the guide if you already have the shader repositories already downloaded.

1. Navigate to the GitHub repository of your choice.

2. Click the green "<> Code" button

   ![<> Code Button](../images/downloading-and-installing/github_shader_repo_code_button_highlight.webp)

3. Click the "Download ZIP" button in the "<> Code" dropdown.

   ![Download Zip Button](../images/downloading-and-installing/github_download_zip_button_highlight.webp)

   This will download an archive of the shader repository from that GitHub site.

---

## Step 3: Open the shader repository archive and move the shader files to the proper location

1. Open up the `reshade-shaders` folder that you created in Step 1.

2. Open up the shader repository that you have downloaded in Step 2.

3. Copy the `Shaders` and `Textures` folders from the shader repository archive, and place them into the `reshade-shaders` folder.

   ![Copying Shaders and Textures Folders](../images/downloading-and-installing/c_and_paste_shaders_and_textures_folder.webp)

      If Windows is warning you of files already existing in that location with the names, simply click "Replace the files in the destination."

      ![Merge or Replace Files Prompt](../images/downloading-and-installing/windows_replace_prompt.webp)

   Remember that not every shader repository will have the same structured layout, you might have to dig deeper, collect the shader and texture files manually , or place the shaders and their textures manually within the `reshade-shaders\Shaders` and `reshade-shaders\Textures` folders.

---

## Step 4: Setting ReShade to look in the proper location for shader and texture folders.

1. Launch your game.

2. Open ReShade and navigate to the "Settings" tab.

3. Locate the "Effect Search Path" and "Texture Search Path" arguments.

   If you are starting with a fresh install of ReShade from a manual install, this area should be blank

   ![Shaders and Textures Search Paths Highlight](../images/downloading-and-installing/effect_and_texture_search_paths.webp)

4. Add the following paths to the arguments

   ![Search Paths Example](../images/downloading-and-installing/effect_and_textures_search_path_examples.webp)

   * `.\reshade-shaders\Shaders\**`- Goes in the arguments for "Effect Search Path"

   * `.\reshade-shaders\Textures\**`- Goes in the arguments for "Texture Search Path"

   {: .note }
   
   If you do not have a free slot to add a search path for, you can click the "**+**" icon located directly under the search paths!

5. Switch to the "Home" tab of ReShade, and click the "Reload" button at the bottom.

   Once done, you should see your shaders then pop in the techniques area of the ReShade "Home" tab. 

</details>