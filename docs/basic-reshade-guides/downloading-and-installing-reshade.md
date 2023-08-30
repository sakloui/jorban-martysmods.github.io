---
title: Downloading and Installing ReShade
layout: page
parent: Basic ReShade Guides
nav_order: 1
---

# Downloading and Installing ReShade

![ReShade Logo](../images/rs_gradiant.png){: style="max-width:17%" }

ReShade is an advanced and customizable post-processing injector designed to enhance the visual aesthetics of video games. It operates by interfacing directly with the game's rendering API, thereby offering a wide range of visual effects, including but not limited to depth of field, color correction, and ambient occlusion.

ReShade is highly compatible and works well with most games, including those utilizing DirectX (versions 9 to 12), OpenGL, and Vulkan.

These guides will walk you through the downloading and installing procedures of ReShade so that you can easily customize your game, the way that you want.

---

<details markdown="block" class="details-tree">
<summary>Downloading the ReShade Installer</summary>

First, visit the [official ReShade website](https://reshade.me/#download) and scroll down to the very bottom.

<video id="rs_scroll.webm" autoplay muted loop style="max-width:55%" src="../images/downloading-and-installing-reshade/rs_scroll.webm" type="video/webm"></video>

<script type="text/javascript">

  /* play video twice as fast */
  document.getElementById("rs_scroll.webm").defaultPlaybackRate = 2.0;

</script>

Once at the bottom, you'll find two distinct ReShade builds.

Below will be information to help you familiarize yourself with which build to choose for your games:

{: .warning }
Only download ReShade from offical sources to avoid malicious files and potential threats!

---

<details markdown="block" class="details-tree">
<summary>Standard ReShade Build (Download ReShade x.x.x)</summary>

The Standard ReShade Build is tailored for online games with strict anti-cheat mechanisms. 

If you're an avid player of online games like Dead by Daylight, PUBG, or Apex Legends, this build is for you.

However, to ensure compatibility with online games, this build limits some advanced features, such as disabling add-ons when a network connection is detected in your game.

This measure prevents misuse of ReShade for cheating or code injection.

</details>

---

<details markdown="block" class="details-tree">
<summary>Full Add-On Support ReShade Build (Download ReShade x.x.x with full add-on support)</summary>

The Full Add-on Support ReShade Build is ideal for offline games or online games that lack robust anti-cheat systems.

If you enjoy games like Final Fantasy XXIV, World of Warcraft, or Baldur's Gate 3, this is the ReShade build for you!

This build supports the full array of ReShade's features and add-ons, offering maximum creative freedom. It allows users to inject a wide range of enhancements into their game, including depth-based shaders like iMMERSE MXAO, iMMERSE Pro RTGI, or StageDepthPlus.

However, remember that using this version of ReShade in online games with anti-cheat solutions can lead to bans. While typically you'll receive a warning before a ban, some systems may enforce immediate bans, so caution is advised!

{: .warning }
Using shaders or add-ons to gain an unfair advantage in games can lead to bans. Always respect the game rules, and expect bans for bypassing these rules by any means!

</details>

</details>

---

<details markdown="block" class="details-tree">
<summary>How to Use the ReShade Installer</summary>

After downloading the right build of ReShade, the information below will help you to use the ReShade Installer.

---

<details markdown="block" class="details-tree">
<summary>Choosing Your Game</summary>

Launch the ReShade installer that you've downloaded previously. 

Once open, You'll be asked to select a game or application to install ReShade to:

![Game List](../images/downloading-and-installing-reshade/rs_game_list.png)

If your game doesn't appear in the game or applicaiton selection menu, you can manually browse for your game by clicking the `Browse...` button at the bottom right hand side of the page.

![Browse](../images/downloading-and-installing-reshade/rs_browse.png)

The browse function lets you pinpoint the executable you want to install ReShade to. This is particularly useful for games from platforms like itch.io, classic games, or emulators like DOSBox and Dolphin.

  * If you are having trouble finding the proper location for your game directory or executable, check out our guide on [finding your game directory and executable](https://guides.martysmods.com/docs/special-and-others/finding-your-game-executable-and-directory/) for help!

</details>

---

<details markdown="block" class="details-tree">
<summary>Choosing the Rendering API</summary>

Rendering APIs like DirectX, Vulkan, or OpenGL are tools that developers use to communicate with your computer hardware for drawing and presenting visuals on screen.

Each game uses a specific rendering API, so it's vital to select the correct one for ReShade to inject properly!

If you're not sure about your game's rendering API, resources like the [PCGamingWiki](https://pcgamingwiki.com) can be a great help! 

However, if you want to guess your game's API, here are some general guidelines:

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

ReShade presets are `.ini` configuration files that users have set up in order to share their customizations to others. These configurations can hold shader load orders, hotkeys, and specific arguments!

Fortunately, installing presets has been made simple with the ReShade Installer, as shaders used by presets will be automatically selected, download, and installed. This removes all the guesswork from ReShade's users, making things much easier than manually installing them.

To install a preset, hit the `Browse...` button in the installer and then select your preset. 

![Preset Image](../images/downloading-and-installing-reshade/rs_preset.png)

If you do not have a preset, you can skip this portion of the installer by clicking `Next` in the bottom right hand corner.

{: .note }
If your preset requires unique shaders and textures outside the installer's offerings, you may need to install them manually.

</details>

---

<details markdown="block" class="details-tree">
<summary>Installing Shaders Using the ReShade Installer</summary>

Shaders are the backbone of ReShade's flexibility and power, enabling users to create unique visual experiences for each game. However, finding and sourcing shader repositories can be tricky as Shader Developers can have differing storage and update methods from others. The ReShade Installer seeks to simplify this for it's users by presenting known, and working, shaders in the installer.

![ReShade Shader Repositories Selection Image](../images/downloading-and-installing-reshade/rs_shader.png){: style="max-width:30%" }

{: .note }
If you've chosen to install a preset with the preset installation page of the ReShade Installer, the necessary shaders will be pre-selected in this section.

---

The two different ways that you can mark shader repositories to be downloaded and installed through the ReShade installer:

  * A **check tick** installs all shaders from each selected repository. Clicking `Next` will install everything for you automatically.

    ![ReShade Shader Repo Check Tick](../images/downloading-and-installing-reshade/reshade_installer_shader_repo_check_tick.png)
  
  * A **square tick** allows you to individually pick which shaders from each selected repository.

    ![ReShade Shader Repo Square Tick](../images/downloading-and-installing-reshade/reshade_installer_shader_repo_square_tick.png)

      {: .note }
      > Choosing the square tick for any shader repositories will bring up a menu to select the specific shaders from the repository marked. 
      > ![ReShade Square Tick Shader Selection Image](../images/downloading-and-installing-reshade/rs_shader_select.png){: style="max-width:30%" }
      > From here, select your preferred shaders and click `Next` to continue.

---

For information about Shader Developers and their repositories, you can click on the blue-highlighted repository or author names. Doing so will take you to their online repository, which often contains detailed shader information and descriptions useful for users.

![ReShade Shader Repo Link Highlight](../images/downloading-and-installing-reshade/reshade_installer_shader_repo_link_highlight.jpg)

</details>

---

<details markdown="block" class="details-tree">
<summary>Finishing the Installation Process</summary>

Once the ReShade Installer has finished, a confirmation screen will show a successful installation.

At this point, you can click `Finish` in the ReShade installer and start your game.

  ![ReShade Complete Image](../images/downloading-and-installing-reshade/rs_complete.png)

If ReShade has been installed correctly, ReShade will show an in-game banner:

  ![ReShade Game Banner Image](../images/downloading-and-installing-reshade/rs_game_banner.png)

If ReShade is not presenting this banner, it hasn't injected into your game. 

</details>

---

<details markdown="block" class="details-tree">
<summary>Common Issues After Installing</summary>

### Common Issues

The most common issue that prevents ReShade from injecting is selecting the wrong API or executable/program when prompted in the ReShade installer. However, other issues can occur, such as:

  * The game not allowing ReShade.
  
  * The user not having the proper dependancies [(.NET Framework)](https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net481-web-installer).

  * Conflicting modifications.



