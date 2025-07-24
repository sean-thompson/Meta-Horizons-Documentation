# Meta Horizon TypeScript API 2.0: JSON PPVs & Versioning

[source](https://developers.meta.com/horizon-worlds/learn/documentation/mhcp-program/community-tutorials/meta-horizon-typescript-api-20-json-ppvs--versioning-)

Author: Laex05

## Introduction

#### Creator Skill Level

Intermediate

#### Recommended Prerequisite Background Knowledge

Some TypeScript experience is recommended as well as access to the desktop editor, and VS Code.

#### Description

Learn how to create, store, and manage JSON Objects as Player Persistent Variables (PPVs) in Meta Horizon, including versioning for updates and expansions. Given Meta Horizon’s 10kb data limit for PPVs, we’ll show you how to evaluate and optimize your JSON Object’s size.

This knowledge enables the storage of hundreds of variables in a single JSON PPV, facilitating the creation of experiences that remember visitor progress and allow seamless continuation. Additionally, it supports the growth of player data in future updates without the need for new JSON PPVs.

#### Learning Objectives

By reading and reviewing this written guide you will be able to:

*   Create and store JSON Objects as Player Persistent Variables

*   Add versioning to JSON PPVs: allows for updating and adding new variables

*   Check the variable’s max size

## Step 1: Create a JSON PPV

Once the world is loaded, click the systems drop-down and select “Persistent Variables.”

![Screenshot 2024-03-12 165250.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452885043_512509794620310_1164532069211912730_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=UAs3lkbJ0e8Q7kNvwGICS1y&_nc_oc=AdkyqGBvca8F3NtzunQZ7pz_us5JfkI0xQd8LGnEFrgAllQgfGNeOO9zHsO69Q72zHw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRX7lN-UrG3idqqcd236nq6_LQ662sBPluOa7XeBN6Kuw&oe=689BA492)

Click the plus icon to create a variable.

In this example, we will name it “TestVar” making sure to select “{ } Object” from the drop-down.

![Screenshot 2024-03-12 165344.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652041_512509847953638_1230264767479043441_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=p8Vd57AVkbIQ7kNvwEMgqok&_nc_oc=Adn3ZcTY8ZIcJi-lhCs-aVc_6zMMFx7pcJOur7r5DyVVtMcVZOKA6ohsZTkypy0l6CM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfS1EDjAW-BPNgBi0VojaEYflFzwBUL3QQYW6VH_-qpVdQ&oe=689B9AEC)

Now that JSON Object PPV has been created, it can be used in TypeScript scripts by referencing it using the string name it was given: “TestVar.”

## Step 2: Create Scripts

To begin, we will create two scripts with the specified names seen below. It’s important to verify that Meta Horizon’s 2.0 API is selected by accessing the settings via the gear icon. 

![Screenshot 2024-03-12 165632.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452915617_512509827953640_3795839271183190167_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=7VSrXr3qfbUQ7kNvwG2XGXk&_nc_oc=AdnIajJSb_1boG9eeKyfBETdhnbZccCJ4YFH9LuNO3JRYTqtCAgSNwZa5KOqhi7bPzA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfSaVJTDH0Owdm9iaNc0rIBWlQipVCWsyar1Z3X1Y8OJTw&oe=689BA53D)

### Specified Script Names:

*   PlayerVar_Defs

*   PlayerVar_Manager

### Mentor’s Note

Defs and _Manager are two of several naming conventions I use in my scripts to help organize and plan my code. There are no right or wrong approaches, so feel free to adopt one that works well for you.

_Defs store type declarations, classes, and enums.

_Manager handles logic and typically has a Component that attaches to a single object in the world.

Other naming conventions I use include, \_Data, \_Entity, and _Func.

### Script Setup

As of the current Meta Horizon desktop build (March 2024), creating a new world requires the initial creation of a 1.0 script prior to switching the script mode to 2.0. Once the switch is made, the 1.0 script can be deleted.

Access to this feature is found under the script tab: select the gear icon, followed by Script Settings to view the API Version drop-down:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452690902_512509841286972_4120111531248974789_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=IXJCfS4mmCAQ7kNvwG639Hy&_nc_oc=Adlh6uLYZyHpyK_rfSZDKWW4RFCpqfdBMMpD6Ee2BUlFM9QT6FsPYkh8nG992WbRNKs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfTvMA2k7rsdg9X-3MTUHPFh40-PcgFRKGCyFO-x9zhZ2Q&oe=689BAACC)

