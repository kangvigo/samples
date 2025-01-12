---
languages:
- csharp
products:
- dotnet-core
page_type: sample
name: "Diagnostic scenarios sample debug target"
urlFragment: "diagnostic-scenarios"
description: "A .NET Core sample with methods that trigger undesirable behaviors to diagnose."
---
# Diagnostic scenarios sample debug target

The sample debug target is a simple `webapi` application. The sample triggers undesirable behaviors for the [.NET Core diagnostics tutorials](https://docs.microsoft.com/dotnet/core/diagnostics/index#net-core-diagnostics-tutorials) to diagnose.

## Build and run the target

After downloading the source, you can easily run the webapi using:

```console
dotnet build
dotnet run
```

## Target methods

The target triggers undesirable behaviors when hitting specific URLs.

### Deadlock

`http://localhost:5000/api/diagscenario/deadlock`

This method will cause the target to hang and accumulate many threads.

### High CPU usage

`http://localhost:5000/api/diagscenario/highcpu/{milliseconds}`

The method will cause to target to heavily use the CPU for a duration specified by {milliseconds}.

### Memory leak

`http://localhost:5000/api/diagscenario/memleak/{kb}`

This method will cause the target to leak memory (amount specified by {kb}).

### Memory usage spike

`http://localhost:5000/api/diagscenario/memspike/{seconds}`

This method will cause intermittent memory spikes over the specified number of seconds. Memory will go from base line to spike and back to baseline several times.
