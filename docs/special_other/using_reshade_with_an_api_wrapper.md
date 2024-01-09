---
title: Using ReShade with a Rendering API Wrapper
layout: page
nav_order: 7
parent: Special & Others
---

# Using ReShade with a Rendering API Wrapper

Rendering API wrappers are powerful tools that can bridge different versions of rendering APIs. 

Commonly, they enable conversion of older APIs (e.g., DirectX 9) into modern ones like Vulkan. 

This can offer benefits like ensuring ReShade shaders compile smoothly or boosting performance in older games.

---

## DXVK: Wrapping DirectX to Vulkan

DXVK is a tool designed to transform DirectX games to run on the Vulkan API. It's especially valuable for adapting older DirectX 9 games to benefit from newer compute shaders incompatible with DX9.

<details markdown="block" class="details-tree">
<summary>Installing DXVK</summary>

### 1. Download DXVK

Acquire the latest DXVK version from [their GitHub releases](https://github.com/doitsujin/dxvk/releases).

### 2. Locate Your Game Directory

For this guide, ULTRAKILL will serve as our example.

* If you're unsure where your game directory is located, please see our guide on [how to locate your game's executable](https://guides.martysmods.com/docs/special_other/finding_your_game_executable.html) for assistance!

### 3. Determine Game's Rendering API & Architecture
Refer to [PCGamingWiki](https://pcgamingwiki.com/) to understand your game's rendering API and architecture.
![Game's API](./images/using_reshade_with_an_api_wrapper/pcgamingwiki_game_api.png)
![Game's Architecture](./images/using_reshade_with_an_api_wrapper/pcgamingwiki_game_api_bit_arch.png)

### 4. Extract DXVK Files

* Unzip the DXVK archive (e.g., `dxvk-2.2.tar.gz`) using a tool like [7zip](https://www.7-zip.org/).

* Within the archive, you'll spot two directories: `x64` and `x32`.
![DXVK Archive](./images/using_reshade_with_an_api_wrapper/dxvk_7zip_arch.png)

Ensure to choose the appropriate architecture based on the details from PCGamingWiki (Step 3).

### 5. Choose the Relevant DXVK DLL

Inside the chosen architecture directory, you'll find multiple files. These correspond to different rendering APIs:

> - **dxgi.dll** - DX11/DX12
> - **d3d11.dll** - DX11
> - **d3d10core.dll** - DX10
> - **d3d9.dll** - DX9

### 6. Transfer the DLL to Game Directory

Ensure the chosen DLL is in the same location as the game's executable.
![Transfer DLL](./images/using_reshade_with_an_api_wrapper/dxvk_install_drag.png)

### 7. Reinstall & Test ReShade

Install ReShade for your game using the Vulkan API and give it a test run. 

If ReShade doesn't display after Vulkan installation, you might have selected an incorrect application or used the wrong architecture/DLL.

</details>

---

<details markdown="block" class="details-tree">
<summary>DGVoodoo 2</summary>

Coming soon >:)

</details>