## Step 3: Prepare Scripts

To get started delete all the prefilled code from the \_Defs file, and adjust the \_Manager to explicitly import Component, rather than * as “hz” importing all.

Note: This is a personal preference, please choose the approach that works best for you.

### Mentor’s Note

I personally like the explicit approach as you will know all items that have been imported from specific APIs, and you can do less typing, which is always nice!

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452576403_512509797953643_5285657881568124068_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=2QxiqVumSPwQ7kNvwG38Hq6&_nc_oc=AdkQlz9P9SJYUeujv08Kih_kLbEc3Sy9gRQRzvnGjpIdRQVZY34Z0HgV_7WHo1x27GE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfTwMVwRaqsi3phnekeU-qaNMVDTPDsIwSnYtQ5kwd0Ygw&oe=689B9A71)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452532488_512509834620306_1267219142950200425_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=kDK1_SGEyl0Q7kNvwGe5d34&_nc_oc=AdkDgwmnAZmkOEStKwJu71lW5VgrvcH9FQyp9RrJZiOZLqXNE8FLLy4qVBvsy_5ZNf0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfSrd59xXBwp7cQQ6l2SsYpQN4fSXm4Lv1psocEpT-5pCw&oe=689BBC01)

## What Are JSON Objects?

JSON objects are powerful variables that can store various types of data. JSON objects can even nest inside of each other. These may be referred to simply as objects, variable folders, or more informally “bags of stuff.”

This is a simple example storing just two variables for tracking a player’s name and number of visits:

```
const playerInfo = { name: ‘playerName’, visits: 0 };
```

In TypeScript it is often necessary to define a type to describe the object, for instance, in this case we would have:

```
type PlayerInfo = {name: string; visits: number};
```

We then need to declare the Type when creating the playerInfo variable:

```
const playerInfo: PlayerInfo = { name: ‘playerName’, visits: 0 };
```

Notice that the variable is in camelCase and the type is in PascalCase. This differentiation shows that the playerInfo is the object variable storing the data. And, PlayerInfo is the type we are declaring it to be.

Next let’s look at a complex example, with nested objects and multiple variable types. In this example, notice that when the type is larger the variable is broken onto its own line:

```
type PlayerInfo = {
name: string,
visits: PlayerVisits,
scores: PlayerScores,
};

type PlayerVisits = {
totalVisits: number,
uniqueDays: number,
totalTimeMins: number,
lastVisitTimeSinceEpochMs: number,
};

type PlayerScores = {
fastestTime: number,
highScore: number,
};

const playerInfo: PlayerInfo = {
name: ‘playerName’,
visits: {
totalVisits: 0,
uniqueDays: 0,
totalTimeMins: 0,
lastVisitTimeSinceEpochMs: 0,
},

scores: {
fastestTime: 0,
highScore: 0,
},
};
```

## Step 4: Connect Events

Next, we will connect the CodeBlockEvents for player enter and exit world to local methods. We have also added a console log to the methods to confirm the script is working.

![Screenshot 2024-03-12 171631.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452881431_512509817953641_3022961139974047751_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=TKXDyTsciF4Q7kNvwEUuWHr&_nc_oc=AdnuArMuOnBCIwPZagz9Gyod6ln1omMU6AwzZ7o2yYsD_sqigtrCHRauL6g2XgJgxp4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRwRTcO8hbj6FOXbxCGVWT_vID_oKwy4HNFHq10JBiMXg&oe=689BB2DF)

