---
icon: material/account-arrow-up
hide:
  - toc
---

# :material-account-arrow-up: Buff IDs

!!! warning
    
    * Many of the hashes are hardcoded in the executable.
    * Rows are also present in the `status` [table](../../tables/table_database.md).

Used by:

* :material-account-cog: Character Action Parameters (`system/player/data/{id}/{id}_action`)
    * `ActionInfo` -> `supportEffectList_[1]`

### List

{{ read_csv('buff_ids.csv') }}

### Specific

!!! note

    These will only work for the specified characters.

{{ read_csv('buff_ids_specific.csv') }}

### Sound Files

Part of the Wwise `core.bnk`. `core_status_{em/pl}_{s/m/l}_{name}_{start/end/dot}`, Example: `core_status_em_m_stun_start`

Will match from `status` table.

```
0 = "atkup"
1 = "defup"
2 = "atkdown"
3 = "defdown"
4 = "damagecut"
5 = "regeneration"
6 = "muteki"
7 = "tsuigeki"
8 = "hyperarmor"
9 = "illusion"
10 = "protect"
11 = "protected"
17 = "antidebuff"
18 = "drain"
20 = "guts"
21 = "strength"
22 = "gyakkyou"
23 = "criticalup"
24 = "hateup"
25 = "autorevive"
26 = "magicvortex"
27 = "concentration"
28 = "ironmeiden"
29 = "idodragon"
30 = "idosuper"
31 = "undead"
33 = "phantasmagoria"
36 = "em1806"
37 = "maxhpdown"
38 = "doubletap"
39 = "uniqueguts"
41 = "barrier"
42 = "dmgup"
43 = "sharpshoot"
44 = "senrai"
45 = "pl2100super"
```