# Throwing

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/throwing)

A grabbable object that is being held by a player can be thrown with the standard controls for throwing grabbable objects on web and mobile (enabled by default). It is possible to override these standard controls in order to trigger throwing of a held object and to customize the throwing arc.

To disable the standard throwing controls you can set Enable Throwing Controls (Web & Mobile) to off:

![alt text](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653336_512535234617766_1315218671583337035_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=quKQgl4FyfQQ7kNvwHjhS71&_nc_oc=AdnSAaCOJFyX_18sc0Jbte3ByIVPqGzBtglvc8ELCg2OV5aIWDBo6UKH8F0XBKKraGw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Xfe9Mrc4YSX52bcE82FAmg&oh=00_AfTsC5hDPMWz2AtLndqpuAO7O6UiFnZhxOXMXtHebpmYIQ&oe=689BBCD8)

The [Player.throwHeldItem method](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_player#throwhelditem) is used to throw an object. When calling this method, the [ThrowOptions type](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_throwoptions) defines the properties for customizing how an object is thrown. The default values are defined by the [DefaultThrowOptions variable](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_defaultthrowoptions) .

Here’s an example that makes the player throw an object when they press the primary button on web and mobile.

```
this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnIndexTriggerDown, (player: hz.Player)=> {
  // Ignore on VR devices
  if (player.deviceType.get() == hz.PlayerDeviceType.VR) {
    return;
  }

  // Setup the throw options
  let opt = {
    speed: 25,
    pitch: 30
  }

  // Calling Throw Held Item
  player.throwHeldItem(opt);

}
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 