Ensure that the PlayerVar_Manager script is attached to an object in your world. In this example, I used a text object:

![Screenshot 2024-03-12 171735.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452513283_512509791286977_42569017604569069_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=bhsb_ih6b70Q7kNvwGGMlNu&_nc_oc=AdkzFnxvBGQVOQkBOXuoDa53SY7VNzpsU7JN3B4ZrUtrJVYHZNgRXpqI288haiSw-XI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfQThQ-7IyQiEDOFAX2f2FPCeNTx-3TG6WLaJPy-lZuKrQ&oe=689BAF67)

![Screenshot 2024-03-12 171909.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452742345_512509761286980_4350714917524728780_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=g7TiNgXThpYQ7kNvwE_jUn1&_nc_oc=AdkZPK4vzqwYg-GtI9KtWJwwVnsR9OExqxexd9mS7RCRjsPAmSheuhPLtKXeZbo_pZA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRB0Mx5_nVTQhAjh94OKws0QdPOjQtdfKYlHuk_4PO51Q&oe=689BBB35)

![Screenshot 2024-03-12 171909.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452701864_512509787953644_6289865107426242307_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=H3yxg_6-stUQ7kNvwEOM5-g&_nc_oc=Adk6y0VOJKex_T1ZCYgah6OKApL2oTu5jO_95JLIOb89QHeU8Fn9Ezac8Squkn9DfQ8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfROb1SEfVEVHjK6Cmwz5eds1ACQcEXXnwQZZOkQFnn18Q&oe=689B9C12)

## Step 5: Define Type

Before we can get and set a JSON Object PPV, we need to define it. Because this type is stored in a _Defs script, we need to be able to access it from our other script files. To do this we add the word export to the front.

![Screenshot 2024-03-12 181652.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452506810_512509757953647_8787940282338034104_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=3OG6hjHpJ1oQ7kNvwH3e9jj&_nc_oc=AdkOW8_YsO6E4G7CQkCpQS2tXMfQL4WOchD8kjERsHgTzQT969mtqGi53zafzilLprc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfSXY_aTHyOS0Pl0kpc-oz1KhX60d5u0exH10VbU6V7fRQ&oe=689BAA7A)

Now that we have exported the type, we can import it into any of our other scripts by typing “PlayerVar” and clicking “enter” or “return” on our keyboard to import the type.

## Step 6: Map PlayerVar

Now that our \_Defs file is setup, we need a place to store all of our player variable data. We will do this in a \_Data script.

Create a new script in Meta Horizon named “PlayerVar\_Data,” and then we will delete all of the prefilled code as we did with the \_Defs script.

![Screenshot 2024-03-12 181658.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452554819_512509784620311_8209205062022272298_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=m5J5eu7oxR8Q7kNvwH-IBI3&_nc_oc=AdnGz5NZkK7annLCEshqUHQspEkGSZMdmnAxw3fEVrGYFhQcTqz53P1cdLY6Elu2BDg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfS-3aNXCQ5FYJ48fB1ZB1QSIsZBW7oyccjQRUtNJgX2Mg&oe=689BA325)

We will only need to write one line of code, and as we do, VS Code will write the import lines seen in the screenshot on lines 1 and 2.

```
export const allPlayerVarData = new Map<Player, PlayerVar>();
``` **Note:** You will need to press enter after typing “Player” and “PlayerVar” for these two types to be imported. If your IDE, in this case VS Code, doesn’t support automatic importing you may need to write lines 1 and 2.

## What is a Map?

A map is a data type that is similar to a list, but does not use indexes. Instead you can have one of the first type (the key), with the second type “mapped” to that key.

In this example (seen in the image above) we have a player as our key. Because a player cannot be in the world twice, only unique players can exist in our world, it makes for a perfect key. Then the data we are mapping to that player is the PlayerVar type we defined in the _Defs file.

