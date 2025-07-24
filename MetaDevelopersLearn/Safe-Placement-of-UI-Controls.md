# Safe Placement of UI Controls

[source](https://developers.meta.com/horizon-worlds/learn/documentation/create-for-web-and-mobile/designing-worlds-for-mobile-and-web/safe-placement-of-ui-controls)

When designing your game’s user interface, consider both the gameplay controls and transient platform UI (such as notifications, NUX prompts, world chat etc) which can partially or permanently obscure your interface.

The following illustration provides general guidance for where you can place UI, combining both desktop and mobile surfaces:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/509604780_745983691272918_5952935465294181313_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=Q-Lxj8n6Ki8Q7kNvwFlSYTQ&_nc_oc=AdmuvYUUWYry04oyqzhBIlT2xKisW27Laxg7tl6ZahXc6yC0vF7t2Sqml7M3yxf-YkU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfTlH90khTn7Dz4N-9wjgIU_pEaZWybmDjPu7AVRbE3Nag&oe=689B8FA7)

 *![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452615758_512532801284676_8886395584801346512_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=gRL0ljxgBjgQ7kNvwGbCv-f&_nc_oc=Adkm6CY-9cI6Frf1R0uGnte8n-OSz9CTdCJEFaWex9ESz0de-2FMHiEOsBc3Zupsm4o&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfQ-h_uAmhMZBzuSUvGYsUAjqqYvdUkYgWPaqC8d7RgBxg&oe=689BA844)
    
     Unobstructed.

 *![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452883040_512532784618011_112216473924849842_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=gvrpIjjcZ7cQ7kNvwGpvnGk&_nc_oc=Adkwcocc1ja-rmGwJgqfhMAr-Yyixzm7zg9z7QsQ-FA3Wd5yj-Ddeqw_AwaQYizJ_es&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfR67Nwn2p062ntpCNajGaiuRaKXY4SNOVhG7Fyk9Mx7iA&oe=689BB033)
    
     Potentially obstructed.

 *![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452665546_512532781284678_1258298437483562209_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ih2fHARqNS8Q7kNvwE3PLmc&_nc_oc=AdlfLacdzk6OF95tqNgOwGErj-TKo2NXXirYHxFALZ1OUGSj9dQL1clTcG8JChZcJB0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfRqjKUI7A9XbfaQn1IC15hNjWH6Cu4JVMoDxAomfKnnTQ&oe=689BACEF)
    
     Permanently obstructed.

> **Note**
> 
> : The amount of space will vary depending on the features your world has enabled, how you set up grabbables, and the user’s screen size.

Always test your world on both mobile and desktop, to check for any overlapping or obscured UI.

For a deeper look at why these regions, let’s take a look at each surface with all possible UI states enabled:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/509151822_745983701272917_9141791513895038562_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=OlTTHKIXCJAQ7kNvwGN2N__&_nc_oc=AdnL4wjv8iKkqugE9z3QKuBY-UIvzIthvoOri3neWHWfQakKgylAG-gmnRRrb-Pi2rU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfSxtO7CriYkHgd7KF0zyY_8duXTI-jRbDhZWCmooULbKQ&oe=689B942D) *Mobile (@844x390)*![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502376601_745983697939584_8080560317875431090_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=8qcoX0VP7Y8Q7kNvwEhKWCy&_nc_oc=AdmE3wklwSxPLGwROSjd3S15Br02me1TB9FS6eScLVTvgM4eYSSLFPhRXLOVDpy7ypg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfRBTajwoufDQA1WqTDhRx2zesNQsirJ1ssTmyyPQJzbiA&oe=689B943C) *Desktop (@1920x1080)* Taking into account the typical usage percentage of each gameplay control and the the frequency of each transient UI element, the per-surface safe zones look like this:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502518075_745983717939582_4989666402508662381_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=WHlkTYZ1T6QQ7kNvwGWJ5nX&_nc_oc=Adn6Zke-PbP0F2LQJNzNFahaUjVJ7B_T7wIGpiPuYsapiWpLoWzHK9MH8e2Vfamg25s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfSoDIvGTwqAYcMdfrob10ZYt9Y7w7OE7u-VesIRXgliLw&oe=689B959E) *Mobile (@844x390)*![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502376413_745983714606249_2349111694637599823_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=JXI7luEPgOsQ7kNvwFRJ1cx&_nc_oc=AdmCerL2aG0HGqaVk2EBp5Gs-ENCv-84Wr3HTqLqtyqNgvOgZYYMXkhPLPPnKSX-Cvw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfSUgrzxeZzXGtkq4DQSWQzbfNOLkc5zbPfS5C4i_ncAng&oe=689BACDC) *Desktop (@1920x1080)* ## Mobile

The most important thing to note for mobile controls is that they are contextual. The number of on-screen buttons is determined by how you set up your grabbables.

For example, if you have a simple world with grabbables that have either one or no actions, then you’ll have more available UI space than a world using complex grabbables, custom input etc.

No held item:

Item with Primary & Secondary actions: 

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502492839_745983687939585_875131652642446139_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=caCPC6POp1QQ7kNvwEqLwEB&_nc_oc=AdnVetsgaBQtTH_TOTnFqV274CgOnwnqt7j3ig-A-aici-Edze6EI7NTIOWAeiLTDro&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfS0Vm5pOo-rI4kAmJsXIYDFQgmAulzAZTkrYqTs--J8rw&oe=689BB990)

Item with Primary, Secondary and Tertiary actions Holstering enabled on world: 

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/508824712_745983694606251_244768444164627274_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=8G9N_Hhkwg0Q7kNvwGZkvRC&_nc_oc=AdlsmnKEbaBZKyYKurEJtTJYYzSmbyXIpEf7uR69-xeid5gAhIfIMqwV4bctJNwEPEg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfTftn387xYXdzWo7p8MhkJIFxeh-Z2RGQqKzZhuXAfKpA&oe=689B95CE)

Item with Primary, Secondary and Tertiary actions Holstering enabled on world Using Custom input: 

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/502543755_745983707939583_3529442285019198701_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=5NgN5GqsDIoQ7kNvwH1M9wP&_nc_oc=AdmgR14UMPF779YTo7AorFkKkd0b_V4JXiydDYwrKIvkEWImPHl_aUlflFvarORCKQs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfRRDe8qWuSFfH0Dyd9gzC3zE8eS7TMy_O-XkPTPQNsThg&oe=689B9E6E)

## Desktop

Desktop controls are also contextual, but they’re limited to a list anchored in the bottom right portion of the screen.

You generally have more space available on desktop, because the on-screen elements are confined to the top left, top right, and bottom right corners.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/508853395_745983711272916_8522145247231328435_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=guSTgr-Dmh0Q7kNvwEXh6U_&_nc_oc=AdmODrz2L-AgaVBTvd_DZEH52ii4o7ULbGXJP2OsOhJXMICl-uSX0otKng24co-pv6U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=qFf9TylquzYsQ0A1RgHCjg&oh=00_AfQlpJokL5u3NYORVn34oITxiV3QzX_Q2N6hCUiHGAa4Hg&oe=689BA7BA)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 