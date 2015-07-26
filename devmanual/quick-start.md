# Quick Start

There are a couple of packages for MapSurfer.NET available on [GitHub](https://www.nuget.org/packages?q=mapsurfer.net).
To start developing, you need to add some assemblies into your application. It can be done by typing the following command into the Package Manager Console window:

>%!COMMAND-LINE!% PM> Install-Package MapSurfer.NET

Next, it is required to reference two source files [AssemblyLoader.cs](https://github.com/MapSurferNET/MapSurfer.NET-CodeSamples/blob/master/Common/AssemblyLoader.cs) and 
[MSNUtility.cs](https://github.com/MapSurferNET/MapSurfer.NET-CodeSamples/blob/master/Common/MSNUtility.cs) that help to detect
a proper version of the framework and load its core assemblies and plugins.

```cs
 static Program()
 {
    // Register assembly loader
    // Uncomment if needed
    string version = MSNUtility.TryDetectInstalledVersion();
    MSNUtility.SetCurrentMSNVersion(version);
    AssemblyLoader.Register(AppDomain.CurrentDomain, version);
 }
```

```cs
    static void Main(string[] args) 
    {
      // Initialize internals 
      CoreUtility.Initialize();

      string mapPath = @"C:\Users\Public\Documents\MapSurfer.NET\2.1\Samples\Projects\Bremen.msnpx";// @"\map\example.msnpx";
      // Load map from file and initialize data source providers.
      using (Map map = Map.FromFile(mapPath, true))
      {
        map.Size = new SizeF(600, 600);
        map.ZoomToFullExtent();

        using (IRenderer renderer = RendererManager.CreateDefaultInstance())
        {
          using (RenderSurface surface = RenderContext.Render(map, renderer))
          {
            surface.Save(@"D:\Temp\000.png", new object[] { ImageFormat.Png });
          }
        }
      }
    }
```
