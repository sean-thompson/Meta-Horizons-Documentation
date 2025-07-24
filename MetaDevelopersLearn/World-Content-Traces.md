# World Content Traces

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/world-content-traces)

World content traces are a special type of [trace](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/tracing/) that allows you to get frame-by-frame details on your world’s performance and understand how the assets in your world might contribute to it. World content traces include data on:

*   3D models

*   Textures

*   Audio assets

*   Colliders

*   Lights

Unlike other types of trace data, you’ll use the Desktop Editor to view and analyze world content traces.

## Prerequisites

*   [Enable the Utilities Menu](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/enable-the-utilities-menu/)

## Start a world content trace

*   Look at your left wrist to bring up the wrist wearable.

*   Select **Tracing**, then select **World Content**.

*   Select **Start tracing** to start the trace. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452627729_512538211284135_1680560941989953568_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=0qxCgrb4CjkQ7kNvwGG3W0g&_nc_oc=AdnP_flx-W15Fj149zYR4qrrEuMFF18xAPuS_p0EEhfcPreFoMUtyhdOtJVWkC109Ro&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfRqWXml4NqVZKBaLjfuIXvO6YRtANh7rcqFY_Orx4mzAQ&oe=689BAC35) 

*   Select **Stop trace** to stop the trace. After stopping the trace, a toast notification will appear to let you know that a data file has been uploaded. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452909159_512538197950803_5004692860220154049_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=qSbsXM0U4WIQ7kNvwHTPsoK&_nc_oc=AdkZaFf3Uo-B2MgQZQwkrwj1wUfRNebCEPefnYNZO04Uzsfg8ff4AC4Oej2Trgut2kc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfRspchcRsCXUL_L0aX8Vzg-X22v33iExs1FUT-Sa0XUwQ&oe=689BC48A) 

## View world content trace data

*   Download your world content trace file from the [Horizon Creator portal](https://horizon.meta.com/creator/performance/traces/) . World content traces have “_worldcontent” at the end of the trace name. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452832291_512538194617470_4099386902496975441_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=0CR6chOk5QIQ7kNvwGDPu5R&_nc_oc=AdmgbCbJoo2_0f4omn1dmm5MBquoqyqMx6n5Vyo-IT8CHdvBx3uvC-umGI-0p7VAdtg&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfSBjF0jlhd13Ir8Lw6LITzOAuNVI6ruy8Hocdmf6Jom1A&oe=689BC3D7) 

*   Open Desktop Editor.

*   Navigate to a world in edit mode. The world you open doesn’t need to be the same as the one the trace is from.

*   Click the **Performance** tab. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452756660_512538271284129_7566327077660467518_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=vAXjULbxipgQ7kNvwFdI_cb&_nc_oc=AdkA-p9PN4bKlP0fNZ1GL9TIEgErkhD5_dfk7y-VdTKAKoJ81TfK74hlffgdjUn8fO4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfQETjzH-wn8jfp4rojugkEXpFokd4fLp7Vh3dkchBNwsg&oe=689BB5B2) 

*   Click **Open a trace** and select one of the world content trace files you downloaded.

You can now use the **Performance** tab tools to:

*   View [performance metrics](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/enabling-and-modifying-the-realtime-metrics-panel) across each frame in your trace.
    

*   View a list of assets that were present in each frame, sorted by the size/complexity of those assets. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452414112_512538191284137_6726784812718804958_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=dJQLR239CDMQ7kNvwFlrpIQ&_nc_oc=Admur6T0U2nXp5h9m9TR2pXhlbM46j3Wj8OGo-8a1QxGUAI43romAZGEebAzWcT3hGk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfSrIa7Pn2f0tlYyx_Oy-0I4T-nxQ6SDO_hmT7bTv4X4vQ&oe=689B9113) 

## Analyze world content trace data

### How to read a trace

*   Use the **Frame Time** graph at the top to navigate between frames. You can drag the blue handles to adjust how many frames are covered in the metric graphs below. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452717824_512538247950798_380120614586118556_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=1-EziDBrMTwQ7kNvwHP5fvb&_nc_oc=AdnHAuaz3idjDUCQRAXtGW2EL6vs601sOuWSqyPUkHjKoC15Lj9e_9vPWSrslQGCKFQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfTmyskmVI0pBGGx7xwWxneohDbxeN6ULee2yIwPGv2PIA&oe=689BB60D) 

*   Read the performance metrics on the left of the trace to find frames with spikes or that don’t hit the performance targets. These are frames where the world might be encountering performance bottlenecks. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452576402_512538244617465_7223126358225556361_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=tYzZ_lI1_FAQ7kNvwGGE5ow&_nc_oc=AdlGETYH9Ow-c11ae1gzSbOi-8onBkKLDPnW66d1FdAf-1cRTAqgQDfTvMbknhe-boc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfS9KVKaylMi_FruWBmzcu7yjXf8t6edp3eG0EcEv8O0KA&oe=689BC206) 

