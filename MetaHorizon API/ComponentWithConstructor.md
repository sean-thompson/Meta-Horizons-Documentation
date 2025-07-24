# ComponentWithConstructor type

[source](https://developers.meta.com/horizon-worlds/reference/2.0.0/core_componentwithconstructor)

The base type of a [component](/horizon-worlds/reference/2.0.0/core_component) that takes a prop definition. This can be used to set default props for a base component.

## Signature

```
export declare type ComponentWithConstructor<TPropsDefinition, S extends SerializableState = SerializableState> = ComponentWithoutConstructor<TPropsDefinition> & {
    new (): Component<ComponentWithConstructor<TPropsDefinition, S>, S>;
};
```

## References [SerializableState](/horizon-worlds/reference/2.0.0/core_serializablestate) , 

[Component](/horizon-worlds/reference/2.0.0/core_component)

, 

[ComponentWithConstructor](/horizon-worlds/reference/2.0.0/core_componentwithconstructor)