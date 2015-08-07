# GDAL

## Introduction

GDAL allows reading raster geospatial data formats. The full list of supported formats can found on [this](http://www.gdal.org/formats_list.html) page.

## Configuration

In MapSurfer.NET, **GDAL** data source provider operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
GDALPath | String | Specifies the directory where GDAL is installed. | No
CacheSize | Integer | Specifies the size of the cache in GDAL. | No
File | String | Specifies the path to a file. | No
Extents | String | Specifies the data extent. | No
ResampleAlgorithm | String | Specifies the algorithm which will be used for data re-sampling. Possible values are "nearestneighbour", "bilinear", "cubic", "cubicspline" and "lanczos". Default value is "nearestneighbour". | No
TransparentColor | String | Specifies the color in html format for transparent pixels. | No
StoreInMemory | String | Specifies whether the raster image is stored in the memory or not. Default value is False. | No
Downsampling | Boolean | Specifies whether the down sampling will be performed or not. Default value is False. | No
 