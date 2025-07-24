# PropsDefinitionFromComponent type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_propsdefinitionfromcomponent)

A helper utility that derives prop types from a component class type.

## Signature

```
export declare type PropsDefinitionFromComponent<T> = T extends ComponentWithoutConstructor<infer TPropsDefinition> ? Readonly<TPropsDefinition> : never;
```