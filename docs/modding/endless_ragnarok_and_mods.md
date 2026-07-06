---
icon: material/exclamation
---

# :material-exclamation: Endless Ragnarok and Mods

New game, mod breakage. This is kind of a classic that we have no control over, but we've established a list of things to look out for.

!!! warning
    **You should turn off ALL mods in Endless Ragnarok.**

## For Users

### :material-cog: The mod loader (gbfrelink.utility.manager)

The mod loader has already been updated locally and the new version **will be released when Endless Ragnarok is released.**

It retains compatibility with both 1.3 and Endless Ragnarok (2.0).

### :material-human: Model Mods

Unfortunately, **not all model mods are compatible out of the gate with Endless Ragnarok.** Any model mods that make changes to a model's material files will need to be [updated/edited].

You can however force such mods to work.

> [**More info on this dedicated page.**](../models/updating_models_for_er.md)

### :material-sack: Item Uncap

Item uncaps [such as this mod](https://www.nexusmods.com/granbluefantasyrelink/mods/528) will not be compatible until a new version is made.

**Please use your items/vouchers before taking off the mod. Otherwise items will recap to the original maximum (999)**.

### :material-table: Table/Gameplay mods

The vast majority of table/gameplay mods are **not compatible with Endless Ragnarok**. due to the nature of [tables](../tables/table_database.md) and columns shifting.

These will require to be manually updated.

### :material-plus: QoL Mods (such as code injection mods created by Nenkai)

In general code-injection mods also broke due to compiler changes from their end, however some of them have already been updated ahead of time (and will be released with ER):

* [Detailed SBA & Enemy Percentage](https://www.nexusmods.com/granbluefantasyrelink/mods/428)
* [Auto-copy Session Id to Clipboard](https://www.nexusmods.com/granbluefantasyrelink/mods/565)
* [Discord Rich Presence](https://www.nexusmods.com/granbluefantasyrelink/mods/540) (will need to be filled with quest ids and images)
* [Return Imbued Stones](https://www.nexusmods.com/granbluefantasyrelink/mods/425) (70%, still needs to be verified to be working with ER)
* [Automatic Power Adjustment](https://www.nexusmods.com/granbluefantasyrelink/mods/539)

Mods that are deprecated and will not be updated as Endless Ragnarok has it built-in:

* [Worldwide Matchmaking](https://www.nexusmods.com/granbluefantasyrelink/mods/335)
* [PS4 and PS5 Original Controller Input Buttons UI](https://www.nexusmods.com/granbluefantasyrelink/mods/570)
* Skip Logos

Any other mods will require an update.

---

## For Modders

### GBFRDataTools

[GBFRDataTools](https://github.com/Nenkai/GBFRDataTools) only requires a file list update, which will not happen immediately on release (as I (Nenkai) would like to enjoy it, but contributions are also welcome).

### File Name Logger

Also updated locally, and will be released on ER update.