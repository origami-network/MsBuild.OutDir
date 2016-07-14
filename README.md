# MsBuild.OutDir

MsBuild targets that allow control publishing projects to dedicated folder through `OutDir` property.

The intention is to help extract requred files from build process to dedicated folder,
by reporducing Web Application project type behaviour.

In Visual Studio IDE it works transparently and do not change default behaviour.

## Install

In order to install it from NuGet Gallery:
```
PM> Install-Package MsBuild.OutDir
```

**NOTE:** Do not use this package in Web Application project while it already have this functionality.

## Usage

When run in continous integration process execute MsBuild with `OutDir` paramter
```
msbuild example.sln /property:OutDir=C:\Some\Custom\Path
```

As result of build the `C:\Some\Custom\Path` will contains folders with `_Published` prefix. By default it will be:
 * `_Published`**`Libraries`** - for project producing assembly libraries.
 * `_Published`**`Applications`** - for project producing executable libraries.
 * `_PublishedWebApplications` - for Web Application projects as it is standard behaviour.

## License

MsBuild.OutDir set of packages is released under the [MIT license](http://www.opensource.org/licenses/MIT).