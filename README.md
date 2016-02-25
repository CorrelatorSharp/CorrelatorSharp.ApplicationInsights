## What is this?

CorrelatorSharp.ApplicationInsights is an add-on for Microsoft Application Insights that enables support for [CorrelatorSharp](http://correlatorsharp.github.io).

## Get it


|   Where    |    What   |
|-------------|-------------|
| NuGet       | [CorrelatorSharp.ApplicationInsights](https://www.nuget.org/packages/CorrelatorSharp.ApplicationInsights/)
| Latest Build (master)      |   [![Build status](https://ci.appveyor.com/api/projects/status/9pcvgwmtjvk064kw/branch/master?svg=true)](https://ci.appveyor.com/project/CorrelatorSharp/correlatorsharp-applicationinsights/branch/master)  |


## Using it

```csharp
TelemetryConfiguration.Active.TelemetryInitializers.Add(
		new CorrelatorSharp.ApplicationInsights.OperationIdTelementryInitializer());
```

This will initialize the following properties in the Application Insights telemetry:

* Operation Id (built-in property)
* Operation Name (built-in property)
* `ParentOperationId`

**IMPORTANT NOTE:** You need to remove the built-in Application Insights operation id telemetry initializer - otherwise they will overwrite each others properties.