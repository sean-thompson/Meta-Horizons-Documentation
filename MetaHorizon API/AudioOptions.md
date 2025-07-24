# AudioOptions type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_audiooptions)

Provides [AudioGizmo](/horizon-worlds/reference/2.0.0/core_audiogizmo) playback options for a set of players.

## Signature

```
export declare type AudioOptions = {
    fade: number;
    players?: Array<Player>;
    audibilityMode?: AudibilityMode;
};
```

## References [Player](/horizon-worlds/reference/2.0.0/core_player) , 

[AudibilityMode](/horizon-worlds/reference/2.0.0/core_audibilitymode)

## Remarks

fade - The duration, in seconds, that it takes for the audio to fade in or fade out.

  

players - Only plays the audio for the specified players.

  

audibilityMode - Indicates whether the audio is audible to the specified players. See [AudibilityMode](/horizon-worlds/reference/2.0.0/core_audibilitymode) for more information.

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)