Exporting this map as a constant prevents overwriting it with a new map. Instead, modifications must be made using the map’s set and delete methods, which will be discussed later in this document.

We also export this data, because it is very likely you will need to use it across multiple scripts. Since we will not be setting the PPV until the player leaves the world, this means that the map will store the player’s JSON Object PPV for the duration of their stay. In other words it is the source of truth for the most up-to-date variable values.

## Step 7: PlayerVar_Manager

In this step, we will start to write some code.  On the next few pages, we will provide in-depth explanations for each line:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452578528_512509781286978_2962179804368749502_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=nnvkt4vGHwoQ7kNvwFPbQx1&_nc_oc=AdkV82FQQQP2-2cTfRI0TaEHuYnuopk3IE-WjLy1gr-ZmqveY-H7tCHjfSdXvgjlTsU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfSWmeX6a5s9WS-c1R1fuQE5aoMqrSf051xM5QVJ1lO_CA&oe=689BB524)

At the beginning of the script, you’ll encounter the variables. These variables are globally scoped variables, which means they are accessible from anywhere inside this script. These variables are constants; for instance, the playerVariableVersion should only be updated manually when introducing new variables—a process detailed later in the document (Step 9). Similarly, the playerVarName remains unchanged as it serves as a reference to the PPV variable.

![Screenshot 2024-03-12 181721.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452893310_512509764620313_8601289411585962013_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=beZfXVr5kv8Q7kNvwFpjCnT&_nc_oc=AdmNlCXeEG0yWKvNPnad8yaTdLe0cPn5VtiHRUnUGn_U1lu5aRJ474j_Y9fyj1_9VBs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfS6b96Bc3xBqGnwxdflam6ZAVIq2KsYCZXfaNn38cM0dg&oe=689B9F82)

In playerEnterWorld we first get the PPV. Notice that it could be null, we handle this in the initializePlayerVar method (seen at the end of this step). Which we use to create a newPlayerVar. We have to create a newPlayerVar because the player may have last played in an older version with less variables stored in the PlayerVar type.

![Screenshot 2024-03-12 181721.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452963336_512509777953645_4263171605963207015_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=sZ3MV2jMrjgQ7kNvwEMOJGA&_nc_oc=AdmtrbItMnPe2yn50tktfjC572df3fykmHKIu2I6J3jY84_0O_YkBR0Y542KqYE9558&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfT0sg7WYXcSnTIefv9jDzdQdD4QYQbLKep7isQXQ-nyDA&oe=689B97A8)

Then we update the visits to be visits + 1, using the shorthand visits++. To make sure this is working we add a console log.

The last step is to add the player to the map we created in the previous step. We do this by using the .set method, which will replace the previous value if it has already been set. You can use the .has method, if you want to see if the player has already been mapped.

In playerExitWorld we get the playerVar from the map, which if you hover over the const playerVar will show that it is of type PlayerVar or Undefined. This is because it is possible that a player has not yet been mapped. We can check for this with if (playerVar) which checks if it is “true,” meaning not *undefined*, 

*null*, *false* or sort of false (i.e., 0, empty string). We can use an else statement that calls on console log if it is undefined; this can help locate bugs now and in the future. It is recommended to use checks like this in your code.

![Screenshot 2024-03-12 181721.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452673104_512509774620312_3142404411627905147_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=7Rj3BXrdg0gQ7kNvwFbrmsC&_nc_oc=Adlu5wXPaT8c3Pc3PEpHC60x3lf_aabE8w7GRR7jDX8O8u9wTjwVIshY6rUqeXWD7X0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfQJcUJV5l30nUNYcDexILJNxL5To2XTfc-xyNjWr-Skag&oe=689BA411)

Now that we know playerVar is defined, we can set the player’s JSON Object PPV, which saves their JSON Object to the world’s persistent storage.

At the very end, we delete the player from the map.

