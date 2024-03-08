---
icon: octicons/arrow-switch-16
---

# Mod Manager

The Reloaded II mod manager combined with the Granblue Fantasy Relink Mod Manager mod is the primary way to manage mods for GBFR. It quickly handles what would normally be a multi-step process with GBFRDataTools for all managed mods.

!!! warning

    The Mod Manager is currently incompatible with other hooking utilities such as **SpecialK**.

## Setting up Reloaded II

* [From the latest Reloaded II release](https://github.com/Reloaded-Project/Reloaded-II/releases/), either download `Release.zip` and extract, or download `Setup.exe` and run.
* Locate `granblue_fantasy_relink.exe` and register it in Reloaded II by clicking on the + icon on the left side.
* Download the [Granblue Fantasy Relink Mod Loader](https://github.com/WistfulHopes/gbfrelink.utility.manager/releases) and extract it in Reloaded II's folder under the `Mods` folder. It should be looking like this:

<figure markdown>
  ![image](mod_manager_mods.png)
  *Make sure to extract `gbfrelink.utility.manager` into its own folder.*
</figure>

---

## Installing Mods

When installing mods, simply extract them into the `Mods` folder aswell.

!!! tip

    For more information if needed, refer to the Reloaded II [Quick Start Guide](https://reloaded-project.github.io/Reloaded-II/QuickStart/).

---

## Creating Mods for the Relink Manager

First, follow the [Reloaded II Creating Mods tutorial](https://reloaded-project.github.io/Reloaded-II/CreatingMods/) for general information.

In addition, all asset mods for Relink require the following setup:

* Set the Granblue Fantasy Relink Mod Manager as a dependency. Reloaded II will prompt you to set mod dependencies when creating the mod.
* Assets must be contained within `GBFR\data`. For example, a mod for `model\pl\pl0101\pl0101.minfo` must be located at `(Mod Directory)\GBFR\data\model\pl\pl0101\pl0101.minfo.`

:material-download: An example mod can be found [here](gbfrelink.recolor.bluehair.zip).
