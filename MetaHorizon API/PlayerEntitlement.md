# PlayerEntitlement Interface

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_playerentitlement)

Represents an in-world item a player is authorized to access due to a purchase, achievement, or some type of reward system.

## Signature

```
export interface PlayerEntitlement
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**description**</td>
      <td>The description of the item as it appears in the UI.

Signature

```
description: string;
```</td>
    </tr>
    <tr>
      <td>**displayName**</td>
      <td>The name of the item as it appears in the UI.

Signature

```
displayName: string;
```</td>
    </tr>
    <tr>
      <td>**quantity**</td>
      <td>The number of items player has entitlements to.

Signature

```
quantity: number;
```</td>
    </tr>
    <tr>
      <td>**sku**</td>
      <td>The SKU of the item.

Signature

```
sku: string;
```</td>
    </tr>
  </tbody>
</table>