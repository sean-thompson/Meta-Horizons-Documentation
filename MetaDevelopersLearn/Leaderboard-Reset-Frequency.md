# Leaderboard Reset Frequency

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/quests-leaderboards-and-variable-groups/leaderboard-reset-frequency)

Important

This feature is not available to all creators.

## Overview

Horizon’s Leaderboard Reset Frequency feature lets you set an option to reset a leaderboard at periodic intervals. You can configure the reset interval to one of the following values:

*   **Daily**: Resets every day at 12:00 AM Pacific Time.

*   **Weekly**: Resets every Monday at 12:00 AM Pacific Time (every Sunday night).

*   **Monthly**: Resets on the 1st day of every calendar month at 12:00 AM Pacific Time.

*   **Never**: Never resets. This is the default setting.

## Linking persistent variables

If you use a persistent variable to store a player’s scores in the leaderboard, then you can link the persistent variable so that it’s reset along with the leaderboard. In addition, if a player’s persistent variable is linked, all player entries for the persistent variable become zero when the leaderboard resets.

## How to set the leaderboard frequency

Learn the workflow involved in setting the leaderboard frequency by following these steps.

*   Choose a reset cadence for a new or existing leaderboard.
    
    *   In the CUI, navigate to **Systems** \> **Leaderboards**. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452887990_512510354620254_7933510091704899504_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=o0yFMVO8hwUQ7kNvwGcpxsf&_nc_oc=AdkVQO6_yG-6ewiH1KC9ssvKNgyRo4tfRoIuAV3R3ro-T16lBYzm0LlBNVvYfcZn_FU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=zpCq37GciMt5TD6C161BDQ&oh=00_AfRzDnGnRNO3YewuBZopEnIgXZIbO6SAo8IpOBRvIh_sdg&oe=689B8DAE) 
    
    *   Either create a new leaderboard by selecting **Create Leaderboard**, or edit an existing leaderboard by selecting **Edit**. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452413517_512510364620253_2373137635050804707_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=0vqv68Dy3UoQ7kNvwE9H_b5&_nc_oc=Adnahrzcq80UwpnrVQNvuICf_LMinhktOBZ3RGYW5Q9kPmS2JVL3P6egkPSHGHDDObo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=zpCq37GciMt5TD6C161BDQ&oh=00_AfTRTIAfyU8YaTpexrQDoj1mQQbGyagTNFRuutCTZBE_ow&oe=689BAFF9) 
    
    *   Beside **Reset frequency**, select the interval that you want. This can be Daily, Weekly, or Monthly. The value defaults to Never. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452953630_512510321286924_6693651382984821063_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=T_EVA6JQ1AQQ7kNvwEOz8v1&_nc_oc=AdkgTZ05KAMWU-IjJ8v7NjANnO2-Qur-nUKkG7T-uSS124TBeP5WjUDg9ic7Myb3_4Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=zpCq37GciMt5TD6C161BDQ&oh=00_AfRq8z4Cpf0TGEj-wOTNbP2XSuvzFqJVbN2cI38ShcBhyg&oe=689B946F) 
    
    *   Save your changes by selecting **Save**.

*   Optional: Link a player’s persistent variable to the leaderboard reset.
    
    *   Set **Reset persistent variable (optional)** to Yes. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452588453_512510267953596_8425387457302036980_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=MG9rjBdBGG4Q7kNvwFusVqH&_nc_oc=AdnfKkKqFeag5eSOI75p1TS3Lj1gn7WhKaKMZ1pMVQMNlHmRN8M7LzcA4oAyQThQtZ4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=zpCq37GciMt5TD6C161BDQ&oh=00_AfQXRFMc8ti70EBk5BO-uXpOSFHiXgQVX82ZO6UBHZC6gA&oe=689BA0B9) 
    
    *   Select a persistent variable from one of the variable groups attached to this world.
        
        > **Note**
        > 
        >  : You can link only persistent variables with a number data type. 
        > 
        > ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452757986_512510257953597_3604445875626678830_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=LngnH2vaOlkQ7kNvwEQ0Jl3&_nc_oc=Admf5P7nG5Fe7LByIYH-R4VRK7i_Zjkg5CWqcAXioVeUKVaRBoGxxr025fvMwvY_ls8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=zpCq37GciMt5TD6C161BDQ&oh=00_AfQSFioxZULUoQzH58dZOLx1vNxY1gK43gWBuf3S5r-3FQ&oe=689BA54D) 
    
    *   Save your changes by selecting **Save**.

## How leaderboard frequency affects world visitors

*   All leaderboard entries are cleared on reset.

*   Any user entries to the linked player persistent variable are set to zero.

*   The Leaderboard gizmo shows a reset countdown for any leaderboard that periodically resets.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452818142_512510254620264_910205012762278358_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=Ree8adV6LHYQ7kNvwHf3XYr&_nc_oc=AdmteeU8anoUxQ7LGARP1a-J5Z8316uXmXmmBvUW5OI8_J41IdmNk8_srYqyWgnaiUg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=zpCq37GciMt5TD6C161BDQ&oh=00_AfQe-Q4lZv-oAK1zl8CcflwoifWZ27SaHGQXO0QMAXuqoA&oe=689B9CA6)

*   If there are active users in a world when a leaderboard is scheduled to reset, then all leaderboard(s) scheduled to reset at that time automatically reset.

*   If there are no users in the world at the time of the reset, then the reset happens silently, and changes are reflected the next time a player enters the world.

## Known Issue

The effect of a leaderboard reset takes time to propagate to the gizmo due to propagation delay. In most cases, this delay goes unnoticed. But in a scenario where there are active players updating their leaderboard scores at reset time, there might be a few second delay before all entries are cleared.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 