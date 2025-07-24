# Physics best practices

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/physics-best-practices)

## Collidable objects

Collidable objects in the world require physics processing to determine if something is interacting with them. Optimize physics processing by disabling colliders on any objects that aren’t interacted with or are outside the game play areas. In manual traces, large numbers of colliders will be reflected in Physics.Simulate times. If you have access to developer builds of Meta Horizon Worlds, the number of colliders in the world will be broken out in the Physics::Overlaps # trace. As a rule of thumb, the number of overlaps should be kept below 400.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452877335_512527657951857_3801136528294471333_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=3sZ6CMi2hf4Q7kNvwHmgdwG&_nc_oc=AdkXa-ILcZTJ056URrM9mlqVPIDQ0RepeBBNyXgCm4dVTKJeTxmEb3nuhGRKIF78eoY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfS5sTkIBQxOxJmXeHI8MEbo09ykf3mkwJ_PGy6-b62k6w&oe=689B9E59) *UpdateRunner::PrePhysicsUpdate and UpdateRunner::Physics.Simulate in high collider world* To view colliders in the world, toggle **Collision** in the **Utilities** menu. This highlights all collidable objects in the world with an orange tint.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452946039_512527631285193_2371780646691338084_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=UQB1vMk4lfEQ7kNvwH6iinY&_nc_oc=Adkk-I430EFv7QmDkGmOgj-YNDkuA_1RNEgum1HSUnf-dbu15pcatjMu0t1FAmHmpZ8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfSf65FkaDEcE46Cfa4Bu7Ye55t30yDelYQRZ9f0Hn73Eg&oe=689BA87D) *Collision in the Utilities menu*![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452756686_512527627951860_2329805199404162916_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=sJrPoSuT0QsQ7kNvwHRiJsn&_nc_oc=AdkQr0M-Lqf63fKy7bVzdufvP4hWi1yYwrV6Kay7p2swU6Vcodn7nPDvSbYq3z0XqxA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfTlW2-B-FLcqyEh6T1-NP6cpXwGYGMFF_UaYrQrVm6tDw&oe=689BC5C1) *Collision off*![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452753829_512527634618526_2579740434491253389_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=VeNE36VTb9YQ7kNvwEZDGig&_nc_oc=Adn1FK1GdlZk548q6VlDLgt8IF578yj5g1LM8cREJsoOfaBDPHoaEweUIsZ_h1emqFY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfT89bU40GnPKs8OTo_H974E7Xs0hLqWTW2g0jKUjGcMGA&oe=689B9D0C) *Collision on* With highly detailed objects in play, disable the detailed colliders, then wrap the detailed object in a primitive collider such as a cube (best), sphere, or capsule collider. This only requires one physics test for collision and usually results in no loss of functionality or visual fidelity.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452665277_512527621285194_3611445575214330481_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=8PPG2qjbSr0Q7kNvwG3OFQr&_nc_oc=AdkaoQMOVdNMmQgq3bAmfswXbpQ1nKEHjLyaKhDDwVHiupYrOEG8f_hb3voxEORXxr0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfT54yqTQFoFubFkmhAzYX8PpNt-Nh7zCRt66-VLtzKMjA&oe=689BBB25) *Complex object made of non-collidables with simple collidable cube*![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452863867_512527617951861_5367078100115098540_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=kGXCKvPRRRIQ7kNvwGN4DQm&_nc_oc=AdkQhCfQ-Gn7kBI1g9Th6fQrXc4NGPAXystjENEsEemaCP9dVWCum0ErgprJOIDXA_I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfRinxW2r3owsB6cD-nS9n5S8Tqh9NjF1uWf6dHYGZjCnw&oe=689B9505) *Enclosed in a non-visible collidable object* For best performance, you should attempt to leverage primitive colliders (as shown below). The only exception is for things that you collide with very often/all-the-time may be better as a single, large mesh. Testing can help determine which gives better performance.

This is especially true for worlds that are using [Custom Model Import](/horizon-worlds/learn/documentation/custom-model-import/getting-started-with-custom-model-import) , as using non-mesh colliders and non-primitive colliders will incur an additional, high, and spiking cost associated with rendering.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452910318_512527614618528_4434551703431817239_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=FkKMHcGSaz8Q7kNvwFrVVhW&_nc_oc=AdnEltpEEvt_IXXStaoBIxbuVCvRX5ar87G33tKIg3q4PHe4GMiwgmpjfA0Z5kITuPk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfQyvZFDO1_9YjALyofZG9aWUqHSeGUK8RUY4cpjb3Z4sA&oe=689BA3FA) *World Editor showing raw primitive colliders* ## Grabbables

In order for grabbables to have good performance, it is important to minimize the number of collidable components on the grabbable object. For a rule of thumb, the maximum number of collidable components any grabbable should have is 2.

## Triggers

The number of triggers in the world has a runtime cost associated with it. This is seen by an increase in *Physics.Simulate* and the *TriggerRuntimeIntegration::Update* markers. Active triggers still have a runtime cost in the world even if they are inaccessible to the player.

Even objects outside the player area that have a trigger will still contribute to frame time.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452954317_512527611285195_3156202454148406245_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=TZlWvQN7umYQ7kNvwGpJuIM&_nc_oc=Adm3HQQhMbBwwKIucdhsU6q3tw8qQmNytfElRALW176GLqjYF-COqIioF5Pdfv8hBCA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=h27BnViNaBAeJ4KURWYkCA&oh=00_AfSLvDmcBZe5_VS19t1cJfgAk5xbYtvpZ2KSxoXhERN4vw&oe=689BAE02)

For best performance, disable triggers far away from the player, in areas like buildings (until the player enters the building), and areas inaccessible to the player.

## Collidable property

Entities when using the Scripting API have a [collidable property](/horizon-worlds/resources/scripting-api/core.entity.collidable.md/?api_version=2.0.0) that can be enabled or disabled. In worlds where the physics cost is high, and players are collectively moved to another area such as PvP worlds, consider setting the collidable property to false to turn off the colliders in areas the players aren’t present. Since this is a bridge call, as mentioned in the [CPU and TypeScript optimization and best practices](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-best-practices/cpu-and-typescript-optimization-best-practices#typescript-optimization) , ensure these are spread across several frames to reduce any spikes during gameplay.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 