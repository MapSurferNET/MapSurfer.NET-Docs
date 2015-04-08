## Running a Web Service using IIS 7.5 ##

This tutorial shows how to publish a map to the web using Internet Information Services (IIS).  

Suppose you have a project file **Bremen.msnpx** (see [Examples](https://github.com/MapSurferNET/MapSurfer.NET-Examples)) with your custom map styles. In order to publish it, you need to perform the following steps:

> !!Step 1!! [Install IIS 7.5](http://www.iis.net/learn/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7).

<center></center>
> !!Step 2!! Create a directory **MSNWebService** in **C:\inetpub** (location and folder name is optional).

<center></center>
> !!Step 3!! Copy the template of a web service from the folder **{MapSurfer.NET Path}\{Version}\Web\MapService** or **{MapSurfer.NET Path}\{Version}\Web\ASP.NET** (for versions greater than 2.0) to the folder **MSNWebService**.   

<center></center>
> !!Step 4!! Open **Internet Information Services (IIS) Manager**.

<center></center>
> !!Step 5!! Create a new **Application Pool** with the name **MSNPool**. For this pool, set .NET CLR version to v4.0.30319.  

<center></center>
> !!Step 6!! Go to **Advanced Settings**… of the application pool.

<center></center>
> !!Step 7!! In **Identity** field select an account that has enough rights. To avoid further problems with the permissions, it is recommended to select **NetworkService** account.  

<center></center>
> !!Step 8!! Add new website with the name **MSNWebService** and **MSNPool**. Specify **Physical path** as **C:\inetpub\MSNWebService**. Set port, for example, to **8001**.  

<center></center>
> !!Step 9!! In the **web.config** file, edit the following parameters as:

```xml
<appSettings>   
   <!-- MapSurfer.NET version -->   
   <add key="MapSurfer.Version" value="1.15" /> 
   <- Set your installed version   
   <!-- Map service log file name -->   
   <add key="MapSurfer.ServiceLogFileName" value=" C:\inetpub\MSNWebService\Logs\ServiceLog.txt" />   
   <!-- Map service settings file name -->   
   <add key="MapSurfer.ServiceSettingsFileName" value="C:\inetpub\MSNWebService\Service1.msnwss" /> 
</appSettings>
```  

> !!Step 10!! Open **Service1.msnwss** file, change elements **ConfigFileName** and **LogFileName** as follows: 


```xml
<?xml version="1.0" encoding="utf-8"?>
<WebServicesSettings xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Services>
   <WebServiceSettingItem>
     <Description />
     <Enabled>true</Enabled>
     <ConfigFileName>C:\inetpub\MSNWebService\tms_config.xml</ConfigFileName> <- Set full path
     <LoggingEnabled>true</LoggingEnabled>
     <LogFileName> C:\inetpub\MSNWebService\Logs\ErrorLog_{0}.txt</LogFileName> <- Set full path
     <LogLevel>Error</LogLevel> <- to log more events use Verbose instead of Error.
     <ServiceName>WMTS Server</ServiceName>
     <ServiceType>WMTS</ServiceType>
     <TraceLoggingEnabled>true</TraceLoggingEnabled>
   </WebServiceSettingItem>
 </Services>
</WebServicesSettings> 
```  

> !!Step 11!! Change the settings for **TiledMap** element in **tms_config.xml** as:

```xml
…
<TileMap href="http://localhost:8001/tms.ashx">      <- your port number and .ashx handler
   <DataContext>
      <RendererName>GDI</RendererName>
      <StylesFileName>C:\Users\Public\Documents\MapSurfer.NET\1.15\Samples\Projects\Bremen.msnpx</StylesFileName>
      <UsePerformanceCounters>true</UsePerformanceCounters>
   </DataContext>
…
   <TileCache>
      <Name>MetaTileDisk</Name>
      <Parameters>
        <Parameter>
           <Name>Path</Name>
           <Value>E:\TileCache\Map</Value>
… 
```  

Note that this file can contain several tile maps with different urls. For each map, you need to specify href and create a corresponding .ashx handler.

<center></center>
> !!Step 12!! Set **Full Control** permissions to the folder **C:\inetpub\MSNWebService\Logs** for the web service user.

<center></center>
> !!Step 13!! To make sure the service is hosted correctly, open your browser and type [localhost:8001/tms.ashx?x=0&y=0&z=0](localhost:8001/tms.ashx?x=0&y=0&z=0). 