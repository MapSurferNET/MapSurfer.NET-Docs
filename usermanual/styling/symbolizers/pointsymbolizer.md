# PointSymbolizer

**PointSymbolizer** specifies how to render graphic symbols for point-like objects such as peaks, airports, POIs, etc.

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No
Graphic | [Graphic](#graphic) | Specifies the graphic object to be rendered. | Yes
GridAlignment | Boolean | Specifies whether to align symbol to a pixel grid. Default value is True. | Yes
LabelBehaviour | [LabelBehaviour](#labelbehaviour) | Specifiews the role and behaviour of a label. | Yes
LabelPlacement | [LabelPlacement](usermanual/labeling/label-placement-types)| Specifies the type of a label placement (e.g. point-like, linear or areal labeling style) | No
PriorityExpression | [Expression](usermanual/expressions/index) | Specifies the priority of a label. Being an expression, this parameter allows to take values from a data source. For example, the value can be [field_priority], where field_priority is an attribute in the data source. Note, an expression must always return a numerical value. | No
Padding | Point | Specifies spacing, in pixels, around the symbol which controls how close adjacent labels can be placed. Default value is (0,0). | No

## Graphic

**Graphic** elements defines a graphic symbol, which can have either a raster or vector-graphic source type. 

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the angle at which the graphic symbols is rotated. Default value is 0.| No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of the graphic symbol from its original position. Default value is (0,0). | No
GridAlignment | Boolean | Specifies whether to align symbol to a pixel grid. Default value is True. | Yes
GraphicSymbols | [GraphicSymbol](/usermanual/styling/graphicsymbols)[] | Specifies a list of symbols that form the graphic symbol. By default, the list is empty. | Yes
Opacity | Boolean |  Specifies the opacity of the graphic symbol. The range of values is [0,1], where value 0  - the symbol is transparent, value 1 - the symbol is completely opaque. Default value is 1. | No
Size | Size | Specifies the custom size of the graphic symbol. Default value is (0,0). | No


## LabelBehaviour

**LabelBehaviour** element specifies the role and behavior of a label placement during [candidate-position generation](/usermanual/labeling/index#candidate-position). 

**Parameters**

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AllowOverlap | Boolean | Specifies whether the label is allowed to overlap other labels. | No
AvoidEdges | Boolean | Specifies whether the label is allowed to intersect boundaries of the map. | No
CollisionDetectable | Boolean | Specifies whether the label is considered as a candidate for a labeling algorithm. If not, the label will be simply rendered. Default value is True. | No
CollisionMeasures  | [CollisionMeasure](usermanual/labeling/collision-measures)[] | Specifies a list of collision measures. | No
DropOnCollision | Boolean | Specifies whether to drop the label if any collision with other labels exists. | No
IgnorePadding | Boolean | Specifies whether to ignore padding parameter of the map object or not. | No
QualityFilter | [Expression](usermanual/expressions/index) | Specifies an expression to filter labels by using [quality functions](/usermanual/labeling/label-placement-types). | No


