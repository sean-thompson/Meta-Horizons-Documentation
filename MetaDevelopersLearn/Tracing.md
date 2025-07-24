# Tracing **Note:** You must [enable the Utilities menu](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/enable-the-utilities-menu/) before continuing.

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/tracing)

Tracing allows you to capture performance data from your world for viewing in Perfetto. Access trace settings and controls by selecting the trace icon 

![Trace icon](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/482030104_666482412556380_2531346198919298275_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=06yuSdBt4jYQ7kNvwGUb7aa&_nc_oc=Adm5j-vWR9ay5RlaQkdoPAmTKdQ9GtynrcupEaGCJttIMHbLJOYPr8cMU-c9W68idIY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfQI4qZvM1MtzqaPiOiZupJ3Lf1yigdTtUoYv6wnKP2VMQ&oe=689BB73F)

 from the wrist wearable or the real-time metrics panel (shown below highlighted in red).

![Trace icon on the real-time metrics panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452817263_512535204617769_564960638721355850_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=Wl6p3IE1BTAQ7kNvwHZmIzM&_nc_oc=Adl8ADSCX9KybQHxnkep6kuFULxRPE5aMjlprMIkL7u9d_3XCCA6FsCtEYKiw4_Hdcs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfRhgHj5IFOtjON0jiaiiHsC94ST6O04eDnnz9l1livmVg&oe=689B9BF8)

Selecting the tracing icon opens the **Start a trace** modal where you can select the type of trace you want to capture and start the trace.

![Start a trace dialog](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452819269_512535177951105_486835410582879203_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=6XnmherRfmwQ7kNvwHJGdJN&_nc_oc=AdmxkopEGrtsSTz0uahV1AM6D0pkUWEXAAEGA-osJlSbNW2LWZxE-qwDaMsqFrFXpao&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfRlTlXVE3TLAowUqiwcuX4iPSGjgOo2pQa0Y6Nc8jDNOw&oe=689BC269)

## Trace types

There are 2 types of traces you can run at this time: **Overview** and **Deep**. Both will save a file that can be viewed in Perfetto.

### Overview

An overview trace can help you set a baseline for how your world is performing in visit mode. It captures high-level data like FPS, CPU, GPU as well as a high-level capture of metrics like physics, rendering and lighting to identify possible sources of performance impact and provide a direction for deeper investigation.

### Deep

Deep traces are the most commonly run because they can give more specific, actionable information when it comes to performance optimizations. A deep trace provides scripting information and metrics like draw calls. It’s best used for identifying specific performance improvements like optimizing physics, colliders, and tri/poly count of certain meshes as well as reducing draw calls in a particular area.

### How trace types relate to old config options

The overview and deep trace types correspond to the previous trace configuration options listed in the table below.

| Trace type | Old config options |
| --- | --- |
| Overview | - Application- Debug- Client/Server |
| Deep | - Application- Deep- Client/Server |

## Start a new trace using the wrist wearable

To start a new trace from the wrist wearable:

*   Look at your left wrist to bring up the wrist wearable.

*   Select **Tracing.**![Utilities menu](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452909242_512535254617764_3464900300897266132_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=wC3Bm21ZLS8Q7kNvwEmf0cG&_nc_oc=Adks941UgxITXilHtWKoKEmhDklrAocAgwHg6RPiBSyeCGTKIzsa91uHmXHCV1r21p0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfQhxyaHxAU7Nvqful8OAR15oJjl-CFdQUqKZ0DZbG9IjA&oe=689BA68B)

*   Use the radio buttons to select the **Overview** or **Deep** tracing scope.

*   Select **Start tracing** to start the trace.

![Tracing dialog](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452665546_512535241284432_1956381104628956841_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=E5veSVga8cYQ7kNvwGnzJas&_nc_oc=Adk21TVDc22NPUhixH8sCYZzDQtO2XNZOqxKcBFPtu53F6yrZEoo2kFcQ57T60FcY1Q&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfTbgUYtFKj8JmsMsVAnxUYQfEemgM2urt6pt9MD0NaN3A&oe=689B9EA3)

## Start a new trace from the Real Time Metrics Panel

To start a new trace from the Performance Metrics panel:

*   On the Performance Metrics panel, select the **tracing** icon. 
    
    ![Tracing icon targeted on Performance Metrics panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452457736_512535224617767_5197004322352436639_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=GE7glKyGqdgQ7kNvwG-zaQ6&_nc_oc=AdnCfeeiW1mq2KNz2OmTEZSmdnL8kBvzVIj-vdw1K7qS4RmZ3yHBeier33xZr-qit-s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfT0Z7kXt_gqmuABn01RgecNsXP0WYhiDnBww3wc3a8EhQ&oe=689BA193) 

