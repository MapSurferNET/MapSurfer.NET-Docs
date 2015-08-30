# Frequently Asked Questions

This page provides answers to questions that are frequently asked by users.

## General Questions 

- [What is MapSurfer.NET?](#What)
- [What platforms are supported by the framework?](#WhatOS)
- [What is required to run MapSurfer.NET?](#WhatRequirements)
- [Which version should I use?](#WhichVersion)
- [Are the builds of previous releases still available somewhere?](#PreviousBuilds)
- [Do I need to install GDAL to run MapSurfer.NET?](#GDALInstall)
- [What to do if MapSurfer.NET craches?](#WhatTodoIfCrashes)
- [What is the performance of MapSurfer.NET in comparison to other existing toolkits?](#WhatIsPerformance)
- [How can I generate a tile cache using my map style?](#GenTileCache)
- [How can I publish a web map service?](#PublishWebService)

## Styling 

- [Where can one find sample projects with map styles?](#WhereSampleProjects)
- [I have map styles in SLD format. Is it possible to use them in MapSurfer.NET?](#SLDStyles)
- [Can I produce cartographically plausible labeling?](#Labeling)

## Development 

- [Can I embed the framework into my application?](#CanEmbed)
- [What is the quickest way to start using MapSurfer.NET assemblies?](#NuGet)
- [I want to develop an application using MapSurfer.NET, where can I find code samples?](#WhereCodeSamples)

## General Questions 
>%!INFO!% <strong id="What">What is MapSurfer.NET?</strong>

MapSurfer.NET is a free, modern and advanced framework for rendering and publishing maps to the web. This framework has a functionality which is very similar to other well-known open source and proprietary software packages such as MapServer, GeoServer, Mapnik or ArcGIS. MapSurfer.NET is written in C# and provides the whole power of the .NET Framework to solve labour-intensive and time-consuming cartographic tasks.

>%!INFO!% <strong id="WhatOS">What platforms are supported by the framework?</strong>

At the moment, MapSurfer.NET can run on Windows and Linux platforms. The support of other operating systems is a high priority task. Thanks to Mono project which makes it potentially possible.

>%!INFO!% <strong id="WhatRequirements">What is required to run MapSurfer.NET?</strong>

MapSurfer.NET requires [.NET Framework 4.5](http://www.microsoft.com/en-us/download/details.aspx?id=30653).

>%!INFO!% <strong id="PreviousBuilds">Are the builds of previous releases still available somewhere?</strong>

Yes, although they are not officially supported. The builds of previous releases for different platforms is given on [this page](/releases).

>%!INFO!% <strong id="GDALInstall"> [Do I need to install GDAL to run MapSurfer.NET?</strong>

In general, you don't have to. GDAL is only needed to work with [GDAL](usermanual/data_sources/raster/gdal.md) and [DEM](usermanual/data_sources/raster/dem.md) data sources.

>%!INFO!% <strong id="WhichVersion">Which version should I use?</strong>

It is highly recommended to use the latest stable release of the framework. More detailed information about available [releases](release-notes.md), you can get on Downloads page.

>%!INFO!% <strong id="WhatTodoIfCrashes">What to do if MapSurfer.NET craches?</strong>

You can either contact us via e-mail (see contact information at the bottom of the page) or post a question on the [forum](https://groups.google.com/forum/#!forum/mapsurfer-net). In both cases, some details or a crash log would be very helpful to resolve an issue.

>%!INFO!% <strong id="WhatIsPerformance">What is the performance of MapSurfer.NET in comparison to other existing toolkits?</strong>

Our [benchmarks](http://mapsurfernet.com/blog/benchmarking-mapping-toolkits-in-tile-seeding) show that MapSurfer.NET is as fast as MapServer and Mapnik written in C/C++.

>%!INFO!% <strong id="GenTileCache">How can I generate a tile cache using my map style?</strong>

You can use either [MapSurfer.NET Studio](/usermanual/tools/msnstudio/export-tile-cache.md) or [MSNMapGen](/usermanual/tools/msnmapgen.md) utility to accomplish this task.

>%!INFO!% <strong id="PublishWebService">How can I publish a web map service?</strong>

A map can be published through a web map service using either [IIS](usermanual/web_services/running-webservice-using-iis75) or a [self-hosting console application](usermanual/web_services/self-hosting-webservice-nancy). For developers, we recommend to look at [this](https://github.com/MapSurferNET/MapSurfer.NET-Web) github repo.


## Styling 

>%!INFO!% <strong id="WhereSampleProjects">Where can one find sample projects with map styles?</strong>

A collection of sample projects is available on [GitHub](https://github.com/MapSurferNET/MapSurfer.NET-Examples).

>%!INFO!% <strong id="SLDStyles">I have map styles in SLD format. Is it possible to use them in MapSurfer.NET?</strong>
 
Yes, it is. [MapSurfer.NET Studio](/usermanual/tools/msnstudio/export-import-styles.md) allows to import or export SLD styles into/from a native format. 

>%!INFO!% <strong id="Labeling">Can I produce cartographically plausible labeling?</strong>

You sure can. MapSurfer.NET equipped with an advanced labeling engine that allows producing map lettering of a superior cartographic quality comparable to hand-drawn maps. For more information, check out [this article](/usermanual/labeling/index.md).

## Development 

>%!INFO!% <strong id="CanEmbed">Can I embed the framework into my application?</strong>

Yes, you can. See a [developer guide](devmanual/embedding-msn-in-custom-application.md) about embedding MapSurfer.NET into a custom application.

>%!INFO!% <strong id="NuGet">What is the quickest way to start using MapSurfer.NET assemblies?</strong>

It is highly recommended to use [NuGet packages](https://www.nuget.org/packages?q=mapsurfer.net) in the development environment. 

>%!INFO!% <strong id="WhereCodeSamples">I want to develop an application using MapSurfer.NET, where can I find code samples?</strong>

An official collection of code samples is available on [GitHub]. (https://github.com/MapSurferNET/MapSurfer.NET-CodeSamples)
