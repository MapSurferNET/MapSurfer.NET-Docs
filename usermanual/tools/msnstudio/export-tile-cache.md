# Export Tile Cache

This article describes steps which need to be performed to generate a tile cache using MapSurfer.NET Studio. These steps are:

<center></center>
> !!Step 1!! Choose File > Export > Export Web Format ...

<center>![](/media/images/21-msnstudio_export_tile_cache.png)</center>

<center></center>
> !!Step 2!! In the Tile Cache Export Options dialog box, select the options  you want, and click OK. For more details about these options see next section.

<center></center>
> !!Step 3!! Next, a dialog box with processing information is shown. It will be closed when the cache is generated.

<center>![](/media/images/26-msnstudio_tile_cache_generation.png)</center>


## Tile Cache Export Options 

The dialog has four groups of settings. These settings are:

### General

This tab allows to specify the bounding box of a map region you want to export, zoom levels and the size of a metatile. The coordinates of the bounding box can be either in Longigute/Latitude coordinates or in the coordinates of the current map projection. 

<center>![](/media/images/22-msnstudio_export_tile_cache_general.png)</center>

### Storage

This tab allows to choose the [type of a tile cache](usermanual/tile_caching/index). By changing the selected tile cache type, you get an access to the set of its configuration parameters.

<center>![](/media/images/23-msnstudio_export_tile_cache_storage.png)</center>

### Image Format

This tab allows to choose and configure image format. The supported image formats are BMP, GIF, JPEG, PNG and TIFF. Each format has its own parameters. For example, by working with PNG format, you can choose an algorithm which will be used for image quantization.

<center>![](/media/images/24-msnstudio_export_tile_cache_image_format.png)</center>

### Processing

This tab allows specifying such parameters as number of threads used for rendering and image processing, the type of memory consumption, etc.

<center>![](/media/images/25-msnstudio_export_tile_cache_processing.png)</center>
