---
title: Using ReShade with a Rendering API Wrapper
layout: page
nav_order: 95
parent: Additional Guides
---

# Using ReShade with a Rendering API Wrapper

Rendering API wrappers are powerful tools that can bridge different versions of rendering APIs. 

Commonly, they enable conversion of older APIs (e.g., DirectX 9) into modern ones like Vulkan. 

This can offer benefits like ensuring ReShade shaders compile smoothly or boosting performance in older games.

---

## DXVK: Wrapping DirectX to Vulkan

DXVK is a tool designed to transform DirectX games to run on the Vulkan API. It's especially valuable for adapting older DirectX 9 games to benefit from newer compute shaders incompatible with DX9.

---

<details markdown="block" class="details-tree">
<summary>Installing DXVK</summary>

---

## **Step 1:** Download DXVK

Acquire the latest DXVK version from [their GitHub releases](https://github.com/doitsujin/dxvk/releases).

---

## **Step 2:** Find your game's directory

Utilize our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/) if assistance is required.

---

## **Step 3:** Find your game's architecture and API

Refer to [PCGamingWiki](https://pcgamingwiki.com/) to find your game's rendering API and architecture.

  ![Game's API](../images/using-reshade-with-a-rendering-api-wrapper/pcgamingwiki_game_api.png)

  ![Game's Architecture](../images/using-reshade-with-a-rendering-api-wrapper/pcgamingwiki_game_api_bit_arch.png)

---

## **Step 4:** Extract DXVK's files

Unzip the DXVK archive (e.g., `dxvk-2.2.tar.gz`) using a tool like [7zip](https://www.7-zip.org/).

Within the archive, you'll spot two directories: `x64` and `x32`.

![DXVK Archive](../images/using-reshade-with-a-rendering-api-wrapper/dxvk_7zip_arch.png)

Ensure to navigate into the appropriate architecture folder based on the details that you've collected from PCGamingWiki in the previous step.

---

## **Step 5:** Choose the relevant DXVK DLL file for your game's rendering API

Inside the chosen architecture directory, you'll find multiple files. These correspond to different rendering APIs:

 * dxgi.dll - DX11/DX12

 * d3d11.dll - DX11

 * d3d10core.dll - DX10

 * d3d9.dll - DX9

---

## **Step 6:** Transfer the DLL to your game's root directory

Ensure the chosen DLL is in the same location as the game's executable.

![Transfer DLL](../images/using-reshade-with-a-rendering-api-wrapper/dxvk_install_drag.png)

---

## **Step 7:** Reinstall ReShade and test

Install ReShade for your game using the Vulkan API and give it a test run. 

If ReShade doesn't display after Vulkan installation, you might have selected an incorrect application or used the wrong architecture/DLL.

</details>

---

## dgVoodoo 2: Wrapping 3DFX Glide and Direct3D / DirectX (1 to 9) to DirectX12

DGVoodoo2 is a powerful tool that enables you to enhance older games by wrapping their outdated proprietary renderers from 3DFX and Direct3D (versions 1 to 9) to more modern DirectX equivalents. By doing so, you can unlock the benefits of modern DirectX features for these older titles.

DGVoodoo2 serves two primary purposes. First, it allows older games to leverage advanced features like Compute Shaders, which were not available on older rendering APIs and GPUs. This means you can enjoy improved graphics and performance in these games. Second, DGVoodoo2 helps improve compatibility with modern operating systems, ensuring that these older titles run smoothly and without graphical issues.

---

<details markdown="block" class="details-tree">
<summary>Installing dgVoodoo 2 for 3DFX Glide</summary>

---

## **Step 1:** Download dgVoodoo2

Acquire the latest version of dgVoodoo2 from [dege's website](http://dege.freeweb.hu/dgVoodoo2/dgVoodoo2/). At the time of writing this guide, the latest version is 2.83.1.

---

## **Step 2:** Extract the downloaded files

Extract the files to a location where you can easily find them later. Ensure that you have write permissions for the chosen directory. It is recommended to extract the files to either the "Documents" folder or the "Desktop". As long as you have write permissions for the directory, any location will suffice.

---

## **Step 3:** Locate your game directory

For this example, I'll be using the old Ubisoft game, POD (Planet of Death), which uses the Glide renderer. The instructions are similar for DirectX, but there might be some differences. If you're unsure where your game directory is located, please see our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/) for assistance!

---

## **Step 4:** Locate the game directory within dgVoodoo2

Now that we have our directory and files extracted, it's time to install dgVoodoo2. To prevent issues, we recommend running the tool as Administrator, as we may need to write to folders that require elevated permissions. After opening dgVoodoo2, you'll be greeted with its main window.

![Main Window, General tab](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_main_window.png)

To start installing dgVoodoo2 for your desired game, click on the "Add" button, and then navigate to the game's directory as located before.

![Find Directory Dialogue](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_directory_dialogue.png)

Now that it's done, we can start configuring it. It is not fully installed yet, but we'll leave that for the end.

---

## **Step 5:** Configure the game

To configure dgVoodoo2 for the game, click on the tab that says "Glide". Most of the options are self-explanatory, but it's worth going through some of them and explaining.

![All of the options and buttons on the tab](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_glide_tab.png)

* The first option worth noting is the 3Dfx card option. This tells the game which "GPU" you have, specifying the GPU functions and specs that dgVoodoo2 will simulate. Most games work on default settings, but some may require specific models.

* The second option is the Onboard RAM, which defines how much RAM your "GPU" has. Most games work with 8MB, but if you want to improve graphics on some games, they may require 16MB.

* In the texturing section, most settings can be left as-is. However, if you feel the need to change them, you can adjust the Memory Size and Texturing options. These are useful for defining the Memory Size each mapping unit has and how many of them. Note that only Voodoo3 and onward had variants with different TMUs, so if you plan on using Voodoo2, this isn't required.

* In the Miscellaneous section, you can enable or disable the "3Dfx Watermark" checkbox to show or hide the watermark in the games. This is purely aesthetic.

After configuring all the settings, all that remains is copying the DLL files and running the game.

---

## **Step 6:** Finishing dgVoodoo2 installation

After completing the configuration, it's time to finish the dgVoodoo2 installation. Open two Explorer windows: one for the game directory and another for the dgVoodoo2 directory. In the dgVoodoo2 directory, navigate to the 3dfx folder, select x86, and drag and drop the 3 DLL files to the game directory. Then, run the game, and it should be installed.

That covers the installation process for dgVoodoo2 glide.
![Final Stretch](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_dlls.png)

</details>

---


<details markdown="block" class="details-tree">
<summary>Installing dgVoodoo 2 for DirectX</summary>

---

## **Step 1:** Download dgVoodoo2

Acquire the latest version of dgVoodoo2 from [dege's website](http://dege.freeweb.hu/dgVoodoo2/dgVoodoo2/). At the time of writing this guide, the latest version is 2.83.1.

---

## **Step 2:** Extract the downloaded files

Extract the files to a location where you can easily find them later. Ensure that you have write permissions for the chosen directory. It is recommended to extract the files to either the "Documents" folder or the "Desktop". As long as you have write permissions for the directory, any location will suffice.

---

## **Step 3:** Locate your game directory

For this example, I'll be using the game TrackMania Sunrise, which is an old DirectX 8-9 game. If you're unsure where your game directory is located, please see our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/) for assistance!

---

## **Step 4:** Locate the game directory within dgVoodoo2

Now that we have our directory and files extracted, it's time to install dgVoodoo2. To prevent issues, we recommend running the tool as Administrator, as we may need to write to folders that require elevated permissions. After opening dgVoodoo2, you'll be greeted with its main window.

![Main Window, General tab](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_main_window.png)

To start installing dgVoodoo2 for your desired game, click on the "Add" button, and then navigate to the game's directory as located before.

![Find Directory Dialogue](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_directory_dialogue.png)

Now that it's done, we can start configuring it. It is not fully installed yet, but we'll leave that for the end.

---

## **Step 5:** Configure the game

To configure dgVoodoo2 for the game, click on the tab that says "DirectX". Most of the options are self-explanatory, but it's worth going through some of them and explaining.

![All of the options and buttons on the tab](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_dx_tab.png)

* The Videocard option is the card that dgVoodoo2 will be emulating. Some games require specific brands for features, but most of the time, the dgVoodoo 3D Virtual accelerated card will work just fine. Set it to the maximum VRAM you have available.

* In the Miscellaneous section, make sure to disable the checkbox with "dgVoodoo watermark". This will remove the watermark on the lower-right of the screen.

After configuring all the settings, all that remains is copying the DLL files and running the game.

---

## **Step 6:** Finishing the dgVoodoo2 installation

After completing the configuration, it's time to finish the dgVoodoo2 installation. Open two Explorer windows: one for the game directory and another for the dgVoodoo2 directory. In the dgVoodoo2 directory, navigate to the MS folder. Take note of which DLLs to move on a game-to-game basis:

* If it's a Direct3D (1 to 7) game, the DLLs are: D3DImm.dll and DDraw.dll.

* If it's a DirectX 8 game, the DLL is: D3D8.dll.

* If it's a DirectX 9 game, the DLL is: D3D9.dll.

If you are unsure about which DLL to use, check the [PCGamingWiki](https://pcgamingwiki.com/) page for the game to determine its architecture and DirectX version.

That covers the installation process for dgVoodoo2 for DirectX.
![Final Stretch](../images/using-reshade-with-a-rendering-api-wrapper/dgvoodoo2_dx_dlls.png)

</details>

