# Setting up NPCs with Navigation

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/npcs/setting-up-npcs-with-navigation)

This page contains a transcript of a video navigating the NPC Example tutorial world. This tutorial is available from the Creation Home by selecting the **Tutorials** option from the Creation Home, then selecting NPC Examples.

The NPC assets used in this tutorial can also be used in your world, and their associated [NPC Scripts](/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-scripts) can serve as a reference for how to configure your own NPCs.

## Video Transcript

Hello and welcome to this video where we’re going to look through NPCs, how to configure and add them to your world, and give them animations and behaviors to get them walking around. This is all based on the NPC examples world \[see the [NPC Scripts](/horizon-worlds/learn/documentation/desktop-editor/npcs/npc-scripts/) documentation\] which you can access by creating a new world in VR and navigating to the Tutorials section when you are choosing your template then choose NPC Example.

That will give you this world where you can see lots of different ways you can use NPCs. Including these ones which animate, welcoming guests, chickens walking around randomly, Androids navigating around slopes following a set path, and monsters that come at you and attack you.

You can take these NPCs and build on top of them. Use the script however you want to add NPCs to your world.

## Enabling API Modules

In order to add NPCs to your world, that isn’t the sample world. The first thing you need to do in the world is make sure you have a couple of TypeScript API modules enabled.

*   Open the Scripts panel, navigate to the Settings.

*   Choose the API category and make sure you have both the `horizon/navmesh` API module enabled and the `horizon/UnityAssetBundles` API module enabled. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459269344_544194318118524_1595620973276139866_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=vmWsjhyV33MQ7kNvwFrMyab&_nc_oc=AdmKQT6oB-7qKXEhhWub7QwZoUZ584KMheap8T5q9mIWuv4pzfMnvjQhIGg_sLMSSo4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfReqvSSJF4QKkEL4dpAFIYjWBGM_PmlR0MJSLjqiAE5dg&oe=689B88EF) 

*   The NavMesh provides the capability for NPCs to walk around and you can create a navigable area for the NPCS to navigate.

*   The Unity Asset Bundles are needed in order to play animations for the NPCs.

## Adding NPCs To Your World

Once you’ve done that you can add NPCs to your world. To add NPCs Open the **Asset library** choose the **Interactive folder** and find an NPC you want to add to your world. 

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459370055_544194311451858_7123180166760742365_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=fkERychGTFQQ7kNvwH9HRN_&_nc_oc=AdmfP_1WiIKl1RcjUQPO1oaC0EeseHTHZyP0IuTD5ySVp1lvlrO97TZFXY3d2Rh8nCA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfSiG8qffcMTB5BOBk84Tb15gbdZH8W_AlXFtOqimdLyxQ&oe=689B9AD8)

Let’s add the NPC Android and let’s position it so it’s on the floor and get it looking at our player.

If you preview now, you can see that the NPC is idly animating, it’s an idle animation and it’s blinking and moving around a little bit. It’s not actually doing anything. Let’s bring the NPC down onto the actual floor. If we want it to follow the player around so that it looks at the player, there’s already a script in here set up to do that.

## Attaching Scripts to NPCs

Let’s attach that script to the NPC, we’re going to attach the NPC stand and look script. We will need to configure the head height depending on what the NPC is, and this is so that it is looking at the appropriate level. The good news is if you need the head height of any of the NPCs you can use these ones here.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459319421_544194314785191_8549108642023721563_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=BIbOue1-aysQ7kNvwH3QHdX&_nc_oc=AdmyU2zfapthNS5ZEC4sL83-2Zb2fX5o6qVksnPsQjMA5eo3YfNo6Y-JXYSubARk338&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfQ-gJjMt9qRNWi_z2MzCBLrvhO3w7NNnDeJCHiWeOlHgg&oe=689BADCC)

This one is set to 1.68, so let’s add that 1.68 to the head height. And now when I preview we’ll see that the npc will look at me as long as I’m sort of standing in front of the NPC. As soon as I go behind the NPC, it’s not interested anymore. So it will look at me whilst I’m walking around in front of it.

## Playing an Animation

