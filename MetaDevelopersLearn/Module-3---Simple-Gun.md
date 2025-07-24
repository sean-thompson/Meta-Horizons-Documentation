# Module 3 - Simple Gun

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/simple-shooting-mechanics-tutorial/module-3-simple-gun)

While its projectiles certainly do, the ProjectileLauncher gizmo has no physical presence in the world. It must be attached to the end of a physical entity. In this example world, it is a simple gun object.

![Image of the basic Gun assembly in the world](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480806005_676362554901699_8187611971142006280_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=hsnryEmao9IQ7kNvwGTKuOX&_nc_oc=AdnaGG8GhuVCjsM9l61okNm-1z3ozRY61b7YM7Y4xC7SBkjzFr6QL0c7XntbHlnPfqQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=UL13VYeb1r-tQoZ9dq4Y5w&oh=00_AfQEIkyeyT3fn7Wf3Xsp448y9Pa5sBDOYZDKSRwcaUYLDg&oe=689B8BA5)

## Concept

In the above image, you can see a set of entities listed underneath the **Gun** entity in the Hierarchy panel. In this case, a “gun” is an aggregate of the following components:

*   **White cylinder**: A very simple physical representation of the gun. This object serves as the parent object to the other components of the gun in the Hierarchy panel.
    
    *   When you need to manipulate the gun as a single entity, select the parent object in the Hierarchy panel.

*   **ProjectileLauncher**: does most of the job to spawn projectiles and send them on their way

*   **LaserSight**: A Raycast gizmo to resolve the potential hit from where the gun is aiming to allow us to place a “laser dot”

*   **ClipAmmoText**
    
     and **TotalAmmoText** as text gizmos to display ammo status just above the gun

*   **GunFireSFX**
    
     and **GunReloadSFX** sound gizmos

*   **GunSmokeVFX**
    
     is a particle FX gizmo for the “smoking gun” effect

*   And text labels to indicate that the white cylinder is, in fact, a gun.

### Grabbable properties

Ok, let’s grab a gun! In the case of this simple gun, we must specify some properties on the parent object of the group. Unless overrides are applied to child objects, all objects in the object group receive these property values.

To make the object group grabbable, you must set the following properties:

![Image of properties in panel that can be used to configure grabbing and interaction](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462289693_563294036208552_1751847987411185253_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=dH3HN0RoY0MQ7kNvwEX99To&_nc_oc=AdkqHcKPfSA6HF77t6b4pPu7Dqd52v9h9Ks0YggbJOcYc3fK82a305ysfws8nTWy21w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=UL13VYeb1r-tQoZ9dq4Y5w&oh=00_AfTdN5jSQYHfr37Cmy0F2DG1njuFsSNCXwMRlgefaIqsqQ&oe=689BA188)

*   **Visible**: Not required, but it’s hard to grab something that you cannot see.

*   **Collidable**: Enable it.

*   **Collision Layer**: You can set this to Everything.

*   **Motion**: Set this value to Interactive.

*   **Interaction**: When motion is Interactive, set this value to Grabbable.

The object group (a gun) can now be grabbed. Additional grab-related properties are now listed in the Properties panel:

*   **Grab lock**: Enable this property to retain the grabbed entity in the hand after it is grabbed.

*   **Grab anchor**: If you want for the avatar to grab the object from a position other than the group’s origin, you can set a “grab anchor” to the relative coordinates of that grab point.
    
    *   These values are relative to the origin of the object or object group.
    
    *   You can set them to be different per hand, even select a specific grab point while the character is aiming.

*   **Avatar pose**: This property sets the avatar’s arm position while holding the group.

![Images of properties that are specific to grabbing](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480585693_676362571568364_1345016757614276474_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=YkbtqCmj4kwQ7kNvwHv7oky&_nc_oc=AdkwPWLPCzT2m69QyxtNhIuoklaSuXI0oceRatiatsaRdGJsfXK27DNru_UHPTmTr6Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=UL13VYeb1r-tQoZ9dq4Y5w&oh=00_AfQXXHLTtdZAGsoLFRqqKEH8EqlVW_LraH3pJyiInndQMQ&oe=689BA692)

## The Script: GunScript.ts

GunScript.ts is attached to the parent object of the gun assembly. **Note**: This script must be set to run in Local execution mode only, which means it runs on the local client only.

*   In the desktop editor, open the **Scripts panel**.

*   Locate the GunScript.ts script. From its context menu, select **Execution mode > Local**.

### Script properties

Select the white cylinder gun, to which the GunScript.ts script is attached. The following properties are available in the Properties panel:

*   **projectileLauncher**: Reference to the projectile launcher entity

*   **ammoPerClip**: Number of shots to fire before reload

*   **clipAmmoDisplay**: Reference to the text gizmo that displays ammo left in clip

*   **totalAmmo**: Total ammo for the gun

*   **totalAmmoDisplay**: Reference to the text gizmo that displays total ammo left

*   **laserGizmo**: Reference to the raycast gizmo to enable the “laser dot” sight

*   **laserPointer**: Reference to the sphere used as a laser dot

