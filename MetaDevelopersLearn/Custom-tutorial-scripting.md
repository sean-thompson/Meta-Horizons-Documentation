# Custom tutorial scripting

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/custom-nux)

## Overview

The Custom Tutorial Scripting API allows developers to create custom tutorials for their worlds, providing a seamless and engaging onboarding experience for new visitors to your world. It offers a set of APIs that can be used to create and manage tutorials, including the ability to show info slides, trigger contol button prompts or tooltips and show a generic “toast” notification.

## Tutorial APIs

*   [showInfoSlides](#showinfoslides-api)

*   [showInputActionMessage](#showinputactionmessage-api)

*   [showToastMessage](#showtoastmessage-api)

## showInfoSlides API

The ‘ShowInfo’ API allows developers to convey information to users via a series of connected modal windows, greatly enhancing the onboarding experience in your world. It can be used to display welcome messages, provide critical updates, or deliver important instructions, ensuring users are well-informed about key aspects or new features in your world.

Each info slide can have a localizable title, message, and image. The image is a texture asset with either (width: 808 height: 412) size or (width: 920 height: 280) size in case it’s a header image. To add an image and get the image URI please follow [instructions](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/custom-action-button-icons#uploading-a-custom-texture) . The image will be scaled to fit the panel size. The title and message are localizable strings that can be translated into different languages.

### Example

The following example shows how to use the showInfoSlides API.

For more details on the showInfoSlides API, check out our API documentation [here](https://horizon.meta.com/resources/scripting-api/core.player.showinfoslides.md/?api_version=2.0.0) .

![Header banner image example (920x280px)](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/495721744_728127426391878_3269922861602016300_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=CBOsauXwuRsQ7kNvwEiY4RU&_nc_oc=AdmoXMSNU0BYm9XF1ZxAe7izdgsIm_-V283jAQ1YUOYMVsj66xPKKt0mFePWTk3TgSc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Qe_9Cj3S5EqYeWxt2KTMgw&oh=00_AfRbuwVykkOzdbQIS96ql3CgRjR--_dljg6vWYjrIbAoqg&oe=689BA447)

![Body image example (808x412px)](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/496476463_728127423058545_2966933219208493660_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=IECUvOmcvegQ7kNvwHk993w&_nc_oc=AdlHZ9gdWTW3E6hpX7g_dt2RKamEku6T3qjCwhsRGrwrnht_TkWAO-qspW9c8-B1tL8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Qe_9Cj3S5EqYeWxt2KTMgw&oh=00_AfSvD0gVc275FWlSn6XNulfM5xv4qS6OK3SEuVBkW5o3hA&oe=689B92EB)

```
player.showInfoSlides([
  {
    title: 'Title Slide #1!',
    message: 'Image width: 920 height: 280',
    imageUri: 'YOUR_TEXTURE_ASSET_ID',
    style: {
      attachImageToHeader: true,
    },
  },
  {
    title: '',
    message: 'Image width: 808 height: 412',
    imageUri: 'YOUR_TEXTURE_ASSET_ID',
  },
]);
```

## showInputActionMessage API

The `showInputActionMessage` API enables developers to trigger an attention-grabbing animation and display a message above an on-screen button for a specified [player input action](https://horizon.meta.com/resources/scripting-api/core.playerinputaction.md/?api_version=2.0.0) . This is particularly useful for button tooltips in timed action prompts and tutorials.

More details about the API can be found [here](https://horizon.meta.com/resources/scripting-api/core.player.showinputactionmessage.md/?api_version=2.0.0) ### Example

![showInputActionMessage visual example](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/514422489_754517583752862_9086806357539250048_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=WNfZGAPShuQQ7kNvwFZdQYb&_nc_oc=AdmsI24_xq-5HKZ98DtTAN2PKuhV510OT_Ql1hVPR9k3Px0DlM56ROJ4tfWucaud44Y&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Qe_9Cj3S5EqYeWxt2KTMgw&oh=00_AfTCPLRrU44Im_SxncUJLHLgq9vzFYy51Umj6Yr2yAtBsQ&oe=689BA990)

```
player.showInputActionMessage(
  PlayerInputAction.Jump,
  'Tap to do something cool!',
  5000, // duration in ms
);
```

## showToastMessage API

The `showToastMessage` API allows you to show a generic toast message notification at the top of the screen. The toast message can be used to display a message to the player, such as an alert, notification, or helpful onboarding message. The toast message is displayed for a set duration and then it disappears.

More details about the API can be found [here](https://horizon.meta.com/resources/scripting-api/core.player.showtoastmessage.md/?api_version=2.0.0) ### Example

![showToastMessage visual example](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/514339962_754517590419528_6522914990856982192_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=tyBJdJGmXnwQ7kNvwHexTND&_nc_oc=Adn9N0CtgwOjI_EcejQbkBzkE2Vws35VqIRCRPYLrouR_vpFcx_USl6UA79tmnv5Ick&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Qe_9Cj3S5EqYeWxt2KTMgw&oh=00_AfR-gCTRMiD7gMghTaSmTm_ghFwGI0VnniaXJiwCI74VkQ&oe=689B9626)

```
player.showToastMessage(
  'This is a custom announcement!',
  5000, // duration in ms
);
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 