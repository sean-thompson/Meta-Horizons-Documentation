# If VS Code can’t find a V2 module

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/if-vs-code-cant-find-a-v2-module)

VS Code ships with a recent stable version of the TypeScript transpiler. By default, VS Code uses this version to provide IntelliSense in your workspace. The workspace version of TypeScript is independent of the version of TypeScript that you use to compile your TypeScript files.

In Meta Horizon Worlds development, you need to change the version of TypeScript if VS Code can’t locate a V2 Meta Horizon Worlds library module when you include it. For example:

![Changing the version of Typescript](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452846047_512510441286912_3891839820288091188_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=BEE_p-_veqwQ7kNvwGSFBcK&_nc_oc=AdmZ9Z2-cBzQo-9nXYC4S42x9UYx7-mZkq3M2l9XJG12lAYSDwdgF5gldiuKhaeXgTE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=URoWJRpnY5ahMn0M1GqB8A&oh=00_AfShT668QW5hPQwBWyw7i_EbioL9tDx7HntTaaejegvOuQ&oe=689B8B9A)

## How to use the workspace version of TypeScript

If VS Code can’t locate a V2 Meta Horizon Worlds library module, you need to configure VS Code to use the workspace version of TypeScript. You should use TypeScript v4.7.4 for all versions of the Meta Horizon Worlds TypeScript API.

*   Open one of the script files from your project in VS Code. Notice the word “TypeScript” in the bottom right part of the screen. Beside it is the version number.

![The Typescript version number](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452672478_512510437953579_5274654559469467809_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=bvP0ZaJRV-sQ7kNvwF5tRVm&_nc_oc=AdncgJ1wZ59jncBhcT1Ln7pfyWoV3WVsv_WAd3XhEJMmotZdbwKlnfX6FWzqJFo8bDs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=URoWJRpnY5ahMn0M1GqB8A&oh=00_AfTfUQWDWCpcjG6jCU9AXAbhqcuD0PguaeBgZKvYNjiysw&oe=689B99C3)

*   Click on the version number. A fly-out menu appears at the top of the screen.

![Version number menu](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452863904_512510491286907_3447494278802419232_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=zXF3JB5Wdm0Q7kNvwFYHRsr&_nc_oc=AdmnWjj-ZhpqgZ4vYj0fS2c0pBVTBsbVsBpfXfyrliu6qJjkDWKkaK2aKBTtroFITp8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=URoWJRpnY5ahMn0M1GqB8A&oh=00_AfRmxgudtcKOfHRJzOI7o7zsYOwawHQh2dLSqhfFmRnekQ&oe=689B9BF1)

*   Select the option **Use Workspace Version**. This configures VS Code to use version 4.7.4.

You should now stop getting the “Can’t find module” error. **Note**: For more information about TypeScript versions, see VS Code’s documentation on [Using newer TypeScript versions](https://code.visualstudio.com/docs/typescript/typescript-compiling#_using-newer-typescript-versions) .

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 