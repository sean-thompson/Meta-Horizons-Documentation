# Horizon TypeScript APIs

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/horizon-typescript-apis)

When working with TypeScript components, you’ll frequently want to use Horizon’s APIs, because they are designed to streamline your development process. These custom APIs define objects that represent different entities, provide libraries for common tasks, and frameworks for building scalable applications.

To use a Horizon API, import it from the `horizon/core` module.

All new Worlds use V2 of the TypeScript API by default. We strongly recommend using V2 of the API, as V1 is no longer updated with new features. You can choose between V1 and V2 of the [API reference docs](https://horizon.meta.com/resources/scripting-api/core.md/?api_version=2.0.0) in the version selector dropdown at the top of the page.

## Other resources

*   View the online Horizon TypeScript API reference [here](https://horizon.meta.com/resources/scripting-api/core.md/?api_version=2.0.0) . Be sure to select the correct version ( **1.0.0** or **2.0.0** ) in the version selector dropdown at the top of the page. New worlds use V2 of the API by default.

*   If you are new to using TypeScript modules, check out the TypeScript [official module documentation](https://www.typescriptlang.org/docs/handbook/modules.html) .

Horizon API content class list example below:

![](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/452665661_512510677953555_9214172361803849395_n.png?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=a_8MESEnXOIQ7kNvwE8RBo6&_nc_oc=AdmXJ9kVvY3SMGw5-BZXHPcyZQQgyuN99sW92g-SGBHh7azHLxOx5QMknbcVvu-MS7I&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=B_fLTAQgeDLcbR3X60TP4A&oh=00_AfR5n6xukvrjZeAsDtBTPS1BCa002l6scFWT-cXKJuZaeQ&oe=689B8CC3) **Note:** This is only a shapshot of the Classes available to you.

## How to import an API - option 1

```
import {Vec3, Color} from 'horizon/core';
const v = new Vec3(1, 2, 1);
const c = new Color(1, 0, 0);
```

## How to import an API - option 2

```
import * as hz from 'horizon/core';
const v = new hz.Vec3(1, 2, 1);
```

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 