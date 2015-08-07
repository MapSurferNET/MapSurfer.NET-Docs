# Vector Tiles

## Introduction

[Vector tiles spec](https://github.com/mapbox/vector-tile-spec) is an open format designed to deliver spatial data using a tile-based approach. More exactly, each tile consists of a collection of geometric features and their metadata. 

There are several services that provide vector tiles for OpenStreetMap data such as [Mapbox](https://www.mapbox.com/developers/vector-tiles/) and [Mapzen](https://github.com/mapzen/vector-datasource/wiki/Mapzen-Vector-Tile-Service).


## Configuration

In MapSurfer.NET, **VectorTIles** data source provider operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Datasource | String | Determines an url of a web service that delivers vector tiles. For example: http://vector.mapzen.com/osm/buildings/{z}/{x}/{y}.mapbox.  One can define a set of urls using the following template: {a,b,c,d}.tiles.osm.org/{z}/{x}/{y}.png. | Yes
Format | String | The format of vector tiles. Possible values are     **Protobuf**, **GeoJson** and **TopoJson**. Default value is Protobuf| No
Extent | String | Extent of geodata. Default values is "-180, -89, 180, 89". | No
Layers | String | A comma-separated list of layers to be fetched from tiles. | No
Mode | String | Working mode of the data source provider. Possible values are     WebService, TileCache and WebServiceAndTileCache | No
Properties | String | Determines a list of properties to be decoded.| No
MaxZoom | Integer | The maximum zoom level of data. | No
ThreadsNumber | Integer | The number of threads used to process data. | No
TileCache | String | Determines a list of parameters for a local [tile cache](usermanual/tilecaching/index.md) which is used to store downloaded tiles. This list must contain parameter **CacheName**, the name-value pairs must be delimited with $;$, where each key and value pair must be delimited with $=$. | No


> %!IMPORTANT NOTE!% The **VectorTiles** data source provider also supports tiles encoded in GeoJSON or TopoJSON [formats](https://github.com/mapzen/vector-datasource/wiki/Mapzen-Vector-Tile-Service#formats).

