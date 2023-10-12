---
title: Finding the Archtecture Type of an Executable
layout: page
parent: Special and Others
nav_order: 97
---

## Finding the Architecture Type of an Executable

When modding with graphics injections, it is crucial to correctly determine the architecture type of your game's executable.

Whether you are a seasoned modder or new to the world of modding, understanding the architecture type is essential for compatibility and proper execution of ReShade and other graphics injections into your game. 

We will explore various techniques and tools that will enable you to identify your application's architecture type with ease.

---

<details markdown="block" class="details-tree">
<summary>Finding the Architecture Type with Task Manager</summary>

1. Open your game, and then `Alt + Tab` to your Desktop.

2. Open Task Manager by pressing `Ctrl + Shift + Esc` or by right-clicking on the taskbar and selecting `Task Manager`.

3. In the Task Manager processes tab, then find your game's executable in the listing. The process name should match the name of the application.

4. Look for the architecture tag next to the process name. 

* 32 Bit: If the application has a 32-bit architecture, it will be labeled as (32 Bits)

 ![Showing Task Manager with Highlight on 32-Bit](../images/finding-the-architecture-type-of-an-executable/hl2-32bit.png)

* 64 Bit: If there is no such tag, it means the application utilizes a 64-bit architecture.

 ![Showing Task Manager with Highlight on No Architecture](../images/finding-the-architecture-type-of-an-executable/ultrakill-32bit.png)

</details>

