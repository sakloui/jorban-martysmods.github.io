---
title: Setting Up User File Permissions
layout: page
parent: Special & Others
---

# Windows File Permisions

Often times, users will have their games installed in locations such as `Program Files (x86)`.

This is not inherently a bad thing, as it's a solid organizational technique to keep programs all within the same folder, or the user can have control over due to the installer that they have chosen to install the game from.

However, sometimes folders like these can cause issues for users, as they are generally locked down by the installer (such as Steam, EAPlay/Origin, Ubisoft Connect, or GOG Galaxy), and prevent ReShade from being able to read or write to specific files that it needs.

This guide will go over how to transfer folder, and the files within them, permissions over to your own user, so that ReShade can be given both read and write access to the files it needs.

{: .warning }
This method will only work for NTFS formatted drives. If you have any other drive formatting, you will not see a `Security` tab in the `Folder Properties` window.

---

### Step 1: Locate the Game Directory

{: .warning }
Before starting, ensure that your game is closed and that no files are open!

The game directory should always be displayed in the error for file permissions.
Utilize this in order to navigate towards the location that you are going to need to edit.

If you are having a hard time with finding the directory of your game, please utilize our guide on [how to find your game directory](https://guides.martysmods.com/docs/special_other/finding_your_game_executable.html).

---

### Step 2: Enter the Properties of the Root Folder for Your Game

Lets use FFXIV as an example here:

Normally the game executable is within the folder `game`. Which would not be the root directory for FFIXV. Instead it would be `FINAL FANTASY XIV – A Realm Reborn\game`.

So you want to right click the folder called `FINAL FANTASY XIV – A Realm Reborn` **INSTEAD OF** `game`.

Once you've found the proper folder and right clicked it, click `Properties`.

---

### Step 3: Navigate to the Security Tab

Within the `Folder Properties` window that has opened up, there should be a few tabs.

The tab you want to select is called `Security`.

This will bring you to a quite confusing tab for most beginners, but this guide will walk you through every step that you would need in order to solve your issue.

---

### Step 4: Click `Advanced`

On the bottom right hand corner of the `Security` tab, there will be an `Advanced` button.

Click that, and a new window should open. This window is the `Advanced Security Settings` window, and will be home to all of the more advanced user settings for folders.

---

### Step 5: Change the Owner of the Folder

Towards the top of the `Advanced Security Settings` window, there will be two arguments:
* Name:
* Owner:

These two arguments give you vital information, such as the folder that you are changing the security settings of, as well as the owner of this directory.

You should have a blue option with a shield that says `Change` - click it.

---

### Step 6: Changing the Owner of a Directory

Once you have clicked the blue `Change` button, a new window will appear with the title `Select User or Group`.

On the top right hand corner of the `Select User or Group` window, select `Object Types`.

This will open a menu that gives you a few options for you to tick on and off.

You want to only have `Users` ticked within this option - as it will help you later on in order to find your user!

Once you only have `Users` checked in the new window, click `OK` at the bottom right hand corner - this will take you back to the `Select User or Group` window.

Now, click `Advanced` on the bottom left hand corner of the `Select User or Group` window - this will bring you to the `Select User or Group (Advanced)` window.

This is where we are going to select your user to become the owner of your game's file directory.

Click `Find Now` on the right hand side of the `Select User or Group (Advanced)` window - this will populate the bottom with all of the users that are on your system.

Here you should see your computer's user name. This username will be identical to the one that shows in your Start Menu and Windows Settings > Account window.

Double click your user!

That will have filled in the location of your user within the `Select User or Group` window. If you have a prompt under `Enter the object name to select (examples):` text portion. You have likely done this process right.

Ensure that the prompt that was entered in that portion is also underlined, that means that the prompt is aware that this is an actual user on your system.

Simply click `OK` in the bottom right hand corner of the `Select User or Group` window.

---

### Step 7: Check `Replace owner on subcontainers and ojects`

Once you have clicked `OK`, you will be ported back to the `Advanced Security Settings` window. This is normal.

You should see a new setting appear for you to toggle that you might not remember before.

This part is vital to ensure that you are the owner of all the files for your game.

Please ensure that `Replace owner on subcontainers and ojects` is checked within the `Advanced Security Settings`. This tick will be under the `Owner:` argument.

Once that is done, hit `Apply` at the bottom right hand corner of the `Advanced Security Settings` window.

You will get a prompt in the middle of your screen - click `OK`.

Afterwards, you will see the `Replace owner on subcontainers and object` option completely removed from your `Advanced Security Settings` window - this is normal, and means that you have done this right!

You are finished - Relaunch your game and verify that the folder/file permissions error is gone in ReShade!
