# Cassandra

## Introduction

[Cassandra](http://en.wikipedia.org/wiki/Apache_Cassandra) is an open source distributed database management system designed to handle large amounts of data across many commodity servers, providing high availability with no single point of failure. 

## Configuration

In MapSurfer.NET, **Cassandra** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
ClusterName | String | The name of a cluster. | Yes
TileSetName | String | The plain-english name of the tileset. | Yes
Host | String | The host name or IP address of the server. | Yes
Port | Integer | The port number of the Hypertable instance. Default value 9160. | No

