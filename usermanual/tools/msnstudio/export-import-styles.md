# Import/Export Map Styles

This section describes the capabilites of MapSurfer.NET Studio to import or export map styles in/from different formats such as SLD (GeoServer, MapServer), CartoCSS (GeoServer, Mapnik) or MapServer's map file.

## SLD Style Documents

The OpenGIS® [Styled Layer Descriptor](http://www.opengeospatial.org/standards/sld) (SLD) and [Symbology Encoding](http://www.opengeospatial.org/standards/se) (SE) are two specifications designed to describe user-defined symbolization and coloring of geospatial data using an XML language.

For further reading on this topic, we highly recommend [GeoServer's manual](http://docs.geoserver.org/stable/en/user/styling/index.html).

MapSurfer.NET Studio allows both importing and exporting SLD documents. Furthermore, it supports both versions of specification 1.0.0 and 1.1.0.

In order to export styles, you need to open/create a project. Once your project open, you can use **Project Explorer** to perform the required operation. 

1. Select a layer which you want to export.

2. Make a right click on a selected layer to show a context menu.

3. Select **Import Styles -> SLD...** menu item.

<center>![](/media/images/30-msnstudio-styles-export-import.png)</center>

4. In the Open dialog box, type the file name and select SLD version and units.

<center>![](/media/images/31-msnstudio-styles-export-dialog.png)</center>

5. Click **Save**.

To import styles into your project, repeat steps 1-3 given above.



