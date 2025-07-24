# PlayAnimationOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playanimationoptions)

The options for the [Player.playAvatarAnimation()](/horizon-worlds/reference/2.0.0/core_player#playavataranimation) method, which triggers a non-looping animation on an avatar.

## Signature

```
export declare type PlayAnimationOptions = {
    playRate?: number;
    looping?: boolean;
    fadeInDuration?: number;
    fadeOutDuration?: number;
    mask?: AvatarAnimationMask;
    callback?: AnimationCallback;
};
```

## References [AvatarAnimationMask](/horizon-worlds/reference/2.0.0/core_avataranimationmask) , 

[AnimationCallback](/horizon-worlds/reference/2.0.0/core_animationcallback)