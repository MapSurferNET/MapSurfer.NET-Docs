### Using Installer Package ###

In order to install MapSurfer.NET on a Linux Operating System, you need to use [Linux Installer](http://mapsurfernet.com/downloads#tab-linux). Step belows describe how to use the installer.

> %!IMPORTANT IMPORTANT:!% Please note, Mono (.NET 4.5) should be installed on your machine, since this is a necessary prerequisite to run MapSurfer.NET. You can download the latest Mono directly from an [official website](http://www.mono-project.com/download/) and install it manually. 

<center></center>
> !!Step 1!! Assume that you want to install MapSurfer.NET into the folder **/usr/lib/MapSurfer.NET/1.16**. For that you need to run Linux installer (for example, MapSurfer.NET-1.16-setup.exe) using the following command: 

<center></center>
>%!COMMAND-LINE!% sudo mono MapSurfer.NET-1.16-setup.exe -path /usr/lib/MapSurfer.NET/1.16 

<center></center>
Once the installer has completed its job, four sub-folders such as Core, Samples, SDK and Web should be created. 

Well done! MapSurfer.NET is now successfully installed. 

### Manual Installation ###

This section contains instructions for manually installing MapSurfer.NET on Linux. 

Suppose you have a copy of a previously installed MapSurfer.NET in a folder **/usr/lib/MapSurfer.NET**. In order to help MapSurfer.NET to find and load all dependencies, we need to tell where to start searching them. This can be accomplished using Mono's registry, which is normally located in **/etc/mono/registry**. In this sub directory, sub keys are stored as sub folders, and values are stored in xml files with the name **values.xml**. The required registry settings can be stored either in **/etc/mono/registry/LocalMachine **(local machine-specific settings) or in **etc/mono/registry/CurrentUser** (user-specific settings). 

> !!Step 1!! Create a new sub-folder in **/etc/mono/registry/LocalMachine/software/mapsurfer.net/1.16**, where 1.16 is the [version](/docs/versioning) of the framework being installed.
 
<center></center>
> !!Step 2!! In the new folder, create a file named values.xml with the following content: 

<center></center>
```xml
<values>
   <value name="InstallPath" type="string">/usr/lib/MapSurfer.NET/1.16</value>
</values> 
```