*   **smokeFX**: Reference to the particle fx gizmo that will show smoke when shooting

*   **gunFireSFX**: Reference to the gun shot sound

*   **gunReloadSFX**: Reference to the gun reload sound

*   **projectileLauncherCooldownMs**: Number of seconds of cooldown between shots (in milliseconds)

*   **projectileSpeed**: Initial speed in meters/second of the projectile **Note**: This property value overrides the corresponding property value on the Projectile Launcher, so that all configuration for the gun object is in one location.

*   **projectileGravity**: Acceleration due to gravity on the projectile **Note**: This property value overrides the corresponding property value on the Projectile Launcher, so that all configuration for the gun object is in one location.

*   **useLaserTargeting**: Toggle usage of the “laser dot” sight

These properties are used as input for the functions in the script.

### Start method

During runtime execution, the start() method is called in this order:

*   First on the server instance

*   Second on any local instance of a player (client) who grabs it

#### Event subscriptions

As part of the script, we create **event subscriptions**, which are listeners for platform-generated events.

In the code, we check to see if the server or the player (local) is running the script. If it’s the player, we register to be notified when there’s a grab (grab start) and a drop (grab stop) event. Each of these subscriptions then calls a local handler to manage the specifics of the events.

```
private grabbingEventSub!: EventSubscription;
private droppingEventSub!: EventSubscription;
private ammoLeft!: number;
private totalAmmo!: number;

public start() {
  const owner = this.entity.owner.get();
  //When the server owns the weapon, ignore the script
  if (owner === this.world.getServerPlayer()) {
    console.log("Script owned by Server Player");
  }  else {
    // Connect to the grab event to cleanup when the weapon is dropped
    this.grabbingEventSub = this.connectCodeBlockEvent(
      this.entity,
      CodeBlockEvents.OnGrabStart,
      this.onWeaponGrabbed.bind(this)
    );

    // Connect to the grab event to cleanup when the weapon is dropped
    this.droppingEventSub = this.connectCodeBlockEvent(
      this.entity,
      CodeBlockEvents.OnGrabEnd,
      this.onWeaponDropped.bind(this)
    );
  }
```

### When a player grabs the gun

Function **onWeaponGrabbed()** does two things:

*   Assign the projectile launcher gizmo to the gun owner manually as ownership is not applied to child objects automatically.

*   Set up the input listeners for aim, shoot, and reload actions

### When a player drops the gun

Function **onWeaponDropped()** resets the actions performed when the weapon was grabbed:

*   Reassign the projectile launcher to the server (AKA server player)

*   Stop listening to input events

### When a player aims

Function **onPlayerAiming()** handles when the player is interacting with the aiming button. When a player is holding the aiming button, we subscribe to the update broadcast event to update the position of the dot on every frame. Otherwise, we disconnect from that event and hide the aiming sphere.

The Aiming pointer is different in VR, Desktop and Mobile:

*   VR: laser dot

*   Desktop: reticle

*   Mobile: reticle

### When a player shoots

When the player is either pressing or letting go of the firing trigger, the **onPlayerFire()** function is called. **Tip**: One technique used to debounce inputs is to respond only when the trigger is released. This seems counterintuitive for a pistol, but in practice it works.

*   First, we check:
    
    *   Is there ammo left remaining in the gun?
    
    *   Is the elapsed time since the last shot longer than the cooldown time?

*   If yes to both:
    
    *   Current time is our new last shot time.
    
    *   We trigger all shooting-related actions:
        
        *   launch the projectile
        
        *   play the gun fire SFX and VFX
        
        *   decrement ammo

### When a player reloads

Again, the function **onPlayerReload()** debounces the input by acting only on button up.

Taking ammo from the total ammo pool, we add as much ammo as the available space in the clip permits, decrementing the total ammo pool by the same amount. Also the “reload” SFX is played.

### Every frame when the player is aiming

The function **onUpdateAim()** is where we move the sphere to “project a laser dot” while the aiming button is held down.

Using the Raycast gizmo, we see if projecting an invisible line in front of the gun “hits” a player, entity, or the world. If it does, we reposition the sphere and make it visible to the local player only.

The gizmo returns a “hit” object. The “hit” object contains data about what type of object it is hitting. On this, we can change the color of the sphere to green for entities and red for players. **Note**: Things happening during the “Update” phase can end up slowing down your update loop and making us lose a frame (or many). If you notice that your game is “hitching” two ways you could mitigate the problems are:

*   Detect what you need to detect (i.e. the player moved) and fire a custom event to handle it asynchronously, and/or

*   Only do something after a certain amount of time has elapsed. Update provides how much time elapsed since last time it was called, keep accumulating until you reached a threshold (let’s say 0.5 seconds) and do something then. That will prevent calculations being performed every frame

*   Since onUpdate executes every frame, you can also choose to execute code every N frames, which is fairly simple to manage and tune. However, the elapsed time for N frames may vary depending on many factors.

### Update ammo display

When the reload or firing actions are executed, a call is made to **updateAmmoDisplay()**, which updates the script properties for 1) current ammo in the clip and 2) total available ammo.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 