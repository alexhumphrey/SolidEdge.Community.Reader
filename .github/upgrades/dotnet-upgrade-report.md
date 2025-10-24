# .NET 9.0 Upgrade Report

## Project target framework modifications

| Project name  | Old Target Framework    | New Target Framework    |
|:-----------------------------------------------|:-----------------------:|:-----------------------:|
| SolidEdge.Community.Reader.csproj             | net48          | net9.0 |
| QA.csproj     | net48       | net9.0      |

## NuGet Packages

| Package Name  | Old Version | New Version | Description       |
|:-------------------------------------------|:-----------:|:-----------:|-----------------------------------------------|
| SharpZipLib   | 0.86.0  | 1.4.2       | Security vulnerability fix        |
| log4net             | 2.0.3       | 3.2.0       | Updated for .NET 9.0 compatibility    |
| System.Configuration.ConfigurationManager | -     | 9.0.10    | Added for configuration support               |
| System.Drawing.Common        | -    | 9.0.0       | Added to replace System.Drawing references   |

## Project feature upgrades

### SolidEdge.Community.Reader.csproj

Here is what changed for the project during upgrade:

- Project converted from legacy .NET Framework format to modern SDK-style project format
- Target framework upgraded from .NET Framework 4.8 to .NET 9.0
- Removed legacy assembly references (Microsoft.CSharp, System, System.Core, System.Data, System.Data.DataSetExtensions, System.Drawing, System.Xml, System.Xml.Linq) - these are now included by default in .NET 9.0
- Updated SharpZipLib package from 0.86.0 to 1.4.2 to fix security vulnerability
- Added System.Drawing.Common package (9.0.0) to maintain System.Drawing functionality that was removed from the core framework

### QA.csproj

Here is what changed for the project during upgrade:

- Project converted from legacy .NET Framework format to modern SDK-style project format  
- Target framework upgraded from .NET Framework 4.8 to .NET 9.0
- Removed legacy assembly references (Microsoft.CSharp, System, System.configuration, System.Core, System.Data, System.Data.DataSetExtensions, System.Drawing, System.Xml, System.Xml.Linq) - these are now included by default in .NET 9.0
- Updated log4net package from 2.0.3 to 3.2.0 for .NET 9.0 compatibility
- Added System.Configuration.ConfigurationManager package (9.0.10) to replace the removed System.configuration reference

## Next steps

- Consider running tests to ensure functionality is preserved after the upgrade
- Review any application configuration files that may need updates for .NET 9.0
- Consider updating any CI/CD pipelines to use .NET 9.0 SDK
- Review and update documentation to reflect the new .NET 9.0 target framework
