# Camera

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/camera)

This article contains how-tos for using the **Camera API**:

## How to enable the Camera API

*   Open the **Scripts** dropdown.

*   Click the **Settings** icon. 
    
    ![Script settings](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452715951_512536464617643_2581711984717896530_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=VSheXqEg978Q7kNvwGh_7oJ&_nc_oc=AdlJAeVLYXcptngsrcpQsTNB5x3sTS567jr9WdFScFNzqpvYfyjIpE3_adVTaYlf5Vc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfTFa14S_hS5kIcpX9SrmgCO1pJpCUaplT-9L8kPuYmzGA&oe=689BABA8) 

*   Enable **horizon/camera**. 
    
    ![Enable Camera API module](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/461688304_558937283310894_7508493344828080857_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=_K4vR9DU3kgQ7kNvwEguYtO&_nc_oc=Admjgzh24qkfs0RW3VIvOdztaaOiNr883xaFUOKHbe84td0vSlxRce7JaJCpfrgLb_M&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfTvAswQAsF5p28I241RT-nn5opPgesKIf9XFDMVKt3svw&oe=689B9149) 

## How to enable Local execution mode **Note**: Any script that manipulates the player’s camera must be executed in Local mode.

When building your script to manipulate the player’s camera, you must set the script to execute in Local mode.

![UI path to set Local execution mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480543861_656120566925898_450547107366261658_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=O2G66mJOVlUQ7kNvwF74j44&_nc_oc=AdmRPENzjzLgJY6Z5G9CRJeK3Sn_OeZ_9K_Ny4pHVrn1EaameAXqcmELYfPui_Ksfog&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfRVBjDLID1oy0XEfujloj3p7gbdqQicCgiWIOK83JGo9Q&oe=689BC16E) *Set Local execution mode for a script* ## How to set the first person camera mode

![First Person Camera Mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/510454911_746565601214727_1073391912782539982_n.gif?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=aatZ7F0R96EQ7kNvwG49WYz&_nc_oc=Admo7MWYdd0tAyFsBKELcmBpkkXBkH99R3YY8YNio20shAK2VL-baCUnp8dqMEEK2OA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfRAzCPYu8XgD8qbvIwPbQqWxNtPGO0F70omBvhwKuhGVw&oe=689BA432)

The Camera API supports the standard first-person game camera that follows the local player avatar. It has no effect in VR, where the first person is always enabled.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModeFirstPerson();
```

It’s also possible to transition to the new camera mode smoothly, by passing camera transition properties to the API. In the following code example, the camera takes half a second to transition from the current camera mode to the first person camera—easing its movement using an ease-in-out function.

```
import LocalCamera, {CameraTransitionOptions, Easing} from 'horizon/camera';

LocalCamera.setCameraModeFirstPerson({
  duration: 0.5,
  easing: Easing.EaseInOut,
});
```

## How to set the third person camera mode

![Third Person Camera Mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502486807_746565597881394_3771075418028817410_n.gif?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=_ckTpaUhSZwQ7kNvwEv1Tou&_nc_oc=AdmAMMW2JActLWf6ww45eQP5RvqM45_yoeGwjdBTPt99rMfoS0XK6RFzmPFS5Z4rapQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfSz0t3DMeVRe5pBmkH64DeIJgH5ybMMsJwT3QsmDqAOQQ&oe=689B9893)

The Camera API enables the standard third person game camera that follows the local player avatar. It has no effect in VR, where the first person is always enabled.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModeThirdPerson();
```

Similar to the previous API, it’s also possible to pass camera transition properties to the API to smooth the transition between the previous camera mode and the new one.

```
import LocalCamera, {CameraTransitionOptions, Easing} from 'horizon/camera';

LocalCamera.setCameraModeThirdPerson({
  duration: 0.5,
  easing: Easing.EaseInOut,
});
```

## How to set the fixed camera mode

![Fixed Camera Mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/512596494_749892187548735_311160336835599494_n.gif?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=qveWUiZ_A-4Q7kNvwEVsSG9&_nc_oc=Adm8HlSUleCE7EBhqP2_IdoJlNF9jFXw5guNJTi-N1O-V5jjFleJIL3sXNDzLsnyZ-4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfQxfxJLH3iH1d9hOsZkRGlmC8A4rp3PS8djMsRxc1pbzQ&oe=689BA98B)

