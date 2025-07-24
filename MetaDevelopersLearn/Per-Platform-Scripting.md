# Per Platform Scripting

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/per-platform-scripting)

You can use TypeScript to identify the type of device that the user is playing on. Use the [**Player.deviceType**

 property](https://horizon.meta.com/resources/scripting-api/core.player.devicetype.md/?api_version=2.0.0) and the [PlayerDeviceType enum](https://horizon.meta.com/resources/scripting-api/core.player.devicetype.md/?api_version=2.0.0) in a switch block.

```
switch (player.deviceType.get()) {
  case PlayerDeviceType.VR:
    // ...
    break;
  case PlayerDeviceType.Desktop:
    // ...
    break;
  case PlayerDeviceType.Mobile:
    // ...
    break;
  default:
    // ...
    break;
}
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 