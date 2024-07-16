---
icon: material/graph
---

# :material-graph: Placement Info File

Placement files (`layout/p{phaseId}/placement_*.msg`) determine how phases (and their stages) should be setup and behave (enemies, routes, treasures & more) - treat them as a [scene graph](https://en.wikipedia.org/wiki/Scene_graph).

## Placement Info

### `groupType_`

Determines the type of `Group` object.

```
0 - stage::placement::Group
1 - stage::placement::ObjectsSet
2 - stage::placement::EnemySet
3 - stage::placement::MobVillageNpcGroup
4 - stage::placement::TreasureSet
5 - stage::placement::NpcChatGroup
6 - stage::placement::ObjectMaker
7 - stage::placement::PlayerCharaNpcGroup
8 - stage::placement::VyrnAssist
```

### `memberType_`

Determines the type of `Member` object. Directly affects the values expected in `values_`.

```
0 = stage::placement::Member
1 = stage::placement::Enemy
2 = stage::placement::BreakObject
3 = stage::placement::Effect
4 = stage::placement::Zone
5 = stage::placement::Behavior
6 = stage::placement::Player
7 = stage::placement::EventNpc
8 = stage::placement::Behavior (#2?)
9 = stage::placement::MobVillageNpc
10 = stage::placement::Route
11 = stage::placement::Point
12 = stage::placement::Behavior (#3?)
13 = stage::placement::Interact
14 = stage::placement::EntityAccessor
15 = Empty?
16 = stage::placement::Treasure
17 = stage::placement::PlayerNpc
18 = stage::placement::SideQuestNpc
19 = stage::placement::LittleSnipper
20 = stage::placement::PartnerCharaNpc
```

??? "Reverse-Engineering Details"

    Signature of the table (1.3.1):

    `48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 83 3D ?? ?? ?? ?? ?? 0F 85 ?? ?? ?? ?? 48 8D 05 ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8D 05 ?? ?? ?? ?? 48 89  05 ?? ?? ?? ?? 48 8D 05 ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8B 8D`

    Static array of 21 elems (size 0x38 each) is created linking to vtables

	```
    vtable:
    	- dtor @ 0x00
    	- dtor2 @ 0x08
    	- createObj @ 0x10
    	- getVtableUnk @ 0x18
    	- unk @ 0x20
    	- unk @ 0x28
	```

## Operation Detail

### `action_`

From 0 to 20

TODO

??? "Reverse-Engineering Details"

	Table signature (1.3.1) `55 56 57 53 48 81 EC ?? ?? ?? ?? 48 8D AC 24 ?? ?? ?? ?? 48 C7 45 ?? ?? ?? ?? ?? C7 45`

	Handled at `4A 8B 4C 30 ?? 48 85 C9 0F 84`

### `what_`

From 0 to 3

* 0 = None
* 1 = Controller (`stage::placement::Controller`)
* 2 = Group (inheriting from/or `stage::placement::Group`)
* 3 = Member (inheriting from/or `stage::placement::Member`)

??? "Reverse-Engineering Details"

	Table signature (1.3.1) `48 8D 05 ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8D 05 ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8D 0D ?? ?? ?? ?? 48 8D 15 ?? ?? ?? ?? 48 89 15 ?? ?? ?? ?? 48 89 0D ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8D 0D ?? ?? ?? ?? 48 8D 15 ?? ?? ?? ?? 48 89 15 ?? ?? ?? ?? 48 89 0D ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8D 05 ?? ?? ?? ?? 48 8D 0D ?? ?? ?? ?? 48 89 0D ?? ?? ?? ?? 48 89 05 ?? ?? ?? ?? 48 8D 0D ?? ?? ?? ?? E9 ?? ?? ?? ?? CC CC CC CC CC CC CC CC 41 56`

	Handled at `4A 8B 4C 20 ?? 48 85 C9 0F 84 ?? ?? ?? ?? 48 8B 01`