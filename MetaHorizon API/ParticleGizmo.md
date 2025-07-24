# ParticleGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_particlegizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a particle effect in the world.

## Signature

```
export declare class ParticleGizmo extends Entity
```

## Methods

<table>
  <tbody>
    <tr>
      <td>**play(options)**</td>
      <td>Plays the particle effect.

Signature

```
play(options?: ParticleFXPlayOptions): void;
```

Parameters

options: [ParticleFXPlayOptions](/horizon-worlds/reference/2.0.0/core_particlefxplayoptions) *(Optional)*

 Controls how the effect is played.

Returns

void</td>
    </tr>
    <tr>
      <td>**stop(options)**</td>
      <td>Stops the particle effect.

Signature

```
stop(options?: ParticleFXStopOptions): void;
```

Parameters

options: [ParticleFXStopOptions](/horizon-worlds/reference/2.0.0/core_particlefxstopoptions) *(Optional)*

 The options that control how the effect is stopped.

Returns

void</td>
    </tr>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the entity.

Signature

```
toString(): string;
```

Returns

string

A string representation of the entity.</td>
    </tr>
  </tbody>
</table>