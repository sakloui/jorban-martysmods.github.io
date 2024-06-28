---
title: "Setting Up Windows File Permissions"
layout: "page"
parent: "Additional Guides"
nav_order: 3
---

# Windows File Permissions

Game distribution platforms like Steam, EA Play/Origin, Ubisoft Connect, and GOG Galaxy often use "Program Files (x86)" directories, which can restrict other software like ReShade from accessing necessary files. ReShade needs both read and write permissions to work properly.

## Identify the Game Directory

The game directory is usually indicated in the error message. However, if you need help finding it, refer to our guide on [how to find your game directory](https://guides.martysmods.com/docs/additional-guides/finding-your-game-executable-and-directory/).

## Access the Properties of Your Game's Root Folder

Right-click the game's root folder (e.g., "FINAL FANTASY XIV – A Realm Reborn"), not the "game" folder. Then, click "Properties".

![Context Menu](../images/setting-up-windows-file-permissions/properties_context_menu.webp)

## Proceed to the Security Tab

In the "Folder Properties" window, select the "Security" tab.

![Folder Properties Security Tab Highlight](../images/setting-up-windows-file-permissions/folder_security_tab.webp)

## Select "Advanced"

Click the "Advanced" button in the lower right corner of the "Security" tab.

![Security Tab Advanced Button Highlight](../images/setting-up-windows-file-permissions/security_tab_advanced_button.webp)

## Modify the Folder's Ownership

In the "Advanced Security Settings" window, click the blue "Change" button next to the "Owner" field.

![Advanced Security Change Button Highlight](../images/setting-up-windows-file-permissions/advanced_security_settings_change_button.webp)

## Update the Directory's Owner

In the "Select User or Group" window, click "Object Types", ensure only "Users" is checked, then click "OK".

![Highlight of Object Types button in Select Users and Groups Window](../images/setting-up-windows-file-permissions/select_users_and_groups_window_object_types_button.webp)

Click "Advanced", then "Find Now". Double-click your username to select it, then click "OK".

![Highlight of User Being Selected in Select Users and Groups Advanced Window](../images/setting-up-windows-file-permissions/select_users_and_groups_advanced_window_select_user.webp)

## Enable "Replace owner on subcontainers and objects"

Ensure "Replace owner on subcontainers and objects" is checked, then click "Apply" and "OK".

![Highlight of Replace Owner on Subcontainers Tick Box in Advanced Security Settings Window](../images/setting-up-windows-file-permissions/advanced_security_settings_window_replace_owner_on_subcontainers.webp)

## Grant "Full Control" Access to Your User

Click "Add" at the bottom right of the "Advanced Security Settings" window.

![Highlight Add button on Advanced Security Settings Window](../images/setting-up-windows-file-permissions/advanced_security_settings_window_add_button.webp)

In the "Permissions Entry" window, click "Select a principal", then "Advanced", "Find Now", and double-click your username.

![Highlight of Principals Having an Entry](../images/setting-up-windows-file-permissions/filled_out_permission_entry_principal.webp)

Ensure "Full Control" is selected under "Basic Permissions", then click "OK".

![Highlight of Full Control Being Selected for Basic Permissions](../images/setting-up-windows-file-permissions/basic_permissions_full_control.webp)

You should see your user listed with "Full Control" access. Click "OK" to finish.

![Highlight of User Being Added in the Advanced Security Settings Window](../images/setting-up-windows-file-permissions/user_added_with_full_control.webp)

Relaunch your game to verify that the permissions error is resolved.