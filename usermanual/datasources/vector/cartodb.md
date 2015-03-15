# CartoDB

## Introduction

CartoDB is a cloud computing platform that provides GIS and web mapping tools for display in a web browser. CartoDB is based on PostGIS and PostgreSQL which allows to interact with custom tables as they were a part of normal database. For more information, visit official [web page](http://docs.cartodb.com/cartodb-platform/sql-api.html).

## Configuration

This section describes configuration parameters used in **CartoDB** data source provider.

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
AccountName | String | Determines a name of the account. | Yes
Domain | String | Determines a domain name. Default value is cartodb.com | No
UserMail | String | User email used for authentication. | Yes
UserPassword | String | User password used for authentication. | Yes
ConsumerKey | String | Consumer key used in [OAuth](http://hueniverse.com/oauth/) authentication. | Yes
ConsumerSecret | String | Consumer secret used in [OAuth](http://hueniverse.com/oauth/) authentication. | Yes
Table | String | Name of a table you want to access. | Yes
GeometryColumn | String | Name of a column with geometry objects. | Yes
Query | String | SQL query. For more details, see official documentation for [PostgreSQL](http://www.postgresql.org/docs/8.4/static/tutorial-select.html). | No
Extent | String | Maximum extent of spatial data in the table. | No

