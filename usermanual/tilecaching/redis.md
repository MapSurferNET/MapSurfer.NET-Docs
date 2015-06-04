# Redis

## Introduction

[Redis](http://en.wikipedia.org/wiki/Redis) is an open source, BSD licensed, advanced key-value cache and store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets, sorted sets, bitmaps and hyperloglogs.

## Configuration

In MapSurfer.NET, **Redis** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
TileSetName | String | The plain-english name of the tileset. | Yes
Host | String | The host name or IP address of the server. | Yes
Port | Integer | The port number of the Redis instance. Default value 6379. | No
Password | String | The database's password. | No
PoolSize | Integer | Connection pool size. Default value is 10. | No

 