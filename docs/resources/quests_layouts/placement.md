---
icon: material/graph
---

# :material-graph: Placement Info

Placement files (`layout/p{phaseId}/placement_*.msg`) determine how phases (and their stages) should be setup and behave (enemies, routes, treasures & more) - treat them as a [scene graph](https://en.wikipedia.org/wiki/Scene_graph).

### `memberType_`

Determines the type of object. Directly affects the values expected in `values_`.

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

    Signature of the table:

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