# Generative AI Creation Code Tool

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/generative-ai-creation-tools/generative-ai-creation-code-tool)

Important

Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs) ! As a member, you gain:

*   Access to monetization opportunities including monthly bonuses, in-world purchases and competition cash prizes.

*   Helpful resources including educational content, technical support and a collaborative creator community.

Important

The desktop editor is in early access and we need your feedback! To report bugs, go to the main menu and select **Report a problem**. To give us feedback, select **Help us improve** from the main menu.

World creators can struggle when learning Typescript and when trying to convert Meta Horizon Worlds concepts into Typescript code. Luckily, the Generative AI Creation Tool is here to help! Conveniently built into the Horizon Desktop Editor, the Generative AI Creation Tool is an authoritative, AI-powered chat assistant. The tool works like a chat app and is as simple as having a back-and-forth, real-time conversation with someone. In this case, that someone just happens to be an [LLM](https://en.wikipedia.org/wiki/Large_language_model) .

The GenAI TypeScript tool has two models available:

*   Llama

*   Specialist

Gen AI Tool Availability & Rates

Horizon desktop editor creation tools with Gen AI are currently only available to users in the United States, Canada, and the United Kingdom (UK) aged 13+. Note that there are daily rate limits per user on content created using Gen AI. Additionally, there are daily rate limits per user on content created using Meta AI. These limits are:

*   Typescript - 1000 requests

*   Audio SFX/Ambient - 200 requests

*   Skybox Generation - 50 requests

*   Mesh Generation - 100 requests

## Comparing Llama and Specialist models

You can use both Llama and Specialist models to:

*   Generate TypeScript code snippets for relatively small tasks.

*   Learn Typescript and Horizon Typescript APIs.

The Llama model works well for quick questions, and general information about Meta Horizon Worlds.

The Specialist model is trained on TypeScript and the Meta Horizon Worlds API. It can generate scripts and answer questions about scripting and TypeScript. The Specialist model works well as a personal tutor to learn TypeScript and familiarize yourself with TypeScript APIs. **Note**: Specialist mode output might have minor formatting issues, especially around separating text from code snippets.

## Generating TypeScript code **Note**: Generative AI Creation Tool can only generate code using [version 2 of the Meta Horizon Worlds Typescript API](/horizon-worlds/learn/documentation/typescript/api-references-and-examples/horizon-typescript-v2-changes) .

The code generation process struggles with complex tasks that use multiple APIs. For best results, keep questions scoped to one API at a time.

Responses will occasionally contain 

[hallucinations](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence))

. This usually happens when there are no supported APIs available for the given prompt.

If a response doesn’t give the expected result, try reframing your prompt to be more clear and specific.

*   Select the **TypeScript** button to the right of **Generate:**![Gen AI typescript option](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462003122_559683906569565_222587818335058641_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=UMTeKPCzulMQ7kNvwEjkFlK&_nc_oc=AdnZcRiCSalrVI31m7OFbQcAXNY0Sp1uJcxxmm39H6SR-blf14weWT9yMhnx3JPUlUw&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Mnk6bIth-83oNwlxqAXiHA&oh=00_AfRXbCuOmOLvZW9mOwlHTXe2RcBZKyfq-UTB7idxbbNtyQ&oe=689B9C1E)
    
    After you make a selection, a list of suggested prompts appears.
    

*   Select either the LLama or Specialist model with the **Model** dropdown.
    

*   Enter a prompt. You may either:
    
    *   Try one of the suggested prompts by selecting it, or;
    
    *   Type your own prompt, and click **Generate**.

*   If the response includes TypeScript code, you can copy and paste the code, or create a new script file from the output.

![Sample typescript output](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/462094240_559683913236231_6101813428505638342_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=EEDm94-Da5gQ7kNvwGD933b&_nc_oc=AdmxZAwSb6-RBYL6pgS1EaDzQx9oeVuTL9wtHa1iKjsFXVXta0NJFpn8ic7MCrHqg5I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Mnk6bIth-83oNwlxqAXiHA&oh=00_AfQTQUNlclBrXTstoTShs7dXrqP-4Szg-vf2xm_1WD0WrA&oe=689B994C) **Note**: To change topics, you must start a new conversation.

Specify whether the result was helpful by clicking either **Like** (thumbs-up), or **Dislike** (thumbs-down). Meta uses this information to fine-tune the LLM.

## View Generative AI tool

After generating code with the generative AI tool, you can view previous chats by selecting the **History** icon.

![Gen AI History pop](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/475752490_643175434887078_4424716622310894767_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=rVU2k-ikIg0Q7kNvwHtc2Ui&_nc_oc=AdkwMnXyT-Gzr-W86aRawVuQaiBpC6-2aiy-ZbWd7S_Bl5CvQMvp-42gp4yFcweUjD8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=Mnk6bIth-83oNwlxqAXiHA&oh=00_AfQRgrDk166A1vmMtXBdtZsiBmXG34ZP9fDGj4eLEEYcvQ&oe=689B9EA1)

After opening the history window you can select a previous conversation. This will restore the selected conversation including the context used to generate content.

## What’s next?

To learn more about Meta Horizon Worlds, try the following:

*   [Create your first world](/horizon-worlds/learn/documentation/get-started/create-your-first-world/)
    
     using our step-by-step tutorial.

*   If you have issues when running the desktop editor, see [Desktop Editor Troubleshooting](/horizon-worlds/learn/documentation/desktop-editor/help-and-reference/troubleshooting/) *   Learn about the desktop editor with the [Introduction to the Desktop Editor](/horizon-worlds/learn/documentation/desktop-editor/getting-started/introduction-to-desktop-editor/) .

*   Learn about the other tools available by reading our [Tools Overview](/horizon-worlds/learn/documentation/get-started/tools-overview/) .

*   Join the [Meta Horizon Creator Program](https://developers.meta.com/horizon-worlds/programs/) to learn about our program benefits.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 