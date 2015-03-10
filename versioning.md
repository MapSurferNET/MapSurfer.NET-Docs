This page contains explanation for version numbering used in MapSurfer.NET.

# Framework #


The versioning of the framework is sticked to the follwoing scheme:

>%!INFO Scheme:!%
>**major.minor.revision**   (Example: 1.16.2)

- major number designates releases that contain significant changes in the framework. These changes might break compatibility with previous versions. The major version changes very rarely.
- minor number is used for releases that introduce minor features, improvements or necessary bug fixes.
- revision number is used when minor bugs are fixed.

# .NET Assemblies #

The MapSurfer.NET's assemblies have different version numbering. Assembly's version consists of four numbers.

>%!INFO Scheme:!%
>**X.Y.D.S**   (Example: 1.162.5491.16601)

- X.Y are two numbers that present a version of the framework. The first number X corresponds to the major number of the framework's version. Y number are encoded values for minor and revision numbers. The minor number equals to the integer division Y/10. The revision number is the remainder of Y/10.
- D.S are an encoded date, where D is the number of days and S is the half of seconds since January 1, 2000.

An assembly with the version 1.162.5491.16601 is a part of MapSurfer.NET 1.16.2, which was released on 13.01.2015.
