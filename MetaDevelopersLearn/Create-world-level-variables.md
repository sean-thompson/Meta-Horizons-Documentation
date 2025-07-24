# Create world level variables

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/variable-groups/world-level-variables)

World level variables allow you to host group activities or create community persistence in your world and persist that information across multiple instances.

## Set up world level variables

Use the following process to create a world level variable:

*   Select **Systems** \> **Variable Groups** from the menu bar.

*   In the Variable Groups panel, click the **Create Variable Group** button, then name your created variable group.

*   After creating the variable group, click the **Create Variable** button. In the **Create Persistent Variable** panel, use the **Variable Type** dropdown to select **World Persistent Variable**. 
    
    ![Create Persistent Variable panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/517447534_760611476476806_2459560139301980966_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=n3mOKtRvOsgQ7kNvwEiKzcU&_nc_oc=AdnUFJwIOhRrzq36sKH9CCZiF4MEEfQSe1YX371Hp_5qJatLvSuP9PW2PuOJSK7Z2GE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=FcbvVbaaoeHGJFdHpr-fFA&oh=00_AfRXZAP6oKsFTj7zgZVDUAVE2EVZ31a-8PI00AK5d5-V1A&oe=689B9E12) 

*   Next, name your created variable and select the **Data Type**. You can choose from the following data types:
    
    *   Number - used by world counter APIS to save community activity counters
    
    *   Object - used by world variable APIs to save complex world states

*   After selecting the **Data Type** input a value for the **Initial Value**.

## Use world level variables

After setting up world level variables, you can use them in your scripts. Reference the following sample scripts to use world level variables in your scripts:

### Import required modules

```
import * as hz from 'horizon/core';
```

### Get a world level variable

```
const value = this.world.persistentStorageWorld.getWorldVariable<string>(
 "VG:WPVar"
);
console.log("World Variable Value: " + value);
```

### Fetch a world variable

```
await this.world.persistentStorageWorld.fetchWorldVariableAsync(
 "VG:WPVar"
).then((value) => {
 console.log("World Variable Value: " + value);
});
```

### Set a world variable

```
await this.world.persistentStorageWorld.setWorldVariableAcrossAllInstancesAsync(
 "VG:WPVar",
 { "key": "value" }
).then((value) => {
 console.log("World Variable Set: " + value);
});
```

## Set world-level counters

After creating a world level variable of type number, you can use it to set world-level counters. The counter APIs can be used to bump certain logic in the game such as `make_wish` or `catch_butteryfly` etc.

Reference the following sample scripts to use world level counters in your scripts:

### Get world counter

```
const value = this.world.persistentStorageWorld.getWorldCounter<string>(
 "VG:WPVar"
);
console.log("World Variable Value: " + value);
```

### Increment a world counter

```
await this.world.persistentStorageWorld.incrementWorldCounter(
 "VG:WPVar",
 10
).then((value) => {
 console.log("World Counter: " + value);
});
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 