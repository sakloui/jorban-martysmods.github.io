---
title: Setting Up Windows File Permissions
layout: page
parent: Additional Guides
nav_order: 3
---

# Windows File Permisions

Game distribution platforms like Steam, EA Play/Origin, Ubisoft Connect, and GOG Galaxy often utilize `Program Files (x86)` directories in order to take control over the installed games and their files. However, this practice can occasionally lead to complications. For instance, these controlled directories may hinder other software, like ReShade, from accessing necessary files due to restricted permissions. ReShade, in particular, requires both read and write permissions to function optimally.

In this guide, we aim to simplify the concept of file permissions, however, this is a complex topic, so we recommend following the guide closely!

---

## **Step 1:** Identify the Game Directory

Before proceeding, ensure that your game is closed and no associated files are open! 

The game directory is typically indicated in the file permissions error message. However, if you need assistance locating your game directory, refer to our guide on [how to find your game directory](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

---

## **Step 2:** Access the Properties of Your Game's Root Folder

For illustration, let's use FFXIV:

The game executable is usually located in the `game` folder, which is not the root directory for FFXIV. The root directory would be `FINAL FANTASY XIV – A Realm Reborn\game`.

Right-click the folder named `FINAL FANTASY XIV – A Realm Reborn`, **NOT** `game`. In the context menu that appears, select `Properties`.

![Context Menu](../images/setting-up-windows-file-permissions/properties_context_menu.jpg)

---

## **Step 3:** Proceed to the Security Tab

In the `Folder Properties` window, select the `Security` tab.

![Folder Properties Security Tab Highlight](../images/setting-up-windows-file-permissions/folder_security_tab.jpg)

While this tab may seem complex for beginners, this guide will walk you through each necessary step to resolve your issue.

![Full Image of the Security Tab](../images/setting-up-windows-file-permissions/security_tab_full.jpg)

---

## **Step 4:** Select `Advanced`

In the lower right corner of the `Security` tab, click the `Advanced` button.

![Security Tab Advanced Button Highlight](../images/setting-up-windows-file-permissions/security_tab_advanced_button.jpg)

This action will open the `Advanced Security Settings` window, which contains more advanced user settings for folders.

![Full Image of the Advanced Security Window](../images/setting-up-windows-file-permissions/advanced_security_settings_window_full.jpg)

---


## **Step 5:** Modify the Folder's Ownership

At the top of the `Advanced Security Settings` window, you'll find two fields:

  * Name: `{Name Of The Folder Location}`

  * Owner: `{Username and Location of User}`

![Highlight of Name and Owner Fields](../images/setting-up-windows-file-permissions/name_and_owner_arguments.jpg)

These fields provide essential information about the folder and its current owner.

Click the blue `Change` button next to the `Owner` field.

![Advanced Security Change Button Highlight](../images/setting-up-windows-file-permissions/advanced_security_settings_change_button.jpg)

---

## **Step 6:** Update the Directory's Owner

After clicking `Change`, a `Select User or Group` window will appear.

![Full Image of Select Users and Groups Window](../images/setting-up-windows-file-permissions/select_users_and_groups_window_full.jpg)

In the top right corner of this window, click `Object Types`.

![Highlight of Object Types button in Select Users and Groups Window](../images/setting-up-windows-file-permissions/select_users_and_groups_window_object_types_button.jpg)

In the menu that appears, ensure only `Users` is checked, then click `OK`.

![Highlight of Users tick in Object Types Window](../images/setting-up-windows-file-permissions/object_types_select_user_only.jpg)

Back in the `Select User or Group` window, click `Advanced`.

![Highlight of Advanced Button in Select User and Group Window](../images/setting-up-windows-file-permissions/select_users_and_groups_window_advanced_button.jpg)

In the `Select User or Group (Advanced)` window, click `Find Now` to list all users on your system.

![Highlight of Find Now button in Select Users and Groups Advanced Window](../images/setting-up-windows-file-permissions/select_users_and_groups_advanced_window_find_now_button.jpg)

Double-click your username to select it, then click `OK`.

![Highlight of User Being Selected in Select Users and Groups Advanced Window](../images/setting-up-windows-file-permissions/select_users_and_groups_advanced_window_select_user.jpg)

---

## **Step 7:** Enable `Replace owner on subcontainers and objects`

Back in the `Advanced Security Settings` window, ensure `Replace owner on subcontainers and objects` is checked.

![Highlight of Replace Owner on Subcontainers Tick Box in Advanced Security Settings Window](../images/setting-up-windows-file-permissions/advanced_security_settings_window_replace_owner_on_subcontainers.jpg)

Click `Apply`, then `OK` in the prompt that appears.

![Highlight of Apply Button in Advanced Security Settings Window](../images/setting-up-windows-file-permissions/advanced_security_settings_window_replace_owner_on_subcontainers_apply.jpg)

The `Replace owner on subcontainers and objects` option should now be removed, indicating the ownership change was successful.

![Notice of Replace owner on subcontainers and objects Argument Now Gone](../images/setting-up-windows-file-permissions/advanced_security_settings_window_full.jpg)

---

## **Step 8:** Grant `Full Control` Access to Your User

Now that you've changed the directory's owner, you need to grant your user full control over the directory.

Click `Add` at the bottom right of the `Advanced Security Settings` window.

![Highlight Add button on Advanced Security Settings Window](../images/setting-up-windows-file-permissions/advanced_security_settings_window_add_button.jpg)

In the `Permissions Entry` window that appears, click `Select a principal`.

![Highlight Add button on Advanced Security Settings Window](../images/setting-up-windows-file-permissions/permissions_entry_principal_highlight.jpg)

This will open the `Select User or Group` window. Click `Advanced`.

![Highlight of Advanced Button in Select User and Group Window](../images/setting-up-windows-file-permissions/select_users_and_groups_window_advanced_button.jpg)

In the `Select User or Group (Advanced)` window, click `Find Now`, then double-click your username.

![Highlight of Find Now button in Select Users and Groups Advanced Window](../images/setting-up-windows-file-permissions/select_users_and_groups_advanced_window_find_now_button.jpg)

This will fill in the `Principal` field in the `Permissions Entry` window.

![Highlight of Principals Having an Entry](../images/setting-up-windows-file-permissions/filled_out_permission_entry_principal.jpg)

Under `Basic Permissions`, ensure `Full Control` is selected, then click `OK`.

![Highlight of Full Control Being Selected for Basic Permissions](../images/setting-up-windows-file-permissions/basic_permissions_full_control.jpg)

Back in the `Advanced Security Settings` window, you should see your user listed with `Full Control` access.

![Highlight of User Being Added in the Advanced Security Settings Window](../images/setting-up-windows-file-permissions/user_added_with_full_control.jpg)

Click `OK` to finish. You can now relaunch your game and verify that the folder/file permissions error is resolved in ReShade!