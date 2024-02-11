---
icon: octicons/arrow-switch-16
---

# Mod Manager

The Reloaded II mod manager combined with the Granblue Fantasy Relink Mod Manager mod is the primary way to manage mods for GBFR. It quickly handles what would normally be a multi-step process with GBFRDataTools for all managed mods.

## Reloaded II

[From the latest Reloaded II release](https://github.com/Reloaded-Project/Reloaded-II/releases/), either download Release.zip and extract, or download Setup.exe and run.

Read the [Quick Start Guide](https://reloaded-project.github.io/Reloaded-II/QuickStart/) to set up Reloaded II for Granblue Fantasy Relink and to learn how to install mods.

## Granblue Fantasy Relink Mod Manager

[Download the Granblue Fantasy Relink Mod Manager](https://github.com/WistfulHopes/gbfrelink.utility.manager/releases/). Extract the mod into `Reloaded-II\Mods`.

---

## Using the Relink Manager

All asset mods for Relink require the following configuration in order to be handled:

* Set the Granblue Fantasy Relink Mod Manager as a dependency.
* Assets must be contained within GBFR\data. For example, a mod for `model\pl\pl0101\pl0101.minfo` must be located at `(Mod Directory)\GBFR\data\model\pl\pl0101\pl0101.minfo`.

!!! tip
    
    The Granblue Fantasy Relink Mod Manager does not need to be enabled on its own! It will automatically be used if a dependent mod is enabled.