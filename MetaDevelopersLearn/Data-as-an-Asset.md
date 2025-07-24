# Data as an Asset

[source](https://developers.meta.com/horizon-worlds/learn/documentation/desktop-editor/assets/data-as-an-asset)

Data as an Asset makes it easier to ingest and access a large amount of data. You can use this data to generate and populate your worlds with content for players as part of a live service model.

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452577444_512500194621270_8611450341367331312_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=9QFYFzKM0SoQ7kNvwHryYJi&_nc_oc=Adk09UuvE5ugeWXzBA0C30Ziy7rikYVfHfyKo64Ui4nBvE1mOCt3M6lGl7OA3o1PMC8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3NJylpd-vJxAWLWwFO922A&oh=00_AfToZJIf0o56KU_VAQmZHWtKfJphyfFxhvKa-TOSXJpbBg&oe=689BBC2E)

## Requirements

*   For Web Asset ingestion, you need access to your team’s Asset Library to upload the assets to the library.

## Uploading Assets to the backend

### Web Asset upload

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/457319138_534069239131032_568264581816929647_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=NlcKb4s54HsQ7kNvwEY8njb&_nc_oc=AdnnG3eEgVzJpzCS5yFAiweXM1ygfqj24Co4j4aUV-NYkPZXVK4OSk6sZLicdoKsZJ4&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3NJylpd-vJxAWLWwFO922A&oh=00_AfR5LuK1BsoAcSZKdRJQnM4iqwQJtiWKSPvy4qGFiDxEaQ&oe=689B8B34) **Note**: We currently only accept JSON files.

