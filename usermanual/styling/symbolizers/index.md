#Symbolizers

A Symbolizer describes how a feature is drawn on a map. The Symbolizer defines both the shape of a geometry and a graphical representation of a feature such as color, opacity, fill pattern, etc.  


MapSurfer.NET has 13 different types of symbolizers. They are:

- [BridgeSymbolizer](/usermanual/styling/symbolizers/bridgesymbolizer.md)
- [CustomValueSymbolizer](/usermanual/styling/symbolizers/customvaluesymbolizer)
- [ExtrudedLineSymbolizer](/usermanual/styling/symbolizers/extrudedlinesymbolizer)
- [ExtrudedPolygonSymbolizer](/usermanual/styling/symbolizers/extrudedpolygonsymbolizer)
- [FramedTextSymbolizer](/usermanual/styling/symbolizers/framedtextsymbolizer)
- [GraphicTextSymbolizer](/usermanual/styling/symbolizers/graphictextsymbolizer)
- [LinePatterSymbolizer](/usermanual/styling/symbolizers/linepatternsymbolizer)
- [LineSymbolizer](/usermanual/styling/symbolizers/linesymbolizer)
- [PointSymbolizer](/usermanual/styling/symbolizers/pointsymbolizer)
- [PolygonSymbolizer](/usermanual/styling/symbolizers/polygonsymbolizer)
- [RasterSymbolizer](/usermanual/styling/symbolizers/rastersymbolizer)
- [TextSymbolizer](/usermanual/styling/symbolizers/textsymbolizer)
- [TunnelSymbolizer](/usermanual/styling/symbolizers/tunnelsymbolizer)


> %!IMPORTANT IMPORTANT:!% Please note that [OpenGIS Symbology Encoding Implementation Specification](http://portal.opengeospatial.org/files/?artifact_id=16700) official supports only LineSymbolizer, PolygonSymbolizer, PointSymbolizer, TextSymbolizer and RasterSymbolizer. All other symbolizers are introduced only in MapSurfer.NET. Therefore, they are not necessarily supported by other mapping toolkits.  


## Basic parameters

Each symbolizer type in MapSurfer.NET has the following default parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Abstract | String | An abstract is a brief summary of the symbolizer. | No
Name | String | The name of the symbolizer. Default value is empty string (""). | No
Enabled | Boolean |  Indicates whether the symbolizer is considered in styling or not. Default value is True. | No
