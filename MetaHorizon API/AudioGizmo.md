# AudioGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_audiogizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents an audio gizmo you can use to add music and sound effects to a world and control audio settings.

## Signature

```
export declare class AudioGizmo extends Entity
```

## Examples

```
const soundGizmo = this.props.sfx.as(AudioGizmo);
// Plays audio for all players immediately.
soundGizmo.play();

// Pauses audio for all players after fading out for 1 second.
var pauseOptions: AudioOptions = {fade: 1};
soundGizmo.pause(pauseOptions);

// Stops the audio for the specified player after 0.2 seconds.
soundGizmo.play();
var stopOptions: AudioOptions = {fade: 0.2, players: [this.props.mainPlayer]};
soundGizmo.stop(stopOptions);
```

## Remarks

If you have actions to perform after playback of an audio source completes, you can listen for the 

`OnAudioCompleted` [CodeBlockEvent](/horizon-worlds/reference/2.0.0/core_codeblockevents) .

## Properties

<table>
  <tbody>
    <tr>
      <td>**pitch**</td>
      <td>The audio pitch in semitones, which ranges from -24 to 24. Overrides the pitch level set on the Audio gizmo's Object Property Panel.

Signature

```
pitch: WritableHorizonProperty<number>;
```

Examples

```
const soundGizmo = this.props.sfx.as(AudioGizmo);
const volOptions: AudioOptions = {fade: 0.5};
soundGizmo.volume.set(0.8, volOptions);
soundGizmo.pitch.set(12);
```

Remarks

When configuring the pitch of an Audio gizmo, the following pitch and speed calculations apply:

  

12 semitones = 1 octave.

  

An increase in 1 octave makes the audio 2x as fast.

  

A decrease in 1 octave makes the audio 1/2 as fast.</td>
    </tr>
    <tr>
      <td>**volume**</td>
      <td>The audio volume of the gizmo, which ranges from 0 (no sound) to 1 (full volume). Decimal fractions are allowed (for example, 0.3). Overrides the volume level set on the Property panel of the Audio gizmo.

Signature

```
volume: WritableHorizonProperty<number, AudioOptions>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| pause(audioOptions) | Pauses an AudioGizmo sound.Signaturepause(audioOptions?: AudioOptions): void;ParametersaudioOptions: AudioOptions(Optional) Controls how the audio is paused.ReturnsvoidExamplesconst soundGizmo = this.props.sfx.as(hz.AudioGizmo); const audioOptions: AudioOptions = {fade: 1, players: [player1, player2]}; soundGizmo.pause(audioOptions); |
| play(audioOptions) | Plays an AudioGizmo sound.Signatureplay(audioOptions?: AudioOptions): void;ParametersaudioOptions: AudioOptions(Optional) Controls how the audio is played.ReturnsvoidExamplesconst soundGizmo = this.props.sfx.as(hz.AudioGizmo); const audioOptions: AudioOptions = {fade: 1, players: [player1, player2]}; soundGizmo.play(audioOptions); |
| stop(audioOptions) | Stops an AudioGizmo sound.Signaturestop(audioOptions?: AudioOptions): void;ParametersaudioOptions: AudioOptions(Optional) Controls how the audio is played.ReturnsvoidExamplesconst soundGizmo = this.props.sfx.as(hz.AudioGizmo); const audioOptions: AudioOptions = {fade: 1, players: [player1, player2]}; soundGizmo.stop(audioOptions); |
| toString() | Creates a human-readable representation of the audio gizmo.SignaturetoString(): string;ReturnsstringA string representation of the audio gizmo. |