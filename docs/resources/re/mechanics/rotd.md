---
icon: material/dice-1
---

# Roll of the Die

!!! quote "Sigil Description"

    "*Grants a chance for normal attacks to deal 1x-4x damage.*

    *The 4x multiplier ignores damage cap for a max of 999,999 damage. Otherwise attacks only deal 1 damage.*"

Percentages depends on [`skill_status`](../../../tables/table_database.md) (Key: `SKILL_157_00`)

On attack:

* `1%` = Damage Multiplier = **4x**, Damage Cap set to = 999999
* `5%` = Damage Multiplier = **3x**
* `18%` = Damage Multiplier = **2x**
* `26%` = Damage Multiplier = **1x**
* `50%` = 1 Damage

Average damage multiplier = `0.79x`

!!! tip "Function Handler Pattern"

    ```
    41 57 41 56 41 55 41 54 56 57 55 53 48 81 EC ? ? ? ? C5 78 29 A4 24 ? ? ? ? C5 78 29 9C 24 ? ? ? ? C5 78 29 94 24 ? ? ? ? C5 78 29 4C 24
    ```

    Damage & Cap appear to be set separately.
    ```c
    *(_DWORD *)(_R14 + 208) = 1;// Damage
    ...
    *(_DWORD *)(_R14 + 612) = 999999; // Cap    
    ```
