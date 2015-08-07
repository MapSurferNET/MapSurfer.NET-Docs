# PolygonSymbolizer

**PolygonSymbolizer** is used to draw areal features by filling its interior part and stroking its border.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Fill | Fill | Specifies how the interior part of an areal features is filled. | Yes
Stroke | Stroke | Specifies a line symbolization for the border of an area. | No
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No
 

## Fill

The Fill element determines how the interior part of an areal feature is filled. This element has the following parameters:

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Color | Color | Specifies a solid color in RGB format which is used to fill the interior part of an areal feature. Default color is black. | No
Opacity | Single | Specifies the opacity of the painting operation when the area is filled. The range of values is [0,1], where value 0  - the stroke is transparent, value 1 - the stroke is completely opaque. Default value is 1. | No
Outlined | Boolean | Specifies whether the border is outlined using the same color as filling or not. Default value is False. | No
GraphicFill | GraphicFill | Specifies a pattern to fill the area. Default value is null. | No


### GraphicFill

The GraphicFill element defines properties of a pattern filling.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies a rotation angle of a texture or a hatch pattern. Default value is 0. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
GridAlignment | Boolean | Specifies whether the pattern is aligned to a pixel grid or not. Default value is True. | No
GraphicSymbols | [GraphicSymbol](/usermanual/styling/graphicsymbols)[] | Specifies a list of symbols that form the pattern. By default, the list is empty. | No
Opacity | Single | Specifies the opacity of the pattern. Default value is 1. | No
Size | [Size](https://msdn.microsoft.com/en-us/library/system.drawing.size%28v=vs.110%29.aspx) | Specifies the size of the pattern in pixels. Default value is (0,0). | No
TileWrapMode | [TileWrapMode](https://msdn.microsoft.com/en-us/library/system.drawing.drawing2d.wrapmode%28v=vs.110%29.aspx) | Specifies how a texture or gradient is tiled. Default value is Tile. | No


## Stroke

Stroke specifies a style of a polygon boundary. Stroke is rendered on top of the Fill. Stroke is defined in a corresponding section of [LineSymbolizer](/usermanual/styling/linesymbolizer.md#stroke):

