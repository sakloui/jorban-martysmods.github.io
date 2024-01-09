---
title: Manual ReShade Installs
layout: default
nav_order: 3
parent: ReShade Guides
---

# ReShade Manual Installation Guides

Some games might not support the standard automated install process of the ReShade Installer due to permission constraints, improper administrative privileges, or even missing user dependencies.

The guides below aim to help users understand and navigate the processes required to manually install ReShade and get past some of these contraints.

---

<details markdown="block" class="details-tree">
<summary>Installing ReShade Manually</summary>

{: .note }
When manually installing ReShade, you have to manually install shaders as well.

## **Step 1:** Identify your game's architecture and API

1. Navigate to [PCGamingWiki](https://www.pcgamingwiki.com/wiki/Home).

2. Use the search bar to find your game.

   ![Search Bar](../images/manual-reshade-installs/pcgw_search.jpg)

3. Locate the API tab on your game's page, typically towards the end.

   ![API Tab](../images/manual-reshade-installs/pcgamingwiki_api.jpg)

---
 
## **Step 2:** Download the ReShade Installer

Download the latest ReShade installer from the [official ReShade website](https://reshade.me).

---

## Step 3: Download and install 7Zip

Download and install the latest `.msi` version from [7Zip's official website](https://www.7-zip.org/download.html).

WinRar can serve as an alternative, but this guide utilizes 7Zip.

---
 
## Step 4: Extract the ReShade binary

1. Right-click the ReShade Installer `ReShade_Setup_x.x.x.exe`, hover over 7Zip, and select "Open Archive."

   ![Open with 7Zip](../images/manual-reshade-installs/reshade_setup_open_with_7zip.jpg)

2. Choose the necessary DLL from the options:

    * `ReShade64.dll` for 64-Bit

    * `ReShade32.dll` for 32-Bit

         ![Extract DLL](../images/manual-reshade-installs/7zip_extract_reshade_binaries.jpg)

---
 
## Step 5: Rename the ReShade binary based off of your game's API

Right-click the `ReShadeXX.dll` you've extracted and choose "Rename." Then, rename it according to your game's rendering API:

   * `dxgi.dll` - DirectX 10/11/12

   * `d3d12.dll` - DirectX 12

   * `d3d11.dll` - DirectX 11

   * `d3d10.dll` - DirectX 10

   * `d3d9.dll` - DirectX 9

   * `opengl32.dll` - OpenGL

   ![Rename DLL](../images/manual-reshade-installs/extacted_reshade_binary_rename.jpg)

---
 
## Step 6: Move the renamed ReShade binary

Position the renamed DLL into the root folder of your game, the same directory where the game's executable is located.

If you're unsure of your game's executable location, follow [our guide on identifying your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/).

![Place in Game Folder](../images/manual-reshade-installs/place_reshade_binary_game_folder.jpg)

Upon completion, your game should launch with ReShade injected!

![Successful Installation](../images/manual-reshade-installs/ultrakill_reshade_installed.jpg)

</details>

------

<details markdown="block" class="details-tree">
<summary>How to Manually Inject ReShade</summary>

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

   ![Search Bar](../images/manual-reshade-installs/pcgw_search.jpg)

3. Proceed to the API section on your game's page (usually located towards the end).

   ![API Section](../images/manual-reshade-installs/pcgamingwiki_api.jpg)

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

   ![Open with 7Zip](../images/manual-reshade-installs/reshade_setup_open_with_7zip.jpg)

2. Extract the desired DLL:

   The DLL architecture should match the injector you've previously downloaded.

   * `ReShade64.dll` for 64-Bit

   * `ReShade32.dll` for 32-Bit

   ![Extract DLL](../images/manual-reshade-installs/7zip_extract_reshade_binaries.jpg)

---

## Step 6: Position the files properly in your game's folder

Move both the `injectXX.exe` and `ReShadeXX.dll` files to your game directory.

   If you're unsure of your game's executable location, follow [our guide on identifying your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/).

   ![File Placement](../images/manual-reshade-installs/place_reshade_dll_and_inject_in_game_folder.jpg)

---

## Step 7: Identify the game process name

1. Launch the desired game.

2. Open Task Manager and right-click on your game under the processes tab, then select "Go to Details."

   ![Go to Details](../images/manual-reshade-installs/task_manager_go_to_details.jpg)

3. The highlighted executable displays the game's process name.

   ![Executable Name](../images/manual-reshade-installs/task_manager_details_view_exe.jpg)

---

## Step 8: Inject ReShade

1. Close your game.

2. Navigate to your game's directory and open a command prompt by typing `cmd` into File Explorer's address bar.

   ![Open CMD](../images/manual-reshade-installs/cmd_in_file_explorer.jpg)

3. Input `inject[x32/x64].exe "name_of_the_process.exe"` and hit Enter.

   ![Inject Command](../images/manual-reshade-installs/type_inject_params.jpg)

4. Open your game.

   If executed correctly, ReShade should be active once the game begins.

   ![Successful Injection](../images/manual-reshade-installs/ultrakill_reshade_installed.jpg)

</details>

---

<details markdown="block">
<summary>Manually Installing Shaders for ReShade</summary>

This guide will go over how to install ReShade shaders manually without having to run the ReShade Installer.

This guide assumes that you already have ReShade installed.

---

## Step 1: Create a reshade-shaders folder

1. Navigate to your game directory.

   If you're unsure of your game's executable location, follow [our guide on identifying your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/).

2. Create a `reshade-shaders` folder in the same location as your ReShade binary and enter the `reshade-shaders` folder.

   ![Newly Created reshade-shaders Folder](../images/manual-reshade-installs/new_reshadeshader_folder.png)

3. Create two new folders within `reshade-shaders` called:

   * `Shaders`

   * `Textures`

   ![Newly Created Shader and Texture Folders](../images/manual-reshade-installs/new_shader_and_textures_folders.png)

---

## Step 2: Download the shader repository(s) required

This guide will be utilizing the iMMERSE repository on GitHub, however, you can utilize any shader repository for this guide. 

Skip this portion of the guide if you already have the shader repositories already downloaded.

1. Navigate to the GitHub repository of your choice.

2. Click the green "<> Code" button

   ![<> Code Button](../images/manual-reshade-installs/github_shader_repo_code_button_highlight.png)

3. Click the "Download ZIP" button in the "<> Code" dropdown.

   ![Download Zip Button](../images/manual-reshade-installs/github_download_zip_button_highlight.png)

   This will download an archive of the shader repository from that GitHub site.

---

## Step 3: Open the shader repository archive and move the shader files to the proper location

1. Open up the `reshade-shaders` folder that you created in Step 1.

2. Open up the shader repository that you have downloaded in Step 2.

3. Copy the `Shaders` and `Textures` folders from the shader repository archive, and place them into the `reshade-shaders` folder.

   ![Copying Shaders and Textures Folders](../images/manual-reshade-installs/c_and_paste_shaders_and_textures_folder.png)

      If Windows is warning you of files already existing in that location with the names, simply click "Replace the files in the destination."

      ![Merge or Replace Files Prompt](../images/manual-reshade-installs/windows_replace_prompt.png)

   Remember that not every shader repository will have the same structured layout, you might have to dig deeper, collect the shader and texture files manually , or place the shaders and their textures manually within the `reshade-shaders\Shaders` and `reshade-shaders\Textures` folders.

---

## Step 4: Setting ReShade to look in the proper location for shader and texture folders.

1. Launch your game.

2. Open ReShade and navigate to the "Settings" tab.

3. Locate the "Effect Search Path" and "Texture Search Path" arguments.

   If you are starting with a fresh install of ReShade from a manual install, this area should be blank

   ![Shaders and Textures Search Paths Highlight](../images/manual-reshade-installs/effect_and_texture_search_paths.png)

4. Add the following paths to the arguments

   * `.\reshade-shaders\Shaders\**`- Goes in the arguments for "Effect Search Path"

   * `.\reshade-shaders\Textures\**`- Goes in the arguments for "Texture Search Path"

      ![Search Paths Example](../images/manual-reshade-installs/effect_and_textures_search_path_examples.png)

   {: .note }
   
   If you do not have a free slot to add a search path for, you can click the "**+**" icon located directly under the search paths!

5. Switch to the "Home" tab of ReShade, and click the "Reload" button at the bottom.

   Once done, you should see your shaders then pop in the techniques area of the ReShade "Home" tab. 

</details>