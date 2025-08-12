---
icon: material/scale-balance
---

# :material-scale-balance: Quick Quest Power Scaling

Quick Quest has an interesting feature where party members (whether online or offline) may be power adjusted depending on the current quest.

## Condition for Power Adjustment

In order to check whether power adjustment (internally refered as level sync) should be used, three components are used:

* The character's current PWR which we will refer to as `currentCharacterPWR`
* The quests's `recommendedCombatPwr` in the [base info](../../quests_layouts/quest_base_info.md), which defines the recommended PWR
* The quest rank (difficulty)'s `maxPWRForLevelSync` in the `quest_rank` [table](../../../tables/table_database.md).

Then it comes down to :

```csharp
if (currentCharacterPWR > recommendedCombatPwr + maxPWRForLevelSync)
{
    // ... power adjustment is enabled
}
```

`maxPWRForLevelSync` allows for defining an upperbound range on top of the recommended PWR for which power adjusting should be be available and depends per difficulty.

* Easy: up to `1000` extra PWR
* Normal: up to `1000` extra PWR
* Hard: up to `2000` extra PWR
* Very Hard: up to `2500` extra PWR
* Extreme: up to `3000` extra PWR
* Maniac: up to `4000` extra PWR
* Proud: up to `99000` extra PWR (essentially no realistic upperbound, so this difficulty is never scaled)

For example, a maniac quest that has its recommended PWR set to `10000` will adjust characters that have a PWR above `14000`.

## Scaling itself

The scaling itself largely depends on the player's PWR, and depends on information from the [chara_level_sync](../../../tables/table_database.md) table.

In particular, the game will select the last row in which the cutoff is right below the character's PWR. (game loops from the last row to the first one).

From there, the game can limit the following attributes:

* Attack Masteries (`ap_tree_atk`, where on the tree to start as locked)
* Defense Masteries (`ap_tree_def`, where on the tree to start as locked)
* Weapon Masteries (`ap_tree_wep`, where on the tree to start as locked)
* Hp
* Attack
* Character Level (internally)
* Weapon Level
* Weapon Awakening Level
* Weapon Mirage Munitions
* Overmastery Level
* Fate Episode "Level" (`chara_status_fate`)
* Max Trait Level (when combined across sigils/stones/weapon)
* PWR (internally)

---

### Signatures

* `CurrentCharaInfo::MaybeApplyQuestLevelsAndQuickQuestSyncing(CurrentCharaInfo* this)` - `55 41 57 41 56 41 55 41 54 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? C5 F8 29 7D ? C5 F8 29 75 ? 48 C7 45 ? ? ? ? ? 49 89 CC C6 81 ? ? ? ? ? 83 B9`
* `LimitTraitLevelsForQuickQuest(char questFlags, char a2, float a3, void* traitPairList)` - `55 41 57 41 56 41 55 41 54 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? C5 F8 29 7D ? C5 F8 29 75 ? 48 C7 45 ? ? ? ? ? 49 89 CC C6 81 ? ? ? ? ? 83 B9`
* `CharacterManager::SetQuickQuestLevelSyncState(CharacterManager* this, uint charaIdHash, bool enabled)` - `55 41 56 56 57 53 48 83 EC ? 48 8D 6C 24 ? 48 C7 45 ? ? ? ? ? 45 89 C6 89 D6 48 89 CF 48 81 C1 ? ? ? ? 48 8B 87 ? ? ? ? 48 8D 55 ? FF 50 ? 39 75 ? 0F 84 ? ? ? ? 8B 97 ? ? ? ? 21 F2 48 8B 87 ? ? ? ? 48 8B 9F ? ? ? ? 48 89 D1 48 C1 E1 ? 48 8B 4C 0B ? 48 39 C1 0F 84 ? ? ? ? 39 71 ? 74 ? 48 01 D2 48 8B 14 D3 66 66 66 2E 0F 1F 84 00 ? ? ? ? 48 39 D1 0F 84 ? ? ? ? 48 8B 49 ? 39 71 ? 75 ? 48 39 C1 0F 84 ? ? ? ? 48 8B 49 ? 48 85 C9 0F 84 ? ? ? ? 8B 99`
