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

### 3	Testing Environment, Datasets and Settings
Our experiments have been performed on a machine with an Intel® Core™ i5-2500 CPU @ 3.30 GHz running Windows 7 Professional x64 with 8GB installed memory. The runtime execution environments of our test application were JRE 8 (x64) and .NET Framework 4.5 (x64) respectively.

We ran our tests on datasets derived from OpenStreetMap data. More precisely, we took shapefiles of land areas (continents and islands) from [OpenStreetMapData](http://openstreetmapdata.com/data/land-polygons) web site. Two shapefiles (split versions) with data in [WGS84](http://openstreetmapdata.com/info/projections#wgs84) and [Mercator](http://openstreetmapdata.com/info/projections#mercator) projection, with about 400Mb in size each, were used.
Each toolkit has been configured using the following parameters:

Toolkit	| Shapefile Index | Metatile | Image Format | # of Threads	| Cache Format
------------ | ------------- | ------------- | ------------- | ------------- | -------------
GeoServer    | yes   | 8x8	| png8 | 4 | disk directories
MapServer    | yes | 8x8 | png8   | 4 | disk directories
Map Suite    | yes     | 1x1	| png24	| 4 | disk directories
MapSurfer.NET	| yes	| 8x8 |png8	| 4	| mbtiles
Mapnik/TileMill	| yes | 8x8 | png8 | 4	| mbtiles

It is important to make a note of some differences in configuration and custom changes in tile seeding procedures. First, [Map Suite Tile Cache Generator](http://thinkgeo.com/forums/MapSuite/tabid/143/aft/10446/Default.aspx) does not have capabilities to work with metatiles or save tiles in png8 format. Nevertheless, we decided include this library in our tests. Second, we make use MapServer and [C# mapscript](http://mapserver.org/de/installation/dotnet.html) to render and slice metatiles into smaller tiles. Third, it can be seen in the table that TileMill and MapSurfer.NET use an mbtiles storage. According to our prior tests, the difference in performance between “disk directories” and mbtiles is not significant (less than 1%).

The shapefiles and index files were stored on Samsung SSD P810 128GB. Western Digital WD1002FBYS Caviar RE3 SATA 1TB hard drive was used to store tile caches. For Test #3, we use the same Western Digital SATA disk to store data in a PostgreSQL database.


### 3.1	Map Styles
In the experiments, we use two maps styles. These styles are:

#### Style 1
_CartoCSS_

```cs
 #landpolygons {
   polygon-fill:#000;
   line-color:#ffffff;
   line-width:1;  
 }
```

_SLD_
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
</UserStyle>
```
 
 #### Style 2
 
 In Style 2, we have added a TextStymbolizer to label polygons.
 
_CartoCSS_

```cs
 #landpolygons {
   polygon-fill:#000;
   line-color:#ffffff;
   line-width:1;  
   
   ::label{
     text-face-name:"DejaVu Sans Book";
     text-name:"[FID]";
     text-fill:#444;
     text-halo-fill:rgba(255,255,255,1.0);
     text-halo-radius:0;
     text-size:9; 
  }
 }
```

_SLD_
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

## 4.	Comparisons
The following sections compare mapping toolkits using different data storages and map styles.

## 4.1 Test #1: Shapefile without Re-projection

In this section, we present the results of our benchmarks evaluating time needed to render a large shapefile (approx. 400 Mb) without re-projection and tiles seeding for small scales (see Figure 1), to be exact for zoom levels 0 to 9. We used Style 1 in this scenario. 

<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image005.png)</center>
**Figure 1**

A bar chart in Figure 2 shows the throughput comparison of mapping toolkits.

<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image006.png)</center>
**Figure 2**

Figure 3 illustrates the results of the second benchmark, which has been carried out using Style 2.
<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image007.png)</center>
**Figure 3**

## 4.2 Test #2: Shapefile with Re-projection

In this section, the mapping toolkits are tested on how fast they can re-project vector data. The task was to re-project the coordinates of geometries from WGS84 (EPSG:4326) to Spherical Mercator projection (EPSG:3857). The Style 1 was used in this benchmark.

<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image008.png)</center>
**Figure 4**

## 4.3 Test #3: PostgreSQL (PostGIS) without re-projection

In this section, the results of our experiments using PostgreSQL 9.3 (PostGIS 2.0) as data storage are given. The shapefile used in Test #1 has been imported into a PostgreSQL table using the same EPSG:3857 projection.

<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image009.png)</center>
**Figure 5**

## 4.4 Tests Summary

This section summarizes the results of our benchmarks given in sections 4.1-4.3. As can be seen from charts (see Figure 1-5), in most tests, especially when the number of tiles is very large (i.e. at z8 or z9), the best performance has been shown by MapSurfer.NET framework. 
We aggregated 


<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image010.png)</center>
**Figure 6**

<center>![](http://mapsurfernet.com/media/images/Blog/Post-Performance_Comparison_Tile_Seeding/image011.png)</center>
**Figure 7**

## 5.	Conclusions
Lastest version of the toolkits
Memory consumption 700 mb and 250 Mb


## See also
* [Q&A: Mapnik Performance, Just as Important as Its Beauty](https://developmentseed.org/blog/2010/oct/19/qa-mapnik-performance-just-important-its-beauty/)
* [WMS Performance Shootout 2009](http://www.slideshare.net/gatewaygeomatics.com/wms-performance-shootout)
