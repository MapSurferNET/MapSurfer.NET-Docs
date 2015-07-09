TODO# CustomValueSymbolizer

CustomValueSymbolizer is a wrapper which is used to evaluate properties of symbolizers in runtime. This symbolizer helps to change those properties that are not defined as expressions. CustomValueSymbolizer has the following parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No
InternalSymbolizer | Symbolizer | Specifies the symbolizer which property is being customized. | Yes
PropertyName | String | Specifies the symbolizer property to be changed. | Yes
ValueExpression | String | Specifies the value of the property. | Yes

The following example demonstrates how to draw a solid line with variable width taken from a data source.

```cs
InternalSymbolizer: LineSymbolizer
PropertyName: Stroke.Width
ValueExpression: [width]
```
