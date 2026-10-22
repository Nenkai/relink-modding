---
icon: material/account-arrow-down
hide:
  - toc
---

# :material-account-arrow-down: Debuffs

!!! warning
    
    * Many of the hashes/ids are hardcoded in the executable.
    * Rows are also present in the `status` [table](../../tables/table_database.md).

## Category
*Used by:*

* :material-xml: [BXM] Used by attack bxms (`type_`)
* :material-graph: [FSM] `BT::AreaEffectAttackAction` (`category_`)
{{ read_csv('debuff_ailment_categories.csv') }}

## Debuff Type
Used by:

* :material-xml: [BXM] Used by attack bxms (`type_`)
* :material-graph: [FSM] `BT::AreaEffectAttackAction` (`type_`)
* :material-graph: [FSM] `BT::BadStatusCondition` (`badStatusHash_`)
* :material-graph: [FSM] `BT::Em0102AreaEffectAttackAction`
* :material-graph: [FSM] Anything inheriting from `ShotAttackAction`

!!! note

    'status' Ids can be found in the 'status' table

## Player Receiving
If a player is hit with a hitbox which contains this information, this is how it is translated.
{{ read_csv('debuff_ailment_player_receiving_ids.csv') }}

## Player Receiving
If an enemy is hit with a hitbox which contains this information, this is how it is translated.
{{ read_csv('debuff_ailment_enemy_receiving_ids.csv') }}
