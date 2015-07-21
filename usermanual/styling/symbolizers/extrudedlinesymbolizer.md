# ExtrudedLineSymbolizer

ExtrudedLineSymbolizer is used to represent a face, which is an extruded version of a linear feature. 

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
FacesColor | Color | Specifies the color of the faces. | No
FillOpacity | Single | Specifies the opacity of the faces Default value is 1. | No
FrameColor | Color | Specifies the color of the frames. | No
FrameOpacity | Single | Specifies the opacity of the frames. Default value is 1. | No
FrameWidth | Single | Specifies the width of the frames. Default value is 1. | No
HeightExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute the extrusion of a linear feature. | No
Scale | Single | Specifies the scale of the extrusion. Default value is 1. | No
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No
