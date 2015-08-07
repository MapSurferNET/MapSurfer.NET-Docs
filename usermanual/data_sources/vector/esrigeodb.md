# ESRI Geodatabase

## Introduction

An ArcGIS geodatabase is a collection of geographic datasets of various types stored in a folder, a Microsoft Access database, or a multiuser relational database (such as Oracle, Microsoft SQL Server, PostgreSQL, Informix, or IBM DB2). The basic dataset types of the geodatabase are:

- Feature classes
- Raster datasets
- Tables

## Configuration


This section describes configuration parameters used in **EsriFileGeoDB** data source provider.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Path | String |Determines a path to the the file. The path can also be relative to the directory where map project is stored. | Yes
Table | String | Determines the name of a table from which the data are fetched. | Yes
Query | String | Specifies a query to select data from the table. | No
