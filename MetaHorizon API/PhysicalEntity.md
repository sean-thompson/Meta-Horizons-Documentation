# PhysicalEntity Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_physicalentity)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents an entity influenced by physical effects in the world, such as gravity.

## Signature

```
export declare class PhysicalEntity extends Entity
```

## Remarks

For more information, see the [Spring Physics](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/api-references-and-examples/spring-physics) guide.

## Properties

<table>
  <tbody>
    <tr>
      <td>**angularVelocity**</td>
      <td>The angular velocity of an object in world space.

Signature

```
angularVelocity: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
    <tr>
      <td>**gravityEnabled**</td>
      <td>Indicates whether a gravity effect is applied to an entity. True if a gravity effect is applied to the entity, false otherwise.

Signature

```
gravityEnabled: WritableHorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**locked**</td>
      <td>`true`

 if the physics system is blocked from interacting with the entity; `false` otherwise.

Signature

```
locked: HorizonProperty<boolean>;
```</td>
    </tr>
    <tr>
      <td>**velocity**</td>
      <td>The velocity of an object in world space, in meters per second.

Signature

```
velocity: ReadableHorizonProperty<Vec3>;
```</td>
    </tr>
  </tbody>
</table>

## Methods

| applyForce(vector, mode) | Applies a force at a world space point. Adds to the current velocity.SignatureapplyForce(vector: Vec3, mode: PhysicsForceMode): void;Parametersvector: Vec3The force vector.mode: PhysicsForceModeThe amount of force to apply.Returnsvoid |
| applyForceAtPosition(vector, position, mode) | Applies a force at a world space point using a specified position as the center of force.SignatureapplyForceAtPosition(vector: Vec3, position: Vec3, mode: PhysicsForceMode): void;Parametersvector: Vec3The force vector.position: Vec3The position of the center of the force vector.mode: PhysicsForceModeThe amount of force to apply.Returnsvoid |
| applyLocalForce(vector, mode) | Applies a local force at a world space point. Adds to the current velocity.SignatureapplyLocalForce(vector: Vec3, mode: PhysicsForceMode): void;Parametersvector: Vec3The force vector.mode: PhysicsForceModeThe amount of force to apply.Returnsvoid |
| applyLocalTorque(vector) | Applies a local torque to the entity.SignatureapplyLocalTorque(vector: Vec3): void;Parametersvector: Vec3The force vector.Returnsvoid |
| applyTorque(vector) | Applies torque to the entity.SignatureapplyTorque(vector: Vec3): void;Parametersvector: Vec3The force vector.Returnsvoid |
| springPushTowardPosition(position, options) | Pushes a physical entity toward a target position as if it's attached to a spring. This should be called every frame and requires the physical entity's motion type to be interactive.SignaturespringPushTowardPosition(position: Vec3, options?: Partial<SpringOptions>): void;Parametersposition: Vec3The target position, or 'origin' of the springoptions: Partial<SpringOptions>(Optional) Additional optional arguments to control the spring's behavior.ReturnsvoidExamplesvar physEnt = this.props.obj1.as(hz.PhysicalEntity); this.connectLocalBroadcastEvent(hz.World.onUpdate, (data: { deltaTime: number }) => {  physEnt.springPushTowardPosition(this.props.obj2.position.get(), {stiffness: 5, damping: 0.2}); }) |
| springSpinTowardRotation(rotation, options) | Spins a physical entity toward a target rotation as if it's attached to a spring. This should be called every frame and requires the physical entity's motion type to be interactive.SignaturespringSpinTowardRotation(rotation: Quaternion, options?: Partial<SpringOptions>): void;Parametersrotation: QuaternionThe target quaternion rotation.options: Partial<SpringOptions>(Optional) Additional optional arguments to control the spring's behavior.ReturnsvoidExamplesvar physEnt = this.props.obj1.as(hz.PhysicalEntity); this.connectLocalBroadcastEvent(hz.World.onUpdate, (data: { deltaTime: number }) => {  physEnt.springSpinTowardRotation(this.props.obj2.rotation.get(), {stiffness: 10, damping: 0.5, axisIndependent: false}); }) |
| toString() | Gets a string representation of the entity.SignaturetoString(): string;ReturnsstringThe human readable string representation of this entity. |
| zeroVelocity() | Sets the velocity of an entity to zero.SignaturezeroVelocity(): void;Returnsvoid |