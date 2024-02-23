---
icon: octicons/arrow-switch-16
---

# Mod Manager

The Reloaded II mod manager combined with the Granblue Fantasy Relink Mod Manager mod is the primary way to manage mods for GBFR. It quickly handles what would normally be a multi-step process with GBFRDataTools for all managed mods.

!!! warning

    The Mod Manager is currently incompatible with other hooking utilities such as **SpecialK**.

## Reloaded II

[From the latest Reloaded II release](https://github.com/Reloaded-Project/Reloaded-II/releases/), either download Release.zip and extract, or download Setup.exe and run.

Read the [Quick Start Guide](https://reloaded-project.github.io/Reloaded-II/QuickStart/) to set up Reloaded II for Granblue Fantasy Relink and to learn how to install mods.

## Granblue Fantasy Relink Mod Manager

:material-arrow-right: [Download the Granblue Fantasy Relink Mod Manager](https://github.com/WistfulHopes/gbfrelink.utility.manager/releases/tag/v1.0.1). Extract the mod into `Reloaded-II\Mods`.

---

## Creating Mods for the Relink Manager

First, follow the [Reloaded II Creating Mods tutorial](https://reloaded-project.github.io/Reloaded-II/CreatingMods/) for general information.

In addition, all asset mods for Relink require the following setup:

* Set the Granblue Fantasy Relink Mod Manager as a dependency. Reloaded II will prompt you to set mod dependencies when creating the mod.
* Assets must be contained within `GBFR\data`. For example, a mod for `model\pl\pl0101\pl0101.minfo` must be located at `(Mod Directory)\GBFR\data\model\pl\pl0101\pl0101.minfo.`

:material-download: An example mod can be found [here](gbfrelink.recolor.bluehair.zip).
