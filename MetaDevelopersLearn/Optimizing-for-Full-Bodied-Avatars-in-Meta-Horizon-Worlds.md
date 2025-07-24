# Optimizing for Full-Bodied Avatars in Meta Horizon Worlds

[source](https://developers.meta.com/horizon-worlds/learn/documentation/full-bodied-avatars/optimizing-for-fullbodied-avatars-in-horizon-worlds)

Legs are a highly requested feature in Meta Horizon Worlds, and we need your help to make sure everyone has the best experience possible!

We are continuing to iterate on and improve this new feature and will be rolling out more updates in the coming months, including future gizmos and attributes.

In the meantime, we have compiled some common interactions we recommend testing in your worlds, along with suggestions for how you can optimize the user experience.

## Sitting

We are planning to create a feature that allows users to sit down on designated objects, however, this functionality will not be available for the initial release. If your world includes objects like chairs, couches, benches, etc. that act as a place for users to sit down, you will have the option to toggle the collider button on or off for an object. If the collider button is on, instead of sitting down, users will stand on top of the object.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452955956_512524657952157_7212687131136946060_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=qc239jKv8tYQ7kNvwHfr11M&_nc_oc=Adl3ZG3SY8WMdttjke3RDpjuH6itjR9zR0P2UN26GXpNVdln-YjRFBJ034hxObWTn4M&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkeQ1isygKaD-398Cn08Dg&oh=00_AfS1tOo3NakKp6bQk3sSvkzca3E1n4-5ndOfHBzYyvOMuQ&oe=689BBF0A) **Option 1:** We recommend keeping the collider toggle off for objects that moonlight as a place to sit down. This will result in the users’ legs going through the object keeping the same height and line of sight that users previously had when they hover over objects.

![](https://scontent.oculuscdn.com/v/t64.5771-25/75207242_562279153227418_599634313314509174_n.gif?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=AZoGaAj_gDUQ7kNvwHfgvFd&_nc_oc=AdmrxejNrEsU4I4snB5Wml-B7jUGYm-0lQcQmea9fSSp-BNUGbJ9IYP3mGxJ7_Hi9ys&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfTfJeGRtRdyt7Dp5_syc7diYkj0yuReBHy7tcyh_fbRlg&oe=689BA107)

![](https://scontent.oculuscdn.com/v/t64.5771-25/38982610_542616035054591_8643514275666338455_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=MZimllBoTCAQ7kNvwGOh1T-&_nc_oc=AdkYeU3nV_QBXEWoHf3MMjTTSYVd4Wvwb-71z-yrLqrDkAJwe_-KB-tjK92lsZF1CO8&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfRpmv-9YbYlbYPr-Gsgv4QmfcKgu6_nIAnGIQIydoQzJQ&oe=689BC10C)

Along with the recommendation of keeping colliders off for objects meant for seating, you can modify objects to cover the entire lower parts of the avatar’s bodies. This hides the avatar legs going through the object which can help with the overall aesthetic experience of your world.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452877644_512524711285485_7785913168880931089_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=inFfKyT5uLwQ7kNvwF1eo_q&_nc_oc=AdkozeO-UjeMgrF9HII76k8rhgPek_ZEGdQOs5XG_oSgGh-njYqVXeYrLlZrIBMaDzw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkeQ1isygKaD-398Cn08Dg&oh=00_AfSHF82CBzM2Te_CaqcGoGXiEl044MpQahrFpJE2JBllnw&oe=689B9FCB)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452513279_512524654618824_1566021560621853229_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=IyohY4Koql4Q7kNvwHfnmJp&_nc_oc=AdlNZAfJtGfttbyE6ttULwMjQbqIhXnlBJSxB90iZnvBi-8sC54xEAmiZDXWxH-aOwQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkeQ1isygKaD-398Cn08Dg&oh=00_AfSs92dYYyAVmCQPh8GG5z9azSIfEgd0yR9Pb57uzfKZuw&oe=689BBF04) **Option 2:** Alternatively, you can remove seating objects entirely, and convert tables into high top tables or high top bars and remove seats. *![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452671989_512524651285491_369048775729201604_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=mnEWjH0AB_UQ7kNvwEyFn8W&_nc_oc=Adk0niOe5FwPxNglVtaOBPehtDmKh0JDLTrIhyyAQpsWaik7vCwIrU-kE3l0ko0V2oM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=bkeQ1isygKaD-398Cn08Dg&oh=00_AfTyMrOJg1-kNU17vpFhR6CnJeTBI3VwfigvMZ4jG2kBzA&oe=689BAF30)* ### Clipping of Feet on Ramps and Stairs

Feet may clip when walking on ramps and stairs that use an (invisible) ramp as a collider. Adjust colliders to prevent clipping of feet into stairs, ramps or the ground. This may also help ensure drop shadows show up consistently across worlds. **Option 1:** Move the (invisible) collider ramp up so that feet don’t clip, but this might create some floating feet. **Option 2:** Remove the invisible ramp collider and turn on collisions for individual stairs. Make sure the height between stairs is low enough that users don’t need to jump to go up them.

![](https://scontent.oculuscdn.com/v/t64.5771-25/75221323_871126325010914_1249234752214974528_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=6_9PpUyWHy8Q7kNvwH5lR36&_nc_oc=Adk9vP7nvwK6UpMR0ubpN7wqV9Vq40d_2R78y7V0fm86WI3vidN98EebU90fz8bBXCU&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfTA5DXTDqfAx0ssEKGfB22KBxpeh9i715eqNNAA7t5J0Q&oe=689BA633)

![](https://scontent.oculuscdn.com/v/t64.5771-25/39031387_1126158859510461_3379014022272679256_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=DHoM6aB2t0cQ7kNvwFdmJ88&_nc_oc=AdlMVtA3_AWBQ8PZko8GjZCZyLISxBCYGqUlMT1UgAktw_cE4IXB5d4-pR6AO56hofY&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfSuHR66yXX-iJGqIZHLo4_YmHFH2Qmm_O6BVWcxHTldKQ&oe=689BA828)

![](https://scontent.oculuscdn.com/v/t64.5771-25/38974721_534714159465403_1403686194185599494_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=aBxJiawqDFEQ7kNvwHVbDcO&_nc_oc=AdlCOnmC75nZOYEX0j8jL7dESjXnFO1Crf1pU3m6ofpLuCL4dJ9SyqQsQt3X20KGmC8&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfRHSbisLv0borfsl0M_cRHhcouQotU7JFr7J-FI_sFM2A&oe=689B9D31)

### Frequently Asked Questions

*   Can I share that I have early access to legs with users outside of the early access program?
    
    *   No, please keep this information confidential.

*   I can see everyone’s legs. Can people outside of early access see my legs too?
    
    *   No, only people within the early access program can view legs. Think about it like having ‘legs glasses.’ You can see other users’ legs but they can not see your legs.

*   Why can’t I see my own legs?
    
    *   You may not be able to see your own legs when you look down but you are able to view them using the mirror or selfie camera.

*   Will the addition of legs impact my world capacity?
    
    *   Legs should have a minimal impact on world complexity / capacity.

*   Can I assign a different damage value for legs?
    
    *   This functionality is not supported at this time. Damage to legs will register the same as damage to torso.

*   Am I able to create attachables for legs?
    
    *   You are not able to create attachables for legs at this time but this functionality may be available with future updates.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

![](https://scontent.xx.fbcdn.net/hads-ak-prn2/1487645_6012475414660_1439393861_n.png)