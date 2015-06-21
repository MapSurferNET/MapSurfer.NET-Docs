## 1. Introduction

The unprecedented growth of different cartographic web services (Google Maps, Here Maps, Bing Maps, Navteq, Mapbox, CartoDB etc.) and the availability of a huge variety of user-defined maps have rapidly expanded the distribution of maps. The most common way of distributing maps through internet is using a [web map tile service](https://en.wikipedia.org/wiki/Web_Map_Tile_Service) (WMTS). WMTS is a standard protocol for serving a set of pre-rendered georeferenced map images, called tiles, over the Internet. The most obvious benefit of a tile based approach is that map tiles can be prepared (rendered) beforehand at any location. Use of tile caches increases the performance and scalability of map services significantly.
Nowadays, a great variety of software packages for rendering maps exist. For example, these packages are [ArcGIS Server](http://www.esri.com/software/arcgis/arcgisserver), [QGIS Server](http://live.osgeo.org/en/quickstart/qgis_mapserver_quickstart.html), [MapServer](http://mapserver.org), [GeoServer](http://geoserver.org), [Mapnik](http://mapnik.org), [Cadcorp GeognoSIS](http://www.cadcorp.com/products/server/geognosis), [Thinkgeo's Map Suite]((https://thinkgeo.com/map-suite-developer-gis/)), and many others. There are two basic factors that show how powerful a certain software package is. These factors are: _the capability to produce a cartographically plausible product_ and the _performance of the software_. In the context of [WMS Shootout](http://wiki.osgeo.org/wiki/FOSS4G_Benchmark) (see also this [post](https://developmentseed.org/blog/2010/oct/19/qa-mapnik-performance-just-important-its-beauty/)), there have been many attempts to compare the performance of different tools in rendering spatial data. According to the latest available benchmarks, conducted in [2010](http://svn.osgeo.org/osgeo/foss4g/benchmarking/wms/2010/results/benchmarking2010.odp)-[2011](http://svn.osgeo.org/osgeo/foss4g/benchmarking/wms/2011/presentation/benchmarking2011.pdf), the winners were **MapServer** and **Mapnik**, as they shew the best performance in the tests and left far behind other competitors.

This article concentrates on comparing performance of different existing GIS applications and libraries in map generation, namely in [tile seeding](http://docs.geoserver.org/latest/en/user/geowebcache/seeding.html). Generally, the performance of such programs depends on different factors such as data fetching, feature rasterization (rendering), image quantization, disk writing, memory re-allocation etc. All these factors influence the performance of tile seeding as well. 

Note that the given benchmark is only roughly presents the actual performance of the tested toolkits, as their performance characteristics are [platform dependent](http://svn.osgeo.org/osgeo/foss4g/benchmarking/wms/2011/presentation/benchmarking2011.pdf) and we conducted our experiments only on a Windows machine. Furthermore, it is rather difficult to properly configure the toolkits as they have diverse set of parameters. Nevertheless, we tried to do our best to make the comparison of the software packages under equal conditions. 

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

## 3.	Comparisons

### 3.1	Testing Environment, Datasets and Settings
Our experiments have been performed on a machine with an Intel® Core™ i5-2500 CPU @ 3.30 GHz running Windows 7 Professional x64 with 8GB installed memory. The runtime execution environments of our test application were JRE 8 (x64) and .NET Framework 4.5 (x64) respectively.

We ran our tests on datasets derived from OpenStreetMap data. More precisely, we took shapefiles of land areas (continents and islands) from OpenStreetMapData web site. Two shapefiles (split versions) with data in WGS84 and Mercator projection, with about 400Mb in size each, were used.
Each toolkit has been configured using the following parameters:


Toolkit	| Shapefile Index | Metatile | Image Format | # of Threads	| Cache Format
------------ | ------------- | ------------- | ------------- | ------------- | -------------
GeoServer    | yes   | 8x8	| png8 | 4 | disk directories
MapServer    | yes | 8x8 | png8   | 4 | disk directories
Map Suite    | yes     | 1x1	| png8	| 4 | disk directories
MapSurfer.NET	| yes	| 8x8 |png8	| 4	| mbtiles
Mapnik/TileMill	| yes | 8x8 | png8 | 4	| mbtiles


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