The Camera API enables you to set the camera to a fixed world position and rotation. It has no effect in VR, where the first person is always enabled. By calling this API without any parameter, the camera remains fixed in place from its current position and orientation.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModeFixed();
```

It’s also possible to pass a specific position and rotation, as well as camera transition properties to smooth the transition.

```
import LocalCamera, {CameraTransitionOptions, Easing} from 'horizon/camera';

LocalCamera.setCameraModeFixed({
  position: new hz.Vec3(0, 1, -5),
  rotation: hz.Quaternion.fromEuler(new hz.Vec3(0, 0, 0)),
  duration: 0.5,
  easing: Easing.EaseInOut,
});
```

## How to set the attached camera mode

![Attached Camera Mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/511998276_749892190882068_8309516645733119512_n.gif?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=qX1j_ZfIqZ8Q7kNvwHO4sR6&_nc_oc=AdnqtvV7nBzy5hu1Axp4gemOBCeAfjBRFeP7VMKFCkRCAzqmoqCb3WxpCF6hIZ4bVwQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfQPhtppqqgDZvbXvf7ZyEV43-3OZx4z8w82d3rssAJraw&oe=689B9E62)

The Camera API allows you to attach the camera to a target entity, automatically following its position and rotation. It has no effect in VR, where the first person is always enabled. When the target entity is destroyed, the camera tracking stops, and it remains where it was before losing the target.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModeAttach(targetEntity);
```

It’s also possible to specify a position offset to follow the target from a distance, and a translation and rotation speed, as well as camera transition properties to smooth the transition.

```
import LocalCamera, {CameraTransitionOptions, Easing} from 'horizon/camera';

LocalCamera.setCameraModeAttach(targetEntity, {
  positionOffset: new hz.Vec3(0, 0, -5),
  translationSpeed: 1,
  rotationSpeed: 1,
  duration: 0.5,
  easing: Easing.EaseInOut,
});
```

## How to set the pan camera mode

![Pan Camera Mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/510420742_746565594548061_7310173553163183147_n.gif?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=fU9JVo0NO0oQ7kNvwGvqoGF&_nc_oc=AdmWEXOwbpdEoxQYyALu7L8hVMt0KictwCvM2RqMmizek9JtEr0Vo58FhA8zyKqGdPs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfRGV-eRVH4v3NWsgLBe3fIwwrUN0p_Q-sCyms09SWd1EA&oe=689B9C9D)

The Camera API enables you to set the camera to pan adjacent to the avatar at a fixed vector from the avatar. It has no effect in VR, where the first person is always enabled. It is also possible to set a translation speed.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModePan({
  positionOffset: new hz.Vec3(25, 0, 0),
  translationSpeed: 1,
});
```

## How to set the follow camera mode

![Follow Camera Mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/509278614_746565587881395_3141091227219055282_n.gif?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=i1YO3tH6xo0Q7kNvwEWuo0U&_nc_oc=AdlWojkKhguV-sZiDQrWQUef9J98tmE3WOg_RzPFKIaSIhZVsVSzXUYa7R_fl_2qPAA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h_05zF-C1w67osLvp5BzhA&oh=00_AfQ4yD6o5ZpJo_j-zbMUOPRxjfhB-6A96xVRZMO7r4wvKg&oe=689BC1D2)

The follow camera mode is similar to the orbit camera mode, where the camera direction is not tied to the direction the avatar is facing. However, follow camera differs from the orbit camera as it can automatically rotate back behind the avatar as the player moves. This makes it easier for players to orient their avatar and their camera in the world.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModeFollow();
```

