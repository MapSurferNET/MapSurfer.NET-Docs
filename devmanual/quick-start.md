#  Quick Start

### Installation
There are a couple of packages for MapSurfer.NET available on [GitHub](https://www.nuget.org/packages?q=mapsurfer.net).
To start developing, you need to add some assemblies into your application. It can be done by typing the following command into the Package Manager Console window:

>%!COMMAND-LINE!% PM> Install-Package MapSurfer.NET.Core 

### Configuration

Next, it is required to reference two source files [AssemblyLoader.cs](https://github.com/MapSurferNET/MapSurfer.NET-CodeSamples/blob/master/Common/AssemblyLoader.cs) and 
[MSNUtility.cs](https://github.com/MapSurferNET/MapSurfer.NET-CodeSamples/blob/master/Common/MSNUtility.cs) that help to detect a proper version of the framework and load its core assemblies and plugins.

Then, in the entry point of your application, add the following lines of code:

```cs
 static Program()
 {
    // Register assembly loader
    string version = MSNUtility.TryDetectInstalledVersion();
    MSNUtility.SetCurrentMSNVersion(version);
    AssemblyLoader.Register(AppDomain.CurrentDomain, version);
 }
```

Since several versions of MapSurfer.NET framework can be installed on a machine at the same time, the function MSNUtility.SetCurrentMSNVersion is specially designed to setup which of those versions is going to be used.
Note, calling methods of MSNUtility and AssemblyLoader classes needs to be done before you call any other method that contains references to MapSurfer.NET classes. Otherwise, a required assembly won't be found as your application is not aware where MapSurfer.NET's assemblies are located.

Before working with MapSurfer.NET, initialize it by calling CoreUtility.Initialize() method. This function should be called only once.

### Working with the framework

This section presents and example that shows how you can render a map and save it as a raster image.

```cs
 static void Main(string[] args) 
 {
   // Initialize internals of the framework
   CoreUtility.Initialize();

   // A path to a file containing map styles.
   string mapPath = @"C:\Users\Public\Documents\MapSurfer.NET\2.1\Samples\Projects\Bremen.msnpx";
   // Load map from a file with styles and initialize data source providers.
   using (Map map = Map.FromFile(mapPath, true))
   {
     // Set the size of the map in pixels.
     map.Size = new SizeF(600, 600);
     // Set the scale and the extent of the map.
     map.ZoomToFullExtent();

     // Create an instance of the default renderer, GDI in our case.
     using (IRenderer renderer = RendererManager.CreateDefaultInstance())
     {
       // Render map to a RenderSurface
       using (RenderSurface surface = RenderContext.Render(map, renderer))
       {
         // Save the content of the surface into an image file, by defining its format (e.g., BMP, GIF, PNG, etc.)
         surface.Save(@"D:\Temp\000.png", new object[] { ImageFormat.Png });
       }
     }
   }
 }
```

> %!IMPORTANT IMPORTANT:!% Note, the given example requires at least MapSurfer.NET v.2.1. Older versions of the framework might have a distinct API.
