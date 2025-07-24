# Module 6 - Game Start and Collection

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/build-your-first-game/module-6-game-start-and-collection)

## Manually triggering game start

Bring those gems back!

A common way to have players start a game is to add a Trigger Zone gizmo through which players pass to initialize the game. Let’s set that up in our game.

### Add a trigger zone

In the desktop editor, select **Build menu > Gizmos**:

![Screenshot of selecting Gizmos from the Build menu](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489125328_692135299991091_4111077702588148303_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=kAtgCocAYksQ7kNvwHfhkje&_nc_oc=AdkD3bE1oKirKqHgSCRgrHxq3iGhWffb5yTQZlviwH3kXZ7s1SMcLbyzKarkSerd_zk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfTdsYFu56cH9JSrbU_tIc92A1PdeoTE4-j09hAR83XHbw&oe=689BAB5D)

Click and drag the **Trigger Zone icon** to add a trigger zone to the world:

![Screenshot of selecting the Trigger gizmo from the Gizmos panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489035548_692135403324414_320847249441776665_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=9550de4LgjAQ7kNvwHSX8Q7&_nc_oc=AdkgIE04eD62Ykibo-l5fkH8G9neD41D9Ag7H4HW3_FITa8bpK-td310U8btZu2l0ZQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfT1OkI_6V-XsVLhzFRLwHS0dO4FO24rtF1VbfTlzzjaBA&oe=689BA5B4)

Click the **Move tool** in the toolbar. Move the Trigger Zone to the Start platform in the corner of the provided course.

Scale the trigger zone using the **Scale tool** available in the toolbar. Make it the same length and width of the visible, raised platform.

![Screenshot of selecting the Scale tool in the toolbar](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/480829176_662906912913930_5978396360539499939_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=WXqxk2ks5pYQ7kNvwH1EftY&_nc_oc=AdmF9phAIkEM35Mv8WX-a2w-UdFZ44bHkTxSqYxJTXLJgy3E-7a9grsDYeoLr_bltUI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfQNma0Ky03KbliB4Xv1xeSWhS27aZ1fVNfIYimPWqeq6w&oe=689BB6CE)

The course should look similar to the following:

![Screenshot of finished trigger zone in the desktop editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481054503_662906919580596_1618625342451013238_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=Tj_d6jQerdUQ7kNvwE0CnGI&_nc_oc=AdlGg0R7QJjESAQ75uTLDq2W8RvPXKWMV9M6VT_P4Q2QHAh98oEm9Hxi-ivL0gJLSIs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfRP8jb2GT8iod2Yr56OdGtR_b6Pl8SeV3a6KbNnSDefBg&oe=689BAB2F)

### Trigger zone coding **Trigger zones** support some useful built-in Code Block Events. Each time a player enters the trigger zone, the `OnPlayerEnterTrigger` event fires. To access this event, we attach a script to our trigger zone entity and build the code there. **Note:** You can build the script from scratch in the following steps, or you can refer to the `StartGameTrigger_COMPLETE.ts` script in the tutorial world for the finished script.

*   In the Script panel, create a new script.

*   Name it `StartGameTrigger`.

*   In the Main window, select the trigger zone entity.

*   In the Properties panel for the trigger zone entity, attach the new `StartGameTrigger` script.

*   Open the new script in your editor.

In the `start()` function, connect to the `OnPlayerEnterTrigger` event. Arguments:

*   Reference to the trigger zone ( `this.entity` )

*   Reference to the `onPlayerEnterTrigger` event.

*   This event takes a **callback function** as the third argument and passes the player object to that callback, when the listener detects the `onPlayerEnterTrigger` event. In the following code, this player reference is named `enteredBy` and can be referenced, if needed, in the callback function.

Create an event handler method for this event binding and call to it from within the callback function:

```
start() {
    this.connectCodeBlockEvent(
      this.entity,
      hz.CodeBlockEvents.OnPlayerEnterTrigger,
      (enteredBy: hz.Player) => {
        this.handleOnPlayerEnter();
      }
    );
  }

  private handleOnPlayerEnter(): void {
  // TODO
  }
```

We already set up our `GameManager` script to subscribe to `setGameState` events. So, we import the event and `GameState` enum into our `StartGameTrigger`:

```
import {setGameState, GameState} from 'GameManager';
```

We can configure our event handler to emit an event to start the game:

```
private handleOnPlayerEnter(): void {
    this.sendLocalBroadcastEvent(setGameState, {state: GameState.Playing});
}
```

## Checkpoint

Done with setting up the gems and the triggering of them into the world! We can verify all of the work we have done:

*   Click the **Reset world simulation** button in the toolbar.

*   Press the **Play button** to enter the world in Preview mode.

*   When first entering Preview mode, you should not see any gems in your course.

*   Run through the Start platform area which has our trigger zone.

*   All of the gems should appear in your course!

### Troubleshooting

If you are not seeing the expected results:

*   Review console for scripting errors.

*   Verify that all scripts are attached and props, on triggers and gems, are set.

## Entity collisions

