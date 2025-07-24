# OnPlayerPurchasedItemEventPayload type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_onplayerpurchaseditemeventpayload)

Content of the data sent when a player purchases an item from an in-world shop

## Signature

```
export declare type OnPlayerPurchasedItemEventPayload = {
    playerId: number;
    shopId: number;
    consumedItemSku: string;
    consumedItemQuantity: number;
    grantItemSku: string;
    grantItemQuantity: number;
};
```