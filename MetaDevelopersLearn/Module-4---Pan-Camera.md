# Module 4 - Pan Camera

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/camera-api-examples-tutorial/module-4-pancamera)

The pan camera setting moves the player’s camera to follow their avatar at a consistent offset. Having the camera follow the avatar gives a lot of creative freedom for experimenting with different types of gameplay, and allows for sidescrolling, top-down and isometric influenced gameplay.

In this tutorial, climbing the steps switches the camera to pan camera mode, and sets the camera’s position to be 10 offset from the player on the X-axis.

![Sidescroller for Camera API Examples](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481083958_662040649667223_5274211912720354602_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=tzUVuAgQ3-AQ7kNvwH-MTHG&_nc_oc=Adnz0XgT4qLMtqkpLK2OW8LfsTJyG_nEArmLo4OkYNCWoEyqRRPthQ3qokGtAOMs-lc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=nyK-6iq2SGOu3pKCEjRiOg&oh=00_AfQ1k8SXfSEqSwe8RZcsCaUeqmYSqrY9x8ulJ9LZPmDxoQ&oe=689BABBE)

Entering the top-down area also switches the camera to pan mode, but notice that we have set the camera’s position to be 20 units offset from the player on the Y-axis, which gives a top-down perspective.

![Top-down for Camera API Examples](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481919765_662040659667222_299852821914515850_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=UuksEi1LA5oQ7kNvwH9ZdCT&_nc_oc=AdnMnyNyK9Y15c2m6reinzraH0zJ4yKYspHJIB3olkn25rRkRgoQP3fouIVSvp7RD9Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=nyK-6iq2SGOu3pKCEjRiOg&oh=00_AfQhZvydfkIi_Zqm4tjkJvgTjRIhXf0mWFne_JcFLN8vDQ&oe=689B9E4C)

The PanCameraTrigger.ts script is essentially an extension of the CameraTrigger script with some additional properties:

| Parameter | Description |
| --- | --- |
| cameraOffset | The camera’s offset from the player’s avatar in Vec3 format. Note that the camera will always target the player’s avatar at the center of the frame.If not set the default value in this tutorial is (2, 0, 0). |
| translationSpeed | The speed the camera can move, decoupled from the avatar’s speed. This allows for smoother camera transition when the player starts and ends their movement.If not set, the default value in this tutorial is 4.0. |
| collisionsEnabled | Whether the camera should collide with objects in the world.If set to true, the camera will move closer to the player when there is an obstacle to its position with the offset.If set to false, the camera will ignore obstacles in the world, passing through them or behind them to maintain its offset position. |

When a player enters the Trigger Zone, the SetCameraCollisions and SetCameraPan events are emitted, which are received by the `PlayerCamera.ts` script. In `PlayerCamera.ts`:

*   A listener for `SetCameraCollisions` triggers a call to the `setCameraCollisions()` function.

*   A listener for `SetCameraPan` triggers a call to the `setCameraPan()` function.

For more information on parameters of this event and the above functions, see [Module 2 - PlayerCamera Overview](/horizon-worlds/learn/documentation/tutorial-worlds/camera-api-examples-tutorial/module-2-playercamera-overview) .

## Checkpoint

In this module we explored using the Pan Camera to offset the player’s camera at a specific position from the player, which enables interesting game mode variations on mobile and web such as sidescrolling and top-down.

Next, we explore Fixed Camera modes and use cases.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 