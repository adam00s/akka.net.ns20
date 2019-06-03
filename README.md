## Motivation

This is adaptation of https://github.com/akkadotnet/akka.net to work for project compiled for dotnet standard 2.0, where there is problem with conflict of Serialization attribute.

## Build

Build it just as normal akka.net, but on master brunch (dev is not modified).

```
.\build.ps1 Nuget
```

Get needed NuGet packages from `bin/nuget` folder and put it in some folder in your solution, modify/create `nuget.config` to contains 

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <packageSources>
        <add key="MyLocalSharedSource" value="some\folder" /> <!-- can be relative path -->
    </packageSources>
</configuration>
```
-- More info at the end of https://stackoverflow.com/questions/10240029/how-do-i-install-a-nuget-package-nupkg-file-locally

In your solution go to NuGet manager, enable "prerelease" packages and select version with `...-?-custom` suffix.
