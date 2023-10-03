---
title: 32 or 64 Bits 
layout: page
parent: Special and Others
nav_order: 5
---


## Determining the Architecture of an Executable ##

When installing a ReShade Addon or manually adding ReShade to your game, you may come across file names that end with either 32 or 64. This number indicates the architecture for which the addon or ReShade .dll file was designed. If you're unsure which file to install for your game, follow these simple steps to determine if the game is 32 or 64 bits.

1. Open the game you want to check and press Alt+Tab to switch to a different window.

2. Open the Task Manager by pressing Ctrl+Shift+Esc or by right-clicking on the taskbar and selecting "Task Manager".

3. In the Task Manager window, locate the process for the game you're checking. The process name should match the name of the game.

4. Look for the architecture tag next to the process name. If the game has a 32-bit architecture, it should be labeled as (32 Bits). If there is no such tag, it means the game utilizes a 64-bit architecture.

Here's an example screenshot showing the architecture tag in Task Manager:

![Architecture](../images/32-or-64-bits/bits.png)

---