Outside of our PlayerVar_Manager class, we can create functions. Note that these are similar to methods, but methods are stored inside classes. In this case, we are creating a function called initializePlayerVar, which will return a PlayerVar.

This function is important because it allows us to take a potentially null/undefined value, or partially defined value, and create a new object variable. **Please note**: There is an error as of the time of writing in Meta Horizon’s API, which says the variable could be defined or null, but is actually defined or undefined. This distinction caused an error with the code seen at the beginning of this step, **below the code is corrected, checking the truthiness of (prevPlayerVar) rather than (prevPlayerVar !== null).**![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452415047_512509744620315_2203337898861099810_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=iLK78-UBKaAQ7kNvwH1j9gD&_nc_oc=Adm_qySoWf03xuz24eE0sYO9W5VDypYXK87CxYMc7Cnt_g4xhM6u02SIKgSNt_5i2tA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfTCJz8L4QfnEj0jGsrit1wgIXQAHa9oydB7WaK1KuJusQ&oe=689B99D6)

The first thing we do in this function is create a brand new object variable with values we would assign to a first-time visitor. That way if the prevPlayerVar is not truthy we return those values. Otherwise, we can check that the version contains values we want to recall, and save them to the new object.

Now you can compile your newly saved code and test it. If all goes well, every time you preview the world, your number of visits will go up by one, and log to the console!

## Step 8: Test PlayerVar Size

Now that we have our JSON Object PPV, we need to make sure we don’t run it over the 10,000 character limit. To test this we can create an artificial maxed variable and stringify it to see how long it is.

![Screenshot 2024-03-12 184022.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452751568_512509754620314_8517786802089207349_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=BfjUfl9g7qQQ7kNvwFqTa2T&_nc_oc=AdkUcapAsLna9DNV2SlA_RB7ll8PpOtNd1IGFOHT8NVaSe-50r7i6VrSJK3OilgZrf0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRlx5VWWewLtZhJWxg7ivg-61PYftaJ8aB9DiJn9Eq54g&oe=689B97D5)

In our testPlayerVarSize function, we have created a testPlayerVar variable with larger-than-possible values. We then calculate the length using JSON.stringify, and the .length property of strings. We then simply log that number to the console.

All that is left, is to call this in the start method. When we are done, we can delete this line of code from start, and write it in anytime we need to check the max length.

![Screenshot 2024-03-12 184035.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452616143_512509751286981_1414151313288137369_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=YX2-3K3a_dkQ7kNvwFwdADl&_nc_oc=AdmXgGHvNY4VourjWtDrXDYmvlqfpRt06Oo6zRrV10qw_VjGUukyMondViJnp4yFX1s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRBbp-M7asF9A8fYXZXB250UlPpcYQsdh6v9AZIow9Xnw&oe=689BC0CB)

## Step 9: Add More Variables

Start by updating the type to include additional variables. In this case we added isAFK and afkCount:

![Screenshot 2024-03-19 at 12.18.46 PM.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452916228_512509767953646_8032047240862163427_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=OiskidVuG5kQ7kNvwFtUlz9&_nc_oc=AdnPN8b2a0e_TUmKJn4bHyaTePO2YAvXYN8fEq352TGKczTchhf7oX0V3Y2r6FdCswY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRnn62bJtq08mE1gC0CDE4One-ibp3wXQmm-yHA3b3JpQ&oe=689BB067)

We then add these to the initialize and test size functions:

![Screenshot 2024-03-12 185301.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452742345_512509857953637_3325756538951273658_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=YHep9yBc_NIQ7kNvwFbLd54&_nc_oc=AdnQchKuYQ7IyQED8Aei4eRbMY29D3lmy-vLF_QRXGD5a2qWglNDLdi-9400LpYIJzI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfQFlmVGSxH5rU2qy2Ub01drqKqoInN7ZeZ3cxR_SiermQ&oe=689BB24D)

