# OracleSpatial 

## Introduction

Oracle Spatial is an advanced feature of the Oracle database that allows store and process spatial data. 

## Configuration

This section describes configuration parameters used in **OracleSpatial** data source provider. They are:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Connection | String |  Defines the string used to open an Oracle database. | Yes
GeometryColumn | String | Determines a spatial column that contains data of a spatial data type (e.g., geometry or geography). | Yes
Query | String | The query used to select data from a database. | Yes
Owner | String | The owner of the retrieved data set. | No
Extent | String | Sets the extent of spatial data in a table. It is used by MapSurfer.NET Studio to speed up Zoom To Layer function.| No


> %!IMPORTANT IMPORTANT:!% OracleSpatial plugin requires [Oracle Data Provider for .NET](http://www.oracle.com/technetwork/topics/dotnet/index-085163.html) (see also
> [Nuget package](https://www.nuget.org/packages/Oracle.ManagedDataAccess/) to be installed on a computer. You can also install the required assemblies manually by copying 
> **Oracle.ManagedDataAccess.dll** assembly into **MapSurfer.NET_Installation_Folder\Core\Plugins\Providers\MsSQLSpatial**. Dynamic link libraries 
> **Oracle.ManagedDataAccessDTC.dll** and **Oracle.ManagedDataAccessIOP.dll** need to be copied into **Native.x64** (for 64-bit OS) or **Native.x86** (for 32-bit OS)
> directory respectively. 

> %!IMPORTANT NOTE!% This provider is available since v2.6.

> %!IMPORTANT NOTE!% **[OGR](usermanual/data_sources/vector/ogr.md)** is another data source provider that can access spatial data from Oracle.
