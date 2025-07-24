# Adding and manipulating objects tutorial

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/batting-cage-tutorial)

In this tutorial, you’ll learn how to create a simple Meta Horizon Worlds game. The tutorial shows you how to create a world, add assets to it, write scripts to attach to entities to create behavior, and try going to the world on a mobile device and in virtual reality.

The key learning objectives are the following:

*   Writing TypeScript code

*   Setting entity ownership

*   Handling object collisions

*   Trying the world on mobile and in virtual reality

## Prerequisites

This tutorial requires you to use the Meta Horizon Worlds desktop editor. See [Install and run the desktop editor](/horizon-worlds/learn/documentation/get-started/install-desktop-editor) for instructions.

## Section 1: Create a new world

In this section, [create a new world](/horizon-worlds/learn/documentation/desktop-editor/getting-started/creating-a-new-world) for your game. **Note**: When you’re building your world, Meta Horizon Worlds automatically saves your progress and it’s part of your online save flow.

## Section 2. Create an avatar, a bat, and a ball

In this section, you’ll spawn an avatar into your world, and then you’ll add a baseball bat and a baseball to your world.

*   Select the **SpawnPoint** gizmo in the Hierarchy. This is the avatar.
    
    ![Select the spawn point gizmo in the hierarchy](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462689916_564911232713499_6993527411397223752_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=A6pKuX_ZFA8Q7kNvwHf0P5l&_nc_oc=AdlzX518oJVQpoxWP3EDxpSypWA0SdFQaeltnoPsxey0N70ElVzirKQaeteuDOwV3ck&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfTSW49AbYYenQWadO9d38j2hFft9nTKvzqYUFieRnSDEA&oe=689B9259)
    

*   Focus the camera on the avatar by pressing the “F” key.
    
    ![Focus the camera on the avatar](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462608481_564911246046831_3937497365964477693_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=bAsCLVd8_RwQ7kNvwHSUbgA&_nc_oc=AdnCzgzKpTbzqo5dpVvOG9rI5Gyg1WM1HpzF_Ea7OvDHVJ11Ozci8VMS7B5MxOX06Ww&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfToa_ApJNRabSimqxY4KFv2qyT45fmeSlIK64sxE24Egg&oe=689BA7DE)
    

*   Spawn a new cylinder object into the scene, and name it “Bat”. Click **Build** \> **Shapes** \> **Cylinder**.
    
    ![Spawn a new cylinder object into the scene](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462701132_564911262713496_1343372135349431875_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ef340Zd15SQQ7kNvwFzIGzt&_nc_oc=AdlEk8kgRPaNrKHkr_P6ySRG5cBiq6Wz0aCutc9ehV-rYQ_LY0UymxUyAHv7umZaLA0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfT6GLuyFU3dx4-y163KzgeHDHFimb0m9tTwucyygSIEQA&oe=689B93F1)
    

*   Spawn a new sphere object into the scene, and name it “Ball”. Click **Build** \> **Shapes** \> **Sphere**. Your Hierarchy should now look like this:
    
    ![Spawn a nhew sphere object into the scene](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462654269_564911229380166_1772788500717622981_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=u38-sfYecN4Q7kNvwHsr26T&_nc_oc=AdkDXZmRfGJ_suFe47BZ8rJYU4n3QvL-DkhHCLlkHwZyjcHevHg8dKoCPJLaTK1tfKo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfT8zXr_AKfvzgLHxOVHA2nuTnwiJs_zlyiLBPwHeeJDaw&oe=689B9B1D)
    

*   Resize the cylinder to resemble a bat, and place it in front of the spawn point.
    
    ![Resize the cylinder scale values](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462644158_564911279380161_1594296782694451642_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=lel5IG6XW2UQ7kNvwH425Ad&_nc_oc=AdmBa4XbWbMNnJb_vrHmzfbEJO6ZAl6Glmy-HLTSlgh4t0MQJkHvh1P1GDNTWiPKL88&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQnJ8C8KAMRByBzKY670U1Aa_lICRkmxs6Vvu4DNpOfNA&oe=689B8C4E)
    

