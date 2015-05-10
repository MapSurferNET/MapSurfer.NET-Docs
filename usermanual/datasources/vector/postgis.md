# PostGIS  

## Introduction

[PostgreSQL](http://www.postgresql.org/) is the world's most advanced object-relational database management system with an emphasis on extensibility and standards-compliance. Among a variety of features, it supports geographic information system data types, such as geometry primitives, spatial operations and indices, etc., through [PostGIS](http://postgis.net/) extension.

Internally, MapSurfer.NET uses [Npgsql](http://npgsql.projects.pgfoundry.org/) data provider to access a PostgreSQL database.

## Configuration

This section describes configuration parameters used in **PostGIS** data source provider. They are:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Connection | String |  Defines the string used to open a SQL Server database. | Yes
Table | String | The table name. | Yes