The gems hide and show correctly, but running into them doesn’t do anything. We must set up the collision events between players and gems.

Click the **Stop button** in the toolbar to stop the simulation, which stops all scripts from running and returns the gem objects to their original (hidden) position:

![Screenshot of the Stop button in the toolbar of the desktop editor](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490183383_692135389991082_8612843187370717632_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=fL86Yim2Td0Q7kNvwHciPRN&_nc_oc=Adm6ZOSuKckZfZ9Sfmr-7CvwhQtbrdZootPMP_kmZTP8UlpXHiFZKc_N5Gz64blwWOo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfT8Z1bUuMd6Ps4qIgDSa_LJzDTgGfBgDz9IIVaM084MtA&oe=689B923F)

### Set gem properties

For a platform-style game, a player should collect a gem by simply running into it. Whenever a player collides with a gem, an event should fire to handle the effects of collecting the gem. We can configure our gems to receive collision events in the Properties panel for each gem.

![Screenshot of selected gem and its Properties panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489857671_692135406657747_3269629125234067770_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=Pd-0unR4r98Q7kNvwHOzeOQ&_nc_oc=AdngZaRSgRXiPJL_PNPitcHzyfKxQo-6dBLClAhGqwM0uPStGd7Fzu7GsRD8wV6C8ko&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfRODZUTVgWaqeCtA1XHqarP9c9418quWMcVuED5TRRNiQ&oe=689BA10C)

Select one of the gems on your course, and configure the following properties:

*   **Collision Layer**: `Players Only`.
    
    *   Our demo game here has no other objects in motion, so this setting is not important at present. However, it’s a good practice to scope as tightly as possible, in case you decide to add other objects in the future.

*   **Motion**: `Interactive` *   **Interaction**: `Grabbable` *   In this game, we just want a player to collect a gem when colliding with it. We do not want the player to have to physically grab a gem.
    
    *   However, we need `Grabbable` to be set for our gems to be interactive and to receive events from player interactions.

We can still set up our objects to behave exactly as we prefer.

![Screenshot of selected gem and its collision-related properties](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489142265_692135339991087_261137589439071753_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=fXY6H91XOWIQ7kNvwH_4Pw6&_nc_oc=AdkZujZ4SQ7GEgjxDZ99hsPDvm6qT6e6sofuepy0Xe7e2uhxWXlC2RaO8D8wB-uydQM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfTOAi3XmYlg5v3kHC2Tpo56pJlYteV0IWonj-nvtJO0jA&oe=689B911F)

Set the following collision-related properties:

*   **Collision Events**: `Players` *   Disable events from `Player Heads` and `Player Hands`. Enable for `Player Torsos` only.
    
    *   To avoid multiple collision events from firing when a player runs into a gem, we only need events from the player torsos.

*   To disable the default grabble behavior, set **Who Can Grab?** property to `Script Assignee(s)`.
    
    *   With this setting, you must explicitly set a player as an owner in TypeScript for an object to be grabbable by that player.
    
    *   In our game, we won’t set an owner in TypeScript, which results in our preferred collection interaction.

Repeat the application of the above property definitions to each of the 5 gems.

### Bind to collision events

Our gem properties are now configured how we want them. The next step is binding to the correct Code Block Events.

In the `GemController` script, in the `start()` function, add a new Code Block event listener for the built-in `OnPlayerCollision` event:

```
this.connectCodeBlockEvent(
  this.entity,
  hz.CodeBlockEvents.OnPlayerCollision,
  (collidedWith: hz.Player) => {
    this.handleCollision();
  },
);
```

And, as we have done before, create event handler method named `handleCollision()`:

```
private handleCollision(): void {
}
```

## Checkpoint

We can verify collisions are working as expected by adding a console log to the event handler:

```
private handleCollision(): void {
  console.log('gem collision');
}
```

Press the **Play button** to activate the world simulation, which also executes scripts:

![Screenshot of the Play button highlighted in the toolbar](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489312364_692135343324420_2299170072300284243_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=XpO4kr35NCoQ7kNvwFFXCFR&_nc_oc=AdnyVid3KpRgXbRpK5HIIsuHwko-ZDWkq75b7ozIBMMb_CeNtJBomDRREfQHjXwCvp8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfSKb7AcPP8Bs76n-RJQNedEXn99TPmKdv25hhz4oPTgOA&oe=689BA694)

### Console results

![Results in the Console tab](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481080474_662906932913928_2876650707859435079_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=-nJGhT78ISkQ7kNvwFCvM5A&_nc_oc=AdkM9cVoCavf7Ji5H-NyRxgvLwEclPY9FiISBw_0n08blxtMV7Rw9SdSmUY8bSa4hpU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Ci_dEckF0y6Nnz5iAK95nw&oh=00_AfTAdxS0ydpk2FS98OsZNoRLCBcn9PKm9NM_C4ZGS6UhtA&oe=689BA1DD)

It works!

### Troubleshooting

Our collision events are triggered from the player’s torso only. If the gems aren’t getting collected based on player collisions, verify that the position reference objects are placed close to chest height on your avatar.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 