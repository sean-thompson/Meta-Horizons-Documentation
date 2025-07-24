# TypeScript Tutorial

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/typescript-tutorial)

## Build your first Hello World with TypeScript and the Desktop Editor

Follow these steps to access the Desktop Editor

*   Navigate to *Scripts -> CreateNewScript*.

*   We will use a starter script named Shoot.

*   Choose the *:* menu next to the new script. You can select “Open in External Editor” if using a preferred editor. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452888405_512535114617778_4622023437168026365_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=JCZ70rGmAM4Q7kNvwGEChMg&_nc_oc=AdkpIhitoGx4KExb1cQ9rUhhXKASYG8PRsyYRJERKRHmZWEopmwoJq1yEOZ2Xh-kFdo&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=-mFkvyz5MiIp1ZHY4jxNjg&oh=00_AfR9jfHjf7Xmxe5RX_5luaBouo_w8i5oYJskEBozJuHB0Q&oe=689B8E10) 

*   The `start()` function is called whenever the object it is attached to is created. To print to the debug console for an object created, add a *console* print:
    
    ```
    start() {
      console.log("Hello, World!");
    }
    ```
    

*   Save the file.

*   In the Desktop world editor, connect your new script to an object you have in the hierarchy. Scroll down to the bottom of the property panel on the right. Select “Attached Script” and choose the script file named “Shoot:Shoot”. This will associate the script with the object. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452635355_512535174617772_4931592019167273635_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=HAUmW26ZcEsQ7kNvwH8VPJU&_nc_oc=AdkK2lEG6JHOkBSvUNKjRPhY7mOheqlBQJuVIqUZKfjtaOwe7cSUF29fZkzThZj8Hc8&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=-mFkvyz5MiIp1ZHY4jxNjg&oh=00_AfSwyEPGkoHTjWv6Hk_PodB8bvCCrAzJ_UoAmFgHn7Bppg&oe=689BBAA3) 

*   Preview the world by clicking on the person icon next to the wrench. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452460755_512535221284434_2821360807848336884_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=_NyEaqoeOGcQ7kNvwH6-ZOB&_nc_oc=Admr-VOHf5H2Ofmk5F2w-S_cYLcmJNDS_15YBYl_1Lg88npuQFyanHea8Q6mIG34AjI&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=-mFkvyz5MiIp1ZHY4jxNjg&oh=00_AfTJaY0s7j_zYUluwcg4ey-qmcA84rLlTn3E-NpOzUsEFQ&oe=689B9C33) 

*   Press escape and click on Console window at the bottom of the editor. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452683821_512535171284439_1029448456687135659_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=eGypE3bCHWIQ7kNvwEZXCJo&_nc_oc=AdnlxjoYZl7f9ghRff1uF4RGgZICCFs5qGekQo-dMRMWg957tDyXEmJ6OI4Mz_he7-I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=-mFkvyz5MiIp1ZHY4jxNjg&oh=00_AfQik38aatyyQelLnWXj7_AM1LkUDFO_5S-XcZnqHwJTrw&oe=689BBBA9) 

*   When the object you associated the script with is created, the console will print the  debug message you specified. 
    
    ![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452992907_512535111284445_4360884428134174850_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=NyitoGbERKAQ7kNvwFmMnTn&_nc_oc=AdnOKArVxb7y2vqlboRFndiwqLvb0kF_RNXGHei87RzEC9-wERTGnPQgilA-xYvrKcQ&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=-mFkvyz5MiIp1ZHY4jxNjg&oh=00_AfSO91Fx8Umk9_2mzOm_KMrhCtj-9DQ2rqFQeiTZ3zjQrA&oe=689BBBBC) 

### Sharing Code Between Scripts

Scripts can share code with other scripts in your world. This can be done with the **`export`** keyword in TypeScript. You can export types, functions, classes, and even values from one script and import them to another. The module name is the name of the script. So if you have a script name `Script1`, you can import any exports from it by using this code: 

**`import` `\*` as `S1` from 

`'Script1'`** `;`.

#### Module1

TypeScript example

```
//Module1

export function add(a: number, b: number) { 
  return a + b;
}

export type MyScalar = number \| string;

export const ModValue = 42;

export class Person { 
  name: string;     

  constructor(name: string) {   
    this.name = name; 
  } 

  sayHello() {   
    console.log(`Hello my name is ${this.name}`);
  }
}
```

#### Script1

TypeScript example

```
// Script1
import type {MyScalar} from 'Module1';
import {Person, ModValue, add} from 'Module1';

const p = new Person('Jon');
p.sayHello(); // logs 'Hello my name is Jon'

let v: MyScalar = ModValue;
console.log(v); // logs 42
v = 'string';
console.log(v); // logs 'string'

console.log(add(5, 8)); // logs 13
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 