## 1. Introduction

The unprecedented growth of different cartographic web services (Google Maps, Here Maps, Bing Maps, Navteq, Mapbox, CartoDB etc.) and the availability of a huge variety of user-defined maps have rapidly expanded the distribution of maps. The most common way of distributing maps through internet is using a web map tile service (WMTS). WMTS is a standard protocol for serving a set of pre-rendered georeferenced map images, called tiles, over the Internet. The most obvious benefit of a tile based approach is that map tiles can be prepared (rendered) beforehand at any location. Use of tile caches increases the performance and scalability of map services significantly.
Nowadays, a great variety of software packages for rendering maps exist. For example, these packages are ArcGIS Server, QGIS Server, MapServer, GeoServer, Mapnik, Cadcorp GeognoSIS, Thinkgeo's Map Suite, and many others. There are two basic factors that show how powerful a certain software package is. These factors are: _the capability to produce a cartographically plausible product_ and the _performance of the software_. In the context of WMS Shootout (see also this post), there have been many attempts to compare the performance of different tools in rendering spatial data. According to the latest available benchmarks, conducted in 2010-2011, the winners were MapServer and Mapnik, as they shew the best performance in the tests and left far behind other competitors.

This article concentrates on comparing performance of different existing GIS applications and libraries in map generation, namely in tile seeding. Generally, the performance of such programs depends on different factors such as data fetching, feature rasterization (rendering), image quantization, disk writing, memory re-allocation etc. All these factors influence the performance of tile seeding as well. 

Note that the given benchmark is only roughly presents the actual performance of the tested toolkits, as their performance characteristics are platform dependent and we conducted our experiments only on a Windows machine. Furthermore, it is rather difficult to properly configure the toolkits as they have diverse set of parameters. Nevertheless, we tried to do our best to make the comparison of the software packages under equal conditions. 

## 2.Software packages
The goal of this article is to provide performance comparisons between different free, open source and commercial applications and toolkits for rendering maps. They are:
 
* [GeoServer](http://geoserver.org)
* [Mapnik](http://mapnik.org)/[TileMill](https://www.mapbox.com/tilemill/)
* [MapServer](http://mapserver.org) 
* [Map Suite](https://thinkgeo.com/map-suite-developer-gis/)
* [MapSurfer.NET](http://mapsurfernet.com)

A full description of each tested toolkit is given in the table below.

Toolkit	| Language | Runtime Environment | Architecture | Version	| Build Date
------------ | ------------- | ------------- | ------------- | ------------- | -------------
GeoServer    | Java   | JRE 8	| x64 | 2.7.0 | 20.03.2015
MapServer    | C/C++  | unmanaged code | x86   | 6.4.1 | 02.01. 2014
Map Suite    | C#     |.NET 4.0	| x64	|8.0.0.0 | 22.12.2014
MapSurfer.NET	| C#/C++	|.NET 4.5 |x64	|2.0.3	|02.06.2015
Mapnik/TileMill	| C++/Node.js | unmanaged code | x86 | 2.2/0.10.1	| 10.10.2012

As it can be seen, the libraries and toolkits are written in different programming languages such as C/C++, C# and Java. Furthermore, they are either compiled into so called unmanaged code (C/C++) or executed in runtime environments such as Java Runtime Environment (JRE) and Microsoft’s .NET framework.



TODO
 
```xml
<UserStyle>
  <FeatureTypeStyle>
    <Rule>
      <Name>Rule1</Name>
      <Title>Polygon with Outline</Title>
      <PolygonSymbolizer>
        <Fill>
          <CssParameter name="fill">#AAAAAA</CssParameter>
        </Fill>
      </PolygonSymbolizer>
      <LineSymbolizer>
        <Stroke>
          <CssParameter name="stroke">#FF0000</CssParameter>
          <CssParameter name="stroke-width">1</CssParameter>
        </Stroke>	
      </LineSymbolizer>
    </Rule>
  </FeatureTypeStyle>
  <FeatureTypeStyle>
    <Rule>
      <Name>Rule 2</Name>
      <Title>Text</Title>
      <TextSymbolizer>
        <Geometry>
          <ogc:Function name="centroid">
            <ogc:PropertyName>the_geom</ogc:PropertyName>
          </ogc:Function>
        </Geometry>
        <Label>
           <ogc:PropertyName>FID</ogc:PropertyName>
        </Label>
        <Font>
          <CssParameter name="font-family">DejaVu Sans Book</CssParameter>
          <CssParameter name="font-size">9</CssParameter>
          <CssParameter name="font-style">normal</CssParameter>
         </Font>
        <LabelPlacement>
          <PointPlacement>
            <AnchorPoint>
              <AnchorPointX>0.5</AnchorPointX>
              <AnchorPointY>0.0</AnchorPointY>
            </AnchorPoint>
          </PointPlacement>
        </LabelPlacement>
        <Fill>
          <CssParameter name="fill">#990099</CssParameter>
        </Fill>
      </TextSymbolizer>
    </Rule>
  </FeatureTypeStyle>
</UserStyle>
```

