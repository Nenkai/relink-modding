---
icon: material/select-search
---

# :material-select-search: Effect Call Selector

The effect call selector file (`effect/callselector.bxm`) is responsible for showing different effects per weapon attack (or main effect?), used for Ferry, Seofon and Sandalphon. It is mostly a lookup table.

It's also a rather old file by PlatinumGames.

| Attribute | Purpose                                                                             |
| ----------|-------------------------------------------------------------------------------------|
| `DataId`  | Returned Player Obj ID after searching                                              |
| `EstId`   | Returned Effect ID after searching                                                  |
| `ObjId`   | Weapon Obj ID for searching                                                         |
| `Level`   | Unknown.                                                                            |
| `ID`      | Main search key; some kind of EstId, referenced by est VFX files, 'FWK' part, field 'wk1'. wk0 has to be 4. (in the case of esp01?)  |

For instance, for Ferry, the following IDs represent:

* 2 = Normal Attack, Purge Spirit
* 4 = SBA Trigger
* 6, 7, 8 = Onslaught
* 9, 16 = Aerial Barrage (ground slam)
* 17, 18 = SBA 

---

Search function (used by `esp` class handlers): `41 57 41 56 41 55 41 54 56 57 55 53 48 83 EC ? 4C 89 44 24 ? 48 89 4C 24`