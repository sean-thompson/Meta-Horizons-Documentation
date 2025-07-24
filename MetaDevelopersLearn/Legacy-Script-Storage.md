# Legacy Script Storage

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/legacy-script-storage)

Legacy script storage availability

As of 2/20/2025 all new created worlds will use the file backed script storage solution. The contents of this document applies only to worlds created before 2/20/2025 that have not opted-in to the file-backed scripts solution.

There are some important differences between the legacy script storage solution and file-backed scripts for worlds that leverage the legacy solution.

*   There is a size limit per script of 32 kb.

*   [Scripts in legacy worlds don’t have an ID and rely solely on script names.](/horizon-worlds/learn/documentation/typescript/script-storage/filebacked-scripts#How-script-identification-works)

*   There are some differences in [asset behavior](/horizon-worlds/learn/documentation/typescript/script-storage/filebacked-scripts##benefits) between the legacy and FBS as script storage options.

## Opt-in to file-backed scripts solution

If your created world is on the legacy system, you can always opt-in to the file-backed scripts system at anytime. **Note**: Clones of worlds that don’t use file-backed scripts will not use file-backed scripts unless opted-in.

To opt-in to file-backed scripts as your script storage solution use the following process:

*   Open the **Scripts** dropdown and click the **Settings** gear. 
    
    ![Horizon scripts drop-down menu](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452597170_512510831286873_3548532530261191130_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=dxsCHvqnnSQQ7kNvwFcRTj4&_nc_oc=AdnebiHCXVbxNn0becwG1MGoikA0ex_lf7yIk5ruU1twCNa8vff6OZcy2ONN3ckEV30&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T4OjBkX0-eek9XKdz9n2Tg&oh=00_AfSHf6BvY0YukW1X6V2DBiwS3Lc-v7V0J2dCy8PoMHK2tw&oe=689BB420) 

*   Under **File-Backed Scripts**, click **Review**. 
    
    ![File-backed scripts review option select](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452615549_512510827953540_9044292763116055780_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=9gt1qrHn93wQ7kNvwH9KH06&_nc_oc=AdlwScKJZwzKsjE4eQpH9RpdUIsFT0Rr_inMI9cbM6IxMKGLXth5VA29DEsOJ04D1KY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T4OjBkX0-eek9XKdz9n2Tg&oh=00_AfRvXQj-zqli3IAOdnu6_uOqSGreVUM-VQjcqPc9MTj_iw&oe=689BA3D6) 

*   After reading the information, click **Update**. 
    
    ![File-backed scripts update window](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452815592_512510834620206_8372864601099325167_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=qjEFMvapEEcQ7kNvwGiSCX-&_nc_oc=AdkScDm5atsuXDPt4jEvq9x_r1DHCEmLR_4QO01iNH9zraLyUYOCb5_rPOp8gRW2ZrE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T4OjBkX0-eek9XKdz9n2Tg&oh=00_AfSjL1Oqv4nl654fKyF63hYFSim8zxThtLoWENcZVoZhrQ&oe=689BADD5) 

*   Once you click **Apply**, your changes will be saved and your world and all the scripts in it will be migrated to FBS. 
    
    ![Script settings window after opting in to FBS](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452632855_512510837953539_4593726217778374945_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=ODw3eEMyS0cQ7kNvwGkQ9EJ&_nc_oc=Adkjjo78UEl7y7p8f6IK5yaYhyoW1e9cDFzLwsfz7RI-pUmbtxdwV859bkVCwFn5gtI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=T4OjBkX0-eek9XKdz9n2Tg&oh=00_AfSZ9Wwi66NqftXExl0EbKHMWG3yiQQ2E21bSKAgyLkvDg&oe=689BA28C) 

*   A notification will appear when the migration is complete.

## What to look out for after opting in a world

After opting in a world, there are some scenarios where you may need to manually update your scripts and assets to make sure they behave as intended.

### Existing assets won’t be automatically migrated to the new script storage method

If your world uses a mix of world scripts and asset scripts, you must manually recreate your assets to republish them with references to the newly stored scripts. If you skip this step, existing assets aren’t guaranteed to work as intended and won’t get the benefits of the new script storage method.

New assets created in opted-in worlds will use the new script storage method.

### The new script storage method doesn’t allow for multiple versions of the same script in a world (conflicting script versions)

If your world contains assets that reference a different version of a script than the one in the world, those assets will instead reference the world’s script version when spawned. If your world contains spawned assets that reference different versions of the same script, each of the spawned assets will now use the same version of the script. They will use the script version in the world if it exists, or the script version attached to whichever asset is spawned first.

When either of these situations occur, you should see a message in the scripting console to let you know that your world had conflicting script versions and the references have been automatically changed to resolve any conflicts.

To prevent any unintended behavior, update your assets to reference the intended script version. You can do this by recreating the asset with the intended script version, pulling it into the world, and resaving the asset.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 