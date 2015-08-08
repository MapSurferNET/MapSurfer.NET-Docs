# CouchDB

## Introduction

[CouchDB](http://en.wikipedia.org/wiki/CouchDB) is an open source document-oriented NoSQL database that uses JSON to store data and JavaScript as its query language.

## Configuration

In MapSurfer.NET, **CouchDB** tile cache operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
DatabaseName | String | The name of a database. | Yes
TileSetName | String | The plain-english name of the tileset. | Yes
Host | String | The host name or IP address of the server. | Yes
Port | Integer | The port number of the CouchDB instance. Default value 5984. | No
UserName | String | The name of a user. | No
Password | String | The user's password. | No
