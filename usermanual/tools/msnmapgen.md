### Generating maps using MSNMapGen ###

This tutorial describes how to generate raster (as a single file or tile cache) or vector maps using a console based application called MSNMapGen.

On Windows: 

>%!COMMAND-LINE!% MSNMapGen.exe [Arguments]

On Linux:

>%!COMMAND-LINE!% ./MSNMapGen.sh [Arguments]


#### Arguments ####

Argument      | Short form   | Description  | Mode 
------------- | ------------ | ------------ | ----
-help         | -h           | Display usage information. | 
-map          | -m           | The path to a file that contains map styles (see [MapSurfer.NET Studio](/usermanual/tools/MSNStudio)). |  1,2
-size         | -s           | The size of a map in pixels. Default value is 256x256. | 1
-output       | -o           | The path to a file that is being generated. Default value is output.png. | 1
-format       | -f           | The format of a file that is being generated. Default value is image/png. Other possible values are **image/png24**, **image/png8**, **image/pnga**, **image/bmp**, **image/gif**, **image/jpeg**, **image/tiff**. | 1
-renderer     | -r           | Default value is GDI. **Note:** Cairo renderer is not supported on Linux yet. | 1
-bbox         | -b           | The extent of a map region. The coordinates should be in the same projection as the map. Example: -bbox 959125.94,6339502.88, 972540.64,6349038.40. | 1
-tilecachegen | -tcg         | This file can be created using [MapSurfer.NET Studio](/usermanual/tools/MSNStudio) (see File > Export > Export To Web Format...) | 2