*   Select a specific frame by clicking on it on the performance graph. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452845714_512538267950796_8211092699235899949_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=iU8Q_m9lw2QQ7kNvwGTX2x6&_nc_oc=Adk4SDceBwJxPIYp7bSmaMkJkGLxy8bHx32g8dBHDzwj8akxUwUCA9sjOtneFK8VGAQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfT3RPqyahxolH54grosy4-Cez_K7gIfAypSaW2KO2Ydqw&oe=689BAC7A) 

*   Once you’ve selected a frame, the panel on the right will display a table of the objects or assets present in that frame. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452943077_512538264617463_7118884114866526517_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=Kya5FFNjwhIQ7kNvwGX6lYS&_nc_oc=AdmvpWC65APS5z5_EZcLFk6c1x0AxO4iazTWHEvPo0HtbBft7pTUhLcWxubQ4R8KVVI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfTZCNxzu9xDWCqAFk1WBy_QULhrIZpxtl7mdG2rZw7Z1A&oe=689B985B) 

*   Use the dropdown to navigate between asset categories. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452653820_512538214617468_298449349691023926_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=9EXN0W62-38Q7kNvwEeAfXK&_nc_oc=Adn2PhRq9XqydTG28_JSjsC7E7bTAVjlESOO8wShdE2VckEjAOBhiWtPJ_f1ZKgV8Ko&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfTLti9YZ8-dMAGvrMdM7fxQbfV_qkd6PkZiiaG2SVTfCg&oe=689B9ECB) 

*   Select the **Memory** tab to view how assets impact memory usage. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452412458_512538207950802_8887585162205000161_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=B7EbkKy7lFoQ7kNvwEW3VH4&_nc_oc=Adkyfc66ohyXaAfLcnxvQhevo6G7qrRdlIs2VZlxwqZd8l0YOxdPRx0qzoYf0SnDqlE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfSEl8_HtbHkbIXkeBK-SQeLqmDKeBzdTknwNHVgkhJ8hQ&oe=689B9620) 

*   Using the information in each table, you can identify assets to optimize or remove to increase performance.

#### Example 1: Memory

Let’s say you see a spike in memory for a particular frame.

*   Using the **Performance** panel, navigate to the target frame and select the **Memory** tab on the right. In the **Memory** tab, you will see a list of assets that contributed to the frame’s memory usage, sorted by their size.

*   Use this table to identify which textures, audio, or 3D models to optimize to reduce the memory load on your target device(s).

#### Example 2: Rendering

Let’s say you see a spike in the draw calls and verts metrics for a particular frame.

*   Using the **Performance** panel, navigate to the target frame. The panel on the right will display a list of 3D models that present in the selected frame, sorted by number of vertices. You can also use the dropdown to view other asset categories like textures and lights that may have contributed to the frame’s high draw call values.

*   Use these tables to identify which assets to optimize to reduce the rendering load on your target device(s).

### Other tips

*   Some assets have long names that don’t fit in the table’s cell. Hovering over an asset shows the full asset name. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452853418_512538251284131_3322849073149633988_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=DblAVBOv4igQ7kNvwGuLNF6&_nc_oc=AdnmM1h0aKjKdbYMf1Snr_12g0oWm1rh2QntohIm-4dsDJGIdA8I8iy2r5ERRz5mA_c&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfTWK8UxsjAfUSdnbZee4vfpaeqpaTHUhtdLGtBkycKZeg&oe=689BC2E4) 

*   The table allows you to see which objects use a particular asset. Hovering over a cell in the “Used by” column shows which objects use that asset. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452732874_512538277950795_656838585926029692_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=H-CRZpztDCgQ7kNvwGuYAfm&_nc_oc=AdnmyqnCIINtUu8mpJQfUxMCyH5fa4PG0WGZwnINa95bSu9BhDFmRTqfW8btjTMVER0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfSxEs8QPBTHgfR4WQtvaZhRUig2D_8BXWar_yVmKBrLEw&oe=689BAD0A) 

*   You can select the header of a column to sort the table by that column. For example, selecting the **Triangles** column sorts the table by the number of triangles. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452933997_512538274617462_4478955592479502121_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=dZAYrd1J7PUQ7kNvwHE0Xd7&_nc_oc=AdnxWdCJFTFDfeZ8POI1hB9PFmlRyfCkNRKLHFVjULB9b4COfEK-5ZprlZvsFI1HGYI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfQbpaqhGlc9ccXZdOmfLKygtO0JrcsI22NSd1cwiW5QJg&oe=689BA76F) 

*   Use the search feature to find assets or filter through certain characteristics by name. For example, typing “box” shows rows that contain cells with the string “box”. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452506089_512538201284136_2002422724315318226_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=9Az_pwlbUhoQ7kNvwEZi-uo&_nc_oc=AdkNGq_yh-X7BMF2_cXYi6r8lIOWCr5j0lUu2sY0LoNKr9YttFmU8WAybw24oUvzvwk&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=1uVdamKuUD3sh89Kk85cIg&oh=00_AfQffK0ljLSDJzev60R69MTRDUKUigtNmWE5jityOJTqiA&oe=689B915D) 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 