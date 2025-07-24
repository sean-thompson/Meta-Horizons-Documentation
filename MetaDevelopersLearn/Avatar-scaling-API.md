# Avatar scaling API

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/api-references-and-examples/avatar-scaling-api)

This topic describes the `avatarScale` property in the [Player](/horizon-worlds/reference/2.0.0/core_player) class, which is used to scale avatars. Use cases of this API include creating asymmetrical experiences where some players are larger than others, as well as dynamic changes of players during gameplay.

In the following image of [Kaiju City Showdown](https://horizon.meta.com/world/1279402616789539) , the Kaiju player is larger than the rest of players using the API.

![The Kaiju player is larger than the rest of the players](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/487459574_686297430574878_1704284363227182690_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=OZ9VJA-T2jUQ7kNvwGcXBOb&_nc_oc=AdkGKfW_q4sYSw5ddyXd_oUcxZODagCexb4CnjHwKiYW9VNJfKicBStPZXN85i-_tfc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=eWVm7v6tcMUzbqMuHuJnbw&oh=00_AfS4zrVZmViaQeZYbQVWsa59eKUXZz3d248ORrrAU76WNg&oe=689B8CDA)

You can now unlock new content on the platform. The API enables creators to incorporate mechanics such as platform jumping and puzzle games that rely on scaling avatars up or down in order to progress in the game. Additionally, you can use avatar scaling as part of a progression system for prestige or reputation.

The following image shows the avatar at the beginning of the game.

![The avatar before it's scaled down](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/487334824_686297433908211_277638335994097776_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=CPYAvj1edRoQ7kNvwFuDkOo&_nc_oc=AdlKg0B3bTcsNYuPXGgPIVDWFUP2evKfOHRbTru1OdpZM1iyY4Ff3XmdxaI9HLS6VpI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=eWVm7v6tcMUzbqMuHuJnbw&oh=00_AfQXhP2Fqpwuh8g0_qjdfGS-ITZ9d2KV5Taw4qYo1p2Zyw&oe=689BAB85)

The following image shows the avatar is scaled down to jump through the doughnut hole.

![The avatar scaled down to fit through the doughnut hole](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/487357450_686297427241545_4741437208343931387_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=-RpCkfVfsmcQ7kNvwFgVVPd&_nc_oc=AdkaNT0BHMp3XQIH5UqaJOE5awKQeyrn56mT-WZesZLEQhJvZpchI16AlF22TngTVow&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=eWVm7v6tcMUzbqMuHuJnbw&oh=00_AfRpfoRGfb_puLTXVSI8a5UWTXLIAkk_5ncMLPo1keQqnA&oe=689BA80E)

## Prerequisites

*   [TypeScript API version 2.0.0 or later](/horizon-worlds/learn/documentation/typescript/upgrade-world-to-typescript-api-v200)
    
    .

*   The API is available in [horizon/core/player](/horizon-worlds/reference/2.0.0/core_player) .

*   [Enable the API module](/horizon-worlds/learn/documentation/typescript/upgrade-world-to-typescript-api-v200#upgrading-your-world)
    
    .

## Limitations

The recommended range for scaling avatars is between 0.05 and 50. Values outside of this range may cause unexpected behavior due to engine limitations.

## Best practices

The recommendation is to change the scale when the avatar teleports to another location or when the screen is in transition. Avoid changing the size too often.

## Sample code

The following sample shows you how to use the `avatarScale` property in the [Player](/horizon-worlds/reference/2.0.0/core_player) class. When the user uses the [right grip action](/horizon-worlds/reference/2.0.0/core_playerinputaction) , the player avatar scale will be increased. When the user uses the [left grip action](/horizon-worlds/reference/2.0.0/core_playerinputaction) , the avatar scale will be decreased. Keep in the mind that the example only iterates between 3 different scales, which are 10%, 100%, and 500%. Additionally, the sample also uses custom input APIs, learn more in the [developer guide](/horizon-worlds/learn/documentation/create-for-web-and-mobile/typescript-apis-for-mobile/custom-input-api) and the [API reference guide](/horizon-worlds/reference/2.0.0/core_playercontrols) .

```
import * as hz from 'horizon/core';

class SetAvatarScale extends hz.Component<typeof SetAvatarScale> {
  static propsDefinition = {};

  growInput?: hz.PlayerInput;
  shrinkInput?: hz.PlayerInput;

  avatarScales: number[] = [0.1, 1, 5];
  avatarScaleIndex: number = 1;

  start() {
    this.connectCodeBlockEvent(
      this.entity,
      hz.CodeBlockEvents.OnPlayerEnterWorld,
      (player) => {
      this.entity.owner.set(player);
    });

    if (this.entity.owner.get() == this.world.getServerPlayer()) return;

    this.growInput = hz.PlayerControls.connectLocalInput(
      hz.PlayerInputAction.RightGrip,
      hz.ButtonIcon.Expand, this);

    this.growInput.registerCallback((_, pressed) => {
      if (pressed) this.changeAvatarScale(1);
    });

    this.shrinkInput = hz.PlayerControls.connectLocalInput(
      hz.PlayerInputAction.LeftGrip,
      hz.ButtonIcon.Contract, this);

    this.shrinkInput.registerCallback((_, pressed) => {
      if (pressed) this.changeAvatarScale(-1);
    });
  }

  changeAvatarScale(increment: number) {
    let player = this.entity.owner.get();
    this.avatarScaleIndex = Math.min(
      Math.max(0, this.avatarScaleIndex + increment),
      this.avatarScales.length - 1);
    player.avatarScale.set(this.avatarScales[this.avatarScaleIndex]);
  }
}

hz.Component.register(SetAvatarScale);
```

## What’s next?

Try more tutorials and follow examples in these topics:

*   [Scripting](/horizon-worlds/learn/documentation/typescript/typescript)

*   [Tutorial worlds](/horizon-worlds/learn/documentation/tutorial-worlds/build-your-first-game/module-1-build-your-first-game)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 