# Memcached

## Introduction

[Memcached](http://en.wikipedia.org/wiki/Memcached) is a general-purpose distributed memory caching system that uses RAM to cache data and objects.

## Configuration

In MapSurfer.NET, **Memcached** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Host | String | The host name or IP address of the server. | Yes
Port | Integer | The port number of the memcached instance. Default value 11211. | No
TileSetName | String | The plain-english name of the tileset. | Yes
UseAuthentication | Boolean | Defines whether to use authentication or not. | No
UserName | String | The name of a user. | No
Password | String | The user's password. | No
Protocol | String | The type of the communication between client and server. Possible values are either **text** or **binary**. Default value is **text**. | No
