# OpenStreetMap Data

## Introduction

OpenStreetMap (OSM) is a collaborative project to create a free editable map of the world. The initial map data was originally collected by volunteers performing systematic ground surveys using a GPS unit and other devices. 

The OSM geospatial data are stored and processed in different [formats](http://wiki.openstreetmap.org/wiki/OSM_file_formats). Two main formats are:

- [OSM XML](http://wiki.openstreetmap.org/wiki/OSM_XML) – xml-format provided by the API
- [PBF](http://wiki.openstreetmap.org/wiki/PBF) – highly compressed, optimized binary format that uses Google's [Protocol Buffers](http://en.wikipedia.org/wiki/Protocol_Buffers).

There are several servers that provide regularly updated data extracts from OpenStreetMap database such as [Geofabrik](http://download.geofabrik.de) and [Planet OSM](http://planet.osm.org)

## Configuration

This section describes configuration parameters used in **OSM** data source provider.


Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
File | String | Determines a path to the the file. The path can also be relative to the directory where map project is stored. | Yes
BuildSpatialIndex | Boolean | Determines whether a quadtree spatial index is created or not. This index improves the performance of reading data from disk. It requires write permissions to a corresponding folder. Possible values are True or False. Earlier versions also require parameter FileBasedIndex to have the same value. | No
TagsFilter | String | Determines a comma-separated list of tags to be considered. | No
Query | String |Specifies a query which is used to filter data before storing it in RAM. Example: [highway] = "motorway" and [highway] = "trunk". For more details, see [Expressions](usermanual/expressions/index.md). | No

> %!IMPORTANT NOTE!% For big data sets, it is recommended to utilize more memory-efficient data source providers such as [PostGIS/PostgreSQL](usermanual/data_sources/vector/postgis.md), [Microsoft SQL Spatial](usermanual/data_sources/vector/mssqlspatial.md) or [MySQL Spatial](usermanual/data_sources/vector/mysqlspatial.md).

