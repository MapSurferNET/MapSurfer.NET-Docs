# MBTiles

## Introduction

[MBTiles](http://wiki.openstreetmap.org/wiki/MBTiles) is a file format developed by MapBox for storing map tiles in a SQLite database. For more details see format specification on [GitHub](https://github.com/mapbox/mbtiles-spec).

## Configuration

In MapSurfer.NET, **MBTiles** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Path | String | Determines a path to the the file. | Yes
Password | String | The user's password to connect. | No
Pooling | Boolean | Enables pooling mode. | No
Name | String | The plain-english name of the tileset. | Yes
Version | Integer | The version of the tileset, as a plain number. | Yes
Type | String | The type of a the tilset; either overlay or baselayer. | Yes
Format | String | The image file format of the tile data: png or jpg. | Yes
Description | String | Additional information about the tileset. | No


