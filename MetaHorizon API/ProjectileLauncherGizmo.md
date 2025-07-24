# ProjectileLauncherGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_projectilelaunchergizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a projectile launcher in the world.

## Signature

```
export declare class ProjectileLauncherGizmo extends Entity
```

## Remarks

For information about usage, see [The Magic Wand](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/developing-for-web-and-mobile-players-tutorial/module-6-room-a-the-magic-wand) tutorial.

## Properties

<table>
  <tbody>
    <tr>
      <td>**projectileGravity**</td>
      <td>The gravity applied to the projectile.

Signature

```
projectileGravity: WritableHorizonProperty<number>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**launch(options)**</td>
      <td>Launches a projectile with options.

Signature

```
launch(options?: LaunchProjectileOptions): void;
```

Parameters

options: [LaunchProjectileOptions](/horizon-worlds/reference/2.0.0/core_launchprojectileoptions) *(Optional)*

 Optional options for launching projectile

Returns

void</td>
    </tr>
    <tr>
      <td>**launchProjectile(speed)**</td>
      <td>> Warning: This API is now obsolete.
> 
>   
> 
> use 
> 
> `launch`
> 
>  instead.
> 
>   

Launches a projectile.

Signature

```
launchProjectile(speed?: number): void;
```

Parameters

speed: number *(Optional)* Optional. The speed at which the projectile will launch from the launcher.

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