## Hosting Web Service in Console Application using Nancy ##

This tutorial outlines basic steps needed to run a web map service using a console application based on [Nancy](http://nancyfx.org/).  

Suppose you have a project file **Bremen.msnpx** (see [Examples](https://github.com/MapSurferNET/MapSurfer.NET-Examples)) with your custom map styles. The steps given below describe how to publish this map:

> !!Step 1!! Open folder **..\MapSurfer.NET\2.0\Web\Nancy\Self-Hosting**. In this folder, you find **MSNNancySH.exe** application which we are going to run.

<center></center>
> !!Step 2!! Create a temp directory (for example, C:\Temp\MSNWS1)  

<center></center>
> !!Step 3!! In this folder, create a file named **mymap.config**. Edit this file by adding the following (see also MSNNancySH.exe.config as a template):

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <startup> <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5"/>
    </startup>

  <appSettings>
    <!-- The uri that the host will listen to. -->
    <add key="Nancy.Uri" value="http://localhost:8001"/>
    
    <!-- MapSurfer.NET version -->
    <add key="MapSurfer.Version" value="2.0"/>

    <!-- MapSurfer.NET installation path. This parameter should be used when MapSurfer.NET was not installed for everyone on the current machine and the service runs under the user which has not installed the framework. If this parameter is active then the parameter MapSurfer.Version is not taken into account.  -->
    <!--   <add key="MapSurfer.InstallPath" value="Your path" /> -->

    <!-- Map service name -->
    <add key="MapSurfer.ServiceName" value="MapSurfer.NET Web Map Service"/>
    <!-- Map service log file name -->
    <add key="MapSurfer.ServiceLogFileName" value="C:\Temp\MSNWS1\ServiceLog.txt"/>
    <!-- Map service settings file name -->
    <add key="MapSurfer.ServiceSettingsFileName" value="C:\Program Files\MapSurfer.NET\2.0\Web\Config\Service1.msnwss"/>
  </appSettings>
</configuration>

```  

<center></center>
> !!Step 4!! Open **C:\Program Files\MapSurfer.NET\2.0\Web\Config\Service1.msnwss** file, change elements **ConfigFileName** and **LogFileName** as follows: 


```xml
<?xml version="1.0" encoding="utf-8"?>
<WebServicesSettings xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Services>
   <WebServiceSettingItem>
     <Description />
     <Enabled>true</Enabled>
     <ConfigFileName>C:\Program Files\MapSurfer.NET\2.0\Web\Config\\tms_config.xml</ConfigFileName> <- Set full path
     <LoggingEnabled>true</LoggingEnabled>
     <LogFileName> C:\Temp\MSNWS1\Logs\ErrorLog_{0}.txt</LogFileName> <- Set full path
     <LogLevel>Error</LogLevel> <- to log more events use Verbose instead of Error.
     <ServiceName>WMTS Server</ServiceName>
     <ServiceType>WMTS</ServiceType>
     <TraceLoggingEnabled>true</TraceLoggingEnabled>
   </WebServiceSettingItem>
 </Services>
</WebServicesSettings> 
```  
<center></center>
> !!Step 5!! Change the settings for **TiledMap** element in **tms_config.xml** as:

```xml
…
<TileMap href="http://localhost:8001/tms.ashx">      <- your port number 
   <DataContext>
      <RendererName>GDI</RendererName>
      <StylesFileName>C:\Users\Public\Documents\MapSurfer.NET\2.0\Samples\Projects\Bremen.msnpx</StylesFileName>
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

Note that this file can contain several tile maps with different urls. You need to specify a href for each individual map.

<center></center>
> !!Step 6!! Run the command
>%!COMMAND-LINE!% MSNNancySH.exe -conf "C:\Temp\MSNWS1\mymap.config"

<center></center>
> !!Step 7!! To make sure the service is hosted correctly, open your browser and type [localhost:8001/tms.ashx?x=0&y=0&z=0](localhost:8001/tms.ashx?x=0&y=0&z=0). 