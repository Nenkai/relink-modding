---
icon: material/account-cog
---

# :material-account-cog: Action / Parameters

Each Player character has a `{model_id}_action` and a `{model_id}_parameter` file in `system/player/data/{model_id}`.

* The parameter file will list off the player's Damage caps in an array, with identifying numbers
* The action file will list off the player's actions, listing the [motions](motions.md) associated with each one, as well as how the game should treat each action.

## Action File

The Action file will list off the player's actions, listing the motions associated with each one, as well as how the game should treat each action.

Actions, when called, can have projectiles or other attacks linked to them that do not use the `XML/BXM` file format. these will be located in the FSMs for that character.

| <div style="width:185px">Name</div> | Type   | Description |
----------------------------|--------|-------------|
`id_ `                      | string | This will be the number used to refer to the action by other files or other actions in branching paths.
`abilityTag_`               | string | Names the skill, refers to `ability` [table](../../tables/table_database.md). This is only used for actual abilities, not just normal actions. Example: "AB_PL0000_09" (this is Gran's 9th ability, which the ordering of abilities can be found by matching this against the Text file for the abilities, or removing all selected abilities in game, and counting from top to bottom).
`saveActionType_`           | int | Unknown.
`straddleFlagBit_`          | int | Bit flags. Controls how the game will handle the action. Bit 1 made the move assigned to this flag be affected by quick charge on Vaseraga.
`usePoint_`                 | int | Whether to grants honors to the player upon using the action
`autoHomingType_`           | int | Unknown. Possibly impacts how the game handles targeting while this move is called
`autoHomingOffsetDistance_` | int | Unknown.
`abilityStocks_`            | int | This will be the number of charges an ability can hold, like *Lancelot*'s Lawinsturm
`saveAbilityChargeType_`    | int | 1 will make the ability function like an other, 2 will set it to be a 1 time use, like Seofon's 7SB or Tweyen's 2CS
`abilityChargeTime_`        | int | Ability cooldown.
`abilityChargeDelayMin_`    | int | Extra timer that will delay the cooldown starting, this does not impact Cascade
`abilityChargeDelayMax_`    | int | Extra timer that will delay the cooldown starting, this does not impact Cascade
`branchXAtk_`               | int | When X is pressed during this action, so long as the flags are set to allow X presses, then the action listed in this will begin
`branchYAtk_`               | int | Same as above, but for Y
`branchXAtk_Just_`          | int | When X is pressed within a specified window in the flags for the action/motions, it will go to the action listed
`branchYAtk_Just_`          | int | Same as above but for Y
`branchXAtk_Hold_`          | int | Allow charging actions after this one. This functions a little weirdly, as the action seems to be needed to be specified in both the hold and press entries, and requires the following action to accept the input
`branchYAtk_Hold_`          | int | Same as before but for Y
`branchAtkHit_`             | int | Unknown.
`dist_`                     | int | Unknown.
`type_`                     | uint | Unknown.
`controlTypeHash_`          | uint | Unknown. [List of Control Types](control_types.md)
`supportTypeHash_`          | uint | Unknown. **Appears to be completely unused by game code**.
`actionName_`               | string | **Possibly unused.** Generally a name assigned to the action by the devs.
`saveMotId{number}_`        | uint   | [Motions](motions.md) being called by this action. saved motions can be confusing at times, as certain actions will not play them in order, such as Parries
`actionFreeWork{number}_`   | uint   | Values associated with the action, such as for *Zeta*, when she does a Rhapsody parry, the angle of bounce and force behind the lift will be listed here
`freeWork{number}_`         | uint   | Unknown. 5 and 6 are seemingly always 1 
`bulletType_`               | uint   | Refers to the FSM associated with the action, I do not know where this is set however, as to add FSM links. Flags are required in the action to call the FSM
`bulletFreeWork{number}_`   | uint   | Unknown.
`supportEffectList_`        | uint[] | Utilizes a hash and 6 values in an array format to state the buffs that will be applied to the character or team members when this player calls this action, so long as the required flag is in any of the [motions](motions.md) tied to the action. 1st value = How many buffs the game will attempt to give, 2nd value = [Buff Id](buff_ids.md)
`uiIconCategory_`           | uint   | Possibly unused.
`actionCategory_`           | uint   | Unknown. Compared against `abilityBit_` in certain FSM nodes such as `AIBattleRequestAbilityAction` and `AIBattleUseIdAction`.
`isTriggerAttackHit_`       | uint   | Unknown.
`damageLimitType_`          | uint   | Should be unused after 1.3, the game migrated to the next value
`damageLimitDataIndex_`     | uint   | Specifies the damage cap in the Parameter File's Damage cap index that is associated with this action
`relatedAbilityType_`       | uint   | Associates the action with the id assigned, possibly not needed, changing it still allowed the action to function as intended
`indirectDamagePoint_`      | uint   | Additional honors, possibly given on granting buffs to other players, not fully aware of how honors works
`isIndirectDamageAddMulti_` | bool   | Unknown. `true` for *Vane*'s Bubble
`isCheckComboCutAbility_`   | bool   | Unknown.

### Spawned Entities

Some players spawn weapons/entities during their attacks, those characters include:

* *Eugen* - Grenades
* *Rosetta* - Roses and normal attacks/combo finishers
* *Katalina* - Ares
* *Seofon* - Avatar
* *Cagliostro* - Almost all of her attacks
* *Sandalphon* - Gems thrown during specific attacks
* *Ferry* - Pets

The weapons will have motion files and BXMs specific to them.

For some characters, the weapons will handle their own hitboxes

For other characters, the weapons are mostly decoration

For *Cagliostro* and *Rosetta*, the Weapon animation assignments are located in the parameter file, where each action will be assigned a weapon animation (or multiple).

---


*Credits: MidnightAugur*