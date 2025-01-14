---
icon: material/sword-cross
---

# Quest IDs

:material-lightbulb: Data Version: `1.3.x`

List is interpolated using `system/table/text/text_stage.msg`

!!! note
    A quest should have:

    * [BaseInfo](./quests_layouts/quest_base_info.md) file, with quest details
    * FSM Files (`system/fsm/quest`), normally linked by the BaseInfo file
    * An entry in `quest/BaseInfoFolderList`
    * Entries in various quest related [tables](../tables/table_database.md)
    * Optionally an entry in the [streaming prefetch](./formats/stpr.md) file for which assets are preloaded.

* `1xxxxx` = Main Quest
* `2xxxxx` = Challenge/Side Quest
* `3xxxxx` = Fate Episode
* `4xxxxx` = Multiplayer/Quest Counter
* `5xxxxx` = Towns/Lobbies
* `6xxxxx` = Dummy/Practice
* `7xxxxx` = Short Story/Misc

{{ read_csv('quest_id.csv') }}