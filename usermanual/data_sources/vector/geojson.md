# GeoJSON

## Introduction

[GeoJSON](http://en.wikipedia.org/wiki/GeoJSON) is an open standard format for encoding collections of simple geographical features along with their non-spatial attributes using JavaScript Object Notation. 

## Configuration

This section describes configuration parameters used in **GeoJSON** data source provider.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
File | String |Determines a path to the the file. The path can also be relative to the directory where map project is stored. | Yes
FileBasedIndex | Boolean | Determines whether the quadtree spatial index is created or not. This index improves the performance in fetching data. It requires write permissions to a corresponding folder. Possible values are True or False. | No
Encoding | String | Specifies the character encoding to read data from .geojson file. Default value is UTF8. | No