If you wanted to play an animation, one simple way that’s already set up in here is to add a trigger so that we can essentially play the animation. Put that above the NPC and make sure it’s selectable in screen mode, and attach the trigger NPC emote script. It will need a reference to NPC so let’s drag it from the hierarchy into the NPC property, let’s rename it to NPC android so there’s something relevant and it will need the name of the animation. At the moment it’s going to play an emote celebration so now when I interact with that trigger, the NPC is looking at me and playing that emote.

For a list of all the different animations you can use, head to the NPC Agent script. You’ll see all the different emotes up here.

```
export enum NPCAgentEmote {
  Wave = "EmoteWave",
  Celebration = "EmoteCelebration",
  Taunt = "EmoteTaunt",
  Yes = "EmoteYes",
  No = "EmoteNo",
  Point = "EmotePoint",
}
```

We should mention that certain NPCs have certain animations, so the android for example has celebration, yes, no and waving emotes whereas the skeleton doesn’t have celebration and yes or no, but it does have taunt, and it does have the ability to attack and it also has a hit animation and can play a death animation if it takes too much damage.

```
// Public methods
triggerAttackAnimation() {
  this.triggerAnimation("Attack");
}

triggerHitAnimation() {
  this.triggerAnimation("Hit");
}

triggerEmoteAnimation(emote: NPCAgentEmote) {
  this.triggerAnimation(emote);
}

setMaxSpeedToWalkSpeed() {
  this.navMeshAgent_?.maxSpeed.set(this.props.walkSpeed);
}

setMaxSpeedToRunSpeed() {
  this.navMeshAgent_?.maxSpeed.set(
    Math.max(this.props.walkSpeed, this.props.runSpeed)
 );
}
```

## Playing Different Animations

To play a different animation all you would need to do is copy from here and paste it in the trigger NPC emote properties and there we go, so now it’s doing a yes animation. A little bit more info on how the animations are played, if we scroll down in here we’ll see there is this trigger animation function which we can call from the class, and essentially we do this line of code here.

```
triggerAnimation(animationName: string) {
  if (animationName === "Death") {

    // Kill and revive if this is the death animation
    this.assetRef_?.setAnimationParameterBool("Death", true);
    this.async.setTimeout(() => {
      this.assetRef_?.setAnimationParameterBool("Death", false);
    }, 4000)

  } else {
    this.assetRef_?.setAnimationParameterTrigger(animationName, false);
  }
}
```

AssetRef is a reference to the Unity Asset Bundles that’s underpinning the npc and we set the animation parameter trigger and pass in the string of the animation that we want to play. This property is true or false, true if you want the animation to play locally or false if you want it to play in the default mode on the server.

We should add that the death animation is slightly different because you’re actually changing the state of the NPC, it’s not just playing an animation then returning to how it was before. It is going to play this death animation and then stay lying down on the floor. So we actually are using the set animation parameter bool, passing in the death string and then true to say that we’re making this NPC death true.

The death boolean is now going to be true, and when we want the npc to get back up, we just do the same set animation parameter bool and death string, and we pass false so that it stands back up.

We’re essentially setting whether this NPC is dead or not using this true or false here. True is dead, and false is not dead. So if we wanted to we could make NPCs get killed. That’s how we’re playing the animation behind the scenes.

If you don’t want to go this far into the code. You could just add the NPC stand and look script. And they’re in here and there’s an event declared at the top of the file, so you just would fire the play animation event to that NPC, passing in the name of the animation you want to play and an optional parameter of a player and essentially when we sent the player in there too, the NPC will look at that player when it plays that animation.

```
export const LookAtPlayer: hz.LocalEvent<{player: hz.Player}> = new hz.LocalEvent<{player: hz.Player}>('LookAtPlayer');
export const StopLookingAtPlayer: hz.LocalEvent<{player: hz.Player}> = new hz.LocalEvent<{player: hz.Player}>('StopLookingAtPlayer');
export const PlayAnimation: hz.LocalEvent<{animation: string, player: hz.Player | undefined}> = new hz.LocalEvent<{animation: string, player: hz.Player | undefined}>('PlayAnimation');

export class NPCStandAndLook extends NPCAgent<typeof NPCStandAndLook> {

  static propsDefinition = {...NPCAgent.propsDefinition,
    lookAtAllPlayers: {type: hz.PropTypes.Boolean, default: true},
    changeTargetDelayMin: {type: hz.PropTypes.Number, default: 1},
    changeTargetDelayMax: {type: hz.PropTypes.Number, default: 5},
  };

  static dummy: number = 0;
  players: hz.Player[] = [];
  playerToLookAt: hz.Player | undefined;
  reevaluateTimer: number = 0;
```

