# Performance Scrubbing

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/performance-scrubbing)

Horizon’s scrubbing feature enables you to analyze performance events in your world. This testing procedure will help you identify events that are causing slowdowns and will provide important clues on what to do. Scrubbing can help you solve performance problems by making it possible to selectively step through and analyze graphical data displayed in the Performance Metrics panel. This data includes metrics for frame time (FPS), GPU time, scripting, physics workload, other users building in Horizon, and more. These graphs are compiled from the last several thousand frames, about 30 seconds while playing at target FPS. Scrubbing adds the ability to inspect the graphs and test the data in the following ways:

*   Select a range of frames from the total recorded.

*   Move and resize the selected range.

*   For all metrics, select an individual frame to see the value at that frame.

*   Determine which metrics are above their target value, including when that happened.

*   Expand metrics to see metadata, such as the average, minimum, maximum, and target values.

This scrubbing procedure can be done from within Virtual Reality (VR). You don’t have to take off your VR headset, and you don’t have to use passthrough. This will allow you to analyze and test performance and regressions easier and more efficiently.

## Use case

You’re testing a new weapon in your world, so you have the real time metrics panel open. When you fire the weapon, you notice that your frame time graph spikes, revealing a slow down in your world’s performance. To find out why this may have happened, you click “inspect” and open the scrubbing panel. You look for the spike in frame time, adjusting the scrubber to highlight the frame where it occurred. You scroll through other metrics, noticing that there is a spike in the scripting metric. Scrubbing has given you a clue that you should check the scripts for the new weapon and work on their performance to fix the spike.

## How to perform a scrubbing test

Follow this procedure to perform a scrubbing test to analyze the data provided in the **Real-time Performance Metrics** panel:

*   Open the **Personal UI** (PUI).

*   Click **Settings**.

*   Select the **Utilities** menu if it’s not already on. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452532074_512527651285191_8177576968897515344_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=Z7MCTD3Q03QQ7kNvwEFydvV&_nc_oc=AdlBGw5wZHJEyBa7stoslbYeBSAbMu5tExVhAIhN7urwoDRLt7rdO8Pes9rypiO5Ms4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfTPionnSZXY7MHrq_5r0ehWJkmQjmB7ODoD3BhwmdFE8w&oe=689BAF35) 

*   Travel to a world that you can use as a test, such as Super Rumble or Arena Clash.

*   After it loads, look at your avatar’s wrist. Turn your wrist to make the wearable appear. This  wearable is a hands-free tablet-like device that displays the **Utilities** menu.

*   On the **Utilities** menu, select **Real-time metrics**. The **Real-time Performance Metrics** panel will then open. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452701462_512527674618522_722303316862230619_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=CNar8soWe9QQ7kNvwE9BnwG&_nc_oc=Adnexd-9sIyPhncWE7CJHMMgsEL7oEvppo_9hXbSOLEEZjptXCaFB2laosW0LoQb9pg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfSiChbUIy9l1MYl_bH8n32ZpYWFY41HsYSqg00nzF0mMA&oe=689B9E67) 

*   Perform an action to start compiling metrics that you can analyze. For example, you could pick up a weapon and shoot it, use your Super Power, or shoot a drone. As a result, you might see spikes in some of the real-time graphs or other details indicating activity.
    
      
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452814680_512527671285189_2521814497190586262_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=JaLDxIakKhQQ7kNvwGej-r_&_nc_oc=Adnync1PyJLuuxKPAjqPARR1ccMZT0AgKEaOlqcYm5v1oIK5T4GnWGruh-5g2awI7KI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfRWJhMNPcb9baPXX1GHjdAHn0emwnw0keAaJ5_SwIQqJQ&oe=689BADF0)

*   After you’ve put some data into the **Performance Metrics** panel, select the **Inspect** button, and scroll down to see the available metrics. Notice that spikes from the real-time graph  also appear here. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452589609_512527667951856_3972198912793986595_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=KkVu8z_Wc3UQ7kNvwEsvF2Y&_nc_oc=Adm16ZoQAgYlS1lRxn5E9A51BEb4MaU_lm8wVha2dTQqVbUdAOcmcVZLciJgLyjs5Go&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfR1qDRCep_gjHFD-EaxCYGUyx8qt_ujyg14NDl5ZSIzJg&oe=689BA7FA) 

*   Now you can use scrubbing to evaluate the data to identify where the performance problems are coming from. Here’s how to use scrubbing to test performance issues:
    
    *   Adjust the viewing range by clicking and dragging the sides of the blue range selector in the **Frame Time** header graph. This will change the data displayed in the graph. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452485848_512527644618525_1671174476556124032_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=OyCkOGhHBQMQ7kNvwEgBNiw&_nc_oc=AdkambEtQf7WXLkrhxrkLtnz46CuYstGjvY_7A_va5M1LbQVk4ftxXQiISCn-J0GiLY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfR0ec6wNUBWbIHOu-rnoEGJOLAlc8GlI6OJBqc7ssWtvw&oe=689BA3F0) 
    
    *   Move the range selection without changing its size by hovering over the middle of the blue range selector and grabbing and dragging it. This will change how the data is displayed in the graph. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452934094_512527661285190_955464009422810835_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=J3B3bZ8BMKwQ7kNvwGj_qts&_nc_oc=AdnyU0eNFpI_N6H-RAWiveEJzfBvi7nqQ2rlOprNf7lmhm3vR5_lxL6q7Kf7EuxaBE0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfToua8kf6QHkvpLiq5kjwI8VsccOS6DviUfDSQYMvqqAQ&oe=689B91EF) 
    
    *   Reduce the vertical height of the graphs to allow for more graphs in one view by clicking on the metric metadata next to the graphs. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452751750_512527641285192_9124308518466871664_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=hzdegYrYLgsQ7kNvwER_KZ0&_nc_oc=AdmGeVCMofyMHkNsrkzmhJukZ9wzyse8foRf8-IBFt3gm3Af4POysP0L-tiPr-CZSBY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfRSn-3F15NqZrkBIGFxPsdCaVsRBkd5IxiUWDqoQ8WTKA&oe=689B9366) 
    
    *   View the value of all metrics at that frame by clicking a frame in the graphs in the metrics list.
    
    *   To move forward and backward by a set number of frames, use the **Forward** and **Backward** buttons above the graphs. 
        
        ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452694024_512527647951858_1112702379597418669_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=I9oP6a4O-4YQ7kNvwGWK_-I&_nc_oc=Adk0g9jg9GXYaz5AeAgndMsjwksscf8WbpH0cl2sf-Gsb7itLCp-W8Gxisjr18KpT88&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=IRBVoog_Wc9Z4CXyyuNk-g&oh=00_AfQo2eIpbwXjGWRFapMSw8bJ-C5ETf5XU8pxV7C0_TflPg&oe=689B9CDA) 
    
    *   Move a graph around your view by grabbing the white bar beneath the panel.

*   When you’ve finished analyzing the data, you can return to the **Performance Metrics** panel again by clicking the **Back** button, or you can close the performance tools entirely by clicking **X**.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 