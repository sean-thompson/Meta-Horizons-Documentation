# Push Button Interactions

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/tools-for-creating-worlds-for-mobile/push-button-interactions)

To create pushable buttons in Meta Horizon Worlds, it’s a common practice to use a Trigger Zone just above the button. When the player puts their hand in the Trigger Zone, it causes the world to behave as if they pressed the button.

This scenario looks like this:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452874518_512527161285240_7815018326525079371_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=_ucMFvpDnTAQ7kNvwH1ksCN&_nc_oc=AdltxVFRogBOwdSLB_7gjga21mGeHuPSUFpPg3Alx2i4vvADxebnPCW9Co9dV2FaHOY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=RW8dHZQVpKIXZn5xYqpihw&oh=00_AfS9gk3EewHTMBo1J1vwLpKOjMXR8lde2pf3I6xyFa-2zg&oe=689B904E)

Since web and mobile players don’t directly control their hands, it’s difficult for them to put their avatar within the Trigger Zone (unless they jump on it). To overcome this limitation, you can enable the setting **Selectable in screen mode** on the Trigger Zone:

*   Open your creator menu and select **Gizmos**.

*   Select **Trigger Zone**.

*   Grab your Trigger Zone gizmo and move up on your right thumbstick to select **...Properties**.

*   Turn on the toggle next to **Selectable in Screen Mode**.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452576381_512527201285236_2682068290829855911_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=QIYf45Wq-YwQ7kNvwGQGRGQ&_nc_oc=AdkJ9DPtbEcmLTYzOWsn6se1B3AFp6ZctXb7ZWkWC8tjQE-wJ4COo_O1CjjC2vSeAw4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=RW8dHZQVpKIXZn5xYqpihw&oh=00_AfSRmdNKcoKNLRF651QvwjVPVJk6CWkAxNSFir4oVH7Zrg&oe=689B9CDD)

 This image is taken from the Desktop Editor, but the same functionality is available in the Properties panel for entities in VR build mode. The Desktop Editor is only available to creators with access to advanced tooling.

The result enables web and mobile players to look towards the Trigger Zone and press **E** on web, or tap the button on mobile, to fire the **OnPlayerEnteredTrigger** event for that Trigger Zone.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452635178_512527147951908_8921893521680369107_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=7pbNKgWE7gMQ7kNvwFY0prz&_nc_oc=AdkZlkE5HW7JKRIiVt5j5UpRVJPm9W73-X2nIE4H4cgnR2qxzOKyzEERhbyUi5hQMxo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=RW8dHZQVpKIXZn5xYqpihw&oh=00_AfRzXRnwvmPRlR8bMaqH04oZrDUaq8QEgEu2LijmFreEkg&oe=689B9E05)

 This image is taken from the Desktop Editor, but the same functionality is available in the Properties panel for entities in VR build mode. The Desktop Editor is only available to creators with access to advanced tooling.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/474747253_637349498803005_7294516228122331774_n.jpg?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=xK86tWwJGjIQ7kNvwFCtzrr&_nc_oc=AdkDKKPPS4BfcIRHK0fsPAykc5ub_2_AfCbwID-De9bY7Y7QXSzbDs2sgnlndjllfo8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=RW8dHZQVpKIXZn5xYqpihw&oh=00_AfRwbvL1wrcu-u9b4YVs8bp7Gb-8_3YdP7zKI7Aqd0iJuA&oe=689BBCE0) **Note:** If you place your **Trigger Zone** inside or behind a collidable object, the collider will prevent web and mobile users from interacting with it. When you set a trigger to **Selectable in Screen Mode**, make sure the trigger zone is bigger than the object, or turn the object’s collidability off.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 