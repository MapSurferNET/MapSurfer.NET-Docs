# ESRI Shapefiles



The shapefile format is a digital vector storage format for storing geometric location and associated attribute information. This format consists of several files. The list of files supported by MapSurfer.NET is: 

**Mandatory files**

- **.shp** — shape format; stores the feature geometry itself
- .shx — shape index format; a positional index of the feature geometry to allow seeking forwards and backwards quickly
- **.dbf** — attribute format; columnar attributes for each shape, in dBase IV format


**Other files**

- **.prj** — projection format; the coordinate system and projection information, a plain text file describing the projection using well-known text format
- **.sbn** and **.sbx** — a spatial index of the features
- **.cpg** — used to specify the code page (only for .dbf) for identifying the character encoding to be used
- **.mdix** — a quadtree spatial index, analouge of .qix format used by MapServer, Mapnik and GDAL/OGR.


Parameter Name | Description | Required
------------ | ------------- | -------------
File | Determines a path to the the file. The path can also be relative to the directory where map project is stored. | Yes
FileBasedIndex | Determines whether the quadtree spatial index is created or not. This index improves the performance of reading data from disk. Possible values are True or False. | No
MemoryMappedFile | Creates a memory-mapped file that enables to work with extremely large files. Possible values are True or False. | No
Encoding | Specifies the character encoding to read data from .dbf file. | No
BufferSize | A positive integer value greater than 0 indicating the buffer size in bytes. The default buffer size is 512.| No