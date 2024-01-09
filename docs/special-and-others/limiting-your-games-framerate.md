---
title: Limiting Your Game's Framerate
layout: page
nav_order: 4
parent: Special and Others
---

# How to Limit Your Game's Framerate

High FPS (Frames Per Second) can sometimes interfere with the optimal functioning of shaders in ReShade. This guide provides several methods to limit your game's framerate.

---

<details markdown="block" class="details-tree">
<summary>AMD Adrenalin | Driver-Based (For AMD GPU only, Affects All Games)</summary>

You can use AMD Adrenalin's `Frame rate target control` feature to limit the FPS of your games:

{: .warning}
Note: This will affect all games on your system.

---

## **Step 1:** Open Adrenalin

- **Quick Access**: Right-click your desktop and select `AMD Software: Adrenalin Edition`.

  ![Adrenalin from Desktop](../images/limiting-your-games-framerate/amd_desktop_context_menu.jpg)
  
- **Alternative Access**: Use the Windows Search Bar to find `Adrenalin`.

  ![Adrenalin Search](../images/limiting-your-games-framerate/amd_start_search_software.jpg)

---

## **Step 2:** Enable "Frame rate target control"

1. Navigate to `Gaming` in the top bar and select `Graphics`.

   ![Graphics Selection](../images/limiting-your-games-framerate/amd_graphics_gaming_highlight.jpg)

2. In the `Graphics` tab, go to the `Advanced` section and turn on `Frame rate target control`.

   ![FRTC Option](../images/limiting-your-games-framerate/amd_enable_frtc.jpg)

3. Adjust the `Max FPS` according to your needs.

   ![Set Max FPS](../images/limiting-your-games-framerate/amd_frtc_tune.jpg)

</details>

---

<details markdown="block" class="details-tree">
<summary>NVIDIA Control Panel | Driver-Based (For NVIDIA GPU only, Affects All Games)</summary>

You can use NVIDIA's Control Panel to globally limit the FPS of all your games:

{: .warning}
Note: This will affect all games on your system.

---

## **Step 1:** Open NVIDIA Control Panel

- **Quick Access**: Right-click your desktop and select `NVIDIA Control Panel`.

  ![NVIDIA from Desktop](../images/limiting-your-games-framerate/nvidia_desktop_context_menu.jpg)
  
- **Alternative Access**: Use the Windows Search Bar to find `NVIDIA Control Panel`.

  ![NVIDIA Search](../images/limiting-your-games-framerate/nvidia_start_search_software.jpg)

---

## **Step 2:** Adjust 3D Global Settings

1. On the left panel, select `Manage 3D Settings`.

   ![Manage 3D Settings](../images/limiting-your-games-framerate/nvidia_manage_3d_settings.jpg)

2. Switch to the `Global Settings` tab.

   ![Global Settings](../images/limiting-your-games-framerate/nvidia_global_settings_tab.jpg)

3. Enable `Max Frame Rate` and select a value between 20 and 1000.

   ![Set Max FPS](../images/limiting-your-games-framerate/nvidia_max_frame_rate.jpg)

</details>

---

<details markdown="block" class="details-tree">
<summary>NVIDIA Control Panel | Driver-Based (For NVIDIA GPU only, Specific Games)</summary>

You can use NVIDIA's Control Panel to limit the FPS for specific games:

---

## **Step 1:** Open NVIDIA Control Panel

- **Quick Access**: Right-click your desktop and choose `NVIDIA Control Panel`.

  ![NVIDIA from Desktop](../images/limiting-your-games-framerate/nvidia_desktop_context_menu.jpg)

  
- **Alternative Access**: Use the Windows Search Bar to find `NVIDIA Control Panel`.

  ![NVIDIA Search](../images/limiting-your-games-framerate/nvidia_start_search_software.jpg)

---

## **Step 2:** Adjust Per-Game 3D Settings

1. On the left panel, select `Manage 3D Settings`.

   ![Manage 3D Settings](../images/limiting-your-games-framerate/nvidia_manage_3d_settings.jpg)

2. Navigate to the `Program Settings` tab.

   ![Per Game Settings](../images/limiting-your-games-framerate/nvidia_perapp_settings_tab.jpg)

3. Click `Add` next to `Program to customize:`.

   ![Add Game](../images/limiting-your-games-framerate/nvidia_perapp_settings_tab_add.jpg)

4. Select the game you want to limit.

   ![Select Game](../images/limiting-your-games-framerate/nvidia_perapp_settings_tab_app.jpg)

5. Enable `Max Frame Rate` and choose a value between 20 and 1000.

   ![Set Game-specific Max FPS](../images/limiting-your-games-framerate/nvidia_max_frame_rate_per_app.jpg)

</details>