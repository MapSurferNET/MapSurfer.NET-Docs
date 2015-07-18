# ExtrudedPolygonSymbolizer

ExtrudedPolygonSymbolizer is used to represent a body that is built by extruding a polygon. 

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
BottomLevelExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a vertical offset of an extruded body. | No
FacesColor | Color | Specifies the color of the faces. | No
FillOpacity | Single | Specifies the opacity of the faces Default value is 1. | No
FrameColor | Color | Specifies the color of the frames. | No
FrameOpacity | Single | Specifies the opacity of the frames. Default value is 1. | No
FrameWidth | Single | Specifies the width of the frames. Default value is 1. | No
HeightExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute the extrusion of a linear feature. | No
HideInvisibleFaces | Boolean | Specifies whether to hide invisible faces or not. Default value is True. | No
Scale | Single | Specifies the scale of the extrusion. Default value is 1. | No
ShadeFaces | Boolean | Specifies whether to shade faces or not. Default value is True. | No
ShadeFaces | Boolean | Specifies whether the top face(roof) is filled or not. Default value is True. | No
TopColor | Color | Specifies the color of the top face. | No
Clip | Boolean | Specifies whether geometry is clipped to map bounds before rendering or not. Default value is False. | No
GeometryExpression | String | Specifies an [expression](/usermanual/expressions/geometrytransformations) to compute a geometry to be used in rendering. This parameter is optional. If it is not specified, a default geometry field of a data source is used. | No
