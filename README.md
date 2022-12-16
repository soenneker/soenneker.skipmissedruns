[![Build Status](https://dev.azure.com/soenneker/soenneker.skipmissedruns/_apis/build/status/soenneker.soenneker.skipmissedruns?branchName=main)](https://dev.azure.com/soenneker/soenneker.SkipMissedRuns/_build/latest?definitionId=1&branchName=main)
[![NuGet Version](https://img.shields.io/nuget/v/Soenneker.SkipMissedRuns.svg?style=flat)](https://www.nuget.org/packages/Soenneker.SkipMissedRuns/)

# Soenneker.SkipMissedRuns
### A tiny Hangfire library to exclude recurring jobs from triggering on startup if they've been missed (because time has passed).

## Installation

```
Install-Package Soenneker.Skipmissedruns
```

## Usage

Make sure to place on the interface if you're using the interface as the Hangfire activator.

```csharp
public interface IHourlyRecurringJob
{
    [SkipMissedRuns]
    Task RunHourly();
}
```