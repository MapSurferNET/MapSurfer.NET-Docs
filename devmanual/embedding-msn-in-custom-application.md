### Embedding MapSurfer.NET in a custom application ###

The MapSurfer.NET API let you embed the framework into your custom application or web service. In order to start using the MapSurfer.NET API runtime assemblies, you need to reference them to your application. These assemblies can be found either in a folder where you installed the framework (e.g., **C:\Program Files\MapSurfer.NET\1.16.2\Core**) or in a folder of [NuGet](http://www.nuget.org/packages?q=mapsurfer.net)'s packages. 

#### Referencing and Loading Assemblies ####

In order to start using MapSurfer.NET in your application, you need to accomplish several steps that are given below. 

> !!Step 1!! Reference at least the assemblies **GeoAPI.dll**, **MapSurfer.Core.dll**, **MapSurfer.Geometries.dll**, **MapSurfer.System.dll** and set **Copy Local** properties to **False**. 

<center></center>
> !!Step 2!! Link two files **AssemblyLoader.cs** and **MSNUtility.cs** to your project. These files are contained either in the SDK samples (see **C:\Program Files\MapSurfer.NET\1.16.2\SDK**) or in [MapSurfer.NET Samples](http://www.nuget.org/packages/MapSurfer.NET.Samples/) NuGet package. 

<center></center>
> !!Step 3!! Add two lines of code (see example below) to the entry point (main) of your application. 

```cs
[STAThread]
static void Main()
{
    // Register AssemblyLoader for the current domain.
    MapSurfer.Utilities.AssemblyLoader.Register(AppDomain.CurrentDomain);

    // Initialize plugins (data source providers, rendering backends, etc.), expression types, unicode tables, etc.
    MapSurfer.Utilities.CoreUtility.Initialize();

    Application.EnableVisualStyles();
    Application.SetCompatibleTextRenderingDefault(false);
    Application.Run(new MainForm());
} 
```

> !!Step 4!! AssemblyLoader class automatically finds and loads MapSurfer.NET assemblies. However, in some cases it can not explicitly resolve required assemblies. As a result, you can receive an exception as:


```cs
An unhandled exception of type 'System.IO.FileNotFoundException' occurred in MyApplication.exe Additional information: Could not load file or assembly 'MapSurfer.Core, Version=1.162.5503.41504, Culture=neutral, PublicKeyToken=null' or one of its dependencies. The system cannot find the file specified.
```

This exception is thrown in two cases. Namely, MapSurfer.NET is not installed on the machine or installed for another user, i.e. no entry in the registry. To solve this issue, you can specify in Application Settings a path to the folder with MapSurfer.NET assemblies. An example below shows how to provide a path to assemblies from a NuGet package. 

```xml
<configuration>
    <startup>
       <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
    </startup>
    <appSettings>
       <add key="MapSurfer.InstallPath" value="C:\MyApplication\packages\MapSurfer.NET.Core.1.16.2\lib\net45\"/>
    </appSettings>
</configuration> 
```

#### Using MapViewer Control

MapSurfer.NET MapViewer is a user interface control that depicts a map or allows panning and zooming of a map. The following steps show how to embed MapViewer Control in a desktop application. 

> !!Step 1!! Install MapSurfer.NET UI package.

<center></center>
> !!Step 2!! Add three references to your project such as **MapSurfer.Windows.Forms.dll**, **NetGraphics32.Drawing.dll**, **NetGraphics32.Windows.Forms.dll** and set **Copy Loca** property to **True**. 

<center></center>
> !!Step 3!! Copy the entire folder **Native.x64** (or **Native.x86** respectively) containing dynamic libraries to the directory with an executable file of your application. 

<center></center>
Please refer to MapSurfer.NET Samples package that contains a ready-to-use demo application. 
<center></center>
> %!IMPORTANT IMPORTANT:!% At the moment MapViewer Control is only supported on Windows operating system.
