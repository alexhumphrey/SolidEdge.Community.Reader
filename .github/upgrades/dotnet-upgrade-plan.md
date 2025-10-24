# .NET 9.0 Upgrade Plan

## Execution Steps

Execute steps below sequentially one by one in the order they are listed.

1. Validate that a .NET 9.0 SDK required for this upgrade is installed on the machine and if not, help to get it installed.
2. Ensure that the SDK version specified in global.json files is compatible with the .NET 9.0 upgrade.
3. Upgrade SolidEdge.Community.Reader.csproj to .NET 9.0
4. Upgrade QA.csproj to .NET 9.0

## Settings

This section contains settings and data used by execution steps.

### Aggregate NuGet packages modifications across all projects

NuGet packages used across all selected projects or their dependencies that need version update in projects that reference them.

| Package Name       | Current Version | New Version | Description|
|:------------------------------------|:---------------:|:-----------:|:----------------------------------------------|
| log4net              |   2.0.3         |  3.2.0    | Incompatible with .NET 9.0           |
| SharpZipLib       |   0.86.0        |  1.4.2  | Security vulnerability         |

### Project upgrade details

This section contains details about each project upgrade and modifications that need to be done in the project.

#### SolidEdge.Community.Reader.csproj modifications

Project properties changes:
  - Project needs to be converted from legacy format to SDK-style
  - Target framework should be changed from `.NETFramework,Version=v4.8` to `net9.0`

NuGet packages changes:
  - SharpZipLib should be updated from `0.86.0` to `1.4.2` (*security vulnerability*)

#### QA.csproj modifications

Project properties changes:
  - Project needs to be converted from legacy format to SDK-style  
  - Target framework should be changed from `.NETFramework,Version=v4.8` to `net9.0`

NuGet packages changes:
  - log4net should be updated from `2.0.3` to `3.2.0` (*incompatible with .NET 9.0*)