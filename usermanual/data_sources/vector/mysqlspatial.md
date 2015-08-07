# MySQLSpatial 

## Introduction

[MySQL](https://www.mysql.com/) is most popular open source relational database. Starting with MySQL 4.1, the database supports the generation, storage, and analysis of geographic features. MySQL implements (spatial extensions)[https://dev.mysql.com/doc/refman/4.1/en/spatial-extensions.html] following the specification of the [Open Geospatial Consortium](http://www.opengeospatial.org/) (OGC). 

## Configuration

This section describes configuration parameters used in **MySQLSpatial** data source provider. They are:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Connection | String |  Defines the string used to open a MySQL Server database. | Yes
Table | String | The table name. | Yes
GeometryColumn (or GeometryField) | String | Determines a spatial column that contains data of a spatial data type (e.g., geometry or geography). | Yes
Query | String | The query used to select data from a database. | Yes
Extent | String | Sets the extent of spatial data in a table. It is used by MapSurfer.NET Studio to speed up Zoom To Layer function.| No


> %!IMPORTANT NOTE!% **[OGR](usermanual/data_sources/vector/ogr.md)** is another data source provider that can access spatial data from MySQL Server.
