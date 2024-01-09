---
title: Limiting Your Game's Framerate
layout: page
nav_order: 11
parent: Special & Others
---

# Limiting Your Game's Framerate

A high FPS (Frames Per Second) can sometimes prevent shaders in ReShade from functioning optimally. 

This guide offers multiple methods to help you limit your game's framerate.

---

<details markdown="block" class="details-tree">
<summary>AMD Adrenalin | Driver-Based (For AMD GPU only, Affects All Games)</summary>

Here's how you can use AMD Adrenalin's `Frame rate target control` feature to limit the FPS of your games:

{: .warning}
This impacts all games on your system.

---

### Step 1: Access Adrenalin

- **Easiest Method**: Right-click your desktop and select `AMD Software: Adrenalin Edition`.
  ![Adrenalin from Desktop](./images/limiting_game_fps/amd_desktop_context_menu.jpg)
  
- **Alternative**: Search for `Adrenalin` in the Windows Search Bar.
  ![Adrenalin Search](./images/limiting_game_fps/amd_start_search_software.jpg)

---

### Step 2: Activate "Frame rate target control"

1. Click on `Gaming` in the top bar and select `Graphics`.
   ![Graphics Selection](./images/limiting_game_fps/amd_graphics_gaming_highlight.jpg)
2. In the `Graphics` tab, go to the `Advanced` section and enable `Frame rate target control`.
   ![FRTC Option](./images/limiting_game_fps/amd_enable_frtc.jpg)
3. Adjust the `Max FPS` as per your preference.
   ![Set Max FPS](./images/limiting_game_fps/amd_frtc_tune.jpg)

</details>

---

<details markdown="block" class="details-tree">
<summary>NVIDIA Control Panel | Driver-Based (For NVIDIA GPU only, Affects All Games)</summary>

Here's how to use NVIDIA's Control Panel in order to globally limit the FPS of all your games:

{: .warning}
This impacts all games on your system.

---

### Step 1: Access NVIDIA Control Panel

- **Easiest Method**: Right-click your desktop and select `NVIDIA Control Panel`.
  ![NVIDIA from Desktop](./images/limiting_game_fps/nvidia_desktop_context_menu.jpg)
  
- **Alternative**: Search for `NVIDIA Control Panel` in the Windows Search Bar.
  ![NVIDIA Search](./images/limiting_game_fps/nvidia_start_search_software.jpg)

---

### Step 2: Modify 3D Global Settings

1. On the left, click `Manage 3D Settings`.
   ![Manage 3D Settings](./images/limiting_game_fps/nvidia_manage_3d_settings.jpg)
2. Switch to the `Global Settings` tab.
   ![Global Settings](./images/limiting_game_fps/nvidia_global_settings_tab.jpg)
3. Activate `Max Frame Rate` and select a value between 20 and 1000.
   ![Set Max FPS](./images/limiting_game_fps/nvidia_max_frame_rate.jpg)

</details>

---

<details markdown="block" class="details-tree">
<summary>NVIDIA Control Panel | Driver-Based (For NVIDIA GPU only, Specific Games)</summary>

Here's how to use NVIDIA's Control Panel in order to globally limit the FPS to specific games:

---

### Step 1: Access NVIDIA Control Panel

- **Easiest Method**: Right-click your desktop and choose `NVIDIA Control Panel`.
  ![NVIDIA from Desktop](./images/limiting_game_fps/nvidia_desktop_context_menu.jpg)
  
- **Alternative**: Search for `NVIDIA Control Panel` in the Windows Search Bar.
  ![NVIDIA Search](./images/limiting_game_fps/nvidia_start_search_software.jpg)

---

### Step 2: Modify Per-Game 3D Settings

1. On the left, click `Manage 3D Settings`.
   ![Manage 3D Settings](./images/limiting_game_fps/nvidia_manage_3d_settings.jpg)
2. Navigate to the `Program Settings` tab.
   ![Per Game Settings](./images/limiting_game_fps/nvidia_perapp_settings_tab.jpg)
3. Click `Add` to the right of `Program to customize:`.
   ![Add Game](./images/limiting_game_fps/nvidia_perapp_settings_tab_add.jpg)
4. Choose the game you want to limit.
   ![Select Game](./images/limiting_game_fps/nvidia_perapp_settings_tab_app.jpg)
5. Enable `Max Frame Rate` and choose a value between 20 and 1000.
   ![Set Game-specific Max FPS](./images/limiting_game_fps/nvidia_max_frame_rate_per_app.jpg)

</details>