# InWorldPurchasable type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_inworldpurchasable)

Represents an in-world item that is purchaseable such as an item or item pack.

## Signature

```
export declare type InWorldPurchasable = {
    sku: string;
    name: string;
    price: InWorldPurchasablePrice;
    description: string;
    isPack: boolean;
    quantity: number;
};
```

## References

[InWorldPurchasablePrice](/horizon-worlds/reference/2.0.0/core_inworldpurchasableprice)