So it gives us the ability to look at a player and then play that animation.

## Configuring Locomotion Navigation Volumes

Let’s now look at how we can configure them to walk around. So we’ve got our Android here and let’s look at how we can make it walk around. The first thing to do is you will need to go to the **Build menu** and go to **gizmos**, and add a **Navigation volume**.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459347215_544194321451857_6608550143407856920_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=adloF0R16oYQ7kNvwEwQGOz&_nc_oc=AdldxtLDkxezBZfuY_kRrCE-VAk2WDtpTj6zLl7MiJe0sh3pe_4Emh8hqXLBPmj7A7I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfTZ045oVdDW69-0gyDZKuo2e7_MNbuLIDELiXQ2SEWxRA&oe=689B9490)

The Navigation volume will be used in order to tell horizon worlds what areas are navigable by the NPC. So you want to stretch this box out to cover the entire floor of what you want to be navigable. Then in our systems drop down, in navigation. If you don’t have a navigation profile already set up, so if you’re not using this world. Then you’ll need to add a new navigation profile.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459317814_544194298118526_5839231836815291134_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=CbB5NtQyVogQ7kNvwHb7o-U&_nc_oc=AdnhSvkxI9gTof3Xgmu1drpH-8ehYvrseRfwSjDPQTqrN4NcbdUlmHwKJc4PHbuWmlM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfT3pnpNu6pFmNtvnZacnwrb0sNvJBQ65zMQ5ZrgDdsB-w&oe=689BA20E)

Give it a name and you can customize what kind of areas are going to be navigable by the NPC using these four properties.

| Property | Description |
| --- | --- |
| Agent Height | How high an area needs to be in order for the NPC to navigate underneath it. |
| Agent Radius | How wide an area needs to be in order for the NPC to be able to walk through it. |
| Agent Slope | How steep a slope an NPC can walk up. |
| Step Height | How high an obstacle needs to be before it will block the NPC. For example, a small stone would be easy for the Android to step over and a bigger rock might be more difficult or might actually obstruct their path.These properties could be different for the Android as opposed to the Chicken. It would be able to step over a smaller stone. |

Create your agent profile and make sure that it is set up, and then you can click bake and that will then take any navigation volumes, and figure out which of these profiles can navigate which areas within those.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459413997_544194304785192_7860506433198863050_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=KdY3ITg6VYEQ7kNvwGw4kED&_nc_oc=AdldaP0sgWvjcYYE65WqxbIuF1WhNkfV6OUDA7v3CIbwdWZJPd9PMBIO3J5SYEIH7gU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfREhaGqX2N7TPIu13ilTGs1uAKIfek4jhTcnbmen7F9PQ&oe=689B8880)

It may look like it didn’t actually do anything but if we toggle on all of these layers we can see which areas are navigable by which navigation profiles. I’ve set all of them to be navigable for all, but for example let’s say if you wanted to see what areas only the monsters can navigate, you can see these areas here for example.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459412835_544194308118525_6094526220034398795_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=b2OxjKihhfQQ7kNvwHLtsfc&_nc_oc=AdmlKD5ZdJZ-ZJPv4mR0i6c9QAgEfSMWxQB4shOBL9hfyqdh6hhjXIMbq_Ke334-IPs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfTh8sj1-py2-3CYQJpMxFYGBe4sfYhJb8-QtaRtUcc08g&oe=689B9ED8)

## Enabling Navigation Locomotion

So, once that has been baked the next thing we need to do is enable the navigation locomotion and disable **Include in Bakes** for any NPCs that we want to be walking around. We need to make sure that the NPC has a navigation profile. So let’s give this one the Android profile and then we can enable **Physical Surface Snapping**.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/459238994_544194301451859_1839034915096672522_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=yRWu-gpQ6mAQ7kNvwFDDQzM&_nc_oc=Adlj9lpQDZ9M-Ugx0_PvTYYRKBQk_SxCs2ozPbExJ0GngEFTQRfoUsrTx4qXB2O-I9g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Zfy_hZd4EvemeRw9mFi3JQ&oh=00_AfT3FMlwWg_om01g0NNSqpYaCtBe0rbEoEw17L_BbCLdjA&oe=689BA642)

