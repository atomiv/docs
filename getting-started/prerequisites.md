# Prerequisites

In order to be able to use Optivem Framework, please ensure you have the following prerequisites:

* .NET Core 3.1
* Visual Studio 2019
* SQL Server 2017

## .NET Core 3.1

Ensure that you have installed the current recommended .NET Core version:

1. Go to [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)
2. Click on "Download .NET Core SDK"
3. Run the installer with default options
4. Restart your computer

## Visual Studio 2019

Ensure that you have installed the latest version of Visual Studio:

1. Go to [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/)
2. In the "Visual Studio 2019" section, see the "Community" section and click on "Free download"
3. Run the installer with the default options
4. Ensure that you have installed the components "ASP.NET and web development"

## SQL Server 2017

Ensure that you have installed the latest version of SQL Server:

1. Go to [https://www.microsoft.com/en-us/sql-server/sql-server-downloads](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
2. Go the the "Developer" edition and click on "Download now"
3. Run the installer with the default options

Then after that, install the latest version of SQL Server Management Studio \(SSMS\):

1. Go to [https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms)
2. In the "Download SSMS" section, click on "Download SQL Server Management Studio \(SSMS\)"
3. Run the installer with the default options

## .NET Tools

Ensure that you have installed .NET EF tools:

1. Run Visual Studio
2. Open the Package Manager Console
3. Run the following command:

```text
PM> dotnet tool install --global dotnet-ef
```

