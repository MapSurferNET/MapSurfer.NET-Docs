### Using a Windows Installer ###

In order to install MapSurfer.NET on a Windows System, you need to use [Windows Installer](http://mapsurfernet.com/downloads#tab-win). Step belows describe how to use the installer.

> %!IMPORTANT IMPORTANT:!% Please note .NET Framework 4.5 should be installed on your machine, since that is a necessary prerequisite to run >MapSurfer.NET. You can download the .NET Framework directly from an [official website](http://www.microsoft.com/en-us/download/details.aspx?id=30653) and install it manually or use Windows Installer.
Windows 8 and Windows Server 2012 include the .NET Framework 4.5. Therefore, you don't have to install this software on those operating systems. 

<center></center>
> !!Step 1!! Run windows installer (for example, MapSurfer.NET-1.16-setup.exe) to re-install or to make an initial installation.

<center></center>
> !!Step 2!! First choose the language of the installation program, then welcome screen shows up.

<center>![](/media/images/1-Setup_Welcome.png)</center>

> !!Step 3!! After you clicked **Next**, you will see a dialog with [License](/license.md) agreement, which you need to carefully read. 

<center>![](/media/images/2-Setup_License.png)</center>

Click I **Agree** if you accept the agreement.

> !!Step 4!! On the next page, you specify for which user this framework will be installed. 

<center>![](/media/images/3-Setup_InstallOptions.png)</center>

Click **Next** to proceed.

> !!Step 5!! Next, the Installation Wizard provides a single feature tree to install dependencies (.NET Framework, [GDAL](http://www.gdal.org/), [Microsoft VC++ Redistributable](http://www.microsoft.com/en-us/download/details.aspx?id=30679) package), different components of MapSurfer.NET (e.g., renderers, data source and tile cache providers), SDK samples and templates for web services. 

<center>![](/media/images/4-Setup_Components.png)</center>

Click **Next** to continue.

> !!Step 6!! In the Destination Folder page, specify location where you want to install MapSurfer.NET. Make sure that you have enough permissions for a selected folder.

<center>![](/media/images/5-Setup_InstallLocation.png)</center>

Click **Next** to continue.

> !!Step 7!! Select the Start menu folder in which to create the program's shortcuts. 

<center>![](/media/images/6-Setup_StartMenuFolder.png)</center>

Click **Install** to setup the framework.

> !!Step 8!! Then, a page with installation progress is shown.

<center>![](/media/images/7-Setup_Installing.png)</center>

> !!Step 9!! As soon as all necessary files are installed, Installation Complete page shows up. 

<center>![](/media/images/8-Setup_InstallationComplete.png)</center>

Well done! MapSurfer.NET is now successfully installed.


### Manual Installation ###

This section contains instructions for manually installing MapSurfer.NET on Windows.

Assume that you have a copy of a previously installed MapSurfer.NET in a folder "C:\MapSurfer.NET". In order to help MapSurfer.NET to find and load all dependencies, we need to tell where to start searching them. This can be accomplished using Registry Editor (Regedit.exe):

> !!Step 1!! Click **Start**, click **Run**, type regedit in the Open box, and then click **OK** (or press Enter).
 
<center></center>
> !!Step 2!! If prompted by User Account Control, click **Yes** to open the Registry Editor. 

<center></center>
> !!Step 3!! Open the registry key **HKEY_LOCAL_MACHINE\SOFTWARE\**, if you installing MapSurfer.NET for all users. Otherwise, open the **HKEY_CURRENT_USER\SOFTWARE\** key (folder).

<center></center>
> !!Step 4!! Create a new subkey MapSurfer.NET such as **HKEY_LOCAL_MACHINE\SOFTWARE\MapSurfer.NET\**. 

<center></center>
> !!Step 5!! Create a new subkey **HKEY_LOCAL_MACHINE\SOFTWARE\MapSurfer.NET\VERSION**, where **VERSION** is the [version of the framework](versioning.md).
 
<center></center>
> !!Step 6!! Create a new value **InstallPath** with the following data "C:\MapSurfer.NET". The result should look like:

<center>![](/media/images/9-Setup_Registry.png)</center>

 
