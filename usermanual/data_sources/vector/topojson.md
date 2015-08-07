# TopoJSON

## Introduction

[TopoJSON](http://en.wikipedia.org/wiki/GeoJSON#TopoJSON) is an extension of [GeoJSON](http://en.wikipedia.org/wiki/GeoJSON) that encodes topology. 

## Configuration

This section describes configuration parameters used in **GeoJSON** data source provider.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
File | String |Determines a path to the the file. The path can also be relative to the directory where map project is stored. | Yes
FileBasedIndex | Boolean | Determines whether the quadtree spatial index is created or not. This index improves the performance in fetching data. It requires write permissions to a corresponding folder. Possible values are True or False. | No
Encoding | String |Specifies the character encoding to read data from .topojson file. Default value is UTF8. | No
