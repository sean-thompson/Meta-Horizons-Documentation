# Using performance tools from web and mobile

[source](https://developers.meta.com/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/using-performance-tools-from-web-and-mobile)

Important

Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs) ! As a member, you gain:

*   Access to monetization opportunities including monthly bonuses, in-world purchases and competition cash prizes.

*   Helpful resources including educational content, technical support and a collaborative creator community.

Important

The desktop editor is in early access and we need your feedback! To report bugs, go to the main menu and select **Report a problem**. To give us feedback, select **Help us improve** from the main menu.

Real-time performance metrics and server-side tracing can help creators find and address performance issues in their worlds. In this article, you will learn how to access the performance tools via browser while visiting your world, alleviating the need to put on a VR headset to get performance data about your world.

Let’s begin with opening the Performance panel.

## Opening the Performance panel

In the web browser, the Performance panel displays a real-time view of all currently selected metrics. While visiting a world, press **P** to open the Performance panel. The panel appears at the bottom of the screen, and the world viewport shrinks to accommodate it. Pressing **P** again closes the Performance panel and expands the viewport back to full size.

![The world with the performance panel opened.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468449886_597918836079405_7058027029312242437_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=9y9Q_7ywHB0Q7kNvwH3PLiX&_nc_oc=AdkVfNw1kvWbJIF6DlRhsQkcILlsMTc8Nbrw9IoighxvDe5eaqbuOz2GbpC1Ovj9zvU&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfQA8kYTm7FFeVMUh73QoRDkPrHz0udeESHwf242AmMMtA&oe=689BABC7)

In mobile, you open the Performance dialog but pressing the **Settings** button (gear and wrench) in the top right corner of the screen.

![The Performance dialog in a mobile world.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490967887_697726326098655_5633090691600198677_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=0RJE6BFOEk0Q7kNvwFoI19H&_nc_oc=AdldFf2Hw3BPgkcM_1-1zKtdghFxpmDWzZrm0fjIHSAc5Kc53xRp6CoUkiNqU3w15Fs&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfTA0TrueKcj3fOyR4fosPFnX-TZo4070wjiUucdsQHHRw&oe=689BA9CC)

## Displaying real-time metrics

You can select which real-time metrics to display in the Performance panel by clicking the **Gear** icon to open the Display Settings. From there,simply check the box next to each metric you’d like to see in the Performance panel. Unselected metrics will not be shown.

You can also set a **Target** number for each metric. When a metric exceeds the defined target, a red dot appears next to that metric as an alert.

![The Display Settings window open in the world. The gear icon used to open the window is highlighted.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468436141_597918822746073_6104268589954704877_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=j8vpWSdmJnIQ7kNvwHkjYEp&_nc_oc=AdmSxIAYEBtK9tpBp6e7Jfu9-cPY2SzT0HfqdcoOL_srQgpXmoEH1nNQ9cVfS_DGl9s&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfRM9Q_CTokAcmy7pTuRKj3Fyt1Vf-qiP3z54ivuLTngTQ&oe=689B91FE)

In mobile, once the Performance dialog is open, click the check box for **Show real-time metrics (RTM) overlay** to see the FPS and CPU metrics.

![The Performance dialog in a mobile world with Show real-time metrics (RTM) overlay selected.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490752050_697726319431989_1096614501547904137_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=AUMBqqfOQ1oQ7kNvwEQ4aq0&_nc_oc=Admqb0SphlAB1Jf5n-CXDiQ4HxFuVwumZURpIU9_lirQpbUEMaV8mr5chFcWY8PvoQQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfQZjPsIfFqTifavYNVxCMeMLMzAfZYOfZHe7XtmYnHQnw&oe=689BB89D)

### Scrubbing (web only)

With Scrubbing, you can review data that has recently appeared on the Performance panel (approximately 30 seconds of data) in detail. Click the **Inspect** button to open the Scrubbing view.

Click and drag the blue box at the top of the panel to the data you would like to review. This box represents a range, measured in frames. You can resize the box by clicking and dragging the handles on the sides of the box.

Below the Frame Time scrubber, a “zoomed-in,” detailed view is shown for each metric, spanning the frames covered by the blue box. By changing the range, you can choose whether to focus on a short span of time, or a broader view over a longer period.

![The world with the detailed view of the Frame Time scrubber opened and a span selected.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468536945_597918829412739_6965456918375424809_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=wl0ZFXqtOIsQ7kNvwHauqJd&_nc_oc=Adn4wSKxZmMxcVakkfvu8EsMwlCdmoBPo_liRxvSMj37VzQZvVPJC0tvS3mw7QWSszQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfTv1WGGQeaZpTETp-dYxLHphx6X1314OrqzUMVnYYK6MQ&oe=689B9BC0)

Click the **Back** button to return to the Performance panel.

## Tracing

With Tracing, you can capture performance data from your world to [view in Perfetto](/horizon-worlds/learn/documentation/performance-best-practices-and-tooling/performance-tools/analyzing-trace-data-with-perfetto) . You can choose between three trace types:

*   **Overview**
    
     \- An overview trace can help set a baseline for how your world is performing in visit mode. It captures high-level data like FPS, CPU, and GPU. Additionally, overview provides a high-level capture of metrics like physics, rendering, and lighting to identify possible sources of performance impact and provide a direction for deeper investigation.
    

