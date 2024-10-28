---
icon: material/account-arrow-down
---

# :material-account-arrow-down: Debuffs

## Category
*Used by:*

* :material-graph: [FSM] `BT::AreaEffectAttackAction` (`category_`)
    * `0x67AE4C55` - Category 0
    * `0x78D65167` - Category 1
    * `0x9CD39782` - Category 2

## Debuff Type
Used by:

* :material-xml: [BXM] Used by attack bxms (`type_`)
* :material-graph: [FSM] `BT::AreaEffectAttackAction` (`type_`)
* :material-graph: [FSM] `BT::BadStatusCondition` (`badStatusHash_`)
* :material-graph: [FSM] `BT::Em0102AreaEffectAttackAction`
* :material-graph: [FSM] Anything inheriting from `ShotAttackAction`

!!! note

    These range from id 1000 to 1022, used by 'status' table

{{ read_csv('debuff_ailment_ids.csv') }}