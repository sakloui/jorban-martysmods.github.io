---
title: ReShade Manual Installations
layout: default
nav_order: 1
parent: Advanced ReShade Guides
---
# ReShade Manual Installation Guides

Some games might not support direct installation through the ReShade Installer due to permission constraints, administrative prompts, or even missing user dependencies.

This guide aims to help users understand and navigate the process of manual installation, ensuring they can seamlessly integrate ReShade into their desired game.

---

<details markdown="block" class="details-tree">
<summary>Installing ReShade Manually</summary>

## Step 1: Identify Your Game's Architecture

1. Navigate to [PCGamingWiki](https://www.pcgamingwiki.com/wiki/Home).
2. Use the search bar to find your game.
   ![Search Bar](./images/manually_injecting_reshade/pcgw_search.jpg)
3. Locate the API tab on your game's page, typically towards the end.
   ![API Tab](./images/manually_injecting_reshade/pcgamingwiki_api.jpg)

---
 
## Step 2: Obtain ReShade Installer

- Download the latest ReShade installer from the [official ReShade website](https://reshade.me).

---

## Step 3: Get `7Zip`

1. Download and install the latest `.msi` version of `7Zip` from [7Zip's official website](https://www.7-zip.org/download.html).
   ![7Zip Download](./images/manually_installing_reshade/7zip_website_download.jpg)

   {: .note} 
   While WinRar can be an alternative, this guide focuses on using `7Zip`.

---
 
## Step 4: Extract ReShade Binary

1. Right-click on the ReShade Installer `ReShade_Setup_x.x.x.exe`, hover over `7Zip`, and select `Open Archive`.
   ![Open with 7Zip](./images/manually_installing_reshade/reshade_setup_open_with_7zip.jpg)
2. Choose the necessary DLL from the options:
>    - `ReShade64.dll` for 64-Bit
>    - `ReShade32.dll` for 32-Bit
   ![Extract DLL](./images/manually_installing_reshade/7zip_extract_reshade_binaries.jpg)

---
 
## Step 5: Rename the Binary

Right-click the `ReShadeXX.dll` you've extracted and choose `Rename`. Then, rename it according to your game's rendering API:

> - **dxgi.dll** - DirectX 10/11/12
> - **d3d12.dll** - DirectX 12
> - **d3d11.dll** - DirectX 11
> - **d3d10.dll** - DirectX 10
> - **d3d9.dll** - DirectX 9
> - **opengl32.dll** - OpenGL

![Rename DLL](./images/manually_installing_reshade/extacted_reshade_binary_rename.jpg)

---
 
## Step 6: Move the Renamed DLL

1. Position the renamed DLL into the root folder of your game, the same directory where the game's executable is located.
   ![Place in Game Folder](./images/manually_installing_reshade/place_reshade_binary_game_folder.jpg)

2. If unsure of your game's executable location, consult [our guide on identifying your game's executable](https://guides.martysmods.com/docs/special_other/finding_your_game_executable.html).

Upon completion, your game should launch with ReShade already integrated!
![Successful Installation](./images/manually_injecting_reshade/ultrakill_reshade_installed.jpg)

</details>

------

<details markdown="block" class="details-tree">
<summary>How to Manually Inject ReShade</summary>

Certain games do not support automatic ReShade injection during runtime. 
This is especially common for UWP (Microsoft Store) games, which often disallow automatic injection. 

Thankfully, Crosire has developed a tool for manual DLL injection into games.

{: .warning} 
Crosire's Inject tool, being an external injector, is more likely to trigger anti-cheat systems. **Use with caution and at your own risk**.

## Step 1: Determine Your Game's Architecture

1. Go to [PCGamingWiki](https://www.pcgamingwiki.com/wiki/Home).
2. Enter your game's name in the search bar.
   ![Search Bar](./images/manually_injecting_reshade/pcgw_search.jpg)
3. Proceed to the API section on your game's page (usually located towards the end).
   ![API Section](./images/manually_injecting_reshade/pcgamingwiki_api.jpg)

---

## Step 2: Download the Right Injector

Choose the injector based on your game's architecture:
* [64-bit Injector](https://reshade.me/downloads/inject64.exe)
* [32-bit Injector](https://reshade.me/downloads/inject32.exe)

---

## Step 3: Download ReShade Installer

Acquire the latest ReShade Installer from the [ReShade website](https://www.reshade.me).

---

## Step 4: Get `7Zip`

1. Download and install the latest `.msi` version from [7Zip's official website](https://www.7-zip.org/download.html).
   ![7Zip Download](./images/manually_installing_reshade/7zip_website_download.jpg)

{: .note} 
`WinRar` can serve as an alternative, but this guide utilizes `7Zip`.

---

## Step 5: Extract ReShade Binary

1. Right-click the ReShade Installer `ReShade_Setup_x.x.x.exe`, hover over `7Zip`, and select `Open Archive`.
   ![Open with 7Zip](./images/manually_installing_reshade/reshade_setup_open_with_7zip.jpg)
2. Extract the desired DLL:
   - `ReShade64.dll` for 64-Bit
   - `ReShade32.dll` for 32-Bit
   ![Extract DLL](./images/manually_installing_reshade/7zip_extract_reshade_binaries.jpg)

{: .note}
The DLL architecture should match the injector you've previously downloaded.

---

## Step 6: Position the Files

Move both the `injectXX.exe` and `ReShadeXX.dll` files to your game directory.
![File Placement](./images/manually_injecting_reshade/place_reshade_dll_and_inject_in_game_folder.jpg)

For assistance locating your game directory, see [our guide on finding your game's executable](https://guides.martysmods.com/docs/special_other/finding_your_game_executable.html).

---

## Step 7: Identify the Game Process Name

1. Launch the desired game.
2. Open Task Manager and right-click on your game under the processes tab, then select `Go to Details`.
   ![Go to Details](./images/manually_injecting_reshade/task_manager_go_to_details.jpg)
3. The highlighted executable displays the game's process name.
   ![Executable Name](./images/manually_injecting_reshade/task_manager_details_view_exe.jpg)

---

## Step 8: Inject ReShade

1. Close your game.
2. Navigate to your game's directory and open a command prompt by typing `CMD` into File Explorer's address bar.
   ![Open CMD](./images/manually_injecting_reshade/cmd_in_file_explorer.jpg)
3. Input `inject[x32/x64].exe "name_of_the_process.exe"` and hit Enter.
   ![Inject Command](./images/manually_injecting_reshade/type_inject_params.jpg)
4. Open your game.

If executed correctly, ReShade should be active once the game begins.
![Successful Injection](./images/manually_injecting_reshade/ultrakill_reshade_installed.jpg)

</details>
