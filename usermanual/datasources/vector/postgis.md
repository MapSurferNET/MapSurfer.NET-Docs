# PostGIS  

## Introduction

[PostgreSQL](http://www.postgresql.org/) is the world's most advanced object-relational database management system with an emphasis on extensibility and standards-compliance. Among a variety of features, it supports geographic information system data types, such as geometry primitives, spatial operations and indices, etc., through [PostGIS](http://postgis.net/) extension.

Internally, MapSurfer.NET uses [Npgsql](http://npgsql.projects.pgfoundry.org/) data provider to access a PostgreSQL database.

## Configuration

This section describes configuration parameters used in **PostGIS** data source provider. They are:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Connection | String | Defines the string used to open a PostgreSQL database. | Yes
Table | String | The table name. | Yes
GeometryColumn (GeometryField) | String | Determines a spatial column that contains data of a spatial data type (e.g., geometry or geography). | Yes
Query | String | The query used to select data from a database. | Yes
Extent | String | Sets the extent of spatial data in a table. It is used by MapSurfer.NET Studio to speed up Zoom To Layer function.| No
SpatialTypePrefix | Boolean | Uses ST_ prefix in queries (for example, ST_XMin instead of XMin). Default value is true. | No
UseSTIntersects | Boolean | The provider uses ST_Intersects function to find objects within a bounding box specified in a query. If the value is false then && operator is used. Default value is false. | No
SRID | Integer | Defines the spatial reference identifier for a geometry object (see [ST_SetSRID](http://postgis.org/docs/ST_SetSRID.html) function). | No 
