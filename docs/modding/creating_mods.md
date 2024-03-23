---
icon: material/folder-plus
---

# Creating Mods

## Creating Mods for the Relink Mod Manager

Once you have modded assets you'd like to mod into the game

1. First, follow the [Reloaded II Creating Mods tutorial](https://reloaded-project.github.io/Reloaded-II/CreatingMods/) for general information about creating a mod for Reloaded-II.
2. Set the Granblue Fantasy Relink Mod Manager as a dependency. Reloaded-II will prompt you to set mod dependencies when creating the mod.
3. Your mod's assets must be contained within the `GBFR\data` folder, and follow the same path as where you first extracted the mods from. 
    * For example, a mod for `model\pl\pl0101\pl0101.minfo` must be located at: `(Mod Directory)\GBFR\data\model\pl\pl0101\pl0101.minfo.`

<video controls>
    <source src="../GBFR Reloaded-II Mod Creation Guide.mp4" type="video/mp4">
</video>

!!! info "Example Mod"
    :material-download: An example mod can be found [here](gbfrelink.recolor.bluehair.zip). This example mod switches Djeeta's modifies Djeeta's original outfit model in the prologue.

If you have successfully gotten your mod to work, congratulations!

---

## Mod Loader Features

The mod loader comes with a few features that you can leverage to make mods easier to build or compatible across versions.

### :material-transfer-up: `.minfo` Spoofing

Sometimes the [Model Info](../resources/formats/minfo.md) (`.minfo`) format is changed and a *version date* is changed across all `.minfo` files. This version is explicitly checked to at least be of a certain date. 

Since `.minfo` files are [FlatBuffers](https://flatbuffers.dev/) files, it is normally fine to just upgrade this version as is. The mod loader will silently upgrade any files if needed.

### :material-file-export: Automatic `.json` -> `.msg`

As of 1.0.5, any `.json` files converted from message pack `.msg` files can be automatically processed by the mod loader and converted back to `.msg`. 

You only have to deal with editing the `.json` file.

---

## Creating Mods for Manual Installation

Refer to [Modding Manually](./installing_mods.md#modding-manually) on the Installing Mods page.

---

## Publishing Mods & Guidelines

[Nexus Mods](https://www.nexusmods.com/granbluefantasyrelink) is the primary website to publish mods.

Before you publish a mod, ensure that you've mentioned the following:

* Which **version** this mod was tested for.
* The **version** of the mod loader (Granblue Fantasy Relink Mod Manager) this mod requires.
* If this mod contains **[table edits](../tables/table_database.md)**, in that case the mod is likely to break in future updates.
* If this mod cotnains UI **texture edits** (any texture that are [spritesheets](https://en.wikipedia.org/wiki/Texture_atlas)), in that case the mod is likely to break in future updates.
* If you've made an UI mod, make sure that you've made both `fhd` and non-fhd versions - if you've only edited textures from the `fhd` folder, users using resolutions above 2k (1920x1080) will be using textures from the non-fhd folder and **not be able to see your texture mods**.