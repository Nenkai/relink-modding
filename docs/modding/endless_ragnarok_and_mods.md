---
icon: material/exclamation
---

# :material-exclamation: Endless Ragnarok and Mods

New game, mod breakage. This is kind of a classic that we have no control over, but we've established a list of things to look out for.

!!! warning
    **Delete `winmm.dll`/`dinput8.dll`/`version.dll`/`scripts folder` from the game folder if it is present.**

## For Users

### :material-cog: The mod loader (gbfrelink.utility.manager)

[The mod loader has been updated. (2.0.1)](https://www.nexusmods.com/granbluefantasyrelink/mods/526)

It retains compatibility with both 1.3 and Endless Ragnarok (2.0).

### :material-human: Model Mods

Unfortunately, **not all model mods are compatible out of the gate with Endless Ragnarok.** Any model mods that make changes to a model's material files will need to be updated/edited.

You can however force such mods to work.

> [**More info on this dedicated page.**](../models/updating_models_for_er.md)

### :material-sack: Item Uncap

Item uncaps [such as this mod](https://www.nexusmods.com/granbluefantasyrelink/mods/528) will not be compatible until a new version is made.

**Please use your items before playing Endless Ragnarok (due to save transfer) and before taking off the mod. Otherwise items will recap to the original maximum (999)**.

Vouchers cap has been increased to 99.999 in Endless Ragnarok by default.

### :material-table: Table/Gameplay mods

The vast majority of table/gameplay mods are **not compatible with Endless Ragnarok**. due to the nature of [tables](../tables/table_database.md) and columns shifting.

These will require to be manually updated.

### :material-plus: QoL Mods (such as code injection mods created by Nenkai)

In general code-injection mods also broke due to compiler changes from their end, however some of them have already been updated ahead of time:

Updated Mods:

* [Detailed SBA & Enemy Percentage](https://www.nexusmods.com/granbluefantasyrelink/mods/428)
* [Auto-copy Session Id to Clipboard](https://www.nexusmods.com/granbluefantasyrelink/mods/565)
* [Automatic Power Adjustment](https://www.nexusmods.com/granbluefantasyrelink/mods/539)
* [Discord Rich Presence](https://www.nexusmods.com/granbluefantasyrelink/mods/540) (will need to be filled with quest ids and images)
* [Return Imbued Stones](https://www.nexusmods.com/granbluefantasyrelink/mods/425) (70%, still needs to be verified to be working with ER)

Mods that are deprecated and will not be updated as Endless Ragnarok has it built-in:

* [Worldwide Matchmaking](https://www.nexusmods.com/granbluefantasyrelink/mods/335)
* [PS4 and PS5 Original Controller Input Buttons UI](https://www.nexusmods.com/granbluefantasyrelink/mods/570)
* Skip Logos


Any other mods will require an update.

---

## For Modders

### GBFRDataTools

[GBFRDataTools](https://github.com/Nenkai/GBFRDataTools) was updated with a new file list aswell as table headers (except some not to encourage cheat creation).

### File Name Logger

~~Also updated locally, and will be released on ER update.~~ TBA.