# WiX

This project just packages the official [WiX release binaries](http://wixtoolset.org/releases/) 
as [NuGet](http://www.nuget.org) packages for easier consumption.

Package version # will strictly follow the official release number. In cases where the 
NuGet package needs an update unrelated to the WiX release, we'll append a fourth revision 
digit. For example, [WiX stable v3.9 R2](https://wix.codeplex.com/releases/view/610859)
is [WiX package version 3.9.2.1](https://www.nuget.org/packages/WiX/3.9.2.1) since we 
tweaked the package to include a wix.props file that automatically resolves/overrides 
the WiX location and means you don't need to update a newly created WiX project in
Visual Studio at all.  

Pre-release versions are also avaialble, with a `-pre` suffix, such as [WiX v3.10.0.2103 Release](http://wixtoolset.org/releases/v3-10-0-2103/) packaged as [WiX package version 3.10.0.2103-pre](https://www.nuget.org/packages/WiX/3.10.0.2103-pre).

## Contributing

The process of publishing new versions of WiX is currently manual, so we appreciate 
contributors that need quicker releases. The process is straightforward:

1. Create a folder under the root named after the release version
2. Download the WiX binaries zip for the release inside it
3. Extract the zip to a `tools` subfolder
4. Copy the WiX.nuspec from one of the other versioned folders
5. Update the `<version>` element to match the downloaded version. 
   If it's not a stable release, append `-pre` suffix.
6. Commit all files and send a PR.

The PR will let us know there's a new version that needs publishing, and we'll push 
it as soon as it's merged.