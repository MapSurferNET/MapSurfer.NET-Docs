# OGR


## Introduction

The [OGR](http://www.gdal.org/) is an open source library written in C++ that is able to read a variety of vector geospatial data formats such as:

- [Aeronav FAA files](http://www.gdal.org/drv_aeronavfaa.html)		
- [ESRI ArcObjects](http://www.gdal.org/drv_ao.html)				
- [Arc/Info Binary Coverage](http://www.gdal.org/drv_avcbin.html)	
- [Arc/Info .E00 (ASCII) Coverage](http://www.gdal.org/drv_avce00.html)
- [Arc/Info Generate](http://www.gdal.org/drv_arcgen.html)				
- [Atlas BNA](http://www.gdal.org/drv_bna.html)				
- [AutoCAD DWG](http://www.gdal.org/drv_dwg.html)				
- [AutoCAD DXF](http://www.gdal.org/drv_dxf.html)				
- [CartoDB](http://www.gdal.org/drv_cartodb.html)				
- [Comma Separated Value (.csv)](http://www.gdal.org/drv_csv.html)				
- [CouchDB / GeoCouch](http://www.gdal.org/drv_couchdb.html)				
- [Cloudant / CouchDB](http://www.gdal.org/drv_cloudant.html)				
- [Czech Cadastral Exchange Data Format](http://www.gdal.org/drv_vfk.html)				
- [DODS/OPeNDAP](http://www.gdal.org/drv_dods.html)				
- [EDIGEO](http://www.gdal.org/drv_edigeo.html)				
- [ElasticSearch](http://www.gdal.org/drv_elasticsearch.html)				
- [ESRI FileGDB](http://www.gdal.org/drv_filegdb.html)				
- [ESRI Personal GeoDatabase](http://www.gdal.org/drv_pgeo.html)				
- [ESRI ArcSDE](http://www.gdal.org/drv_sde.html)				
- [ESRI Shapefile](http://www.gdal.org/drv_shapefile.html)				
- [FMEObjects Gateway](http://www.gdal.org/drv_fme.html)				
- [GeoJSON](http://www.gdal.org/drv_geojson.html)				
- [Géoconcept Export](http://www.gdal.org/drv_geoconcept.html)				
- [Geomedia .mdb](http://www.gdal.org/drv_geomedia.html)				
- [GeoPackage](http://www.gdal.org/drv_geopackage.html)				
- [GeoRSS](http://www.gdal.org/drv_georss.html)				
- [Google Fusion Tables](http://www.gdal.org/drv_gft.html)				
- [Google Maps Engine](http://trac.osgeo.org/gdal/wiki/GMEDriver)				
- [GML](http://www.gdal.org/drv_gml.html)				
- [GMT](http://www.gdal.org/drv_gml.html)				
- [GPSBabel](http://www.gdal.org/drv_gpsbabel.html)				
- [GPX](http://www.gdal.org/drv_gpx.html)				
- [GRASS Vector Format](http://www.gdal.org/drv_grass.html)				
- [GPSTrackMaker (.gtm, .gtz)](http://www.gdal.org/drv_gtm.html)				
- [Hydrographic Transfer Format](http://www.gdal.org/drv_htf.html)				
- [Idrisi Vector (.VCT)](http://www.gdal.org/drv_idrisi.html)				
- [Informix DataBlade](http://www.gdal.org/drv_idb.html)				
- [INTERLIS](http://www.gdal.org/drv_ili.html)				
- [INGRES](http://www.gdal.org/drv_ingres.html)				
- [JML](http://www.gdal.org/drv_jml.html)				
- [KML](http://www.gdal.org/drv_kml.html)				
- [LIBKML](http://www.gdal.org/drv_libkml.html)				
- [Mapinfo File](http://www.gdal.org/drv_mitab.html)				
- [Microstation DGN](http://www.gdal.org/drv_dgn.html)				
- [Access MDB (PGeo and Geomedia capable)](http://www.gdal.org/drv_dgn.html)				
- [Memory](http://www.gdal.org/drv_dgn.html)				
- [MySQL](http://www.gdal.org/drv_mysql.html)				
- [NAS ALKIS](http://www.gdal.org/drv_nas.html)				
- [Oracle Spatial](http://www.gdal.org/drv_oci.html)				
- [ODBC](http://www.gdal.org/drv_odbc.html)				
- [MS SQL Spatial](http://www.gdal.org/drv_mssqlspatial.html)				
- [Open Document Spreadsheet](http://www.gdal.org/drv_ods.html)				
- [OGDI Vectors (VPF, VMAP, DCW)](http://www.gdal.org/drv_ogdi.html)				
- [OpenAir](http://www.gdal.org/drv_openair.html)				
- [ESRI FileGDB](http://www.gdal.org/drv_openfilegdb.html)				
- [OpenStreetMap XML and PBF](http://www.gdal.org/drv_openfilegdb.html)				
- [PCI Geomatics Database File](http://www.gdal.org/frmt_pcidsk.html)				
- [Geospatial PDF](http://www.gdal.org/frmt_pdf.html)				
- [PDS](http://www.gdal.org/drv_pds.html)				
- [PostgreSQL SQL dump](http://www.gdal.org/drv_pgdump.html)				
- [PostgreSQL/PostGIS](http://www.gdal.org/drv_pg.html)				
- EPIInfo .REC				
- [S-57 (ENC)](http://www.gdal.org/drv_s57.html)				
- [SDTS](http://www.gdal.org/drv_sdts.html)				
- [SEG-P1 / UKOOA P1/90](http://www.gdal.org/drv_segukooa.html)				
- [SEG-Y](http://www.gdal.org/drv_segukooa.html)				
- [Selafin/Seraphin format](http://www.gdal.org/drv_selafin.html)				
- [Norwegian SOSI Standard](http://trac.osgeo.org/gdal/ticket/3638)				
- [SQLite/SpatiaLite](http://www.gdal.org/drv_sqlite.html)				
- [SUA](http://www.gdal.org/drv_sqlite.html)				
- [SVG](http://www.gdal.org/drv_svg.html)				
- [Storage and eXchange Format](http://www.gdal.org/drv_sxf.html)				
- [UK .NTF](http://www.gdal.org/drv_ntf.html)				
- [U.S. Census TIGER/Line](http://www.gdal.org/drv_ntf.html)				
- [VRT Virtual Datasource](http://www.gdal.org/drv_vrt.html)				
- [OGC WFS (Web Feature Service)](http://www.gdal.org/drv_wfs.html)				
- [MS Excel format](http://www.gdal.org/drv_xls.html)				
- [MS Office Open XML spreadsheet](http://www.gdal.org/drv_xlsx.html)				
- [X-Plane/Flightgear aeronautical data](http://www.gdal.org/drv_xplane.html)			
- [Walk](http://www.gdal.org/drv_walk.html)				
- [WAsP .map format](http://www.gdal.org/drv_wasp.html)		


> %!IMPORTANT NOTE!% Some of these formats have external dependencies and may require additional binaries which are not included in MapSurfer.NET package.	


## Configuration

In MapSurfer.NET, **OGR** data source provider operates with the following configuration parameters:

Parameter Name | Value Type | Description | Required
------------ | ------------- | ------------- | -------------
File | String | Determines a path to the the data source. The path can also be relative to the directory where map project is stored. | Yes
LayerName | String | Determines the name of a layer. | Yes
LayerIndex | Integer | A positive integer value greater or equal 0 indicating the index of the layer. This parameter is used only when LayerName is not given.| Yes/No
