# RasterSymbolizer

RasterSymbolizer is used to draw a geo-referenced raster image (e.g. satellite image, scanned historical maps, etc.) or terrain elevation data (e.g. DEM) as shaded relief.  

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
ColorMap | [ColorMap](/usermanual/styling/rastersymbolizer.md#ColorMap) | Specifies a continuous palette of colors to colorize an elevation map. | No
CompositingMode | [CompositingMode](/usermanual/image_compositing/index) | Specifies how the raster image is combined with the canvas. Default value is SourceOver. | No
ImageOutline | [Symbolizer](/usermanual/styling/symbolizers) | Specifiews whether and how the raster image should be outlined. Possible values are either [LineSymbolizer](/usermanual/styling/linesymbolizer) or [PolygonSimbolizer](/usermanual/styling/polygonsymbolizer). | No
InterpolationMode | [InterpolationMode](https://msdn.microsoft.com/en-us/library/system.drawing.drawing2d.interpolationmode%28v=vs.110%29.aspx) | Specifies the algorithm that is used when images are scaled or rotated. This parameter is taken into account when Scale is not equal 1. | No
Opacity | Single | Specifies the opacity of the image when it is combined with the background. | No
ShadedRelief | [ShadedRelief](/usermanual/styling/rastersymbolizer.md#ShadedRelief) | Specifies whether and how relief shading is applied to an image. | Yes


## <div id="ColorMap">ColorMap</div>

ColorMap element defines a set of control points, called ColorMapEntry, which are used to colorize an elevation map. Each ColorMapEntry element specifies the color and the quantity value, which is altitude of elevation. In hill-shading, the color of each elevation point is computed using linear interpolation between two color map entries with altitudes above and below the given value.    

The following examples demonstrates a ColorMap to produce a shaded relief given below.

```xml
                  <ColorMap>
                    <ColorMapEntry>
                      <Color>#A3BDE0</Color>
                      <Label />
                      <Quantity>0</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                    <ColorMapEntry>
                      <Color>#C7DAA5</Color>
                      <Quantity>1</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                    <ColorMapEntry>
                      <Color>#DEE5C3</Color>
                      <Quantity>200</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                    <ColorMapEntry>
                      <Color>#B9CFB5</Color>
                      <Quantity>1000</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                    <ColorMapEntry>
                      <Color>#71BF7E</Color>
                      <Quantity>2500</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                    <ColorMapEntry>
                      <Color>#C18E39</Color>
                      <Quantity>3500</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                    <ColorMapEntry>
                      <Color>White</Color>
                      <Quantity>4200</Quantity>
                      <Opacity>1</Opacity>
                    </ColorMapEntry>
                  </ColorMap>
```


<center>![](/media/images/28-styling_colormap.png)</center>


## <div id="ShadedRelief">ShadedRelief</div>


ShadedRelief allows to set parameters of hillshading.


Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
BrightnessOnly | Boolean | Specifies whether the shading is applied using color or only alpha component. Default value is False. | No
CustomShadingMethod | String | Specifies the name of a custom shading method which can be implemented as a plugin. | No
Maximum | Single | Specifies the maximum altitude of elevation. Default value is 8848. | No
Minimum | Single | Specifies the minimum altitude of elevation. Default value is 0.| No
ShaderType | [ShaderType](/usermanual/styling/rastersymbolizer.md#ShaderType) | Specifies the type of a ColorMap. The Custom value means that user-defined ColorMap will be used. Default value is Jet.| No
ShadingMethod | [ShadingMethod](/usermanual/styling/rastersymbolizer.md#ShadingMethod) | The custom value means that CustomShadingMethod is used. Default value is StandardCombined. | No
ShadingParameters | [ShadingParameters](/usermanual/styling/rastersymbolizer.md#ShadingParameters) | Specifies the shading parameters such as sun altitude, sun azimuth or scale. | No



## <div id="ShaderType">ShaderType</div>

The list of pre-defined shader types is:

- Jet 
- Cool 
- Gray 
- LightGray 
- Bone
- Pink
- Copper 
- Hot
- HSV
- Summer 
- Autumn 
- Winter 
- Spring
- Rock 
- Surface 
- LightSurface
- Blast
- Gold
- Custom

## <div id="ShadingMethod">ShadingMethod</div>

The list of pre-defined shading methods is:

- Aspect
- ErdasAspect
- ErdasSlope
- HornSlope
- Standard
- StandardCombined
- ZevenbergenThorne
- ZevenbergenThorneAspect
- ZevenbergenThorneCombined
- ZevenbergenThorneSlope
- Custom


## <div id="ShadingParameters">ShadingParameters</div>


Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Scale | Single | Specifies the ratio of vertical units to horizontal. Default value is 1. | No
SunAltitude | Single | Specifies the altitude of the light source, in degrees. Default value is 45. | No
SunAzimuth | Single | Specifies the azimuth of the light source, in degrees. Default value is 315. | No
ZScaleFactor | Single | Specifies additional scale factor. Default value is 1. | No



