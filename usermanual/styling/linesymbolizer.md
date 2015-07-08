# LineSymbolizer

LineSymbolizer is used to represent linear features by applying a "stroke" to each line segment. 

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Stroke | Stroke | Specifies a line symbolization. Default value is black. | Yes
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No


## Stroke

**Stroke** defines a set of parameters for graphical symbolization of linear features. The **Stroke** has the following list of parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Color | Color | Specifies a solid color in RGB format. Default value is black. | No
DashArray | Single[] | Specifies a list of alternating dashes and spaces in a dashed line. Default value is null. | No
DashCap | [DashCap](https://msdn.microsoft.com/en-us/library/wk68eecs%28v=vs.110%29.aspx) | Specifies the shape type on both ends of each dash in a dashed line. Default value is Round. | No
DashOffset | Single | Specifies the distance in pixels from the start of a line where a dash begins. Default value is 0. | No
LineCap | [LineCap](https://msdn.microsoft.com/en-us/library/system.drawing.drawing2d.linecap%28v=vs.110%29.aspx) | Specifies the cap style used at the beginning and at the end of a line. Default value is Round. | No
LineJoin | [LineJoin](https://msdn.microsoft.com/en-us/library/system.drawing.pen.linejoin%28v=vs.110%29.aspx) | Specifies how the join between two consecutive lines is drawn. Default value is Round. | No
MiterLimit | Single | Specifies a limit on the ratio of the miter length to the width of a stroke. Default value is 4. | No
Opacity | Single | Specifies the opacity of the painting operation when the stroke is rendered. The range of values is [0,1], where value 0  - the stroke is transparent, value 1 - the storke is completely opaque. Default value is 1. | No
Width | Single | Specifies the width (thickness) of a stroke in pixels. Default value is 1. | No
