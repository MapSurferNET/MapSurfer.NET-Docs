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

#### <div id="MBRLongestAxis">MBRLongestAxis</div>

Returns a list of vertices that form the geometry object.

**Syntax**
>%!FUNCTION-SYNTAX!% GeometryTransformations.Vertices([geom_field]) 

**Example**
<center>![](/media/images/13-geomtrans_vertices.png)</center>

#### <div id="ViewTransformation">ViewTransformation</div>

```cs
GeometryTransformations.OffsetCurve(GeometryTransformations.ViewTransformation([_geom_], [_ViewTransformation_]), 5, 2) 
```
