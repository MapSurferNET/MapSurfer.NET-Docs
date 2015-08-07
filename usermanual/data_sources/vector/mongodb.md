# MongoDB 

## Introduction

[MongoDB](http://www.mongodb.org/) is a popular document-oriented (NoSQL) database system. Among other features, MongoDB provides a possibility to handle geospatial information. For more details, see [Geospatial Indexes and Queries](http://docs.mongodb.org/manual/applications/geospatial-indexes/).

## Configuration

In MapSurfer.NET, **MongoDB** data source provider operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
Host | String | Defines the server's host name. | Yes
Port | Integer | Defines the server's port number. Default value is 27017. | No
Database | String |  Sets the optional database name. | Yes
User | String | Sets the default user name. | Yes
Password | String | Sets the default user password. | Yes
Collection | String | Defines a collection on the database with a default document type of BsonDocument. | Yes
GeometryElement | String | Sets the value of an element where Geometry is stored. Default value is loc.| Yes
Query | String |  Defines a [query](http://docs.mongodb.org/manual/tutorial/query-documents/) to find all documents in the specified collection that match it. Example: "{ type: "snacks" }"| No