*   Place the bat in front of the spawn point. To move the bat easily, activate the on-screen Position Manipulator Handles by pressing “W”, and then drag the bat to where you want it.
    
    ![Place the bat in front of the spawnpoint](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462602432_564911236046832_1495750191451500905_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=DY111FbHR6oQ7kNvwFXW92F&_nc_oc=Adns1CuMHEhxYEQJA738ar-rp1ajuHK57ZYoBNjulJdRFdvuf-I72W7U-wGfxA2Ywd0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQxamTk8RF95Tm6P9887o5P29XO0QKmoorCpNKDEIsooA&oe=689B8F4E)
    

*   Resize the sphere to make it the approximate size of a baseball.
    
    ![The resized scale values](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462602083_564911192713503_7226210735996448903_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=NCgul8LNrhkQ7kNvwFs37Cp&_nc_oc=Adn0hz0J7Zc5_wooYZH_EJolVi3ylAJ4htmyFYaNrVkSQndoJ0bTfp0CKXHx3B5jKng&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfTJqV1wNNNPjQwoZYxN5NMFvigZnKUwlctg3QsF12in5Q&oe=689BACB4)
    

*   Reposition the ball high in the air, slightly in front of the spawn point.
    
    ![The ball's new position values](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462683031_564911219380167_3082134887712278052_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=ICaFcuMK6hcQ7kNvwHD0pBx&_nc_oc=AdnnLGhhKZDpKR-dH2TpmTe5fOkb2gJ-ta2W_pA8d5Dx6lQJadRmEij5KCbUm86GLVI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfT_-AVrcOG0h6BB9p65h_LtVKjQBoHzu9huBU1IAi8pgg&oe=689BBE47)
    
    ![This is what the ball looks like high in the air](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462748814_564911202713502_6576691860851034977_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=v0LcPvVkwTQQ7kNvwEYTw9X&_nc_oc=Adkwu1yqHnoaiTSr8fJGeyR5PCjfedM7nPIJsg8mhmwK7Jb2RdMIrKJK81nZGB1uOYk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQnYxAWtpZOSY3CWK4ktQKAGLAU-s40LW2h2TK5bw22hQ&oe=689BA5D6)
    
    You place the baseball up high because it will take time to fall down to the player, and the player needs this time to grab the bat.
    

*   Set the **Behavior** properties on the ball.
    
    *   Select the Ball object from the Hierarchy.
        
    
    *   Enable **Collidable**. This ensures that the ball can collide with other objects.
        
    
    *   Set **Motion** = “Interactive”. When you set this value, the **Interaction** property appears.
        
    
    *   Set **Interaction** = “Physics”.
        
    
    *   Enable **Gravity**, and set it to a custom gravity value to make the ball fall slower so it’s easier for the player to hit. For example, try using a value of “-0.20” instead of the default “-9.81” m/s2.
        
        ![Enable gravity](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462687098_564911276046828_8376701341943687081_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=FVksnKZy5SEQ7kNvwFGyMVN&_nc_oc=AdkrXrjTZSUD68UrzOPf5_5rxT6WrRpTDpzt9CP2gu8PRl_AXAnuYvPtrWzf-tvnT2g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQtwA5sKLipg-s4BH1iZ9eMle0a3Tmq9-PRmmSoEwm7iQ&oe=689B9D7C)
        

*   Set the **Behavior** properties on the bat.
    
    *   Select the Bat object from the Hierarchy.
        
    
    *   Enable **Collidable**. This ensures that the bat can collide with other objects.
        
    
    *   Set **Motion** = “Interactive”. When you set this value, the **Interaction** property appears.
        
    
    *   Ensure that **Interaction** = “Grabbable”.
        
        ![Interaction equals grabbable](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462602868_564911266046829_5568516108201599638_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=G0S32UuL0PwQ7kNvwEVfkh0&_nc_oc=AdnNgPenNUO311OjeXMPqyhhA2MXjbLB7uG3XwFxf03K5rH_2CphPug17H5BAM__Q1E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfSIHHyXx1ZISqT0aX0ZSPdYJqtmiN9Qz94OFUG6JOiabQ&oe=689B9DA7)
        

When you run the simulation, the player spawns into the world. You can move the avatar over to the bat, and you can grab it, but you can’t swing it yet. The ball falls down a couple of seconds later.

## Section 3. Create the floor, and setup ball reinitialization

In this section, you’ll create the floor, and then configure collisions with it.

If the player swings at the baseball and misses, the ball simply falls to the floor. But when this happens, the ball should automatically move back to its original starting position, and then fall all over again. You need to add the code to accomplish this.

*   Spawn a new cube object into the scene, and rename it “Floor”. Click **Build** \> **Shapes** \> **Cube**. Your Hierarchy should now look like this:
    
    ![Rename the cube object floor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462748808_564911242713498_8185972744048961801_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=_-fQknppYi4Q7kNvwHWcLd4&_nc_oc=AdmTZuSsoReJT7Q0U0VbfFSbIlkoJZUDvYbFCsz5oGypBAFqAAxjj66ODLfd2-F89WI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQChGi1RsnErfqyKzU516Bxi2KtpsbfXGEXDjqRK8Z1Lw&oe=689BB7A1)
    

*   Change the dimensions of the Floor object so that it covers a relatively wide playing area.
    
    ![Position and scale the play area](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/472754953_626753169862638_6178594729083770490_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=AAgE12x7O2cQ7kNvwFCWXfm&_nc_oc=Adn6IhSAnbjjidgLaUkKiB0XkQTSo1hvmmM0Tm8_RIGJlRlWI3EXlu21mB4mRr2uPtg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQTSMCOAkEJeFW2h5QuAtMSMTV1I6iXJhGG0AdpgOHY3Q&oe=689B8E7A)
    
    ![Your floor should look like this](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462676686_564911212713501_468507077804114298_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=Z7mu-Jgfje4Q7kNvwF3J5EH&_nc_oc=AdlAUo9_MVuouukzDbiQGI_AUsS-7VG2k3PZzkf-qK5o6BU8nNWQzzA5IcFsuEHB3Yc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfTfx6MEmDepmmh119JMCxsWBUNGz4ZHwHHl5fKVK_675A&oe=689BB46C)
    

*   Add a **Gameplay Tag** to the Floor object, and name it “floor”.
    
    ![Name the gameplay tag floor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462608655_564911259380163_1890197524559525651_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=EAxXGlFLn4MQ7kNvwGUmQZZ&_nc_oc=AdkkKdnqC0Tf5yXxZVKXvbYCHUYu28mGNrgxZ7YBHQUgaAWxLwJhO2sjg8qm4k8N_bA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQG_iKDMqT8eazw5GlP9t30EzzZrDo4HZl9xG7oLBacTA&oe=689B9A77)
    

*   Select the Ball from the Hierarchy.
    

*   Set the following **More** properties on the Ball.
    
    *   Set **Collision Events From** = “Objects Tagged”.
        
        ![Collision events from objects tagged](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462701412_564911199380169_7425995930029656028_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=JAlUIOm4AuIQ7kNvwF7Qwaj&_nc_oc=Adm40iS18nSaKhkbr_j_7Tp7MYd-RVBn7hWj1qWS3Ef7IHhJyd5DXF44Hgt2Pfieg4Y&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQl2WMpes6IDYx9stn8v4uPEOWJoATBcga8wh1nF95PYg&oe=689BAA05)
        
    
    *   Set **Object Tag** = “floor”.
        
        ![Object tag equals floor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462706481_564911196046836_4280703734366345331_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=Y46uzwv6cqgQ7kNvwFGWpe_&_nc_oc=AdmCQcWCYrhZx0sdyyaDIgqfER-IShj-2PsjjDV5ABbnAJ11-9tzDn0Cw-Bs5w3sYSs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQxB6FelBYOL3kJzJbnTPVNl8vWT5CIhZEpeb0j6RErLA&oe=689BB23C)
        

*   Create a script to control the Ball’s behavior. The code listens for collisions between the Ball and the Floor. When a collision occurs, the code resets the ball’s position back to its initial starting point, and it resets its velocity back to zero.
    
    *   Click **Scripts** to open the Scripts panel.
        
        ![The scripts panel opens](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462687098_564911182713504_6689004367218443217_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=hoilWtCOy1sQ7kNvwG7zjYo&_nc_oc=AdmiXlgab9kAiF8OID7yMUuFSBifXI2oRyc29jgUCM3PD8Jh2QYZTWaS9oXyNCcfQiY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQ7zu9TgVp8m1F1pVw3TTh8DFgWSOh-zrsowZ7V5hKLGw&oe=689BA3F3)
        
    
    *   Create a new script by clicking **Create new script**.
        
    
    *   Name the script “BallScript”, and then press **Enter**. The script is created.
        
        ![BallScript appears in your list of scripts](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462671462_564911282713494_2780281265974661818_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=6BwFWdnp8fEQ7kNvwGrNxNL&_nc_oc=AdmGifEFCH56NA9VR63-TfdXQOf5Qsmr5px-XJvzEfDVnUzvEGPPaCnUJU9YWl35CIo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQTUYQ-iaIsgvDqsBaRmNtE8ljZKRF5MG2MjYsCtDXwXw&oe=689BBE2D)
        
    
    *   Open the script in VS Code. Click the menu icon to the right of the script name, and then select **Open in External Editor**.
        
        ![Open the script file in VS Code](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462690751_564911239380165_8519164833044724963_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=hqzh7jNa79oQ7kNvwEzT5yv&_nc_oc=AdnMVrkwDl-CqAHvEHQNtlFmAnkGnQgQ_u48-do6OnZShBfvFX1ZYuvPG_WhdaIHQ68&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfTTudDMY4ExRQH4Dx4S1j8nSmtaMHSSXHFHPnB3mdxmWg&oe=689BB485)
        
        VS Code launches, and opens a new TypeScript code file that contains a default class.
        
        ![The new typescript file opens in VS Code and it contains some default code](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462652837_564911249380164_5111626863521496440_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=metmGDKx5cAQ7kNvwF_rLzS&_nc_oc=Admpx3BpWQyLhYb5bzQ85IjykMegr_VFbeedafzNpu85AdZ16TOf7vtY4PjaEJl2Ogw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQPlZb6VkIrO7W2kiNj5rPlLkEz0RCMwKn__MfaMvtC7w&oe=689B97FA)
        
    
    *   Copy the following code snippet, and paste it on top of the default code in VS Code, and then save it.
        
        ```
        import * as hz from 'horizon/core';
        
         class BallScript extends hz.Component<typeof BallScript> {
        
             static propsDefinition = {};
        
             originalPosition: hz.Vec3 = hz.Vec3.zero;
        
             start() {
                 // Set the original position of the ball so you know where to respawn.
                 this.originalPosition = this.entity.position.get();
        
                 // Listen for ball collisions with any other entity.
                 this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnEntityCollision,
                   (collidedWith: hz.Entity, collisionAt: hz.Vec3, normal: hz.Vec3,
                     relativeVelocity: hz.Vec3, localColliderName: string, otherColliderName: string) => {
        
                         // Move the baseball back to its original starting position.
                         this.entity.position.set(this.originalPosition!);
        
                         // Reset the baseball’s speed to zero.
                         this.entity.as(hz.PhysicalEntity)?.zeroVelocity();
                   });
             }
         }
        
         hz.Component.register(BallScript);
        ```
        

*   Attach the BallScript to the Ball object.
    
    ![Attach the BallScript to the Ball object](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462704360_564911222713500_3418776293222919275_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Bxps4ADIqrgQ7kNvwHS925R&_nc_oc=Admx_IhG0w8_BcnRCmHLJzz7PhfOvLCLv8j7AnvK9CiBbgnFb_pU30q_1l_cpj4jBrs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfT9I0qhC5uDlJm5oOn3CymTx6mpgEGrkJnTlJd8FZdG-g&oe=689B8937)
    

*   Preview your new world in the Meta Horizon Worlds desktop editor. Enter Preview mode by clicking Play on the menu bar.
    
    ![Click the little person icon to enter Preview mode](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/476463623_647505964454025_8787956898410179165_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=Dkej8ZGOUrQQ7kNvwGJJFus&_nc_oc=AdlSWpJBIgpG0d1u-cubrhzevFiPwZhO-KqgvRvsSseY9wbaVJ91z3UG-Ind7rgnOhg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQypStF_DoLxz2_k5mkeYcfEeGoht_amL_MnBcttZfg_w&oe=689BB061)
    

*   Maneuver the avatar over to the bat using the arrow keys, and then grab it by pressing the “E” key.
    
    ![This is what you avatar looks like after grabbing the bat](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462694517_564911206046835_4033375668500902553_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=3RbiYQneFgQQ7kNvwHlfiaH&_nc_oc=Adn8Pr3xA-A2csSpndj_KJPOk8IZEFXx2D1fQlWsAriUGGYyt7VPJ3_rnaab2zr4Br8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfSExQGbiSOprkQwsRTtPjFaPF1tWwi8Jp0azR2rdU0v4w&oe=689BA79B)
    
    You can’t really do much at this point except walk around holding the bat. As you do, the ball continually keeps dropping out of the sky and falling to the floor.
    

*   Exit Preview mode by pressing **Escape** twice.
    

## Section 4. Setup baseball/bat collision detection

In this section, you’ll configure collision detection.

*   Select the Ball object from the Hierarchy.
    

*   Add a **Gameplay Tag** to the Ball object, and name it “ball”.
    
    ![The Ball object has a Gameplay Tag named ball](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462704007_564911272713495_8171981578080402896_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=0dlzhIyn-3AQ7kNvwGfiyIx&_nc_oc=AdlkAymjGhLeSDmcbDnnBA0SXo7_erOhH-ahmq3A7dzoxAJMjvJUaVK-VVzJ67iHnGw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfTJhFcGyB09a0Yd2uV9pL8m3DLqwa0nSkwODw6rhYDR7A&oe=689BA32F)
    

*   Select the Bat object from the Hierarchy.
    

*   Set the following **More** properties on the Bat object.
    
    *   Set **Collision Events From** = “Objects Tagged”.
        
    
    *   Set **Object Tag** = “ball”.
        

*   Create a script to control the bat’s behavior. The code listens for collisions between the bat and baseball. When such a collision occurs, the code displays a message pop-up that congratulates the player for successfully hitting the baseball.
    
    *   Click **Scripts** to open the Scripts panel.
        
    
    *   Create a new script by clicking **Create new script**.
        
    
    *   Name the script “BatScript”, and then press **Enter**. The new script appears in your scripts list.
        
        ![You now have two scripts](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462718796_564911226046833_3172925499326887543_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=M8sDX9wJ-lAQ7kNvwEJQW7p&_nc_oc=Adk7TWHdqT8CkMPMmQ1xV3M2DWy5_cOu2ZlgISEVI8iUMueYZ8swJguVUa1pO8iAmxU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQ-2cIHRzYjwjfGlQ-bJv2onMH0YwagJiCRg1X3iIfo2A&oe=689BBB1F)
        
    
    *   Open the script in VS Code by clicking the menu icon next to the script name, and then selecting **Open in External Editor**.
        
    
    *   Copy the following code snippet, and paste it on top of the default code, and then save it.
        
        ```
        import * as hz from 'horizon/core';
        
         class BatScript extends hz.Component<typeof BatScript> {
        
             static propsDefinition = {};
        
             batHolder: hz.Player | null = null;
        
             start() {
                 // Set the player holding the bat when they grab the bat.
                 this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnGrabStart, (isRightHand: boolean, player: hz.Player) => {
                     this.batHolder = player;
                 });
        
                 // Reset the player holding the bat when they let go of it.
                 this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnGrabEnd, (player: hz.Player) => {
                     this.batHolder = null;
                 });
        
                 // Listen for bat/ball collisions.
                 this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnEntityCollision,
                   (collidedWith: hz.Entity, collisionAt: hz.Vec3, normal: hz.Vec3,
                     relativeVelocity: hz.Vec3, localColliderName: string, otherColliderName: string) => {
                         if (this.batHolder) {
                             this.world.ui.showPopupForPlayer(this.batHolder, "Good job hitting the ball!", 5);
                         }
                 });
             }
         }
        
         hz.Component.register(BatScript);
        ```
        
    
    *   Select the Bat object from the Hierarchy, then navigate to **Properties** \> **Scripts**, and then attach the BatScript to the Bat object.
        
        ![Attach the BatScript to the Bat object](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462687051_564911256046830_3831045490394279727_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=EhFlFHGtZMEQ7kNvwHbHKgh&_nc_oc=AdlMuG5ZwWy8W0FtkZDf918wuxlgnWz6L1850i2k6rZn024kG4eZR7DFOuB6N44ezmQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfS8_qKcBdKz32kLcuR3BX1lDgA4GuNdx9Wo7ioeMO4Sng&oe=689B97F9)
        
        When the player swings and hits the ball, they’ll see a cheerful message that congratulates them. **Note**: You can’t swing the bat in desktop mode. To be able to swing the bat, you must switch to VR.
        
    
    *   This step is optional for the Batting Cage tutorial.
        
        To enable restart of this world, set the ball to its original position by resetting it with a secondary action (the button press) whenever the user wants to do so. To implement this, you can create a scripting event for a [button press](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/action-buttons/#how-to-handle-button-presses) and attach it to a [grabbable entity](/horizon-worlds/learn/documentation/create-for-web-and-mobile/grabbable-entities/intro-to-grabbable-entities/) .
        

## Section 5. Configure local scripting

In this section, you’ll configure the scripts to run locally.

When the player hits the ball, they take ownership of the entity that the script is attached to. In this case, it’s the Ball object. Transfer of ownership causes script processing to switch from the server to the player’s local device. This improves latency for the player. For more information, see [Ownership in Meta Horizon Worlds](/horizon-worlds/learn/documentation/typescript/local-scripting/ownership-in-horizon-worlds) .

*   Change the Execution Mode of both the Ball and Bat scripts to “Local”.
    
    *   Select the BallScript script from the Hierarchy.
        
    
    *   In the **Properties Panel**, set **Script Execution Mode** = “Local”.
        
    
    *   Select the BatScript script from the Hierarchy.
        
    
    *   In the **Properties Panel**, set **Script Execution Mode** = “Local”.
        

*   Update the BatScript script with the following revisions.
    
    *   Adds a property that takes in the Ball entity.
        
    
    *   Assigns the ball entity to the script property “ball”.
        
    
    *   Transfers ball ownership to the player whenever they grab the bat.
        
    
    *   Transfers ball ownership to the server when the player releases the bat.
        
    
    *   Adds a `receiveOwnership()` method that preserves the value of `batHolder` when the script changes ownership.
        
    
    *   Adds the `transferOwnership()` and `receiveOwnership()` methods that preserve the value of `originalPosition` when the entity changes ownership.
        
        This is what your BatScript should look like at this point:
        
        ```
        import * as hz from 'horizon/core';
        
         type State = {};
        
         class BatScript extends hz.Component<typeof BatScript> {
        
             static propsDefinition = {
                 ball: {type: hz.PropTypes.Entity}
             };
        
             batHolder: hz.Player | null = null;
        
             start() {
        
                 // Set the player holding the bat when they grab the bat.
                 this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnGrabStart, (isRightHand: boolean, player: hz.Player) => {
                     this.batHolder = player;
        
                     // Set the ball's owner to the player so that interactions with
                     // the ball execute on the player's client with reduced latency. The bat's
                     // ownership is implicitly transferred to the player upon grab.
                     this.props.ball?.owner.set(player);
                 });
        
                 // Reset the player holding the bat when they let go of it.
                 this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnGrabEnd, (player: hz.Player) => {
                     this.batHolder = null;
        
                     // Reset the ball's ownership to the player.
                     this.props.ball?.owner.set(this.world.getServerPlayer());
                 });
        
                 // Listen for the bat colliding with the ball.
                 // [...] omitted, same as in the previous step.
        
                 // After grabbing the bat, ball ownership transfers. This means you
                 // must ensure that batHolder stays set correctly.
                 override receiveOwnership(state: State, fromPlayer: hz.Player, toPlayer: hz.Player): void {
                     this.batHolder = toPlayer;
                 }
        
                 override transferOwnership(fromPlayer: hz.Player, toPlayer: hz.Player): State {
                     return {};
                 }
             }
        
         hz.Component.register(BatScript);
        ```
        

*   Update the BallScript script with the following revisions.
    
    ```
    import * as hz from 'horizon/core';
    
     type State = {
         originalPosition: hz.Vec3
     }
    
     class BallScript extends hz.Component<typeof BallScript> {
    
         static propsDefinition = {};
    
         originalPosition: hz.Vec3 = hz.Vec3.zero;
    
         start() {
    
           // Set the original position of the ball so you know where to respawn.
           this.originalPosition = this.entity.position.get();
    
           // Listen for ball collisions with the ground.
           this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnEntityCollision,
             (collidedWith: hz.Entity, collisionAt: hz.Vec3, normal: hz.Vec3,
               relativeVelocity: hz.Vec3, localColliderName: string, otherColliderName: string) => {
    
                 // Move the ball back to its starting position.
                 this.entity.position.set(this.originalPosition!);
    
                 // Reset the ball's velocity.
                 this.entity.as(hz.PhysicalEntity).zeroVelocity();
               }
           );
         }
    
         // Get the original position of the ball so that it respawns in the same place.
         override receiveOwnership(state: State, fromPlayer: hz.Player, toPlayer: hz.Player): void {
           this.originalPosition = state.originalPosition;
         }
    
         // Pass the ball's orginal position to the new owner.
         override transferOwnership(fromPlayer: hz.Player, toPlayer: hz.Player): State {
           return {originalPosition: this.originalPosition!};
         }
     }
    
     hz.Component.register(BallScript);
    ```
    
    When the player grabs the bat, they take ownership of the Bat entity. This causes the script component attached to the bat to execute locally on the player’s device (VR headset, web, and mobile). This provides a better visual experience for the player because there is no latency incurred in transmitting rendered scenes from the server to the player’s device.
    

## Section 6. Play in your new world on mobile

*   Publish your world
    
    To [play in your world on mobile](/horizon-worlds/learn/documentation/create-for-web-and-mobile/how-to-test-on-web-and-mobile#mobile) , 
    
    [publish](/horizon-worlds/learn/documentation/save-optimize-and-publish/publish-your-world)
    
     the world first. Provide the necessary information in the **Publish World** dialog, which can be opened by navigating to the dropdown menu on the menu bar or by clicking **Publish** on the top right.
    
    Enter the necessary information such as **Name**, 
    
    **World Rating**, **Comfort Rating**, and **Tags**.
    
    *   You can name your world something unique other than the default name.
    
    *   If you do not wish your world to be visible to the public, ensure that the toggle for **Visible to Public** is turned off.
    
    *   Ensure that mobile is selected as one of the supported devices.
    
    *   Toggle on **Compatible with Web and Mobile** Click **Publish** to publish the world.
    

*   Configure the preview device as mobile
    
    To preview your world on mobile, select **Mobile** as your preview device by going to [Preview Configuration](/horizon-worlds/learn/documentation/desktop-editor/getting-started/preview-mode#how-to-set-the-preview-configuration) . Click the ellipsis button on the menu bar. In **Preview actions**, send a preview build link to your Meta Horizon app.
    

*   Play it on mobile
    
    Open the Meta Horizon app on your mobile device, find the build link under **Notifications** to play in your world. For more related information, see [Testing worlds on mobile](/horizon-worlds/learn/documentation/create-for-web-and-mobile/how-to-test-on-web-and-mobile#mobile) .
    

## Section 7. Play in your new world in VR

In this section, you’ll see what it’s like to play your game in 3D in Meta Horizon Worlds on your Meta Quest VR headset.

*   Grab your Quest headset, strap it on, and turn it on.
    

*   Launch Meta Horizon Worlds on your headset.
    

*   Navigate to the **Create** page. You can get there by clicking the fourth icon from the left on the menu bar at the bottom of the page.
    
    ![Click this icon to navigate to the Create page](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462602868_564911186046837_388520816768644606_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=_DGtLaFGIpoQ7kNvwFTnpLm&_nc_oc=Adk9vZfL12tQPYOn_OtPQgMmmBHtB1w8_mSNWONttL_4x7th_QZuhfGjP9RvUR2eDB4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Lo0Iwpjipqtk6heJi_yuBA&oh=00_AfQMh8Vk4Cy_TJwgS3cxLq9H-D_eDw91v-5kVeUTSlEARw&oe=689B9A32)
    

*   Locate the world that you just created, and then click it to launch it on your Quest VR headset.
    

*   Step up and grab the bat by pressing the secondary trigger on the right Quest controller.
    

*   Swing the bat and try to hit the ball. You can swing the bat by swinging your right arm while holding the secondary trigger down. When you hit the ball, watch for the message: “Good job hitting the ball!”.
    
    If you lose the ball, and you need to reset your progress, you can:
    
    *   Press the menu button on your left controller to open the Personal User Interface (PUI).
        
    
    *   Choose the **Worlds** tab from the PUI menu.
        
    
    *   Locate your world, and then select it.
        
    
    *   Look for the **Reset World Progress** option, and then confirm that you want to reset your progress. **Note:** Resetting world progress deletes all of your progress in the world, including any items or achievements you’ve earned. *You’ve completed this playtest - Congratulations!* ## Exercises

The following list contains suggestions for additional exercises.

*   Reposition the ball’s starting position so that it spawns immediately above the player, wherever the player happens to be.
    

*   Add a sound effect that plays whenever the player hits the baseball.
    

*   Instead of using primitive meshes for the bat and baseball, try using higher quality meshes instead.
    

*   Add a target for the player to aim for when they hit the baseball.
    

*   Track the player’s score whenever they hit the target.
    

*   Store the scores in a leaderboard.
    

*   Make the bat easier to grab by adding explicit grab handles to it.
    

*   When the player releases the bat, make it automatically attach to their hip.
    

*   Spawn a new bat and ball for additional players that enter the world.
    

*   Update your code to add support for desktop and mobile users.
    

## What’s next?

To learn more about Horizon, try the following:

*   See the [Tutorial worlds](/horizon-worlds/learn/documentation/tutorial-worlds/getting-started-with-tutorials/access-tutorial-worlds) for more tutorials.

*   Learn about the desktop editor with the [Introduction to the desktop editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor) .

*   Learn about the other tools available by reading our [Tools overview](/horizon-worlds/learn/documentation/get-started/tools-overview) .

*   Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs) to learn about our program benefits.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 