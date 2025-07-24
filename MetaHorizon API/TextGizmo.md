# TextGizmo Class

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_textgizmo)

Extends *[Entity](/horizon-worlds/reference/2.0.0/core_entity)* Represents a text label in the world.

## Signature

```
export declare class TextGizmo extends Entity
```

## Properties

<table>
  <tbody>
    <tr>
      <td>**text**</td>
      <td>The content to display in the text label.

Signature

```
text: HorizonProperty<string>;
```

Remarks

If the content was previously set with `localizableText`, the getter of this property will return the localized string in the language of the local player. Do not use the returned text in attributes shared with other players. Other players might use differnet languages, and only the `LocalizableText` object is localized.</td>
    </tr>
  </tbody>
</table>

## Methods

<table>
  <tbody>
    <tr>
      <td>**toString()**</td>
      <td>Creates a human-readable representation of the entity.

Signature

```
toString(): string;
```

Returns

string

A string representation of the `TextGizmo`.</td>
    </tr>
  </tbody>
</table>