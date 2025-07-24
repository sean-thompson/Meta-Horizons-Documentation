# Create your first world tutorial, part 2 **Welcome to Part 2 of the Introductory Tutorial: Creating Your First World** In this tutorial, you’ll continue to learn how to create a simple game in Horizon Worlds, where you shoot marauding skeletons in a graveyard. Whereas [part 1 of this tutorial](/horizon-worlds/learn/documentation/get-started/create-your-first-world) showed you how to create a new world and build the basics of the game, part 2 will take you a bit farther. Part 2 shows you how to import custom models, which are which are complex 3D models that are not available in the public asset library. You won’t be creating them here—you’ll use demo assets so you can see how they’re imported. Once you’ve done that, the tutorial shows you how to write a basic script and attach it to the entity to create behavior. The tutorial ends with testing the simple game in virtual reality.

[source](https://developers.meta.com/horizon-worlds/learn/documentation/get-started/create-your-first-world-continued)

Creating customs models is outside the scope of this tutorial, but if you want to find out more about them, see [Creating a custom model](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/creating-a-custom-model) If you’re looking for the first half of the tutorial, go to the [Introductory Tutorial part 1](/horizon-worlds/learn/documentation/get-started/create-your-first-world) .

The key things you should learn from this module are the following:

*   Importing custom models into your world

*   Adding entities to your game

*   Scripting entity behavior

*   Trying your world in virtual reality **Note**: This tutorial assumes that you’ve completed the prerequisites discussed in [Intro Tutorial Overview](/horizon-worlds/learn/documentation/get-started/create-a-new-world-intro) .

This part of the tutorial requires that you first complete [part 1](/horizon-worlds/ learn/documentation/get-started/create-your-first-world) , as this part builds upon that one.

## Step 1: Add a pedestal and a rifle

In part 1 of this tutorial, you created the graveyard. But if you’re going to hunt marauding skeletons, you’ll want to add a rifle and a pedestal to make it easier (otherwise you’d have to use your hands and that gets messy…)

*   Download the [Demo Assets](https://scontent.oculuscdn.com/v/t64.5771-25/57572945_551676440543626_8228778286502058757_n.zip?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=-DpaYKb5tGkQ7kNvwEZcYs6&_nc_oc=AdnSsPHGkXyw5HF8l2tyR-fdfg41V1y93G0cyEypLWgFGDdBrashPGI84YZMzDKttzc&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfRo3lk6KJOUZqsgjiEFp4T5IknT-ZE3WNbH4RTBMp0BEQ&oe=689BAB45) .
    
    This file is a zip archive that contains a number of pre-made assets that you’ll add to your game (like the rifle).
    

*   Extract the contents of the zip archive. folder.
    
    a. Open the downloaded zip file.
    
    b. Click **Extract all**.
    
    c. Browse to a location for the folder on your local hard drive and click **Extract**.
    

*   Add the pedestal to the scene. To do this, click **My Assets** on the **Asset Library** tab at the bottom of the screen
    
    ![The My Assets tab](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/515073444_756887460182541_1703766811137744765_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=yxDdmAa84AQQ7kNvwFiNv1G&_nc_oc=Adm1iEMiuCQjtXNMlrpNh9L_XX195sFqQBQCpF34QLS-bjKNigjIPhyK_bL3XlmWZOE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQcEkvf3J3keclyGdvvTrOrdiIW8zwqM6-DU3_FtsuAmQ&oe=689BB857)
    

*   From the **Add New** list, select **3D Model**.
    
    ![Adding a new 3D model](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/514366312_756887446849209_4679233969024346019_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=AnmqDO6vgeMQ7kNvwE2Yxhh&_nc_oc=AdnH-Ughol-hRrtHg72BopXkkTefD1ghXPGhJvYwFEaXr02T2QZYmhOKRfMuz2sBOVs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTYTwwgq3WxTTAxml8OHyv10IQj5o3gEPZbwfxQ35Nqtg&oe=689BA10D)
    

*   In the **Import Models** dialog box, enable **Preserve offset pivots** if it isn’t selected already.
    
    Because of the way they move, certain assets use [offset pivot points](/horizon-worlds/learn/documentation/desktop-editor/assets/offset-pivots) , where the point around which they turn or pivot is offset from the center of the asset. This is so animation of the asset can look natural.
    
    Ignore the warning the dialog box shows: all the assets that this tutorial works with are [single mesh](/horizon-worlds/ learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/materials-guidance-and-reference-for-custom-models) files.
    
    ![The Import Models dialog box](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/515276565_756887456849208_4413823266568814632_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=e1IIhKK0vVsQ7kNvwFqqNO_&_nc_oc=Adl7Bqs3RxsNIYn9YRo-cZHt4ufiKmdO7H57swF-dRX8cqAgI2DonhXIaBLtpXhvb6c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQD3cxa3xHjT8fG7q6KUk7SZDZzohM_07iI9WZRxUQJHw&oe=689B854F)
    

*   Click **Choose files on your device**, then navigate to the folder in which you extracted the demo assets.
    
    ![Choosing the extracted files.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/514366476_756887433515877_6413619545446559528_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=LMpA9yoVDJoQ7kNvwHKqs5e&_nc_oc=AdnkuMtwlgqhFvceI6m2EFJ6PHT-HrxkXrBBJMqhfwuEaGeH_YQHsAt2CxxMHWWws8k&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTu1RGfHRyUcV28j8AWQaSowGVwpcEBVWOMzhtDWcXacw&oe=689BAB68)
    

*   From the folder on your hard drive, select the `SingleBlock.fbx` and `StoneBlockKit_BR.png` files, and then click **Open**. `SingleBlock.fbx` is the 3D model file (or `.fbx` file) and `StoneBlockKit_BR.png` is its associated texture file. These are the files that make up the pedestal asset.
    
    ![Select the asset files](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/515092034_756887443515876_6027285087868923840_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=q8s6FniVy1QQ7kNvwHHGsDI&_nc_oc=Adn9yzhPx0jMqs5ZOIQzLTBqaonNV_TR7ejrwhuodvYogLxEjS-7E71y-U40ypHELrQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfRDjOygxxFabive0jydWuW4jP2tZlAWSbB4ERtIdj0dHA&oe=689BA3DA)
    
    These are then displayed in the the **Import Models** dialog box.
    
    ![Asset files displayed in the Import Models dialog](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/515097062_756887440182543_8868542573376784040_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=4Mc5hFxBiesQ7kNvwEpOfHv&_nc_oc=AdlA80r6qYYAD8qJlmHa5uP24wXF3_jMi5zn7v2ToqypsiEVX4Pw7PUHp0lr8lmr0tU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQE8e6mdTuhnJO6Mw-QNP0CxJmq8168KtsKPWw20LSl0A&oe=689B976F)
    

*   Click **Import**.
    
    **Note**: If you decide to leave your world at this point, it’s important to wait for the asset files to be imported into the desktop editor before you leave.
    
    The SingleBlock asset will appear in your library when it’s been imported
    
    ![The SingleBlock asset](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/515875637_756887453515875_4696101948964392756_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=GL1xdnKmjukQ7kNvwHDn0df&_nc_oc=Adn2mC6TWCm6P1yt4Lmmj2Yz6X6SgPFd79Trk1xEUDv4vMmIukpdQ35uGhEU61r7BdU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSRp3rWgyjIps5q3Ip7QWPYBIkVN7WpyfNvPiM1Liei2Q&oe=689B93BA)
    

*   After the asset files have been imported, drag the SingleBlock asset into the scene.
    
    ![Inserting the asset](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/514954847_756887450182542_369195396390371839_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=EKfiWyf_0Q8Q7kNvwH7HCDx&_nc_oc=AdnJaUmqs2JaY8dc6dzhcCL7phLyXr8yRVI0RU3ATdChcUcRN38mR__uu18gWA7OQb4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSXtnGo5ySLaluCBhzQJTuj4GE1wthHjfc9Sas60EhHnw&oe=689BB4C1)
    
    The SingleBlock asset appears in the **Hierarchy** panel as an object named “SingleBlock”.
    

*   In the Hierarchy, rename the “SingleBlock” object to “Pedestal”.
    

*   Enable **Snap to surfaces** by clicking the **Snap to Surfaces** button. This allows you to easily position the base of the object along the ground.
    
    ![Click the Snap to surfaces button](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464129353_573870105150945_5383089439026099930_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=ji6qQJuM04MQ7kNvwFasF-l&_nc_oc=AdmmjL_UMHlFEoBPiJOqbhJbLs4KSMIMGuNsSVaCw_ep86Eao8WzOZPUuegxt9h2Y2Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQqBEqM-3RW6nWnyQZZe1MXq94zqBsP9DVId3nNy7bBtA&oe=689BA167)
    

*   With the Pedestal object selected in the Hierarchy, position it by dragging it by the orange dot. You can place the Pedestal anywhere on the ground.
    
    ![Click and drag the orange dot](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475165196_641654818372473_4879658605534264112_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=08Z60-q5kh4Q7kNvwENKgf9&_nc_oc=AdlBpcIwt9i9GPUg-kfmDfNGM8nKL6mp4pwHLnDlq6IJUAA1Rx7VSpSTSk7BmIkjN1g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQ2xx_teqbP51Y1l3UJ7E6ileMf3aPL9c5ZykweKxioHA&oe=689BA5EB)
    

*   Add the rifle asset to the scene.
    
    a. Open the **Assets** panel by clicking the **Assets** tab.
    
    b. Click **Add New**, and then click **3D Model**.
    
    c. In the **Import Models** dialog box, disable **Preserve offset pivots** because the 3D model for the rifle uses [more than one material for the mesh in the FBX file](/horizon-worlds/learn/documentation/custom-model-import/creating-custom-models-for-horizon-worlds/multiple-materials-per-mesh) .
    
    ![Don't preserve Offset Pivots](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464008566_573870171817605_7978731282074208552_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=cHD9KhsKIksQ7kNvwFYSYVA&_nc_oc=Adn-NF-siXRQ30i0p088OvWsG4vglH8nAtjD15WaUxA7-uN3amT-Wa7L1lbrfDfyqj4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfT3isQEb1ztnzyLsVqYroDlk-JC8QTHeHHjeQulVtkpaw&oe=689BB506)
    
    d. Select the asset files to import by clicking **Choose files on your device**.
    
    e. In the file picker window that appears, select the 3D model file (ACWpnBattleRifle.fbx) and its associated texture files (WpnBattleRifleA\_BR.png, WpnBattleRifleA\_MEO.png, WpnIndictator\_BR.png, and WpnIndictator\_MEO.png), and then click **Open**.
    
    ![Select the five asset files](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464310803_573870025150953_4833471769077242766_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=AgIPcM1ohSkQ7kNvwFxq-3C&_nc_oc=AdlOlzLH3Jq1HIJK0i9Xzl2XXm7AbIWOQIsemuz4tBEu9vGAkdu4SYwaG5JTnbH4KKE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfS1ElshCeEd8kwgnPcGIfYGB5xELrtvn42_hREV-qYQUg&oe=689B9E68)
    
    f. In the **Import Models** dialog box, click **Import**. Wait for the asset files to be imported into the desktop editor.
    
    ![This is what the rifle asset looks like after you import it](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464292127_573870045150951_3415127998518177098_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=-Z8Bb8UGUgUQ7kNvwEwTL8K&_nc_oc=Adll28D0FONaWkAuMS-TRhSWGwYRfHQIAKm0a5zFfshBqL9_0xRx6vxQpF7RmYiAU2g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfRZg4dlGiZKUaMy8m8y6gpxier67sP9dOFDlEAkTmO11Q&oe=689BB7C3)
    
    g. Drag the rifle asset into the scene, and place it upon the Pedestal.
    
    ![The rifle floats over the pedestal](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475232756_641654861705802_4132254507512158168_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=-_E2v3LSiTQQ7kNvwG6eR8r&_nc_oc=AdnvhjQhDGd2ttE_Du6mM4F3flIN7Rmce-pijIwyrbabWO8Z2CO4yeqEfmDprl_s4Is&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSUjlfkH9NAqk_f9YsgAejt-v69NKi0-UcPyUC1OT6flQ&oe=689BA1D7) **Note**: If you’re having difficulty positioning the rifle, remember that you can always use the orange surface snapping manipulator to move objects anywhere along the ground. You can activate it by pressing the “W” key. Optionally, using “Ctrl+G” lets you group the pedestal and rifle as one object, so you can move them together.
    

*   In the Hierarchy, rename the “ACWpnBattleRifle” object to “Rifle”.
    

Your Hierarchy should now look like this.

![Notice that the rifle object contains two child objects](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475582112_641654881705800_8956813367946191943_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=B7XPcVrBCM0Q7kNvwH6p-_n&_nc_oc=AdkZtpWS5LWLPvMTMk3dSgTtCHhy2v5gJseNbgsbPwoLUvcd97t6tu329nrGnO87hrw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQIJvQ-x7Wug6GvWMxNQeBot-DbxvPRqlS-WCLmtOEe1w&oe=689B8CDF)

## Step 2: Make the rifle grabbable

In this section, you’ll learn how to make the rifle grabbable by the avatar.

*   Select the Rifle object from the Hierarchy.
    

*   In the Property panel, set the following two property values: **Motion** = “Interactive” and **Interaction** = “Grabbable”
    
    ![Click the drop-down selection list](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/463983859_573870008484288_2943956617777129080_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=c7mJTGM9PFwQ7kNvwFH5OD0&_nc_oc=Adk0YrlomWDcS6Ade1K2egdFf89AlICA_7v1yChZDVj4mgUKtV5C_HZKrLT5rOHi6go&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSKaabHA1f1ny9n4sJUvx5VGLZ6k7SFsMGEvovIiSRfNw&oe=689B9FED) **Note:** The **Interaction** property appears only after you set the **Motion** value to “Interactive”.
    

## Step 3: Try-out your new world

In this section, you’ll try-out your new world to see what it’s like to pick up the rifle.

*   Click the Play button on the menu bar to enter preview mode. **Note**: Ensure you’ve configured world simulation to start automatically whenever you start the preview mode. Click the the ellipsis icon to open **Preview Configuration** and toggle on **Auto-start simulation on Preview entry** and **Auto-stop simulation on Preview entry**.
    
    ![Ensure world simulation is configured to auto start](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/481784596_667180549153233_231569701181011321_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=X5R_vMi0pTIQ7kNvwHubYW2&_nc_oc=Adnja9xE63_8RzIZEoYuurZjD-Iwd_rHUFkobmukHRJbXwDrFuyuorkOA6YPL8I0shM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTfFc9lp8rVXfNWX-1qeKswwGAFlL0cHPDhELm68n_IJw&oe=689B9950)
    

*   Maneuver the avatar over to the rifle using the arrow keys, and then pick it up by pressing the “E” key. 
    
    ![Press E to pickup the rifle](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475655068_641654875039134_3343217904502966675_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=Q72w1fyMzYcQ7kNvwEgJjkw&_nc_oc=AdmoGf-da77WveSPC3vUd2rKNKPps3FyKi2jxo-eznUN5FqQNtLtEMTIhNlwpLcfJUI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTTPvdd1B_MW3AjK75xHCcMJ5YHItTq9AVR0UOyuGwnXQ&oe=689BA1B7)
    
     The way the avatar holds the rifle looks somewhat awkward, but don’t worry, you’ll soon fix that. 
    
    ![That's not how you hold a rifle!](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475514035_641654871705801_2878061070962689344_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=IwJ8YkDvGjcQ7kNvwGuSTR8&_nc_oc=AdnRFilU4_twFGRWSigAnfHdTv4diBhher9ofcx9lw9IJ-Tjs7OLL7u90FEOI5MQISA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSOPmK4i8ucHImrQKddOSMEJRy6qLMdUuZE952GqPXFrw&oe=689B9755) 

*   Exit preview mode by pressing Escape twice.

*   Fix the way the avatar holds onto the rifle. With the Rifle object selected in the Hierarchy, in the Property panel, scroll down to the **More** section, and enable both **Use VR Grab Anchor** and **Use HWXS Grab Anchor**. 
    
    ![These settings fixe the way the avatar hold onto the rifle](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/469860345_607478945123394_6899703159416175623_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=qnJDAz_oKmMQ7kNvwHGHdjU&_nc_oc=AdmDaaIJdPYDTgIwajkhLpK_OPN8EUk0kEZ_knP8hYNS4SRZffbkqqBbNbp_DzIgh8s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfS9acor0-GBQny4EQv7R6h_7-t9Zd_zUYXxKY1BC8k6JQ&oe=689B932B) 

*   Set a pose to use when the avatar holds onto the rifle. With Rifle selected in the Hierarchy, scroll down through the property list until you see **Avatar Pose**. Click the drop-down menu beside it, and then select **Rifle**. 
    
    ![Select the Rifle Pose](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464342330_573869941817628_7549640582068222270_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=TL9Wu91_O9UQ7kNvwEB4hFP&_nc_oc=Adkk3tazuGQs1cqEhi2vwPSXUbRNgb3yltzdyoKuJFadDCtTCwGZ-wtFa0AX2UyJiQk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSyrmT_o94YU4wWWlC-fXej69sJWY84WyflwbpMvyrYFQ&oe=689B98EA)
    
     Now your avatar can hold onto the rifle properly. 
    
    ![Now the avatar holds the rifle more naturally](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475859865_641654841705804_1105400890562108752_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=jBIrmcq0uzQQ7kNvwHyaRov&_nc_oc=AdnoC6ilT3dnKo7yU_p9wtE8lEZymazaKqWuIPLx7q8zTStDwyUSevEL3cMSIoMhBFw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfS9JkTP1OEMELBiuoCKSsvYHRLlH4VBoh66Egwis-wWIA&oe=689B94AC)
    
     But the rifle still doesn’t do anything yet.
    
    ## Step 4: Add a hello world script
    
    You now have a rifle that you can pick up and move around with, but it still doesn’t do anything. In this section, you’ll make something happen when you fire the rifle. You’ll write code that prints “Hello World” in the **Console** whenever you fire the rifle.
    

*   Open the **Scripts Panel** by clicking the **Script Panel** drop-down. The **Scripts** dialog appears. 
    
    ![Click the Scripts Panel drop-down](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/463979710_573870158484273_6956393922882678343_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=HPwuaEeafmMQ7kNvwGQabXS&_nc_oc=Admo4z722rMBDalg4MrFHGu_JDEUBy3YbiSdkzC8pppNxP7AufCiLI1EX7FhlVP8NSQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSFWYgBv5biWw92xqJyM5EfMJHYEI3790NC1sBsrXMK7g&oe=689BACEF) 

*   Create a new script by clicking the plus button. 
    
    ![Click the + button](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464284760_573870108484278_5626008342355283582_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=ix44kwUMN-wQ7kNvwEUENPg&_nc_oc=Adkln6QNtBOx8tGl9VBzLcx8m7ztGFzLBxwpQe5A3SKd3lpLmDe39_eFxToA1XRf7tc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSQC7-bMD7nKLYTdUqefr5AqL7iYTN98uFgRYpqeADc5w&oe=689B8FC8) 

*   Name your script “Shoot”. 
    
    ![Enter Shoot and then press Enter](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464325206_573869988484290_3165699765154261570_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=RuVBAh6VVPIQ7kNvwFokv_F&_nc_oc=AdnvKMA0LpUsucnFgNTkiB-hQJSSSmSycn9tcA7PETMSVUvuwyBzWnUcE0A84C5YU4E&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQAzq1kgQZA0Av2BTFE8dMtqGe0oUceYpf6N55FJG5C0A&oe=689BB78B) **Note:** It takes a few seconds for the script to appear after you’ve inputted the name.

*   Open the script in VS Code. Click the menu icon next to the script name, and then select **Open in External Editor**. 
    
    **Note:**
    
     Currently, scripts can only be opened in the aforementioned way, from the top dropdown menu. 
    
    ![Click the three vertical dots to see the menu](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464107203_573870138484275_3986572612224730853_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=8aMCRLeohMQQ7kNvwFe6GuJ&_nc_oc=AdlL4faijxkNq6kaULtBIwXYfJeCecio6bOvJKAL7pT-Y3BaI5XOFOyah1SvhBBriKQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTVmlAZ2gm_7TCBAaFsDM8MR-U71-U6JtCiqnkI4UlbKg&oe=689BB4D8)
    
    ![Oen the script in VS Code](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464190660_573870198484269_3483053417967741197_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=P2a-zUDhar8Q7kNvwEVeaLb&_nc_oc=AdnvbW0Bkdtv5A90i_5djV_foKKzmoXteUy0RGSTnNHZUiZIWM7p3Msye-NiKDC1_lU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfRL-8zA4WmInVkHeTX8EEKSsYEwSvrI93tT-QE071QmmQ&oe=689BB8AF)
    
     The new script opens in VS Code in a file called `Shoot.ts`. It contains boilerplate code. 
    
    ![This is the default structure of a TypeScript script](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464177291_573870041817618_3500120114101619688_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=FeUNJ7W6JigQ7kNvwE-Ds75&_nc_oc=Adms9M3usOaNiCyAZf_8yKNxu17ADTjtcJYFQb-emzEEGHvuZej73gQlqq5rZq-tJz4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTklMNJAL5TZDJH7x22jcU-lQzlrJFR3kpjGpLq16s7nw&oe=689BA76F) **Note:** The `start()` function is called whenever the entity that the script component is attached to is created. At this point though, you haven’t attached this script component to an entity.

*   Add the following debug statement to the `start()` function. When the entity that this script component is attached to is created, this statement prints “Hello World!” to the **Console**.
    
    ```
    start() {
        console.log("Hello, World!");
    }
    ```
    

*   Save the script file. You can press “Ctrl+S”.

*   In the desktop editor, attach your script component to the rifle entity. a. Select the Rifle object from the Hierarchy. b. In the Properties pane, scroll down to the **Scripts** section. 
    
    ![Click the drop-down selection list to see your script](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464091170_573869985150957_1926137328255172174_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=zLwBN7rKKo0Q7kNvwEa4PZW&_nc_oc=AdkNRgSqYGsN6b6r3nj7I-yPvjTV0y9gHf9j8286Co2rpOX8sP3lAHImSGj50D_Kg6A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQQUy1UQ9inbZ_5qaGg84vK8h8wj__HgWYYFnmT_6qofA&oe=689BB08A)
    
     c. Attach the script component by selecting “Shoot:Shoot” from the **Attached Script** drop-down selection list. 
    
    ![Click on Shoot:Shoot](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464106799_573870071817615_3222010519411086870_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=klwSwKcLUr0Q7kNvwFG7SNF&_nc_oc=AdnBYrVMBCvhZSv6AmyfII9viT_3zNTTGE1R75bszAx3vTmZ7fNXafCTiA6zuxrflrU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQVBnOJ2dg5Aey8cH1-vKoUGgeybx9Cw-Ty5_OIrE5neg&oe=689BB6EF) 

*   Preview your world by clicking the Play button on the menu bar. As soon as the Rifle entity is created, the script prints “Hello, World!” to the **Console**.

*   End the preview by pressing Escape twice.

*   You can see the debug message by clicking the **Console** tab at the bottom of the page. 
    
    ![Hello World! appears down at the bottom of the Message list](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464178601_573870128484276_4374457029334205218_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=9ds6iAOqVuAQ7kNvwEPI7VK&_nc_oc=Adn5Kz_7TWqXUl1XDyrmAsLhmfsqRAe8iZfr-JjkB6PVtQXve9_iWsw-ZEJeWfvZnqQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTb04mZdGfIbhIExrRWw8dBYGzYTiGiRNQbuFCwJJfaCg&oe=689BA730)
    
     You’ve made your world interactive. The script outputs the message “Hello, World!” to the **Console**.
    
    ## Step 5: Refine your script
    
    But you really want the interaction to occur when you pull the trigger, not simply when the rifle is created. In this section, you’ll revise your script to print a message when you pull the trigger. When the rifle is created, an event is also created that fires each time you pull the trigger.
    

*   Replace the code in the `start()` function with the following code:
    
    ```
    start() {
        // React to an event when the user pulls the trigger.
        this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnIndexTriggerDown, (player: hz.Player) => {
            console.log("boom!");
        });
    }
    ```
    

*   Save your script. When editing your script, errors might appear in the **Console**. When this happens, you can clear the error messages from the **Console** by clicking **Clear**. 
    
    ![You can clear the error messages](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464347386_573869901817632_7646464504087582755_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=ShRP1qatUfMQ7kNvwGE11jh&_nc_oc=Adl7GV7wyYAd8_nXlPzbL_KMGJRMT8CVajv5WPAcPgmbvXJvhVf28toM2SdWDxH_RAQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQaChTeoxk4_aD3pjI8PV4h0X7_zceevXzcXy7l0JH2Qw&oe=689B8A7D) **Note:** Normally, you shouldn’t see any error messages in the **Console** window. If you do though, then try copying and pasting the code instead of typing it yourself.

*   Preview your world by clicking the Play button.

*   Walk over to the rifle and grab it.

*   Fire the rifle several times by clicking the **A** button on the screen. As you fire the rifle, notice that a “boom!” message appears in the **Console** window along with the number of times that the message appeared. 
    
    ![Look at all the booms!](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464389048_573870095150946_7738181260387489635_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=p_5bmgfjqiwQ7kNvwEFh4-L&_nc_oc=AdnoAU0FTf1cMqmNzIOrOgewzE7Q-YWFlGHbqL1LunWbWHrWsimbOl5FcwKFfIIR42A&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfRhT4SbFeNwmqF8w5wjz1fQGdjI-nbPYjr8kX9A5XTkKw&oe=689BB8E9) 

*   End the simulation by pressing Escape.
    
    ## Step 6: Add a projectile launcher to the rifle
    
    You now have a rifle that you can pick up and carry around, but it doesn’t actually do anything except print debug messages. In this section, you’ll make the rifle launch projectiles.
    

*   Select the Rifle from the Hierarchy.

*   Focus on the Rifle in the scene by pressing the “F” key.

*   Click the **Build** button. 
    
    ![Click the drop-down button](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464331432_573869915150964_3815683403137700120_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=JtDNBGjBH_kQ7kNvwH1F1_f&_nc_oc=AdmQuOEy4MVAFc61UYHtGx25a7bROC5anD0RlhJjOuYILidA8xET5oEZL_DvBpOpnyk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSWGQyx21JOXK17ANFlV-APEYJT_PqoLbGSdgACdAIr1Q&oe=689BA69A) 

*   From the drop-down menu that appears, select **Gizmos**. 
    
    ![Click Gizmos](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464197626_573869951817627_8947530193925354975_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=kqhThO20GpcQ7kNvwEDeqwZ&_nc_oc=Adl5n6WIlHBCDsRhs-AX-j8sIFYO6X-IaBY66h6YZMYd_XHZcqwQ7ATJbMrCQyejifw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSq_UOxfcFSSYj9M4OEj5jdOhDormZmjEm4oERSfbBuiA&oe=689BA1E9) 

*   Select **Projectile Launcher**. 
    
    ![The icon for the projectile launcher gizmo](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464179364_573869968484292_6347379331044320910_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=B6OUzzPt0sEQ7kNvwESfgvf&_nc_oc=AdmDh0oiplFnaX894oVhAOv4EqPEJuvyLjy-zVD3vp7S3IqFI67OBc-brlTzdfHeJl0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfS-wRCFZ5O9tXh6bFIyYhmr9y3FWM98is558RStuWTcYQ&oe=689BA327)
    
     The **Projectile Launcher** gizmo appears in the scene, and in the Hierarchy. Pressing the “F” key while the object is selected brings the object to focus.

*   Close the **Build Gizmos** panel.

*   Attach the ProjectileLauncher to the Rifle by making it a child of the Rifle. In the Hierarchy, drag the projectile launcher, and drop it onto the Rifle. 
    
    ![Drag and drop](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464060217_573869908484298_3061206173699646062_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=ISrkf0IFZ_4Q7kNvwFufvmV&_nc_oc=AdlGYn1QPMB2CGXMiS19CwM_EcxWpgWo1FXhNNZG79xh3zU-5Lv79vnqoCz1aGNm0hs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfScR0K8nl4jk0XvDC-VuOjDSY5WDxJ3xnhbj5A_Xck3lw&oe=689BA1F6)
    
     The ProjectileLauncher should appear indented in the hierarchy since it’s now a child object of the Rifle object. You can expand the hierarchy by clicking the triangle. 
    
    ![It's now one of the Rigle's children](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464190942_573870178484271_3293882596374239688_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=iBZQbhzmgbYQ7kNvwGi5Uzy&_nc_oc=AdmgZKU2s-uqVGX8gdtRy3j19lzNuxOaVqEKY-uf1kr_g2BgY286ZsdGVINeNWB-zvg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfRi_2oOikbrBFkfc0CNLA-SrOPGw_L-sQ06W_AsPrHO4A&oe=689B9ED2)
    
     With the ProjectileLauncher selected in the Hierarchy, position it relative to the Rifle.

*   Adjust the Position values of the projectile so it aligns with the aim of the rifle. 
    
    ![Align the projectile with the rifle](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475194437_641654878372467_7693479725163060948_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=pkCTvndlMHgQ7kNvwGL-0v2&_nc_oc=AdmJRT530kboMFZ07tYbN4VrHfxpA_58g6ayAAXWbhAZa18AdVWlXy1GFJGjEqQ3fnE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfS_AMsQm9MMFRq3fKcY28JZhbc6hK7i3ldgya-RXIrHhQ&oe=689B8C3C)
    
     These adjustments in settings ensure that the projectile launcher appears at the front of the rifle, and that projectiles fire in the forward direction. Additionally, to make the projectiles easier to see, adjust **Scale** and **Trail Length Scale** based on your preference. Everything is now hooked up. Next, you’ll edit the code to make the rifle interactive.
    
    ### Section 7: Hook up the projectile launcher
    

Earlier in this tutorial, you got a debug message to appear when you pulled the trigger on the rifle. In this section, you’ll update your script to use the projectile launcher whenever you pull the trigger.

*   To use the projectile launcher, you need to reference it in your script. Update the **Shoot** class’s **propsDefinition** with the following statement:
    
    ```
    class Shoot extends hz.Component<typeof Shoot> {
    
        static propsDefinition = {
            launcher: {type: hz.PropTypes.Entity}
        };
    ```
    

*   Add a statement to the `start()` function that creates a reference to the projectile launcher gizmo.
    
    ```
    start() {
    
        // Store a reference to the projectile gizmo in the launcherGizmo variable.
        let launcherGizmo = this.props.launcher?.as(hz.ProjectileLauncherGizmo);
    ```
    
    With a reference to the `launcherGizmo`, you can call a function on it ( `launchProjectile()` ) to launch a projectile whenever you pull the trigger.
    

*   Add a statement just before the `start()` function that adds a property for holding the launcher options.
    
    ```
    // The options to use when launching the projectile.
    launcherOptions: hz.LaunchProjectileOptions = {speed: 50};
    ```
    

*   Add a statement to the **OnIndexTriggerDown** event for launching a projectile.
    
    ```
    start() {
    
        // Store a reference to the projectile gizmo in the launcherGizmo variable.
        let launcherGizmo = this.props.launcher?.as(hz.ProjectileLauncherGizmo);
    
        // Handle the OnIndexTriggerDown event when the user pulls the trigger.
        this.connectCodeBlockEvent(this.entity, hz.CodeBlockEvents.OnIndexTriggerDown, (player: hz.Player) => {
            console.log("boom!");
            launcherGizmo?.launch(this.launcherOptions);
        });
    }
    ```
    
    This change made it so that when the Rifle is created, you hook it up to the trigger, but now this event asks the projectile launcher gizmo to launch a projectile instead of just printing “boom”.
    

*   Save your script.
    

*   In the desktop editor, select the Rifle object from the Hierarchy.
    

*   In the Property pane, scroll down to the **Scripts** section. Notice that there is now a `launcher` property that you can set. This property appears because you added it to the `propsDefinition` in your script.
    
    ![There is a launcher property in the property panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464076144_573870208484268_3571774494949796316_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=RI68XTxgP9sQ7kNvwGcp_vR&_nc_oc=AdlWnFrpBUGROLdY_BPhwiaYty_TUQiM2Op_T6r2qjsTX0a4urfaJqX2QhP26E6Ip_U&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTSv3thLw0ja5jCrxzy_TxpOenLXdvg90rDROWMiilTyA&oe=689B8B85) **Note:** You might have to deselect and then reselect the Rifle object if this new property doesn’t appear.
    

*   Set this **launcher** property to the **ProjectileLauncher** object. Click on the field beside **launcher**, and then select **ProjectileLauncher** from the list that appears.
    
    ![Select ProjectileLauncher](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464035648_573870011817621_4324077274258554259_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=fVQa-4O9hNEQ7kNvwHjRQGI&_nc_oc=AdmpL600xcl4WMCyJblLIoKdnm4nx_1ot5uJzoPZpd-mBdLOZc03ATdFAe9Ry2gW2Y0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfR64-MXOW930gTzK-8HDt1e0GLwoSwirdF26YsWEztPPw&oe=689BAF4E)
    

*   Preview your world by clicking the Play button.
    

*   Walk over to the rifle, grab it, and then click the mouse button. Notice what happens, a shot appears to come out of the rifle when you pull the trigger. Next, you’ll update your script to accumulate points whenever the player hits the target.
    
    ![A shot appears to come out of the rifle](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475273504_641654838372471_3353505584347988670_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=WlYCtYeFeWEQ7kNvwGvFgwE&_nc_oc=AdmRn-tcc-DBbpFh1LjCXgpNfmf03CWxFOLSDif1842DkOrhR76u8Px4d4726-1d4NE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfTg3JpBZWIYV6Z1FWVsLEbN2C5mq2aPLl2oVlAX0CE5Yg&oe=689BA97D)
    

*   Exit Preview mode by pressing Escape.
    

### Section 8: Count points whenever you hit the target

In this section, you’ll update the script so that you score a point each time you hit the target.

*   In the desktop editor, select the SpawnPoint in the Hierarchy.
    

*   Click **Asset Library** \> **Public Assets** under the Scene pane.
    

*   In the Search field, enter “skeletoncrayta” to find the skeleton.
    
    ![Pirate skeleton](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464152935_573869948484294_7911900688495928080_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=OMCy02gUcEsQ7kNvwHQVo3t&_nc_oc=AdkiGlQNDp8rdJgrfiLlNnOavr7Z_bFp6eBGLPlA3by1lvQ1oFFzhWHx63V0W4FAf_w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfR9BlrM_EjVnwqlkbDGrNxORx86auQgqzKf0VSicvb3SQ&oe=689B9A02)
    
    A skeleton object named [UnityAssetBundleGizmo](/horizon-worlds/learn/documentation/desktop-editor/assets/unity-assetbundles/horizon-unity-assetbundles-overview) is added to your Hierarchy, and appears in your scene.
    

*   Rename the skeleton object from “UnityAssetBundleGizmo” to “Target”.
    

*   Position the target anywhere in the scene.
    

*   Update your script so that whenever a projectile hits an object, a point is added to your score. You’ll need to add a variable to track the current point value, and to initialize its value to zero. Add the following statement near the top of your class, just above the `start()` function.
    
    ```
    // Keep track of the user's score.
    points: number = 0;
    ```
    

*   Add another event listener inside the `start()` function that fires whenever a projectile hits an object. Copy the following statements to the end of the `start()` function.
    
    ```
    if (launcherGizmo) {
             this.connectCodeBlockEvent(
                 launcherGizmo,
                 hz.CodeBlockEvents.OnProjectileHitObject,
                 (objectHit: hz.Entity, position: hz.Vec3, normal: hz.Vec3) => {
                     this.points = this.points + 1;
                     console.log("You're up to " + this.points + ' points!');
                 },
             );
         }
    ```
    
    Your complete Shoot script should now look like this.
    
    ```
    import * as hz from 'horizon/core';
    
    class Shoot extends hz.Component<typeof Shoot> {
      static propsDefinition = {
        launcher: {type: hz.PropTypes.Entity},
      };
    
      // The options to use when launching the projectile.
      launcherOptions: hz.LaunchProjectileOptions = {speed: 50};
    
      // Keep track of the user's score.
      points: number = 0;
    
      start() {
        // Store a reference to the projectile gizmo in the launcherGizmo variable.
        let launcherGizmo = this.props.launcher?.as(hz.ProjectileLauncherGizmo);
    
        // Handle the OnIndexTriggerDown event when the user pulls the trigger.
        this.connectCodeBlockEvent(
          this.entity,
          hz.CodeBlockEvents.OnIndexTriggerDown,
          (player: hz.Player) => {
            console.log('boom!');
            launcherGizmo?.launch(this.launcherOptions);
          },
        );
    
        if (launcherGizmo) {
             this.connectCodeBlockEvent(
                 launcherGizmo,
                 hz.CodeBlockEvents.OnProjectileHitObject,
                 (objectHit: hz.Entity, position: hz.Vec3, normal: hz.Vec3) => {
                     this.points = this.points + 1;
                     console.log("You're up to " + this.points + ' points!');
                 },
             );
         }
      }
    }
    
    hz.Component.register(Shoot);
    ```
    

*   Save your script.
    

*   Test your world.
    
    *   In the desktop editor, select the **Console** tab at the bottom of the screen.
        
    
    *   Click the Play button to enter preview mode. Your avatar spawns into your world, ready to go and get the rifle.
        
    
    *   Walk over to the rifle, pick it up, and then fire several shots at the skeleton.
        
        ![Every time to hit the target, the score increments](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475121433_641654885039133_2447663056588542102_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=eEqDHbwQcR8Q7kNvwGh2kkN&_nc_oc=AdkvQESrEmeFrtRcnypoTnr7tCUacZLw9pshYNJ9eVvGBVhDUXo3dK3vqLmB4LkpZ-g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSCHm1BWt-P_s4VvduUvfe9IqNtFHMhEud6vnIJj9o0Ag&oe=689B8DAB)
        
        Every time you hit the skeleton, a message prints to the **Console** that tells you how many points you’ve scored. If a shot doesn’t hit the skeleton, then the console message simply doesn’t appear.
        

### Section 9: Display the score

In this section, you’ll revise your script so that the score appears in the game.

*   Add a **Text** gizmo to your scene.
    
    *   Click the **Build** drop-down.
        
        ![Build an entity](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464331432_573869915150964_3815683403137700120_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=JtDNBGjBH_kQ7kNvwH1F1_f&_nc_oc=AdmQuOEy4MVAFc61UYHtGx25a7bROC5anD0RlhJjOuYILidA8xET5oEZL_DvBpOpnyk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSWGQyx21JOXK17ANFlV-APEYJT_PqoLbGSdgACdAIr1Q&oe=689BA69A)
        
    
    *   Select **Gizmos**.
        
        ![Select Gizmos from the list](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464197626_573869951817627_8947530193925354975_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=kqhThO20GpcQ7kNvwEDeqwZ&_nc_oc=Adl5n6WIlHBCDsRhs-AX-j8sIFYO6X-IaBY66h6YZMYd_XHZcqwQ7ATJbMrCQyejifw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSq_UOxfcFSSYj9M4OEj5jdOhDormZmjEm4oERSfbBuiA&oe=689BA1E9)
        
    
    *   Select **Text**.
        
        ![Select the Text gizmo](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464276063_573870021817620_5656500703368336488_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=tyiRHxFN3dUQ7kNvwHJxUJh&_nc_oc=Adk3I6bLB_zaRvqQdUC9vp7unnBO1SjBFT21T0v42GI7snQHipktKtJrR20c1Ui7T4I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSpVKF7hpkChGr2_DbBsk_FFatqM3_RS7-kCJl4CKGuRA&oe=689B9D09)
        
        A **Text** gizmo is added to the scene.
        
    
    *   Position the **Text** gizmo within the scene so that you can read the score while you’re shooting at the target.
        
        ![Position the Text gizmo so you can read the score](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475549601_641654858372469_2650846579364077855_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=vtmAyqPmfZ4Q7kNvwEUGfu7&_nc_oc=AdmdBisfthwLM6DNTsGn3l9bHJacP-f-fLI0GuCJl7VrZvRifsNr5hTD26PCsctdl1o&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQfFsZQrWIH8ndcASwdMHFInsyWf7hMIW2Xan5tHM910A&oe=689B9D74)
        
        You’ll need to rotate the **Text** gizmo so that the text displays in the correct orientation.
        

*   Update your script to use the **Text** gizmo. Remember, if you want to reference an entity property within a script, then you need to add that property to the `propsDefinition`. Add a `scoreView` property to `propsDefinition`.
    
    ```
    static propsDefinition = {
        launcher: {type: hz.PropTypes.Entity},
        scoreView: {type: hz.PropTypes.Entity}
    };
    ```
    

*   To be able to use the `scoreView` property, you need a reference to `scoreView` as its specific type: `TextGizmo`. Store a reference to the `scoreGizmo` object in your `start()` function.
    
    ```
    // Store a reference to scoreView as its specific type: TextGizmo.
    let scoreGizmo = this.props.scoreView?.as(hz.TextGizmo);
    ```
    

*   Update the scoreboard text by adding a single statement beneath the `console.log` statement that calls the `scoreGizmo.text.set()` function.
    
    ```
    this.connectCodeBlockEvent(
      launcherGizmo,
      hz.CodeBlockEvents.OnProjectileHitObject,
      (objectHit: hz.Entity, position: hz.Vec3, normal: hz.Vec3) => {
         this.points = this.points + 1;
         console.log("You're up to " + this.points + ' points!');
         scoreGizmo?.text.set(this.points + ' points');
      },
    );
    ```
    

*   Save your script.
    
    Your complete script should now look like this.
    
    ```
    import * as hz from 'horizon/core';
    
    class Shoot extends hz.Component<typeof Shoot> {
      static propsDefinition = {
        launcher: {type: hz.PropTypes.Entity},
        scoreView: {type: hz.PropTypes.Entity},
      };
    
      // The options to use when launching the projectile.
      launcherOptions: hz.LaunchProjectileOptions = {speed: 50};
    
      // Keep track of the user's score.
      points: number = 0;
    
      start() {
        // Store a reference to the projectile gizmo in the launcherGizmo variable.
        let launcherGizmo = this.props.launcher?.as(hz.ProjectileLauncherGizmo);
    
        // Store a reference to scoreView as its specific type: TextGizmo.
        let scoreGizmo = this.props.scoreView?.as(hz.TextGizmo);
    
        // Handle the OnIndexTriggerDown event when the user pulls the trigger.
        this.connectCodeBlockEvent(
          this.entity,
          hz.CodeBlockEvents.OnIndexTriggerDown,
          (player: hz.Player) => {
            console.log('boom!');
            launcherGizmo?.launch(this.launcherOptions);
          },
        );
    
        if (launcherGizmo) {
            this.connectCodeBlockEvent(
                launcherGizmo,
                hz.CodeBlockEvents.OnProjectileHitObject,
                (objectHit: hz.Entity, position: hz.Vec3, normal: hz.Vec3) => {
                    this.points = this.points + 1;
                    console.log("You're up to " + this.points + ' points!');
                    scoreGizmo?.text.set(this.points + ' points');
                },
            );
        }
      }
    }
    
    hz.Component.register(Shoot);
    ```
    

*   In the desktop editor, select the Rifle object from the Hierarchy.
    

*   Scroll to the **Scripts** section of the **Property** panel. Since you added `scoreView` to `propsDefinition` in your script, this property now appears in the **Scripts** section of the **Property** panel.
    
    ![The scoreView property appears in the property panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464222401_573870035150952_285145257509364434_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=7IQ_fc4E4MAQ7kNvwGXF2Uo&_nc_oc=AdnaJ7BDl-oTvUI3Ku692fTOp_MoNLEQ51XsWfRDFTvQDnJrq7rhAiMLj-T_Wj3bDNk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfQF6YiCvqGHE4WCVowK3RK-_ZY7t-RFqgmP7Y7TK9MTPg&oe=689B9A75) **Note:** You might have to deselect the Rifle, and then reselect it if this new property doesn’t appear.
    

*   Set the value of `scoreView` to the Text gizmo that you added to the scene. Click the drop-down selector beside the label **scoreView**, and select “Text”.
    
    ![Set the value to the Text gizmo](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464088168_573870068484282_6798580279511898058_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=7wJHA3xTWjYQ7kNvwGNjXSp&_nc_oc=AdnniY_6ElA96W6ynBdUi3ycka-9r1dfd__-FnpLBkXdUjekPNJoyuqHjzWUQE5HPZI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSXrVS9aYfpry7bN5d4MnMI4yWyextqodm69M0vLkKFZQ&oe=689B840B)
    

*   Test your world.
    
    *   In the desktop editor, select the **Console** tab at the bottom of the screen.
        
    
    *   Press the Play button to enter preview mode. Your avatar spawns into your world, ready to go and get the rifle.
        
    
    *   Walk over to the rifle and grab it, and use it to take several shots at the skeleton.
        
        ![Rack up some points by shooting the target](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475293293_641654835039138_2953793375639169747_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=kjNiV2YbHMkQ7kNvwHQAvib&_nc_oc=AdliF4_ECDrG4GEXWtI8SsjkVxew4f6RL7iwYNsmtHZug5y6SSA0eXYJOHXc1AeAi_g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfR904cLz7OOZRIM7Kkk_-wPIHhV5HlHl91cIkmcSw-Cpg&oe=689B9E46)
        
        You should see your score floating in space, and it should increment each time you shoot the skeleton.
        

### Section 10: Create a second rifle

In this section, you’ll convert your Rifle/ProjectileLauncher combination into a Template Asset, and then you’ll use that asset to create another rifle.

*   From the Hierarchy, select the Rifle. This object has the script attached to it, and it’s also the parent of the ProjectileLauncher.
    

*   Right-click the Rifle object in the Hierarchy, and from the menu that appears, select **Create Asset**.
    
    ![Turn the Rifle object into an asset](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464006274_573869955150960_8083174888610967206_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=88t5blw7O2kQ7kNvwGCHJhi&_nc_oc=Adn_ohy1R4xy73zgpr7kbOOqs2WB_6k0EfZ13RjvbndC5SeXlKDEo_dUQqaU4-BOIM8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfRBUAd-N9wK9qwrM8eVrDyndFhuChkVdt_1X6nc_bp7zA&oe=689BA575)
    
    The **Create New Asset** dialog appears.
    

*   Type a name for the asset, and type a description of the asset, and then click **Create**.
    
    ![Fill in the asset name and the description](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/473721798_631480272723261_8456815458843473069_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=1tvljicVUawQ7kNvwFbIsUf&_nc_oc=AdnaAIoOjpREILGg1xR-ajrR6tn9hdn8W8KPBQQ6ruaZkbVuSbOZrlzoY2b-Pr3RZTA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfS_njhjX5UbowJPg9WWMB7E2d95PO9clRVLzKgZ6lXI8A&oe=689BB865)
    

*   Open the **Assets** tab, and then select the **My Assets** folder. You’ll see your second rifle asset there.
    
    ![Your new asset appears in your My Assets folder in your Private Assets Library](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/464099449_573869905150965_6806556283750141783_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=0dTU6Q4OZ_oQ7kNvwGWjNR3&_nc_oc=Adk6Fcfcqkb3FK5Jxu5cpsRcA0EeXs3wJoeN-iuqS25ooIZUdZzhTIwiUTvZjD3qBO4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfSlJyDPo92A-1iJLHoPuoaKRvyrS8wjVKm7Iec6O0BiPQ&oe=689BB25A)
    

*   Click and drag the new AutoRifle asset, and drop it anywhere in the scene.
    
    ![Place the new Rifle anywhere in the scene](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475226479_641654815039140_955495808021670869_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=CkEbNRDnRhkQ7kNvwEMikGD&_nc_oc=Admm6GX19-f6oTSmZcg084YU41KrxhW1Qtv97RPEDiWEJU5-DWs-dOKG0BIv2UPrjSk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3H0GT9M0Q-fvoTNnMTMYvg&oh=00_AfR40l7hU3PleHgHy4i7RI5Eaf5uV053qN7yndOCkGTuSA&oe=689BB100)
    

*   Test your world. Press the Play button to enter preview mode. Your avatar spawns into your world, ready to go and get the second rifle.
    
    Notice that you can use either rifle to shoot the skeleton and generate a score. Each rifle has its own score, which means the text box swaps between the scores as you swap rifles.
    

You’re done! You’ve completed building a game in Meta Horizon Worlds! In the next section (which is optional), you’ll try running your game in 3D on a Meta Quest headset.

## What’s next?

To learn more about Meta Horizon Worlds, try the following:

*   Try the [Batting cage tutorial](/horizon-worlds/learn/documentation/get-started/batting-cage-tutorial) now that you’ve created your first world.

*   Learn about the desktop editor with the [Introduction to the desktop editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor) .

*   Learn about the other tools available by reading our [Tools overview](/horizon-worlds/learn/documentation/get-started/tools-overview) .

*   Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs) to learn about our program benefits.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 