*   On the **Start a trace** panel, use the radio buttons to select your trace type ( **Overview** or **Deep** ).

*   Select **Start capture**.

![Start a trace dialog](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452533388_512535227951100_250312306465638715_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=1Ep0vBr79KAQ7kNvwE7kqNn&_nc_oc=Admz1FCuSI-kIqc8ZTy-xPo1Qz017ckSRUaJ15QbcrnAc8N8Upf_OgBdEYUh-Ec-KzM&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfS0jJuMeKLiq_yoq9mUPj-B2QZ34BzQglq4FnAvmnVEVg&oe=689BC594)

**

## Download the trace file

*   Access the performance trace files from the [Horizon Creator portal](https://horizon.meta.com/creator/performance/traces/) .

*   The most recent trace is always at the top of the page.

*   Select the trace file to download.

![Traces shown on the Horizon website](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452932541_512535251284431_1492424587016857588_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=ZRtPnx6MfYEQ7kNvwGLMDc3&_nc_oc=AdnYAFPa_25Rkc5IbWJp3bYNbMbDvZAsNPCyrJTLGOvt-YMdEjlClpQQ3eMm5OHTajI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfQPlc90YlVS6W-wgoT9XzibIyl8p_fPUdyWabjkOSG-iw&oe=689BAA0D)

## Tracing Scope

The scope of the trace is used to filter various levels of data points.

*   **World:**
    
     This option enables capturing only high level performance data relevant to world performance. World data is a subset of application traces such as Hardware/GPU time and Main Thread information. 
    
    ![World traces](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452830685_512535117951111_5669193774081795886_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=GQx1b24WVHkQ7kNvwHMSGPX&_nc_oc=AdknhpCkY0L2FD9gt_RGVE7e0fI0EJToipgG975F73eN4Zcb7MvZHESaYA-UMX75Y3I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfRDeSe_unv_adESN8dEzksBUCCO8BMvCfE8ocbkUQWZ9Q&oe=689BA43B) 

*   **Application:**
    
     This option enables capturing more granular performance data from the entire application. Application traces will provide an in-depth trace, such as ​​Main Thread, Hardware/GPU, Audio, Rendering Metrics, and UI/React VR. 
    
    ![Application traces](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452522845_512535164617773_8431839052206306537_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=jr5KI3s_UN4Q7kNvwGexmZv&_nc_oc=AdmtAmv6wWJN_C_j-ADo7ckwRAMyZH18J7HqsA-i9e5RToE4jcBnD8PKoI2Dh6ud9Sc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfT8MB8jYah7gkWf4ZZjP1rRieKyBIejnhwQ6W6fUWjPiA&oe=689BC6CC) 

## Tracing Options

Trace options allow you to set the traces you want to see, client, server or both. The default is set to “client.”

*   **Client:**
    
     This option enables capturing only client-side world performance. Client traces provide detailed performance metrics for ​​the main thread, hardware/GPU, audio, rendering metrics, and UI/React VR. 
    
    ![Client options](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452588689_512535267951096_7012576616891124441_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=sZfGTi4k_NYQ7kNvwEnU8u3&_nc_oc=AdmzAPyhYpfgNlkDBSqGkBuL79-TenYdk4_MQaBn7QgA2MjVCX3CWWQNvQYH0ZiwZow&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfRJbBBRafZJCeRCecJA04WpuIu9QaCm_TE4rzfH2Z2XIQ&oe=689BC2BF) 

*   **Server:**
    
     This option enables capturing only server-side world performance, which includes network calls and script updates. 
    
    ![Server options](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452934272_512535274617762_9070031289387483374_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=pu8hkhE84a4Q7kNvwGzpR_O&_nc_oc=AdncGmK5vrouBcdy4PElRTdLXS_eSVkpu3yX1-GKjF0D8ExFTtto5tTK0hboQ3CE7nw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfTkNhuSziw6t1E28hUSyo5-ibmKOA79uwd1kORdZ18kHg&oe=689BB1FB) 

*   **Client and Server:**
    
     This option enables capturing world performance for both client-side and server-side.

## Deep Script Profiling Analysis

This feature enables creative studios to better understand performance bottlenecks by providing detailed information about API calls and event handling in TypeScript.

To enable deep tracing, select “Deep” in the list of trace levels.

![Deep tracing](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452935529_512535264617763_3661555896485590188_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=uch_W98OxAMQ7kNvwGNWs2W&_nc_oc=AdmpCJ-E3tTNb1dzaoCdgS3bi1en7RcG6sj-daEvm3AmkuPzHmN5zKR3F703AibOVtI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=DOA0bhVGgv6HEVEDJSqIkA&oh=00_AfR2bHgDh1LKTx7KbuQ9eaziE2QMHRIKkQV5fdBXffNlJw&oe=689BBF2E)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 