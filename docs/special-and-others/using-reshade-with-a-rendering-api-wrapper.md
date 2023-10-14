---
title: Using ReShade with a Rendering API Wrapper
layout: page
nav_order: 95
parent: Special and Others
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

Utilize our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) if assistance is required.

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

<details markdown="block" class="details-tree">
<summary>DGVoodoo 2</summary>

Coming soon >:)

</details>
