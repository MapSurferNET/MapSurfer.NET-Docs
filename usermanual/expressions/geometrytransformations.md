# Geometry Transformations

## Introduction

Each **Symbolizer** has a property **GeometryExpression** that allows specifying which geometry attribute will be used in rendering. Being an expression, this property can be used to compute feature geometry utilizing one of the supported transformation functions. The return value of transformation function is a **Geometry** object.

### Supported Transformations
 
- [CenterLine](#CenterLine)
- [CenterPoint](#CenterPoint)
- [CentroidPoint](#CentroidPoint)
- [Clip](#Clip)
- [ConstructPoints](#ConstructPoints)
- [ConvexHull](#ConvexHull)
- [Densify](#Densify)
- [EndPoint](#EndPoint)
- [Envelope](#Envelope)
- [Equidistant](#Equidistant)
- [MBR](#MBR)
- [MBRLongestAxis](#MBRLongestAxis)
- [Offset](#Offset)
- [OffsetCurve](#OffsetCurve)
- [Simplify](#Simplify) 
- [Smooth](#Smooth)
- [StartOffset](#StartOffset)
- [StartPoint](#StartPoint)
- [VertexAnchoredSegments](#VertexAnchoredSegments)
- [Vertices](#Vertices)
- [ViewTransformation](#ViewTransformation)


#### <div id="CenterLine">CenterLine</div>

#### <div id="CenterPoint">CenterLine</div>

#### <div id="CentroidPoint">CentroidPoint</div>

#### <div id="ConvexHull">ConvexHull</div>

Returns the convex hull or convex envelope of the points that form the given geometry object.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.ConvexHull([geom_field]) 
 
**Example**
<center>![](/media/images/14-geomtrans_convexhull.png)</center>

#### <div id="Envelope">Envelope</div>

Returns a bounding box of the geometry object.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.Envelope([geom_field]) 
 
**Example**
<center>![](/media/images/10-geomtrans_envelope.png)</center>

#### <div id="MBR">MBR</div>

Returns the minimum bounding rectangle (MBR) of the geometry object.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.MBR([geom_field]) 

**Example**
<center>![](/media/images/11-geomtrans_mbr.png)</center>

#### <div id="MBRLongestAxis">MBRLongestAxis</div>

Returns the longest axis of the minimum bounding rectangle.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.MBRLongestAxis([geom_field]) 

**Example**
<center>![](/media/images/12-geomtrans_mbrlongestaxis.png)</center>

#### <div id="Offset">Offset</div>

Translates the geometry to a new location by adding offset parameters *deltaX* and *deltaY* to each coordinate.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.Offset([geom_field], 5, 5) 

**Example**
<center>![](/media/images/15-geomtrans_offset.png)</center>

#### <div id="Vertices">Vertices</div>

Returns a list of vertices that form the geometry object.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.Vertices([geom_field]) 

**Example**
<center>![](/media/images/13-geomtrans_vertices.png)</center>

#### <div id="ViewTransformation">ViewTransformation</div>

Returns a new geometry object with coordinates transformed to the map view coordinate system that is normally measured in map units (for example, pixels). This function helps to operate with other functions such as OffsetCurve that have parameters measured in map units.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.ViewTransformation([geom_field], [_ViewTransformation_]) 


### Custom Transformations

You can extend the list of supported geometry transformations with your own functions. This can be accomplished by implementing a custom function class inherited from **MapSurfer.Geometries.TransformationFunctions.GeometryTransformationFunction** class. This class should have an overriden **TransformGeometry** function that contains the logic of the function. In order to give a unique name to the function, you need to provide **PluginDescription** attribute to the class. See example below

```cs
using System;
using GeoAPI.Geometries;
using MapSurfer.Configuration;

namespace MapSurfer.Geometries.TransformationFunctions
{
  [PluginDescription("EndPoint")]
  public class EndPointTranformationFunction : GeometryTransformationFunction
  {
    public EndPointTranformationFunction()
    { 
    }

    protected override Geometry TransformGeometry(Geometry geom)
    {
      ICoordinate[] coords = geom.Coordinates;
      return new Point((ICoordinate)coords[coords.Length - 1].Clone());
    } 
  }
}

```