![Screenshot 2024-03-12 185200.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452746744_512509741286982_2246072596883689413_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=efe97X1ssOYQ7kNvwEEoPWa&_nc_oc=Adkcx-TRG60gluxzCA68tvz_yAwUMyp9wlM4i20hkqg2tCE1--Dnsw9ah8bqZctAmBM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfRrY-aZVoAWktMFOqK3rvPBxk_FQ1XR7qBgkHOIyTY3jw&oe=689B9E79)

We also need to update the version number from 1 to 2: 

![Screenshot 2024-03-12 185053.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452701864_512509737953649_3962852608460184155_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=7KEWbsNAdXYQ7kNvwFf-IiU&_nc_oc=AdkOe87I-eLJ7xVeIrlomBrrSKys7zUTu4WpzgP2mSQvh4pIvDnEvz985E6XbSmzS2c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfSWXzpEbFy2QfhndnJpsQ68fNUfsoIRmJGQRuPa36T7hA&oe=689BB26A)

Then we can use this new version number to get the afkCount for players who have visited our world since the variable was added:

![Screenshot 2024-03-12 185249.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452652242_512509854620304_1398487090111015541_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=e_Z699K-z5kQ7kNvwET4RUh&_nc_oc=AdkGRhevKGNIuAGM0lGXH4jVC3AKvHDUmE8EgwCgThmN5Jy10HZ4GMiWLmL7GRbZkmU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfTSMQzyzSubZuLdi8N9jOjdd7Xz-wyRtJmYpGVl0iQysA&oe=689B9D1E)

## Step 10: Use the Variables

To get started using our new afkCount variable, we will connect the CodeBlockEvents for entering AFK to our local method:

![Screenshot 2024-03-12 185526.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452578037_512509851286971_2231847787475568309_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=1Iwu5DfJOLcQ7kNvwFi1n0z&_nc_oc=AdlBfEubNeKVnoucm9lwmnk1T1Zb9KTHcqpu4c50Wxh1TYv003tneZwUq6Qomm0jb7o&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfSiDEzZ_MXP8H1jAw3pjjWz8EBMdtRsWbSaxdANK8WfVQ&oe=689B9F0D)

![Screenshot 2024-03-12 185514.png](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452909009_512509837953639_6530190211756898574_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=N5rgGOQoVNoQ7kNvwED5Swq&_nc_oc=Adl8pn9BIXqlGWEJ0WrljyDmdtAaxZdAFhX18GB43zS8zpZa2A-dUHv-vP5JRKizKgA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T2EwVaKCA6V3SMEry3spPA&oh=00_AfQsi4FSOibD-rpKL_4JMDUB1mHtqKMJjHoVYgRrizzI5A&oe=689BAA0F)

Then we can get the playerVar and check the truthiness, updating the count to be +1. For extra credit try adding the playerExitAFK method and updating the boolean we added to the playerVar. Setting it to true when AFK, and false when they return from AFK.

### Mentor’s Note

When a player arrives to your world, I have experienced in build mode this causing the AFK events to fire before the player enter world event does, so you will need to make sure the map has the player before setting the value, or check the truthiness as we did above.

## Further Assistance

Thank you for following along! This guide aims to unlock your TypeScript super powers, and add awesome new features to your worlds!

If you need additional support feel free to book me (Vidyuu / Laex05) for a 1:1 lesson.

Consider trying the extra credit tasks below to solidify your learning and take it to the next level!

## Next Steps

Below we have provided some challenges for you to try implementing on your own. These do require some outside knowledge, and we encourage you to ask questions in Discord if you get stuck or are unsure how to complete these. And as always I’d be happy to help you get unstuck, I’m just a Mentor Session away.

### Novice

Track player visits and time spent in your world.

### Intermediate

Track unique daily visits a player has had to your world.

### Advanced

Build a streak system to track how many days in a row each player has visited your world.

### Bonus

Give the player a reward for visiting your world once per day, and or when they reach time spent thresholds.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 