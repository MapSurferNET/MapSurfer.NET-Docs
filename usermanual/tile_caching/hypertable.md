# Hypertable

## Introduction

[Hypertable](http://en.wikipedia.org/wiki/Hypertable) is an open source database system inspired by publications on the design of Google's BigTable. 

## Configuration

In MapSurfer.NET, **Hypertable** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Namespace | String | The namespace. | Yes
TileSetName | String | The plain-english name of the tileset. | Yes
Host | String | The host name or IP address of the server. | Yes
Port | Integer | The port number of the Hypertable instance. Default value 38080. | No
PoolSize | Integer | Connection pool size. Default value is 100. | No

