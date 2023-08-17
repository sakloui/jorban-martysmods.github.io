---
title: Finding your Game's Executable and Game Directory
layout: page
nav_order: 1
parent: Special & Others
---

# Finding your Game's Executable and Game Directory

Each system and user setup is unique, resulting in diverse ReShade installations and behaviors.

If you're having trouble locating your game's executable, here's a step-by-step guide to assist you.

---

<details markdown="block">
<summary>Using Windows Task Manager (PREFERED)</summary>

### Step 1: Accessing Task Manager

1. **Option 1**: Right-click the Windows Taskbar and select "Task Manager".
    ![Taskbar Option](./images/finding_game_executable/right_click_taskbar_global.png) (Windows 11)
    ![Taskbar Option](./images/finding_game_executable/right_click_taskbar_global_win10.png) (Windows 10)

2. **Option 2**: Press `Control + Alt + Delete` simultaneously, then select "Task Manager".

3. **Option 3**: Press `Control + Shift + Escape` simultaneously.

---

### Step 2: Locating the Game's Executable

1. With your game running, switch to Task Manager using `Alt + Tab`.
2. In the "Processes" tab, locate your game, right-click it, then choose `Open file location`.
    ![Find Game](./images/finding_game_executable/processes_task_manager_game_right_click_global.png) (Windows 11)
    ![Find Game](./images/finding_game_executable/processes_task_manager_game_right_click_global_win10.png) (Windows 10)

This will highlight your game's application in File Explorer. 

Here, you can identify both the location and the specific executable of the game.

</details>

---

<details markdown="block">
<summary>Finding the Executable through Steam</summary>

### Step 1: Accessing Game Properties

1. Open Steam and navigate to the "Library" tab.
2. Right-click your desired game (e.g., ULTRAKILL) and select "Properties".
   
   ![Right Click Game](./images/finding_game_executable/right_click_game_steam.png)

---

### Step 2: Navigating to 'Installed Files' 

1. In the properties window, select the `Installed Files` tab on the left.
   
   ![Installed Files](./images/finding_game_executable/click_installed_files_tab_steam.png)

2. Confirm you're on the correct page by checking for the bold `Installed Files` text in the middle of the window.
   
   ![Check Installed Files](./images/finding_game_executable/installed_files_tab_steam.png)

---

### Step 3: Browsing Game Files

1. In the `Installed Files` section, click on the `Browse...` button.
   
   ![Browse Button](./images/finding_game_executable/click_browse_steam.png)

2. A File Explorer window will open, showcasing the game's files. Look for files with the `.exe` extension—those are the game executables.

   ![Find Executable](./images/finding_game_executable/game_file_explorer_steam.png)

{: .note} 
> While this method shows you the game's installation location, it may not always reveal the primary executable, especially if a game has multiple executables.
> 
> It's essential to determine the correct one.

</details>
