# Using Variable Groups

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/variable-groups/using-variable-groups)

Variable groups let you create sets of persistent variables that you can share across your worlds. This approach lets you build cross-world experiences using persisted information from any of your worlds. You can access the variable groups system from the **Systems** tab of creator tools. On this tab, you’ll find three sub-tabs that display the following types of variable groups. Those:

*   **Added to the World**

*   **Owned by Me**

*   **Shared with Me**

With the introduction of variable groups, you are no longer restricted to using just six variable groups per world; you can create as many variable groups as you want.

> **Note:**
> 
>  To use the persistent variables from a variable group in your world, you must add that variable group to your world.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452554253_512536417950981_1692974654504870135_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=0EULEnOOsnkQ7kNvwGwS_FP&_nc_oc=AdnP5kygdAXecmQiztanZvn1w1UB7fNgIKoB4xb5Ku9rjZgo_DWNTXKIZdSFMJiSraE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfQO4gd-C_uVkYhVbqa5LVck3miaV5umQK3U_VQ0APrcIQ&oe=689BA780)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452665654_512536497950973_1194272625607849774_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=gJeUqhDQqF4Q7kNvwFISpaD&_nc_oc=AdlhI2M-XsA_ZzH43umFVpx6dJo7PYFPXRYlxo4LyPPEdOhOYaoW3eawVgvjUVihGbs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfR82ddkw8D9_SN9rvofFgoLhgpkJ1RZbWoibsPK5G10ZA&oe=689B9D30)

When you select a variable group, you’ll see all of the persistent variables that it contains. From here you can create, edit, and delete persistent variables from within a variable group.

> **Note:**
> 
>  You are limited to adding up to 100 persistent variables to a variable group.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452852984_512536451284311_5925156470849501450_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=751GERWRv2MQ7kNvwFdtnQn&_nc_oc=AdlpqzI_D9R9QxmxVGe14ZaSdqBKh3Xaur9t7pEFJk22NWUFi5nzKDaWO4v1yZPez-w&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfSRb5Q0Q470salVQgVTjfPblhGKx-DrZoGtPY4jIMMIxA&oe=689BA700)

When you create a variable group, you can edit its name and description, and you can also choose whether you want to add it to the current world.

> **Note:**
> 
>  In order to add the variable group to the current world, you must own that world, and it must have less than six variable groups already.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452756647_512536487950974_3070301593230605430_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=gFm7ShjkFWEQ7kNvwHGhPNU&_nc_oc=AdmLCjzv4SYt3cPE7k7oioXn6IOOGc5y87uYrhxS_Lqoz8iR7sd2jRlKYJee30vqhas&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfTsgFpE6oghxAs8u6AqRBfcuWa9StsWgYll-Kaymvuk5w&oe=689B9537)

Once you create a variable group, you can then edit it, or delete it. Be careful when you delete a variable group, and when you edit its name. Editing the name requires that you update all of your scripts that use persistent variables from that variable group. Deleting a variable group also deletes all of its persistent variables, which breaks any scripts using them.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452864153_512536484617641_8300507730140246292_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=mv9aRL2gRFEQ7kNvwEoZYvh&_nc_oc=Adkq-Zb20dE8GKRm8osBVmjhY2HgGAk6xJcugRtttydyRsG_zlaJfU98tSKgj-6ziI8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfSb_Z6tmUYpzYdXZeRH9zHDdQpsex0MRddLYgAF_Xsl6Q&oe=689B8685)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452873933_512536414617648_4553408675355629305_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=_UPnOarGFvAQ7kNvwFjMDVy&_nc_oc=Adk0fvbSc_cH7j_YUao_FaNrXacZpE6dj_XIDoxaQuSZ-suUL2hOwohLVohKY47w42k&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfTcjsTqa3Yj0BL8mMz6ZpNFPpggeJyLz9jidfHtgBfekg&oe=689BAC2F)

When you add variable groups to your world, you can then access their persistent variables using “set” and “get” persistent player variable code blocks in your scripts.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452819269_512536471284309_8749603936744434663_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=KyrZJyYoApoQ7kNvwEihZH_&_nc_oc=AdnG2xaF8fuiR1shLQeWwSM_1jYGtiW2q3REEA4vudBItW1iWhrWuTwm1lkmxZRk2Lg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfTQI-8SzdMcujxuJe2HIn5n_Yj2qnPpMnaZFwbk2RgB6g&oe=689BB047)

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452885444_512536371284319_6701700970291792058_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=snJB1oQzyXAQ7kNvwGIECZG&_nc_oc=AdlbKIiccmosyA7RohWqGDoSkZt01y2W9ulLqBSkjgf1pNoXFPhpSaqxPv6a7yX7jkA&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=whN02ezc_WVBcb6D5iv9jw&oh=00_AfSJ52D7v-6SZUvu1_TnEDKwDsq_QikBKsmbAZXgm1Wn2g&oe=689BB0A7)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 