# DEM - Digital Elevation Model

## Introduction

**DEM** allows to work with ASTER and SRTM tile sets stored on the disk. This data sources can provide both raster and vector (isolines) elevation data.  

## Configuration

In MapSurfer.NET, **DEM** data source provider operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
GDALPath | String | Specifies the directory where GDAL is installed. | No
CacheSize | Integer | Specifies the size of the cache in GDAL. | No
DataSourceType | String | Specifies the type of a data source. Possible values are "ASTER", "SRTM", "SRTM_v2", "SRTM_v4", "ERS". | No
Path | String | Specifies the directory containing raster images. | No
FileExtension | String | Specifies the extension of raster files.  Default values are .srtm (ERS), .hgt (SRTM, SRTM_V2), .tif (ASTER, SRTM_V4). | No
DataType | String | Specifies the type of data which will be extracted from a data source. Possible values are Raster or Vector. Vector type means that isolines will be automatically extracted from a digital elevation model. Default value is Raster. | No
IsolineInterval | Single | Specifies the interval between isolines. | No
MinElevation | Single | Specifies the minimum elevation to be considered. | No
MaxElevation | Single | Specifies the maximum elevation to be considered. | No
RestoreData  | Boolean | Specifies whether holes in data will be restored or not. Default value is False. | No
ResampleAlgorithm | String | Specifies the algorithm which will be used for data re-sampling. Possible values are "nearestneighbour", "bilinear", "cubic", "cubicspline" and "lanczos". Default value is "nearestneighbour". | No
AutoResolution | Boolean | Specifies whether the data will be automatically re-sampled according to the scale and extent of a map. Default value is False. | No
Downsampling | Boolean | Specifies whether the down sampling will be performed or not. Default value is False. | No