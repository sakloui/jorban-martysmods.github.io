---
title: Finding Your Game Executable and Directory
layout: page
nav_order: 1
parent: Special and Others
---

# Finding your Game's Executable and Game Directory

Each system and user setup is unique, resulting in diverse ReShade installations and behaviors.

If you're having trouble locating your game's executable, here's a step-by-step guide to assist you.

---

<details markdown="block" class="details-tree">
<summary>Using Windows Task Manager (PREFERED)</summary>

## **Step 1:** Accessing Task Manager

Pick one of the options below, to open Task Manager:

---

<details markdown="block" class="details-tree">
<summary>Option 1: Windows Taskbar</summary>

Right-click the Windows Taskbar and select "Task Manager".

   Windows 11:<br>![Taskbar Option](../images/finding-your-game-executable-and-directory/right_click_taskbar_global.png)

   Windows 10:<br>![Taskbar Option](../images/finding-your-game-executable-and-directory/right_click_taskbar_global_win10.png)

</details>

---

<details markdown="block" class="details-tree">
<summary>Option 2: Control + Alt + Delete</summary>

Press `Control + Alt + Delete` simultaneously, then select `Task Manager`.

</details>

---

<details markdown="block" class="details-tree">
<summary>Option 3: Control + Shift + Escape</summary>

Press `Control + Shift + Escape` simultaneously.

</details>

---

## **Step 2:** Locating the Game's Executable

1. With your game running, switch to Task Manager.

2. In the `Processes` tab, locate your game, right-click it, then choose `Open file location`.

    Windows 11:<br>![Find Game](../images/finding-your-game-executable-and-directory/processes_task_manager_game_right_click_global.png)

    Windows 10:<br>![Find Game](../images/finding-your-game-executable-and-directory/processes_task_manager_game_right_click_global_win10.png) 

This will highlight your game's application in File Explorer. 

Here, you can identify both the location and the specific executable of the game.

</details>

---

<details markdown="block" class="details-tree">
<summary>Finding the Executable through Steam</summary>

## **Step 1:** Accessing Game Properties

1. Open Steam and navigate to the `Library` tab.

2. Right-click your desired game (e.g., ULTRAKILL) and select `Properties`.
   
   ![Right Click Game](../images/finding-your-game-executable-and-directory/right_click_game_steam.png)

---

## **Step 2:** Navigating to 'Installed Files'

1. In the properties window, select the `Installed Files` tab on the left.

   ![Installed Files](../images/finding-your-game-executable-and-directory/click_installed_files_tab_steam.png)

2. Confirm you're on the correct page by checking for the bold `Installed Files` text in the middle of the window.

   ![Check Installed Files](../images/finding-your-game-executable-and-directory/installed_files_tab_steam.png)

---

## **Step 3:** Browsing Game Files

1. In the `Installed Files` section, click on the `Browse...` button.

   ![Browse Button](../images/finding-your-game-executable-and-directory/click_browse_steam.png)

2. A File Explorer window will open, showcasing the game's files. Look for files with the `.exe` extension — those are the game executables.

   ![Find Executable](../images/finding-your-game-executable-and-directory/game_file_explorer_steam.png)

{: .note} 
> While this method shows you the game's installation location, it may not always reveal the primary executable, especially if a game has multiple executables. 
> It's essential to determine the correct one.


</details>
