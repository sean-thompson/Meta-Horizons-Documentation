# Collider Visualization User Guide

[source](https://developers.meta.com/horizon-worlds/learn/documentation/vr-creation/getting-started/collider-visualization-user-guide)

Creators can now visualize their collision meshes in VR so they can better manage collision issues, player movement and performance. Using the wearable on the wrist, it’s possible to toggle this feature to see colliders as colored meshes. Different colors distinguish the collision for static meshes vs non static meshes (rigid bodies, grabbables, etc.). **Note:** The [Utilities menu must be enabled](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/enable-the-utilities-menu/) before continuing.

## How does it work?

After the utilities menu is enabled. You will find the “Collision” button. Use your cursor to select the button and toggle the collision visualization.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452702804_512500417954581_4537301140043221409_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=3orfWSDrXlEQ7kNvwGGUZT6&_nc_oc=AdnB9d4ZTPb0SvirbrTIOwJl-1wZyW-rdsK4sB9IZEhgepNxVvz8KUPS4Q1d2uf6-g4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=6wMukxPXvjpbKEsAkrogxw&oh=00_AfQ78sQKx8fTxuLvpwh2o1nk5Y92j-LA28phzkHEO2UQSw&oe=689B943B)

With “Collision” turned on, your world will display collision meshes up to 50 units away. To test this out, you can open the property panel of an object and toggle the “Collidable” option and notice the collision mesh appear and disappear. Static objects will have an orange collision mesh, while dynamic objects will have a purple mesh.

Note that purple meshes for dynamic objects are a concave representation of the actual collision mesh, which may be convex instead. For example, if you have a bucket with a convex collision mesh, the purple visualization would appear concave, making it seem like you could drop objects inside even if that’s not actually possible.

## Hints and Tips

This tool can be handy to investigate at a glance how players interact with the environment, for example whether the chairs around a table will block the users from reaching the table or how players can walk on objects with complex shapes.

Another use case is optimizing the performance of your world by disabling collisions on objects that can’t be reached by players. Once you have identified which areas of the world are not reachable, you can turn on collision meshes to quickly see which objects have collision meshes in the area.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452907966_512500364621253_6194447675355151111_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=BIXFI8FHeisQ7kNvwHi4L_F&_nc_oc=AdmYYwRn-D0p-S8EZcccIW0YWUrih6ChQKQj6SU29GsVY4oFBA90S-W6qFS4qkNLO6k&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=6wMukxPXvjpbKEsAkrogxw&oh=00_AfTUSH79mGECV-cDEo8OcB5ZjoYhOaMA-zoLxJNVOK1Ehg&oe=689BA64A)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452672912_512500404621249_6961473514961222830_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=QKEkfEnTcAAQ7kNvwFQQBqb&_nc_oc=AdlUcRLJbPU-CVS78D1VanNs_LmFmWe2m_aB6PaBLLjKApF455wpClCNXAVOMutoepU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=6wMukxPXvjpbKEsAkrogxw&oh=00_AfSTSDvpPoDSqXWduhvzSf4mFwnOT6m7jKqcmh3iw-Sj-Q&oe=689BB59E)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 