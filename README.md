[![](https://img.shields.io/nuget/v/Soenneker.SkipMissedRuns.svg?style=for-the-badge)](https://www.nuget.org/packages/Soenneker.SkipMissedRuns/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.skipmissedruns/main.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.skipmissedruns/actions/workflows/main.yml)
[![](https://img.shields.io/nuget/dt/Soenneker.SkipMissedRuns.svg?style=for-the-badge)](https://www.nuget.org/packages/Soenneker.SkipMissedRuns/)

# Soenneker.SkipMissedRuns
### A tiny Hangfire library to exclude recurring jobs from triggering on startup if they've been missed (because time has passed)

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