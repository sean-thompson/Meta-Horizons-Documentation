# Module 8 - Adding Polish

[source](https://developers.meta.com/horizon-worlds/learn/documentation/tutorial-worlds/build-your-first-game/module-8-adding-polish)

## Adding text

For a nice bit of polish on this game, we can add text to help players understand what is happening in the game. It would be helpful to display the current game state and the number of collected gems in a scoreboard. We display text for players using a Text gizmo.

#### To add text to your world

From the desktop editor menu, select **Build menu > Gizmos > Text Gizmo**:

![Screenshot of Text gizmo in the world and its Properties panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489116915_692135286657759_3860821810156638796_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=K7vxhZ6CGq0Q7kNvwEersoQ&_nc_oc=Adkm2esZjsV5ebpsGqzsvqkx-UabfxbMhfHjPnOjBjAitbi-HarWY2LiExg6gpiqKgQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=ZerKB4UkZl4VWFM3ElNolg&oh=00_AfQy5ToJH8qsIb8rdkutZ89a7YmJP8s53qWS6Pqfpw_7EA&oe=689BAF5B)

Click the Text gizmo block in the main window to select it.

*   In the Properties panel, name this entity: `Scoreboard`.

*   Use the **Move** tool to position the text near the back wall of the provided course. Place it high enough so that players can see it from anywhere on the course.

This text block is dynamic and displays new information as the game progresses. Through TypeScript, you can set and update the text in Text gizmos.

Our `GameManager` holds the information to display on our scoreboard. In the `GameManager` script, create a new entity component prop for scoreboard by adding a new `propsDefinition`.

```
static propsDefinition = {
  gemOne: {type: hz.PropTypes.Entity},
  gemTwo: {type: hz.PropTypes.Entity},
  gemThree: {type: hz.PropTypes.Entity},
  gemFour: {type: hz.PropTypes.Entity},
  gemFive: {type: hz.PropTypes.Entity},
  scoreboard: {type: hz.PropTypes.Entity}, // new prop
};
```

In the main editor window, connect the Text gizmo entity to the `GameManager` by selecting the game object and using the properties panel:

![Screenshot of selecting Text gizmo in the Game Manager entity's properties](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/489976951_692135309991090_8410354111768044626_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ew4pv6LkxVcQ7kNvwFvGB_g&_nc_oc=AdnCQEoBtlLJkQu5E-nCAEogPKjVQbhIPsVWosZqSl0zRx3FWda4RQllS6FivqsFlYE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=ZerKB4UkZl4VWFM3ElNolg&oh=00_AfRuoU-WXkp4ABFq3frKRVt7NPQOgLHA9yIiU80IDDiLow&oe=689BB126)

Let’s create a single class method to update the Text gizmo, and let other functions in the `GameManager` call this method. In the `GameManager` script, create a function named `updateScoreboard()` that takes a string argument:

```
private updateScoreboard(text: string): void {
}
```

To let Meta Horizon Worlds know we are dealing with a Text entity and to enable access to the Text gizmo TypeScript APIs, we must **cast** our entity prop as a Meta Horizon Worlds Text gizmo. Then, we are permitted to set the `text` property:

```
private updateScoreboard(text: string): void {
  this.props.scoreboard!.as(hz.TextGizmo)!.text.set(text);
}
```

In the above function, the value of the scoreboard property ( `this.props.scoreboard` ) is interpreted ( `.as` ) as a `TextGizmo` entity.

The `TextGizmo` entity supports a `text` property, which can be updated with the `set()` method. To the `set()` method, you can input a string, which is represented as the `text` string parameter in the above function. **To update the scoreboard**:

In the various state management areas of the `GameManager`, you can make a call to the `updateScoreboard()` function to pass in the text of the message to update. The following function is executed when the `GameState` is set to `Ready`:

```
private onGameStateReady(): void {
  this.totalGemsCollected.clear();
  this.updateScoreboard('Ready');
}
```

In the above example, the message `Ready` is passed to the `updateScoreboard()` function, which sets the value on the `TextGizmo` referenced by `this.props.scoreboard`.

Remember to make a call to the `updateScoreboard()` function when a gem is collected in the `handleGemCollect()` method.

```
private handleGemCollect(gem: hz.Entity): void {
  if (!this.totalGemsCollected.has(gem.id)) {
    this.totalGemsCollected.set(gem.id, gem);
    this.updateScoreboard(`Gems Collected: ${this.totalGemsCollected.size}`);
  }

  if (this.totalGemsCollected.size === this.gems.length) {
    this.setGameState(GameState.Finished);
  }
}
```

## Final GameManager script

The final `GameManager` script looks like the following:

```
import * as hz from 'horizon/core';


export const gameStateChanged = new hz.LocalEvent<{state: GameState}>('gameStateChanged');
export const setGameState = new hz.LocalEvent<{state: GameState}>('setGameState');
export const moveGemToCourse = new hz.LocalEvent<{}>('moveGemToCourse');
export const collectGem = new hz.LocalEvent<{gem: hz.Entity}>('collectGem');


class GameManager extends hz.Component<typeof GameManager> {
  static propsDefinition = {
    gemOne: {type: hz.PropTypes.Entity},
    gemTwo: {type: hz.PropTypes.Entity},
    gemThree: {type: hz.PropTypes.Entity},
    gemFour: {type: hz.PropTypes.Entity},
    gemFive: {type: hz.PropTypes.Entity},
    scoreboard: {type: hz.PropTypes.Entity},
  };
  private gameState!: GameState;
  private gems: hz.Entity[] = [];
  private totalGemsCollected: Map<bigint, hz.Entity> = new Map<bigint, hz.Entity>();


  start() {
    this.setGameState(GameState.Ready);
    this.connectLocalBroadcastEvent(setGameState, (data:{state: GameState}) => {
      this.setGameState(data.state);
    });


    this.connectLocalBroadcastEvent(collectGem, (data:{gem: hz.Entity}) => {
      this.handleGemCollect(data.gem);
    });


    const gem1: Readonly<hz.Entity> | undefined = this.props.gemOne;
    const gem2: Readonly<hz.Entity> | undefined = this.props.gemTwo;
    const gem3: Readonly<hz.Entity> | undefined = this.props.gemThree;
    const gem4: Readonly<hz.Entity> | undefined = this.props.gemFour;
    const gem5: Readonly<hz.Entity> | undefined = this.props.gemFive;


    this.gems.push(
      gem1!,
      gem2!,
      gem3!,
      gem4!,
      gem5!,
    );
  }


  public setGameState(state: GameState): void {
    if (this.gameState === state) {
      return;
    }


    switch (state) {
      case GameState.Ready:
        if (this.gameState !== GameState.Playing) {
          this.gameState = GameState.Ready;
          this.onGameStateReady();
        }
        break;
      case GameState.Playing:
        if (this.gameState === GameState.Ready) {
          this.gameState = GameState.Playing;
          this.onGameStatePlaying();
        }
        break;
      case GameState.Finished:
        this.gameState = GameState.Finished;
        this.onGameStateFinished();
        break;
    }


    console.log(`new game state is: ${GameState[this.gameState]}`);
    // this.sendLocalBroadcastEvent(gameStateChanged, {state: this.gameState});
  }


  private updateScoreboard(text: string): void {
    this.props.scoreboard!.as(hz.TextGizmo)!.text.set(text);
  }


  private onGameStateFinished(): void {
    this.totalGemsCollected.clear();
    this.updateScoreboard('Game Over');
  };


  private onGameStateReady(): void {
    this.totalGemsCollected.clear();
    this.updateScoreboard('Ready');
  };


  private handleGemCollect(gem: hz.Entity): void {
    if (!this.totalGemsCollected.has(gem.id)) {
      this.totalGemsCollected.set(gem.id, gem);
      this.updateScoreboard(`Gems Collected: ${this.totalGemsCollected.size}`);
    }


    if (this.totalGemsCollected.size === this.gems.length) {
      this.setGameState(GameState.Finished);
    }
  }


  private onGameStatePlaying(): void {
    this.gems.forEach((gem: hz.Entity) => {
      this.sendLocalEvent(
        gem,
        moveGemToCourse,
        {},
      );
    });
    this.updateScoreboard('Game On!');
  }
}
hz.Component.register(GameManager);


export enum GameState {
  'Ready',
  'Playing',
  'Finished',
};
```

Congratulations, your first Meta Horizon Worlds game is complete!

## Extending this tutorial

You can explore the following ideas for expanding this tutorial world, and taking this foundation even further:

*   Add a skydome through the Environment gizmo.

*   Add ambient sound/music to different game states.

*   Add sounds FX when collecting objects through our established event listeners.

*   Add enemies that make a user drop gems when collided with.

*   Keep track of each player’s score individually and have a winner.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 