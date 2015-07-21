# GraphicSymbols

The GraphicSymbols element defines a list of graphic symbols used, for example, as a pattern to fill a polygon.  This element can contain any number of elements of the following types:  

## ExternalGraphicSymbol

ExternalGraphicSymbol allows using an external graphic file.


Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the rotation (in degrees) of the symbol around its center point. Default value is 0. | No
CompositingMode | [CompositingMode](/usermanual/image_compositing/index) | Specifies how the symbol is combined with the canvas. | No
Description | String | Specifies the short description of the symbol. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
Format | String | Identifies the expected document MIME type. | No
Opacity | Single | Specifies the opacity of the graphic symbol. | No
Path | String | Specifies the location of the graphic file. | No
ResamplingMode | [InterpolationMode](https://msdn.microsoft.com/en-us/library/system.drawing.drawing2d.interpolationmode%28v=vs.110%29.aspx) | Specifies the algorithm that is used when images are scaled or rotated. This parameter is taken into account when Scale is not equal 1. | No
Scale | Single | Specifies the scale of the graphic. Default value is 1. | No


## GlyphGraphicSymbol

GlyphGraphicSymbol allows using a font glyph as a graphic symbol.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the rotation (in degrees) of the symbol around its center point. Default value is 0. | No
Description | String | Specifies the short description of the symbol. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
TextStyle | [TextStyle](/usermanual/styling/textstyle) | Specifies a style of the glyph. | No
Unicode | Short | Specifies the code of a character in the font. Default value is 0. | Yes


## GlyphsGraphicSymbol

GlyphGraphicSymbol allows preparing a texture on the fly using a set of font glyphs as a graphic symbol.


Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the rotation (in degrees) of the symbol around its center point. Default value is 0. | No
Description | String | Specifies the short description of the symbol. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
FillColor | Color | Specifies the color of a glyph. Default value is black. | No
FillOpacity | Color | Specifies the opacity of a glyph. Default value is 1. | No
Glyphs | GlyphItem[] | Specifies the array of GlyphItem objects. | Yes
Scale | Single | Specifies the scale of the texture when it is drawn onto the canvas. Default value is 1. | No
Size | [Size](https://msdn.microsoft.com/en-us/library/system.drawing.size%28v=vs.110%29.aspx) | Specifies the size of the texture. Default value is (32,32). | No

### GlyphItem

GlyphItem defines a font glyph used as an element of the texture.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the rotation (in degrees) of the symbol around its center point. Default value is 0. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
TextStyle | [TextStyle](/usermanual/styling/textstyle) | Specifies a style of the glyph. | No
Unicode | Short | Specifies the code of a character in the font. Default value is 0. | Yes


## HatchGraphicSymbol

HatchGraphicSymbol allows using a [AutoCAD hatch pattern](http://www.cadhatch.com/) as a graphic symbol.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the rotation (in degrees) of the symbol around its center point. Default value is 0. | No
Description | String | Specifies the short description of the symbol. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
FileName | String | Specifies the location of the hatch pattern file. | Yes
FrontStroke | [Stroke](/usermanual/styling/linesymbolizer.md#Stroke) | Specifies a stroke which is used to draw lines in the hatch pattern. | No
Scale | Single | Specifies the scale of the hatch pattern. Default value is 0. | No

## MarkGraphicSymbol

MarkGraphicSymbol allows using predefined vector shapes as a graphic symbols. These shapes are defined through a well-known name.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Angle | Single | Specifies the rotation (in degrees) of the symbol around its center point. Default value is 0. | No
Description | String | Specifies the short description of the symbol. | No
Displacement | [Point](https://msdn.microsoft.com/en-us/library/system.drawing.point%28v=vs.110%29.aspx) | Specifies a displacement of a texture or a hatch pattern. Default value is (0,0). | No
Fill | [Fill](/usermanual/styling/polygonsymbolizer.md#Fill)  | Specifies the style which is used to fill the interior part of the shape.  | No
Stroke | [Stroke](/usermanual/styling/linesymbolizer.md#Stroke) | Specifies a stroke which is used to draw the shape. | No
WellKnownName | String | Specifies the well-known name of the shape of the mark. Supported values are: circle, cross, diagcross, diamond, downtriangle, rectangle, smalldot, star, triangle. Default value is empty string. | Yes

