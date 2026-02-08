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
`abilityTag_`               | string | Names the skill, refers to `ability` [table](../../tables/table_database.md). This is only used for actual abilities, not just normal actions. Example: "AB_PL0000_09" (this is Gran's 9th ability. The ordering of abilities can be found by matching this against `data\system\table\text\[Language]\text.msg`, or removing all selected abilities in game, and counting from top to bottom).
`saveActionType_`           | int | Unknown. Certain numbers can change how the skill cooldown is spent. ie. on skill startup, or when Flag1:7 is called.
`straddleFlagBit_`          | int | Bit flags. Controls how the game will handle the action. May remove the ability to chain to other actions without the right flags.
`usePoint_`                 | int | Whether to grants honors to the player upon using the action.
`autoHomingType_`           | int | Unknown. Possibly impacts how the game handles targeting while this move is called.
`autoHomingOffsetDistance_` | int | Unknown.
`abilityStocks_`            | int | This will be the number of charges an ability can hold, like *Lancelot*'s Lawinsturm.
`saveAbilityChargeType_`    | int | 1 will make the ability function like any other, 2 will set it to be a 1 time use, like Seofon's 7SB or Tweyen's 2CS.
`abilityChargeTime_`        | int | Ability cooldown.
`abilityChargeDelayMin_`    | int | Extra timer that will delay the cooldown starting, this does not impact Cascade.
`abilityChargeDelayMax_`    | int | Extra timer that will delay the cooldown starting, this does not impact Cascade.
`branchXAtk_`               | int | When X is pressed while Flag0:1 or Flag0:24 is enabled in the action being played, it will go to the action listed.
`branchYAtk_`               | int | When Y is pressed while Flag0:1 or Flag0:6 is enabled in the action being played, it will go to the action listed.
`branchXAtk_Just_`          | int | When X is pressed while Flag1:18 is enabled in the action being played, and Flag1:19 is called, it will go to the action listed.
`branchYAtk_Just_`          | int | When Y is pressed while Flag1:18 is enabled in the action being played, and Flag1:19 is called, it will go to the action listed.
`branchXAtk_Hold_`          | int | When X is being held when Flag1:17 is enabled, the action will transition to the action listed here.
`branchYAtk_Hold_`          | int | When Y is being held when Flag1:17 is enabled, the action will transition to the action listed here.
`branchAtkHit_`             | int | When Flag0:19 is called during an action, if attacks have landed prior to the flag being called, the action listed here will begin.
`dist_`                     | int | Affects the distance the action is set to be called at by AI.
`type_`                     | uint | Unknown.
`controlTypeHash_`          | uint | Controls how motions in an action are handled when called. [List of Control Types](control_types.md)
`supportTypeHash_`          | uint | Unknown. **Appears to be completely unused by game code**.
`actionName_`               | string | **Possibly unused.** Generally a name assigned to the action by the devs. Does not seem to impact anything, and is purely for in-house naming.
`saveMotId{number}_`        | uint   | [Motions](motions.md) being called by this action.
`actionFreeWork{number}_`   | uint   | Values associated with the action, such as for *Zeta*, when she does a Rhapsody parry, the angle of bounce and force behind the lift will be listed here
`freeWork{number}_`         | uint   | Unknown. 5 and 6 are seemingly always 1 
`bulletType_`               | uint   | Refers to the FSM associated with the action. This value is only used on specific characters and links from value to FSM are set in the executable. FSM is called by Flag1:4 in the motions tied to the action.
`bulletFreeWork{number}_`   | uint   | Unknown.
`supportEffectList_`        | uint[] | Utilizes a hash and 6 values in an array format to state the buffs that will be applied to the character or team members when Flag1:2 is called during andy of the [motions](motions.md) in this action. 1st value in the array is how many buffs the game should be attempting to give, 2-8th value = [Buff Id](buff_ids.md)
`uiIconCategory_`           | uint   | Possibly unused.
`actionCategory_`           | uint   | BitFlag that affects how this action is called by AI when the skill is available. Each has specific requirements to be active depending on conditions set in the executable. Compared against `abilityBit_` in certain FSM nodes such as `AIBattleRequestAbilityAction` and `AIBattleUseIdAction`.
`isTriggerAttackHit_`       | uint   | Allows supportEffects to be called by a hitbox with atkFlag:29 on hit when set to `true`.
`damageLimitType_`          | uint   | Should be unused after 1.3, the game migrated to the next value
`damageLimitDataIndex_`     | uint   | Specifies the damage cap in the Parameter File's Damage cap index that is associated with this action
`relatedAbilityType_`       | uint   | Associates the action with the id assigned, possibly not needed, changing it still allowed the action to function as intended
`indirectDamagePoint_`      | uint   | Additional honors, possibly given on granting buffs to other players, not fully aware of how honors works
`isIndirectDamageAddMulti_` | bool   | Unknown. `true` for *Vane*'s Bubble
`isCheckComboCutAbility_`   | bool   | When set to `true`, disables players from casting a skill and having access to the skill follow-ups listed in BranchXAtk and BranchYAtk before the skill cooldown is used either by flag1:7, or by other methods. Not tested if it can function on non-skill actions.

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

For *Cagliostro* and *Rosetta*, the weapon animation assignments are located in the parameter file, where each action will be assigned a weapon animation (or multiple).

---


*Credits: MidnightAugur*
