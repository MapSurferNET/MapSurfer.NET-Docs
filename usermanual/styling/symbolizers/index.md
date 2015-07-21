#Symbolizers

A Symbolizer describes how a feature is drawn on a map. The Symbolizer defines both the shape of a geometry and a graphical representation of a feature such as color, opacity, fill pattern, etc.  


MapSurfer.NET has 13 different types of symbolizers. They are:

- [BridgeSymbolizer](/usermanual/styling/bridgesymbolizer)
- [CustomValueSymbolizer](/usermanual/styling/customvaluesymbolizer)
- [ExtrudedLineSymbolizer](/usermanual/styling/extrudedlinesymbolizer)
- [ExtrudedPolygonSymbolizer](/usermanual/styling/extrudedpolygonsymbolizer)
- [FramedTextSymbolizer](/usermanual/styling/framedtextsymbolizer)
- [GraphicTextSymbolizer](/usermanual/styling/graphictextsymbolizer)
- [LinePatterSymbolizer](/usermanual/styling/linepatternsymbolizer)
- [LineSymbolizer](/usermanual/styling/linesymbolizer)
- [PointSymbolizer](/usermanual/styling/pointsymbolizer)
- [PolygonSymbolizer](/usermanual/styling/polygonsymbolizer)
- [RasterSymbolizer](/usermanual/styling/rastersymbolizer)
- [TextSymbolizer](/usermanual/styling/textsymbolizer)
- [TunnelSymbolizer](/usermanual/styling/tunnelsymbolizer)


> %!IMPORTANT IMPORTANT:!% Please note that [OpenGIS Symbology Encoding Implementation Specification](http://portal.opengeospatial.org/files/?artifact_id=16700) official supports only LineSymbolizer, PolygonSymbolizer, PointSymbolizer, TextSymbolizer and RasterSymbolizer. All other symbolizers are introduced only in MapSurfer.NET. Therefore, they are not necessarily supported by other mapping toolkits.  


## Basic parameters

Each symbolizer type in MapSurfer.NET has the following default parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Abstract | String | An abstract is a brief summary of the symbolizer. | No
Name | String | The name of the symbolizer. Default value is empty string (""). | No
Enabled | Boolean |  Indicates whether the symbolizer is considered in styling or not. Default value is True. | No