*   Go to [https://horizon.meta.com/creator/assets](https://horizon.meta.com/creator/assets) *   Click **Import**, and select **Text**.

*   Upload the asset. We only allow JSONs for now. You can use any valid .json you have, or download and upload the attached gamedatanew.JSON file at the bottom of the page.
    
    *   [gamedatanew.json](https://scontent.oculuscdn.com/v/t64.5771-25/39031405_1040126593784425_5457484484185452287_n.json?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=LcZr-1SoZ3kQ7kNvwHt7VFu&_nc_oc=Adnw6V4sipmMnRIPhki_dlPa4IWVzlY6yQcA2sSZOR06mKfPQbfoWMvVhrGHSMah9dw&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQlMoS9pJnLk5-ysn5i7Eg9vjdPOSPhysnowRfftCqvaQ&oe=689BBA87)

*   You can download, edit and do other things with the Asset file, but this UI is the just the same as the Web Asset Ingestion UI.

### Desktop asset upload

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/457288085_534069255797697_3427743522111648183_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=okZlPjGcyvIQ7kNvwF1qajx&_nc_oc=AdnPzqk6yhSAKiHHQllcP8db-gIsb4efFzShiLpoDAxQwgrgurqTtxTYEvCNOsOaXis&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3NJylpd-vJxAWLWwFO922A&oh=00_AfQp3I0I1jMlDrFP80UWZKUbstrNaugUTwCMUJlRVPwY9g&oe=689B8D97) **Note**: We currently only accept JSON files.

*   Open the Desktop Editor for Horizon.

*   Click **Add New**, and select **Text**.

*   Upload the asset. We only allow JSONs for now. You can use any valid json you have, or download and upload the attached gamedatanew.json file at the bottom of the page.
    
    *   [gamedatanew.json](https://scontent.oculuscdn.com/v/t64.5771-25/39031405_1040126593784425_5457484484185452287_n.json?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=LcZr-1SoZ3kQ7kNvwHt7VFu&_nc_oc=Adnw6V4sipmMnRIPhki_dlPa4IWVzlY6yQcA2sSZOR06mKfPQbfoWMvVhrGHSMah9dw&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQlMoS9pJnLk5-ysn5i7Eg9vjdPOSPhysnowRfftCqvaQ&oe=689BBA87)

*   You can download, edit and do other things with the Asset file, but this UI is the just the same as the Desktop Asset Ingestion UI.

## Using the asset in TypeScript

Now that your asset is uploaded, you can pull the data from the asset to the TypeScript layer.

There are 2 ways to do this:

*   Getting the reference to the asset in a component.

*   Or, Creating a reference to the asset by providing the Asset ID, optionally, Asset version ID.

### Getting the reference to the asset in a component.

*   Using a component, for example, your game manager, create a reference to a text asset.

*   Pick from your available assets.

*   Please note that your world will be referencing the Asset version at the moment of assigning. Updates to the Asset will not be reflected until you give a new reference to the asset. If you want your world to reference the latest version of the asset, use the method below of creating a new asset with ID reference.

### Creating a reference to the asset by providing the asset ID, optionally, asset version ID

*   Create a new Asset, with an Asset ID. You can obtain this by inspecting the asset in your Desktop Editor Asset Library interface, or the Web Asset Library interface. Create a new Asset, with an Asset ID. You can obtain this by inspecting the asset in your Desktop Editor Asset Library interface, or the Web Asset Library interface.

*   You can optionally provide the Asset version ID when creating the Asset. You can find this Asset version ID in the Web Asset Library interface.Your world will reference that version of the asset even if the Asset is updated.You can optionally provide the Asset version ID when creating the Asset. You can find this Asset version ID in the [Web Asset Library interface](https://horizon.meta.com/creator/assets) . Your world will reference that version of the asset even if the Asset is updated. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/457409225_534069252464364_3303227658061954721_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=mQEGu7cB-40Q7kNvwHNorV2&_nc_oc=AdmVNxgyOirfkn7_Y5hS1olnRCwTNnXph2XtH8Nsw_eoC0j1cXpVMb4T66_dZpvsGV8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3NJylpd-vJxAWLWwFO922A&oh=00_AfR-DyHzKiqOLAg2EQMiB6fIe_LeVYyTNM0oE3MII1aIgg&oe=689BA413) 

*   To reference the latest version of the Asset whenever it is updated, create a new Asset Object with the ID, but do not provide the optional version ID.

*   For example `let asset = new Asset(ASSET_ID_BIGINT_HERE);` *   Please note that Asset loads are cached. If you are running the world, load the Asset and update it in the backend any new Asset loads will be the ones at time of asset load. You must restart the world to get your latest uploaded Asset version.

Once you retrieve the reference to the Asset object, you can fetch its data and use the following APIs to pull the asset as an object. Within the object, there are

*   `asJson()`. You can provide an expected type to ensure that the JSON returned is of the intended type.

*   `asText()`.

This script verifies whether you are able to pull asset data as a string:

```
import * as hz from 'horizon/core';

interface JSONData {
  qns_type: string;
  difficulty: string;
  category: string;
  question: string;
  correct_answer: string;
  incorrect_answers: string[];
}

/* Here's an example of the JSON data that will be passed in:
[
  {
    "qns_type": "boolean",
    "difficulty": "medium",
    "category": "General Knowledge",
    "question": "Why did the chicken cross the road",
    "correct_answer": "False",
    "incorrect_answers": [
      "True"
    ]
  },
  {
    "qns_type": "boolean",
    "difficulty": "medium",
    "category": "General Knowledge",
    "question": "Why did the cow go moo.",
    "correct_answer": "True",
    "incorrect_answers": [
      "False"
    ]
  }
]
*/

class CheckAssetIntegrity extends hz.Component<typeof CheckAssetIntegrity> {

  static propsDefinition = {
    textAsset: { type: hz.PropTypes.Asset },
  };

  allQnsData: JSONData[] | null = null;

  // called on world start

   async start() {
    let asset = this.props.textAsset!;

    /*
    // create a new Asset and do not provide the version id
    // if you want to reference the latest version
    // of the Asset
    let asset = new Asset(ASSET_ID_BIGINT_HERE); //
    */
    asset.fetchAsData().then((output: hz.AssetContentData) => {
      console.warn(asset.id + " \n" + asset.versionId);
      this.handleExtractAssetContentData(output);
    })
  }

  handleExtractAssetContentData(output: hz.AssetContentData) {
    var text = output.asText();
    console.log("Total text length: ", text.length);
    console.log("First 10 characters of the text for verification: ", text.substring(0, 10));
    console.log("==================================");
    var jsobj = output.asJSON();
    if (jsobj == null || jsobj == undefined) {
      console.error("null jsobj");
      return;
    }
    else {
      this.allQnsData = output.asJSON<JSONData[]>();
    }
  }
}

// This tells the UI that your component can be attached to an entity
hz.Component.register(CheckAssetIntegrity);
```

### Fetch asset options

The options parameter of the fetchAsData method provides the skipCache option, which skips the local cache when fetching asset data. To enable this option, set the skipCache option to true. This option is disable by default.

Enabling skipCache is only useful if you expect the asset that you are referencing to change while the world instance is running, and you have already accessed the asset. For example, if you modify your world assets in response to a live event outside of your live world instances. This is a rare circumstance so you should not enable skipCache most of the time.

## Examples

*   A sample JSON file (trivia.json) with trivia questions in a JSON format. (More questions can be accessed via trivia APIs, such as [Open Trivia DB](https://opentdb.com/api_config.php) ).
    
    *   [trivia.json](https://scontent.oculuscdn.com/v/t64.5771-25/39031427_790113296532639_7185274403668060489_n.json?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=9BwMj7oY8A4Q7kNvwFzOV0-&_nc_oc=Adl2nfQ28lQDZ51XEB6WrWfNT_7BUZMHZ3YFE8oyn6JJ1W18gSYvyyorbCxpWAFx1Ok&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQYwq5RnVckD4D0fRwIFKnnNqAg0K-0SbzA-QcLLQ2nvg&oe=689BB8C3)

*   A Trivia world with a game manager script to load these questions from that JSON asset.

*   A simple trigger script to allow for users to answer these trivia questions.

*   You are able to load versions of Text Assets that were before the current version. This is helpful if you want to lock a version of the Asset to a particular world. You can do this by providing the actual values of the Asset IDs and the version IDs, like the code sample below. You may find more information regarding this in the asset templates.
    
    ```
    const assetId = BigInt(this.props.assetID); // use a string
      const versionId = BigInt(this.props.assetVerID);  // use a string
      asset = new hz.Asset(assetId, versionId);
    ```![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/457409225_534069252464364_3303227658061954721_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=mQEGu7cB-40Q7kNvwHNorV2&_nc_oc=AdmVNxgyOirfkn7_Y5hS1olnRCwTNnXph2XtH8Nsw_eoC0j1cXpVMb4T66_dZpvsGV8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=3NJylpd-vJxAWLWwFO922A&oh=00_AfR-DyHzKiqOLAg2EQMiB6fIe_LeVYyTNM0oE3MII1aIgg&oe=689BA413)

## Notes

*   Spawning a text asset does nothing.

*   You cannot use this API to pull the data of a non-text asset. You will receive null data.

*   You can only upload .JSONs files.

*   Whenever you pull the data object, you are calling into the C# backend from the TS. This is performance intensive and should be done sparingly.
    
    *   You may want to cache the .json object when you create it. The string is already cached when the object is created. If you are using it as a .JSON more than once, we recommend caching it once created.
    
    *   Pull smaller .json files.
    
    *   Pull when refreshing the world and during downtime.

## Performance

*   Currently the Max asset file size is 8MB. The C# to TS bridge currently only accepts this much data in a single call, even though the asset library accepts files of up to 25MB.
    
    *   Speed of upload to the Asset Library for a 1.8 MB file is ~5s.
    
    *   Speed of download to TypeScript for a .json file of size 1.85MB in an empty world is ~2s
    
    *   Speed of updates – How fast does it take to get the latest uploaded asset data?
        
        *   It depends on your file size. We’ve seen 1KB files be updated almost immediately, while 5MB files may take up to 5 mins.
    
    *   Do not use the skipCache option unless you are updating the asset while the world instance is live.

## Downloads [gamedatanew.json](https://scontent.oculuscdn.com/v/t64.5771-25/39031405_1040126593784425_5457484484185452287_n.json?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=LcZr-1SoZ3kQ7kNvwHt7VFu&_nc_oc=Adnw6V4sipmMnRIPhki_dlPa4IWVzlY6yQcA2sSZOR06mKfPQbfoWMvVhrGHSMah9dw&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQlMoS9pJnLk5-ysn5i7Eg9vjdPOSPhysnowRfftCqvaQ&oe=689BBA87) [trivia.json](https://scontent.oculuscdn.com/v/t64.5771-25/39031427_790113296532639_7185274403668060489_n.json?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=9BwMj7oY8A4Q7kNvwFzOV0-&_nc_oc=Adl2nfQ28lQDZ51XEB6WrWfNT_7BUZMHZ3YFE8oyn6JJ1W18gSYvyyorbCxpWAFx1Ok&_nc_zt=3&_nc_ht=scontent.oculuscdn.com&oh=00_AfQYwq5RnVckD4D0fRwIFKnnNqAg0K-0SbzA-QcLLQ2nvg&oe=689BB8C3)

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 