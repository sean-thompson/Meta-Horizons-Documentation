# Aim Direction

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/aim-direction)

## Overview

You can use the **GrabbableAim** property to specify the direction a weapon points when it’s held. Without this, the firing direction of the weapon is driven by animation, which leads to unpredictable results. The aim direction allows you to specify a true aiming reference for projectile launchers that are linked to a grabbable entity, for web and mobile players.

For example, a shotgun setup is displayed below:

![An example shotgun asset that uses the grabbable aim property.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/492655308_705052888699332_2797759283830252011_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=I3tSHbVHPfoQ7kNvwEPBOGX&_nc_oc=Adm0301iQAnBM3tRsr2ymcrapNNtdfJwmr4swzkquVWt4gcYtst8KO8LqizMJKmGf8U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=govB9jpYsVu3Vi0yZqbFJw&oh=00_AfS_YoNYpuX-3ankN1a20zYQb5nZLc23ca0rCSm8Qq9X4g&oe=689BBF31)

### GrabbableAim property

The **GrabbableAim** property represents the position and orientation in which bullets travel, and you can click and drag it into a new position. This setting ensures that the gun aims towards the reticle in the center of the screen, while maintaining any **ProjectileLauncher** offsets for web and mobile players.

From the desktop editor, when a grabbable object is selected you can adjust the GrabbableAim property from the **More** section by enabling **Use VR Grab Anchor**. You can then adjust the **Grab Aim Position** and the **Grab Aim Rotation**.

![The editable properties for an object that uses a VR Grab Anchor.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/491926812_705052892032665_6243466676556598810_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=RkwhJpA4E4cQ7kNvwEzv1uL&_nc_oc=AdmB-YHEpfCZO-dFbkFf1SHXQxmmDaCV6KxyygX_AkBOY7K0eqkK7Mu4kEZEXnHxqsk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=govB9jpYsVu3Vi0yZqbFJw&oh=00_AfRToMi9g4XBS6oZ5dl8KQxNKiDOKAn9mYJE6sVpywI_6A&oe=689BAF17)

Grab Aim Position and Rotation only apply to projectile launchers owned by the player. Make sure to set the player as the owner of the projectile launcher during grab for this feature to work correctly. Setting the local player as the owner of the launcher also provides a better player experience, giving the player instant projectile launcher feedback.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 