# Player Camera

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/tools-for-creating-worlds-for-mobile/player-camera)

## Player Camera

The spawn point can be configured to control the player’s camera and modify its behavior.

To set the player’s camera, select the spawn point and use the **Mobile Camera** drop-down in the object properties window.

The Mobile Camera dropdown offers the following camera modes, with customization options for certain camera modes:

*   **None**: Default setting.

*   **Third Person**: The camera follows the player.

*   **First Person**: The camera is from the player’s point-of-view.

*   **Orbit**: The camera follows the player, but is not fixed behind the player.

*   **Pan**: The camera follows the player at an adjustable, fixed position adjacent to the player.

*   **Follow**: The camera follows the player, but is not fixed behind the player.

![Set Player Camera](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/510881416_749600250911262_533806309759582464_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=NqH4NylltlsQ7kNvwHIAagU&_nc_oc=Admw21vGo50M9956IpoPC_FJbyv4uE_f1sQ0ACDjAc-1QNQeTlLVLJUclo2_ci2VtfM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=idx6aGZLLYz1JJPc7uIZmg&oh=00_AfTxo_edcJZc-HsXco-33peb3a9xF_dceZoduvtZPUA9Iw&oe=689BA58A)

This image is taken from the Desktop Editor, but the same functionality is available in the Properties panel for entities in VR build mode. The Desktop Editor is only available to creators with access to advanced tooling.

## To change the camera perspective:

*   Open your creator menu and select **Gizmos**.

*   Select **SpawnPoint**.

*   Grab your new SpawnPoint gizmo and move up on your right thumbstick to select **...Properties**.

*   Select the dropdown you want to use next to **Mobile Camera**.

## Point-of-View Modes: **Third-person** and **first-person** camera modes provide opportunities for unique gameplay perspectives.

| Camera Mode | Description | Example |
| --- | --- | --- |
| Third-Person | The camera is from the player’s point-of-view. |  |
| First-Person | The camera follows the player. |  |

## Advanced Camera Modes:

The **Orbit**, 

**Pan**, and **Follow** camera modes offer additional customization options to enhance gameplay by adjusting how the camera interacts with the player:

| Camera Mode | Description | Customization Options | Example |
| --- | --- | --- | --- |
| Orbit | The camera dynamically follows the player, but is not fixed behind them. | Camera distance: The distance between the camera and the player. |  |
| Pan | The camera follows the player at a fixed position adjacent to the player, ensuring the camera angle and distance remain constant. | Camera offset: Set the camera’s position relative to the player using a vector with X, Y, and Z parameters. |  |
| Follow | The camera tracks player movements without being fixed behind them. During movement, the camera automatically rotates to align itself behind the player. | Camera Auto Follow Delay: The delay from when the auto-turning is enabled after the camera has stopped being manually rotated.Enable Continuous Rotation: When true, the camera continuously rotates to stay behind the player after movement, unless manually interrupted by player interaction.Horizon Levelling: Enables levelling the camera to the horizon.Rotation Rate: The rate at which the camera rotates back behind the player when they are moving. The lower the number, the slower the camera’s movement. |  |

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 