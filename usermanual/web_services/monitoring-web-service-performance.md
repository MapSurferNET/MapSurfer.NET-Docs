# Monitoring Web Service Performance

Performance plays an important role in running a successful web service. MapSurfer.NET provides several [performance counters](https://msdn.microsoft.com/en-us/library/fxk122b4%28v=vs.140%29.aspx) that you can use to monitor the execution of your web service.


## Web Map Tile Service (WMTS)

Performance counters that are related to a Web Map Tile Service can be found in **MapSurfer.NET WMTS** performance object. This object supports the performance counters listed in the following table.

Performance Counter | Description 
------------ | ------------- 
Metatiles Rendered/sec | The number of metatiles rendered per second.
Tiles Read from Cache/sec | The number of tiles per second read from a tile cache.
Tiles in Queue | The number of tiles in the queue that are waiting to be rendered.
Tiles Rendered/sec | The number of tiles rendered per second.
Total Metatiles Rendered | The total number of metatiles that have been rendered during the lifetime of the current Web service process. 
Total Tiles Deleted  | The total number of tiles that have been deleted during the lifetime of the current Web service process. 
Total Tiles Read from Cache | The total number of tiles that have been read from cache during the lifetime of the current Web service process. 
Total Tiles Rendered | The total number of tiles that have been rendered during the lifetime of the current Web service process. 
Total Tiles Updated | The total number of tiles that have been updated during the lifetime of the current Web service process. 

<center>![](/media/images/29-performance_counters_wmts.png)</center>
**Figure.** An example of performance counters chart.

## Web Map Service (WMS)

At the moment MapSurfer.NET does not provide any specific performance counters to monitor the performance of a Web Map Service. If you are hosting your application in [IIS](/usermanual/web_services/running-webservice-using-iis75.md), you can use default ASP.NET [performance counters](https://msdn.microsoft.com/en-us/library/fxk122b4%28v=vs.140%29.aspx).


> %!IMPORTANT IMPORTANT:!% Note that the user running a web service requires access rights to write the Performance counters.
