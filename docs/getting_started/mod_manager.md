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

## Game Updates

To update to a newer game version properly:

* Rename `orig_data.i` in the game's folder to `data.i`. Otherwise Steam delta patching may attempt to patch a modded `data.i`, leading in an invalid file.
* Remove any tools/patch files you may have installed in the game's folder such as: 
    * `scripts` folder
    * `.asi` files 
    * `winmm.dll`

If that does not work, verify game files integrity.

---

## Creating Mods for the Relink Manager

First, follow the [Reloaded II Creating Mods tutorial](https://reloaded-project.github.io/Reloaded-II/CreatingMods/) for general information.

In addition, all asset mods for Relink require the following setup:

* Set the Granblue Fantasy Relink Mod Manager as a dependency. Reloaded II will prompt you to set mod dependencies when creating the mod.
* Assets must be contained within `GBFR\data`. For example, a mod for `model\pl\pl0101\pl0101.minfo` must be located at `(Mod Directory)\GBFR\data\model\pl\pl0101\pl0101.minfo.`

:material-download: An example mod can be found [here](gbfrelink.recolor.bluehair.zip).

---

## Publishing Mods & Guidelines

[Nexus Mods](https://www.nexusmods.com/granbluefantasyrelink) is the primary website to publish mods.

Before you publish a mod, ensure that you've mentioned the following:

* Which **version** this mod was tested for.
* If this mod contains **[table edits](../tables/table_database.md)**, in that case the mod is likely to break in future updates.
* If this mod cotnains UI **texture edits** (any texture that are [spritesheets](https://en.wikipedia.org/wiki/Texture_atlas)), in that case the mod is likely to break in future updates.
* If you've made an UI mod, make sure that you've made both `fhd` and non-fhd versions - if you've only edited textures from the `fhd` folder, users using resolutions above 2k (1920x1080) will be using textures from the non-fhd folder and **not be able to see your texture mods**.