It is possible to configure the behavior and position of the follow camera by passing the following options to the API. In this example, the listed values are the default values for these options.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraModeFollow({
  activationDelay: 2.0, // The delay from when the auto-turning is enabled after the camera has been manually turned.
  cameraTurnSpeed: 1.0, // Modifier for the speed at which the camera turns to return behind the player avatar.
  continuousRotation: false, // Enable the camera to continually rotate to behind the player once rotation has started and not be interrupted or disabled to only allow the rotation while the player moves.
  distance: 5.0, // The distance from the target to the camera. If not set, the camera remains at its current distance.
  horizonLevelling: false, // Enables levelling the camera to the horizon.
  rotationSpeed: 0.0, // Controls how quickly the camera moves with the player's avatar. The lower the number, the slower the camera's movement. If not set, the camera is always snapped to the position offset from the target.
  translationSpeed: 0.0, // Controls how quickly the camera moves with the player's avatar. The lower the number, the slower the camera's movement. If not set, the camera is always snapped to the target position.
  verticalOffset: 0.0, // Vertical offset up from the target position. The camera continues to look at the player's avatar.
});
```

## How to set the camera field of view

The Camera API lets you set the camera field of view.

```
import LocalCamera from 'horizon/camera';

LocalCamera.overrideCameraFOV(72.5);
```

Similar to the previous APIs, it’s also possible to pass camera transition properties to the API to smooth the transition between the previous camera mode and the new one.

```
import LocalCamera, {CameraTransitionOptions, Easing} from 'horizon/camera';

LocalCamera.overrideCameraFOV(72.5, {duration: 0.5, easing: Easing.EaseInOut});
```

## How to adjust the camera roll

The Camera API lets you adjust the tilt of the camera on the Z-axis, also known as the camera roll.

```
import LocalCamera from 'horizon/camera';

LocalCamera.setCameraRollWithOptions(30);
```

Similar to previous APIs, it’s also possible to pass camera transition properties to the API to smooth the transition between the previous camera mode and the new one.

```
import LocalCamera, {CameraTransitionOptions, Easing} from 'horizon/camera';

LocalCamera.setCameraRollWithOptions(30, {
  duration: 0.5,
  easing: Easing.EaseInOut,
});
```

## How to get the Camera look at position

The Camera API lets you get the world position that the player is currently looking at, ignoring the local player’s avatar.

```
import LocalCamera from 'horizon/camera';

let cameraLookAtPos = LocalCamera.lookAtPosition.get();
```

## How to enable and disable camera collisions

You can use the Local Camera API to enable and disable camera collision. Camera collision gives the camera a physical presence in the world, which means it won’t clip into world geometry, and it won’t see through walls. Instead, the camera is moved closer to the avatar.

Note that small spaces can cause the camera to move very close to the avatar, which can make it difficult for the player to navigate the world. If your world includes a lot of small spaces, then consider:

*   Disabling camera collision

*   Switching to [first-person camera mode](/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/camera/#how-to-set-the-first-person-camera-mode) *   Enabling [perspective switching](/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/camera/#how-to-enable-and-disable-perspective-switching) ```
import LocalCamera from 'horizon/camera';

LocalCamera.collisionEnabled.set(true);
```

## How to enable and disable perspective switching

The Camera API lets you control whether the player can toggle between first and third person modes using **PageUp** and **PageDown**. It does not affect your ability to force first and third person mode via the APIs. This has no effect in VR, where the first person is always enabled.

```
import LocalCamera from 'horizon/camera';

LocalCamera.perspectiveSwitchingEnabled.set(false);
```

## How to modify the camera’s behavior at runtime

It is possible to change the options which define the camera configuration during gameplay. The available options to configure are:

| Camera Mode | Options |
| --- | --- |
| Fixed Camera | positionrotation |
| Attach Camera | positionOffsetrotationOffsettranslationSpeedrotationSpeedtarget |
| Fixed Camera | positionrotation |
| Pan Camera | positionOffsettranslationSpeed |
| Orbit Camera | distanceverticalOffsettranslationSpeedrotationSpeed |
| Follow Camera | activationDelaycameraTurnSpeedcontinuousRotationdistancehorizonLevellingrotationSpeedtranslationSpeedverticalOffset |

In order to configure the camera behavior at runtime, the Camera API enables you to get the camera’s current mode as an object, and then modify the parameters of that object. You must specify which camera mode you are expecting to get in the function call:

```
LocalCamera.getCameraModeObjectAs(AttachCameraMode)?.rotationSpeed.set(10);
```

If the camera mode specified is not the same as the current camera mode, then this function will return null.

```
LocalCamera.setCameraModeFollow();
const cameraMode = LocalCamera.getCameraModeObjectAs(AttachCameraMode); // returns null
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 