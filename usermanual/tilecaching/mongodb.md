# MongoDB

## Introduction

[MongoDB](http://en.wikipedia.org/wiki/MongoDB) is a cross-platform document-oriented (NoSQL) database. More information about MongoDB can be found in [wikipedia](http://en.wikipedia.org/wiki/MongoDB).

## Configuration

In MapSurfer.NET, **MongoDB** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
DatabaseName | String | Determines the name of a database. | Yes
TileSetName | String | The plain-english name of the tileset. | Yes
Host | String | The host name or IP address of the server. | Yes
Port | Integer | The port number of the MongoDB instance. Default value 27017. | No
UserName | String | The name of a user. | No
Password | String | The user's password. | No
