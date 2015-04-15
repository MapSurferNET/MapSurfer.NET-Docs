# MSSQLSpatial - Microsoft SQL Server Spatial Database

## Introduction

Starting with version 2008, Microsoft SQL Server has a builtin functionality to work with [spatial queries](https://msdn.microsoft.com/en-us/library/bb933790.aspx).  SQL Server supports two spatial data types: the **geometry** and the **geography**.

> %!IMPORTANT NOTE!% At the moment MapSurtfer.NET supports only geometry type.

## Configuration

This section describes configuration parameters used in **MSSQLSpatial** data source provider. They are:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Connection | String |  Defines the string used to open a SQL Server database. | Yes
Table | String | The table name. | Yes
GeometryColumn | String | Determines a spatial column that contains data of a spatial data type (e.g., geometry or geography). | Yes
SpatialIndex | String | Defines the name of a spatial index. | Yes
Query | String | The query used to select data from a database. | Yes
Extent | String | Sets the extent of spatial data in a table. It is used by MapSurfer.NET Studio to speed up Zoom To Layer function.| Yes


> %!IMPORTANT NOTE!% **[OGR](usermanual/datasources/vector/ogr.md)** is another data source provider that can access spatial data from Microsoft SQL Server.
