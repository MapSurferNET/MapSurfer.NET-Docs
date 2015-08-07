# GPX

## Introduction

GPX, or GPS Exchange Format, is an XML-based file format that is specially designed to describe GPS data such as waypoints, tracks, and routes.

For further details, see the format description on the [wiki](http://en.wikipedia.org/wiki/GPS_Exchange_Format). 

## Configuration

In MapSurfer.NET, **GPX** data source provider operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
File | String | Determines a path to the the file. The path can also be relative to the directory where map project is stored. | Yes
BuildSpatialIndex | Boolean | Determines whether the quadtree spatial index is created or not. This index improves the performance of reading data from disk. It requires write permissions to a corresponding folder. Possible values are True or False. | No

> %!IMPORTANT NOTE!% GPX files can also be read using another data source provider such as
**[OGR](usermanual/data_sources/vector/ogr.md)**.
