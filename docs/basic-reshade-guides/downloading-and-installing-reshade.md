---
title: Downloading and Installing ReShade
layout: page
parent: Basic ReShade Guides
nav_order: 1
---

# Downloading and Installing ReShade

![ReShade Logo](../images/rs_gradiant.png){: style="max-width:17%" }

ReShade is a post-processing injector for enhancing video game visuals. It interfaces with the game's rendering API for effects like depth of field and color correction. Compatible with most games and APIs like DirectX, OpenGL, and Vulkan, the guides below detail its installation and customization process.

These guides below will walk you through the downloading and installing procedures of ReShade so that you can easily customize your game, the way that you want.

---

<details markdown="block" class="details-tree">
<summary>Downloading the ReShade Installer</summary>

[Visit the official ReShade website](https://reshade.me/#download) and scroll to the bottom.

<video id="rs_scroll.webm" autoplay muted loop style="max-width:55%" src="../images/downloading-and-installing-reshade/rs_scroll.webm" type="video/webm"></video>

{: .warning }
Download ReShade only from official sources to avoid threats and shady software!

You'll find two ReShade builds at the bottom. The information below will guide you on the right build for your games.

---

<details markdown="block" class="details-tree">
<summary>Standard ReShade Build (Download ReShade x.x.x)</summary>

The Standard ReShade Build is tailored for online games with strict anti-cheat mechanisms. 

If you're an avid player of online games like Dead by Daylight, PUBG, or Apex Legends, this is the build to use. However, to ensure compatibility with online games, this build limits some advanced features, like add-ons when a network connection is detected. This measure exists to prevent misuse of ReShade for cheating!

</details>

---

<details markdown="block" class="details-tree">
<summary>Full Add-On Support ReShade Build (Download ReShade x.x.x with full add-on support)</summary>

The Full Add-on Support ReShade Build is for offline games or games without a robust anti-cheat system.

If you play games like Final Fantasy XXIV, World of Warcraft, or Baldur's Gate 3, this is the build to use. 

This build supports the full array of ReShade's features and add-ons, offering total freedom, and allowing users to create presets using a wide range of shaders and add-ons, including depth-based shaders like iMMERSE MXAO, iMMERSE Pro RTGI, or StageDepthPlus.

{: .warning }
Using this build of ReShade in online games with anti-cheat solutions can lead to bans. Always respect the game rules, and expect bans for bypassing these rules by any means!

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>How to Use the ReShade Installer</summary>

After downloading the right build of ReShade, the information below will help you to use the ReShade Installer.

---

<details markdown="block" class="details-tree">
<summary>Choosing Your Game</summary>

Run the ReShade installer.

Select a game or application for ReShade installation:

![Game List](../images/downloading-and-installing-reshade/rs_game_list.png)

If your game isn't listed, click `Browse...` at the bottom right to manually locate it.

![Browse](../images/downloading-and-installing-reshade/rs_browse.png)

This is useful for games from platforms like itch.io, classic games, or emulators like DOSBox and Dolphin.

  * If you need help finding your game directory or executable, check out [our guide here](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/).

</details>

---

<details markdown="block" class="details-tree">
<summary>Choosing the Rendering API</summary>

Rendering APIs (DirectX, Vulkan, OpenGL) are used by developers to display visuals on screen, and each game uses a specific API, which must be correctly selected for ReShade to work!

  * Not sure about your game's API? Check [PCGamingWiki](https://pcgamingwiki.com).

If you want to guess, however, here are some guidelines for what to choose:


---

<details markdown="block" class="details-tree">
<summary>DirectX 9</summary>

![DirectX 9](../images/downloading-and-installing-reshade/rs_dx9.png)

DirectX 9 was widely used from 2005 to 2012. There are many DirectX 9 titles that you can inject ReShade into - however, most modern games are likely to use other rendering APIs.

</details>

---

<details markdown="block" class="details-tree">
<summary>DirectX 10-12</summary>

![DirectX 10-12](../images/downloading-and-installing-reshade/rs_dx10_11_12.png)

DirectX 10-12 is common in engines like Unity and Unreal Engine. It's the go-to choice for most modern games and is the standard for many graphics developers.

</details>

---

<details markdown="block" class="details-tree">
<summary>OpenGL</summary>

![OpenGL](../images/downloading-and-installing-reshade/rs_ogl.png)

OpenGL is used by certain engines and older games. If DirectX isn't an option and your game isn't extremely old, OpenGL is probably the way to go.

</details>

---

<details markdown="block" class="details-tree">
<summary>Vulkan</summary>

![Vulkan](../images/downloading-and-installing-reshade/rs_vk.png)

Vulkan is popular in modern emulators and some newer game releases. For Linux users (using Wine or Proton), Vulkan is a must.

{: .important }
Vulkan installations require admin permissions due to certain system-level changes. Denying this might prevent ReShade from installing.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Installing Presets</summary>

ReShade presets are `.ini` files containing user customizations like shader load orders, hotkeys, and specific arguments.

The ReShade Installer simplifies preset installation by automatically selecting, downloading, and installing the shaders used by presets.

To install a preset, click `Browse...` in the installer and select your preset. 

![Preset Image](../images/downloading-and-installing-reshade/rs_preset.png)

No preset? Just click `Next` to skip this step.

{: .note }
Presets requiring unique shaders and textures, not in the installer, need manual installation.

</details>

---

<details markdown="block" class="details-tree">
<summary>Installing Shaders Using the ReShade Installer</summary>

ReShade shaders enhance game visuals, and are the backbone of customizations for each user. The ReShade Installer makes finding and installing these shaders easy by listing known and working repositories.

Below is the shader installation section of the ReShade Installer. Select the repositories you want and click `Next`.

![ReShade Shader Repositories Selection Image](../images/downloading-and-installing-reshade/rs_shader.png){: style="max-width:30%" }

If you've selected a preset, necessary shaders will be pre-selected here.

---

If you want more information on the repository or Shader Developer, click on blue-highlighted repository or author names for more details.

![ReShade Shader Repo Link Highlight](../images/downloading-and-installing-reshade/reshade_installer_shader_repo_link_highlight.jpg)

---

### Below are the two different ways to mark shader repositories to be downloaded:

<details markdown="block" class="details-tree">
<summary>Check Tick</summary>

* A **check tick** installs all shaders from each selected repository. Clicking `Next` will install everything for you automatically.

  ![ReShade Shader Repo Check Tick](../images/downloading-and-installing-reshade/reshade_installer_shader_repo_check_tick.png)

</details>

---

<details markdown="block" class="details-tree">
<summary>Square Tick</summary>

* A **square tick** allows you to individually pick which shaders from each selected repository.

  ![ReShade Shader Repo Square Tick](../images/downloading-and-installing-reshade/reshade_installer_shader_repo_square_tick.png)

    {: .note }
    > Choosing the square tick for any shader repositories will bring up a menu to select the specific shaders from the repository marked. 
    > ![ReShade Square Tick Shader Selection Image](../images/downloading-and-installing-reshade/rs_shader_select.png){: style="max-width:30%" }
    > Select your preferred shaders and click `Next` to continue.

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>Finishing the Installation Process</summary>

After the ReShade Installer finishes, a confirmation screen appears. Click `Finish` and start your game.

![ReShade Complete Image](../images/downloading-and-installing-reshade/rs_complete.png)

If ReShade is installed correctly, ReShade displays an in-game banner:

![ReShade Game Banner Image](../images/downloading-and-installing-reshade/rs_game_banner.png)

If no banner is shown, that means ReShade didn't inject into your game.

</details>

---

<details markdown="block" class="details-tree">
<summary>Common Issues After Installing</summary>

### Common Problems

ReShade may fail to inject if you select the wrong API or program in the installer. 

Other issues include:

  * Game not supporting ReShade.
  
  * Missing dependencies [(like .NET Framework)](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net481-web-installer).
  
  * Conflicting mods.

