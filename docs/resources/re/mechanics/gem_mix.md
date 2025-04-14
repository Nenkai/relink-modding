# Sigil Synthesis Grand Success

!!! tip

    Handled by `ui::fsm::action::MixGem` fsm component, at `55 41 57 41 56 41 55 41 54 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? 48 83 E4 ? 48 89 E3 48 89 AB ? ? ? ? 48 C7 85 ? ? ? ? ? ? ? ? 4C 8B 2D`.

## Execution

For Sigil Synthesis (known as Gem Mix ingame), the game combines total level of all skills inserted. Lv11+Lv11 & Lv11+Lv11 = 44.

It is then used as a key into `gem_mix_success` table.
* Column 1 is the weight chance for regular success.
* Column 2 is the weight chance for grand success.

All traits from both sigils are put into an array of 4 traits then the list is shuffled.
The first two are taken. That's the new sigil.

If it's a grand success, assign the maximum possible level for the sigil. Otherwise default level.

Cost is determined from `gem_mix_rupi` and `gem_mix_ticket` tables, also based on total level.

## Chance List

Total Sigil Level to Chance
```
44 (4x Lvl.11) = 45%
46 = 48%
48 = 51%
50 = 54%
52 = 57%
52 = 57%
54 = 60%
56 = 70%
58 = 75%
60 (4x Lv.15) = 85%
```

## Other useful signatures

* `GemManager::GetGemInfoFromSlotId(__int64 a1, _QWORD *a2, unsigned int a3)` - `41 56 56 57 55 53 48 83 EC ? 44 89 C3 49 89 D6 48 89 CF 48 81 C1 ? ? ? ? 48 8B 87 ? ? ? ? FF 50 ? 39 D8 0F 84 ? ? ? ? 89 D8 C1 E8 ? 89 D9 C1 E9 ? 0F B6 D3 48 BE ? ? ? ? ? ? ? ? 48 31 D6 48 BA ? ? ? ? ? ? ? ? 48 0F AF F2 0F B6 EF 48 31 F5 48 0F AF EA 0F B6 C0 48 31 E8 48 0F AF C2 48 31 C8 48 0F AF C2 48 23 87 ? ? ? ? 48 8B 8F ? ? ? ? 48 8B B7 ? ? ? ? 48 89 C2 48 C1 E2 ? 48 8B 54 16 ? 48 39 CA 0F 84 ? ? ? ? 39 5A ? 74 ? 48 01 C0 48 8B 34 C6 31 C0 66 0F 1F 84 00 ? ? ? ? 48 39 F2 74 ? 48 8B 52 ? 39 5A ? 75 ? 48 39 CA 74 ? 48 8B 42 ? 48 85 C0 74 ? 8B 50 ? 8B 6F`
* `GetGemMixSuccessForGemSlots` - `41 56 56 57 55 53 48 83 EC ? 4D 89 CE 44 89 C3`
* `RandomManager::GetRandomValue` - `55 56 57 48 83 EC ? 48 8D 6C 24 ? 48 C7 45 ? ? ? ? ? 8B 81 ? ? ? ? 83 F8`
* `GetGemMixRupiCostForGemSlots` - `E8 ? ? ? ? 89 43 ? C6 44 24`
* `GetSigilListForGemMix` - `E8 ? ? ? ? 48 8D 4B ? 4C 8B 43` - Returns a struct containing a count and the list of sigil hashes
* `GetDefaultLevelForGem` - `E8 ? ? ? ? 45 85 FF 74 ? 4C 89 E9`
* `GetMaxPossibleLevelForGem` - `56 57 55 53 8B 71 ? 21 D6 4C 8B 41 ? 4C 8B 49 ? 48 89 F0 48 C1 E0 ? 49 8B 5C 01 ? B8 ? ? ? ? 4C 39 C3 0F 84 ? ? ? ? 39 53 ? 74 ? 48 01 F6 49 8B 34 F1 66 0F 1F 84 00 ? ? ? ? 48 39 F3 0F 84 ? ? ? ? 48 8B 5B ? 39 53 ? 75 ? 4C 39 C3 0F 84 ? ? ? ? 48 8B 5B`
* `CreateNewGem` - `55 41 57 41 56 41 55 41 54 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? 48 C7 45 ? ? ? ? ? 41 89 D5 8B 79`
* `SetGemTrait`- `55 41 57 41 56 56 57 53 48 83 EC ? 48 8D 6C 24 ? 48 C7 45 ? ? ? ? ? 45 89 CE 45 89 C7 89 D3`
* `GetTotalGemLevelFromGemSlotId` - `56 57 53 48 83 EC ? 89 D3 48 89 CE 48 81 C1 ? ? ? ? 48 8B 86 ? ? ? ? FF 50 ? 89 C1 31 C0 39 D9 0F 84 ? ? ? ? 89 D9 C1 E9 ? 41 89 D9 41 C1 E9 ? 44 0F B6 C3 48 BA ? ? ? ? ? ? ? ? 4C 31 C2 49 B8 ? ? ? ? ? ? ? ? 49 0F AF D0 0F B6 FF 48 31 D7 49 0F AF F8 0F B6 C9 48 31 F9 49 0F AF C8 4C 31 C9 49 0F AF C8 48 23 8E ? ? ? ? 4C 8B 86 ? ? ? ? 48 8B B6 ? ? ? ? 48 89 CA 48 C1 E2 ? 48 8B 54 16 ? 4C 39 C2 74 ? 39 5A ? 74 ? 48 01 C9 48 8B 0C CE 66 66 66 66 66 66 2E 0F 1F 84 00 ? ? ? ? 48 39 CA 74 ? 48 8B 52 ? 39 5A ? 75 ? 4C 39 C2 74 ? 48 8B 4A ? 48 85 C9 74 ? 31 C0 81 39 ? ? ? ? 74`
* `AddOrRemoveRupies` - `55 41 56 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? 48 C7 45 ? ? ? ? ? 48 89 CE 89 D1`
* `AddOrRemoveItem` - `55 41 57 41 56 41 55 41 54 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? 48 83 E4 ? 48 89 E3 48 89 AB ? ? ? ? 48 C7 85 ? ? ? ? ? ? ? ? 45 85 C0 0F 84`