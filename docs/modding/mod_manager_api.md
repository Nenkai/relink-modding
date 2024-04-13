---
icon: material/api
---

# Mod Manager API

!!! note
    This page is intended for programmers with knowledge in C#.

As of `gbfrelink.utility.manager` 1.0.8, a modding API is now exposed. 

This API can be leveraged to create file mods through your own C# code. This has the benefit of creating specific mods with a lessened chance of breaking across official game updates.

An example is available at [gbfr.qol.weaponglowcontrol](https://github.com/Nenkai/gbfr.qol.weaponglowcontrol) ([Nexus Page](https://www.nexusmods.com/granbluefantasyrelink/mods/363)), which programatically fetches game files, edits them, and passes them back to the mod loader.

## Setting Up

1. [Setup a development environment](https://reloaded-project.github.io/Reloaded-II/DevelopmentEnvironmentSetup/) for Reloaded-II mods.
2. [Create a New Project](https://reloaded-project.github.io/Reloaded-II/ProjectSetup/) using the Reloaded II Mod template.
3. Add the [`gbfrelink.utility.manager.Interfaces`](https://www.nuget.org/packages/gbfrelink.utility.manager.Interfaces) NuGet package to your project.

## Usage

Refer to the [Dependencies Consumption documentation](https://reloaded-project.github.io/Reloaded-II/DependencyInjection_Consumer/) to understand the concept behind shared libraries.

In your mod's constructor, grab a reference to `IDataManager`:

```csharp
// Fetch IDataManager to manipulate game data
_modLoader.GetController<IDataManager>()?.TryGetTarget(out IDataManager dataManager!);

// Checks if a game file exists (archive file, non-external)
const string TEXT_EN_PATH = "system/table/text/en/text.msg";
if (dataManager.FileExists(TEXT_EN_PATH, includeExternal: false))
{
    // Get the file data
    byte[] file = dataManager.GetArchiveFile(TEXT_EN_PATH);

    // ... Do something with the file

    // Add/Update game file
    dataManager.AddOrUpdateExternalFile(TEXT_EN_PATH, newContents);

    // Apply changes to the game's data.i.
    dataManager.UpdateIndex();
}
```

!!! note
    External files or files altered by other mods cannot be acquired yet.