*   **Deep**
    
     \- A deep trace provides scripting information and metrics like draw calls. It’s best used for identifying specific performance improvements like optimizing physics, colliders, and tri/poly count of certain meshes as well as reducing draw calls in a particular area. Deep traces are the most commonly run because they can give more specific, actionable information when it comes to performance optimizations.
    

*   **Playtest**
    
     \- Playtest capture allows for up to 2 hours of gameplay to be recorded across multiple worlds without needing to be plugged in or running any special software. This type of trace can be taken on any build, anytime, anywhere. Playtest capture generates a report similar to the ones we use internally to track the performance of our hottest worlds and the performance of Horizon itself. Unlike other types of traces, which are viewable in Perfetto, the results of this trace are viewable on the [Horizon website](https://horizon.meta.com/creator/performance/reports) . In general, playtest traces are best used for initial testing.
    

### Starting a trace

In the web browser, click the **Trace** button (red dot with white corner brackets) to open the Start a Trace window.

![The world with the performance panel open, and the trace button highlighted.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468468286_597918839412738_2933779466601780685_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=dyUxxCvuEpQQ7kNvwGFqbUa&_nc_oc=AdnHhZ-G7DskdEjl6FTEz8RSjiazPl00RzQPHRVcI8L5p55dtGuqcW1tl0aeemkIX0g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfTbdSDD2ulEzEfS57ucLZrtfiFTXxa4Bl7QY-1t3ruAWg&oe=689BB266)

Then click **Start capture** to begin a trace. While the trace is running, the Performance panel closes and a “Tracing in progress” panel appears in the lower left corner of the screen, showing the trace’s current status. You can add flags to a trace by clicking the **Flag** button on the panel while the trace is running.

![The world with the Start a Trace window opened and the types of traces displayed.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468431908_597918826079406_8202001262270154656_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=m0VRbuTLjLcQ7kNvwH8H3M7&_nc_oc=AdkPxdebWiQdKHX1rLKhwhPNp4CiiP03a7vAjgtNzUxur-eWwbjjbSkriydT4wrvx1g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfSHfKCTsmKWgl7iUrVX0XMcJMiDcZY0nsSnbEfT1-GLqg&oe=689BBDE1)

In mobile, click the drop-down menu next to the **Start trace** button to select the type of trace you want to run. Click the **Start trace** button to begin a trace.

![The Performance dialog showing the three trace types](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/490711616_697726316098656_6022198852499889232_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=VkfnEMr-zbEQ7kNvwFIUCSf&_nc_oc=AdlILzXyglBA4-crW3idt_zXNdDACwM9ghxxY_n3v4XML_9nD21JMHv3b0GNKdY4mlc&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfQ3VNmtLAailTIL3x8D7_v9Dhwlb_RC-i9EkxzYGGZ3Rw&oe=689B914F)

### Stopping a trace

In the web browser, to end a trace early, click the **Stop** button at the top of the panel.

![A zoomed-in view of the tracing screen, with the stop button highlighted.](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/468496139_597918832746072_314632089191930808_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=IudNYaNvzVQQ7kNvwGIDl5W&_nc_oc=AdkkqkFRMkwR4r2xJmBzNm-P1pVin_VQhReBNuHxd95s5xruPnpUUwp3EmJRnYZFk6g&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfRWS-xUcoaZSaMywZ0KtWOQqdoCRdF3wsN-4OV-2YlPzw&oe=689B9339)

In mobile, to end a trace early, open the Performance dialog and click the **Stop trace** button.

![The Stop trace button on the Performance panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/491696845_697726312765323_5619417363942537487_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=e0LZ9u7RC0IQ7kNvwGFXFpd&_nc_oc=AdkTvLema0AD9x68akI95OG2mIR-ADQw-GnBEMSwQVOeJ-UnmK3QurXzBnWtlwpsdE0&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfTtT4K3J4GfcNm3PM8TWpYbGuwAaWp689lDsCXkDj9whA&oe=689BB75F)

When a trace is completed in mobile or web, the results are uploaded to your [Creator Portal](https://horizon.meta.com/creator/performance/traces/) in the Performance section. You’ll see a confirmation message like the one shown below.

![A message showing trace files uploading on mobile](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/491832834_697726322765322_6948958478433418717_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=Jv6q7nxucTgQ7kNvwHtOLho&_nc_oc=AdkEl-J10qKEGsxUr4Gd6lacE-vT25EVzpXJFthZAKmlhyi_qEtypFtSvOxWCBTobCI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=s_0g46iHIN9XCVfwESsqGA&oh=00_AfQQpSw24PToWyJx-X_j5U-gJt3ELSptQDnNlgOYix8n6w&oe=689BA5D4)

## What’s next?

To learn more about Meta Horizon Worlds, try the following:

*   [Create your first world](/horizon-worlds/learn/documentation/get-started/create-your-first-world/)
    
     using our step-by-step tutorial.

*   If you have issues when running the desktop editor, see [Desktop Editor Troubleshooting](/horizon-worlds/learn/documentation/desktop-editor/help-and-reference/troubleshooting/) *   Learn about the desktop editor with the [Introduction to the Desktop Editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor/) .

*   Learn about the other tools available by reading our [Tools Overview](/horizon-worlds/learn/documentation/get-started/tools-overview/) .

*   Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs/) to learn about our program benefits.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 