It is recommended to turn this on if you have anything in your world like slopes, so that the NPC is always walking on the floor.

Once that is done, we’ll use a different script for this NPC. If we give this the NPCChicken script, we can give it a reference to the Navigation volume, then the NPC will walk around the navigation volume. It will choose a location at random, it will look at it and then it will move towards it. That is what the NPCChicken script does. It is essentially giving it random destinations and making it move around those.

```
setNewDestination(destination: hz.Vec3){
  this.isIdling = false;
  this.lookAt = destination;
  this.async.setTimeout(() => {
    this.entity.as(NavMeshAgent)?.destination.set(destination);
  }, 300);
}

findNewDestination(){
  this.destinationAttempts++;
  const rPosition = this.getRandomDestination();
  const delta = rPosition.sub(this.getHeadPosition());
  const dotFwd = hz.Vec3.dot(this.entity.forward.get(), delta);
  if (delta.magnitude() > 4 || (dotFwd < 0.1 && this.destinationAttempts < 5)) {
    this.async.setTimeout(() => {
      this.findNewDestination();
    }, 200);
  } else {
    this.destinationAttempts = 0;
    this.setNewDestination(rPosition);
  }
}

getRandomDestination(): hz.Vec3 {
  const rx = Math.random() * (this.boundingBox.max.x - this.boundingBox.min.x) + this.boundingBox.min.x;
  const rz = Math.random() * (this.boundingBox.max.z - this.boundingBox.min.z) + this.boundingBox.min.z;
  return new hz.Vec3(rx, 0, rz);
}

update(deltaTime: number): void {
  super.update(deltaTime);
  if (this.navMeshAgent !== undefined){
    const distanceToTarget = this.navMeshAgent.remainingDistance.get();
    if (distanceToTarget < 0.1) {
      if (!this.isIdling) {
        this.randomIdle();
      }
      this.newDestinationTimer -= deltaTime;
      if (this.newDestinationTimer <= 0) {
        this.newDestinationTimer = this.getNewDestinationDelay();
        this.findNewDestination();
      }
    }
  }
}
```

## Additional Scripts

If you want to get involved in the scripting side, you can take a look at the NPCChickenScript. The way that we get an NPC to move towards a new destination is by using `this.enity.as(NavMeshAgent).destination.set`, and then we pass it a `Vector3`.

```
setNewDestination(destination: hz.Vec3){
    this.isIdling = false;
    this.lookAt = destination;
    this.async.setTimeout(() => {
      this.entity.as(NavMeshAgent)?.destination.set(destination);
    }, 300);
  }
```

We are essentially saying move towards this destination, and that is the same for all NPCs.

If we look at the NPCMonster class, it’s the same thing, except we are passing the player’s position on every frame. This script is also able to figure out on every frame who is the closest player and tells it to start walking towards them.

```
private updateWalkAndRunStates(deltaTime: number) {
  if (this.targetPlayer === undefined) {
    this.setState(NPCMonsterState.Idle);
  } else {
    this.navMeshAgent?.destination.set(this.targetPlayer.position.get());
    const distanceToPlayer = this.targetPlayer.position.get().distanceSquared(this.entity.position.get());
    if (distanceToPlayer < this.props.maxAttackDistance*this.props.maxAttackDistance) {
      this.attackTimer -= deltaTime;
      if (this.attackTimer <= 0) {
        this.attackTimer = NPCMonster.attackAnimationDuration;
        console.log("Trigger attack animation");
        this.triggerAttackAnimation();
      }
    }
  }
}
```

We can see this script in action, If I check that my navigation is baked for the monsters layer. I can preview from here.

The NPC Monster will ignore any player until they pick up the sword, when the player picks up the sword, the monster will register them in an array of players, check which one is the closest and move towards them. They also have a trigger volume attached to these NPCs, so when a sword enters that trigger volume it registers as a hit and plays a hit animation. If it takes four hits then it plays a death animation.

So that is how to set up NPCs, how to set up their navigation. We recommend you take a look at this sample world to explore and see what else you can do. You will find Androids with which you can pass them an array of points and they will move between them, you can then add some more logic there to tell them which point to go.

We are excited to see how you will use NPCs in your worlds!

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 