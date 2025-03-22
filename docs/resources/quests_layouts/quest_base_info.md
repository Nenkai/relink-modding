---
icon: material/chat-question
---

# :material-chat-question: Quest Base Info

Quest Base Info files (`quest/{quest_id}/baseinfo.msg`) provides the basic & critical information about any given quest.

!!! note
    The quest id should be present in `quest/BaseInfoFolderList.msg`.

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `category_`              | `int`      | Quest category. 1st hex digit of a quest id, `category_` should be `4` if the quest id is `407320`. Category in general denotes the type of quest.
| `subCategory_`           | `int`      | Quest sub-category. 2nd & 3rd hex digit of a quest id, `subCategory_` should be `32` (decimal) if the quest id is `720009`.
| `serialNumber_`          | `int`      | Serial Number. Last 3 hex digits of a quest id, `serialNumber_` should be `800` (decimal) if the quest id is `407320`.
| `difficultyHash_`        | `string`   | Difficulty name. Directly controls the difficulty of enemies in general. Maps to  `quest_difficulty` [table](../../tables/table_database.md) (hashed).
| `lv_`                    | `int`      | Unknown. Seems to affect enemy levels.
| `time_`                  | `int`      | Quest timer in seconds.
| `lostTime_`              | `int`      | Unknown.
| `clearableTimes_`        | `int`      | Unknown.
| `mobIdHash_`             | `string`   | Display mob name. Maps to `mob` [table](../../tables/table_database.md).
| `sortNo_`                | `int`      | Sorting order. Greater number means further down in the quest listing.
| `main_`                  | [Main](#main)  | Main story quest information (quest category has to be `1`).
| `challenge_`             | [Challenge](#challenge)  | Challenge (side-quest) quest information (quest category has to be `2`).
| `fateEpisode_`           | [FateEpisode](#fate-episode)  | Fate Episode quest information (quest category has to be `3`).
| `multi_`                 | [Multi](#multi)      | Multiplayer quest information (quest category has to be `4`).
| `shortStory_`            | [ShortStory](#short-story)  | Short Story quest information (quest category has to be `7`).
| `occurrenceList_`        | [Occurrence][](#occurrence) | Unknown.
| `orderList_`             | ?[] | Unknown.
| `successList_`           | ?[] | Unknown.
| `failureText_{}`         | `TXT_QT_PARTYDEATH` | Message to show on failure.
| `reward_`                | Reward | Reward information.
| `fsmDataList`            | [FSMData](#fsmdata) | List of FSM files linked to this quest.
| `targetList_`            | [Target](#target) | List of targets (current objectives) for the quest.
| `subMissions_`           | [SubMission](#sub-mission) | List of sub-goals/missions and their rewards.
| `sectionSortListGuid_`   | ?[] | List of sections. **`guid_` array should directly match `guid` in `sectionlist.json`.**
| `lotData_`               | `string` | Unknown. Maps to `treasure_chest` [table](../../tables/table_database.md).
| `rewardRank_`            | `int` | Reward Rank. **Very Important** as it controls the rewards available per lot in the `reward_lot` [table](../../tables/table_database.md) - reminder that enemy drops also point to the reward table so rank can also change their death drop.
| `placementsInfo_`        | [PlacementInfo](#placement-info) | Information about items that can be picked during the quest.
| `exPlacementFilesInfo_`  | ?[] | List of placement files, possibly maps to `layout/p{phaseNumber}/placement_{type_name}_{suffix}`.
| `startEventInfo_`        | ? | Unknown.
| `endEventInfo_`        | ? | Unknown.
| `isConsumeAppend_`       | `bool` | Unknown.
| `consumeCounts_`         | `int[]` | Unknown.
| `clearTimeMax_`          | `int`  | Unknown. In seconds.
| `clearTimeMin_`          | `int`  | Unknown. In seconds.
| `resetTownTreasureType_` | `int`  | Unknown.
| `specialRegulationInfo_` | `?[]`  | Unknown. Possibly never used.
| `actionDropRewardList_`  | `?[]`  | Unknown. Used in a few story & fate episode quests, possibly unique rewards for certain things.
| `preLoadQuestFSMFileInfos_` | `PreLoadQuestFSMFileInfo[]` | List of FSMs to pre-load, possibly optional. `index` is the same as suffix unless `names` is provided, which can point to fsms that are not quest fsms. Use `.yml` extension regardless of actual extension.
| `preLoadVoiceEventFileInfos_` | `PreLoadVoiceEventFileInfo[]` | List of voice files to pre-load (sound, lipsync). 
| `overrideAttribute_` | `int` | Unknown.
| `isBroadcastVersion_` | `bool` | Unknown.

---

### Main

!!! note
    Only when quest category is `1`.

| Attribute                    | Type       | Description                                        |
|------------------------------|------------|----------------------------------------------------|
| `type_`                      | `int`      | Unknown.
| `rcommendedCombatPower_{}`   | `int[]`    | Recommended PWR per story difficulty
| `isChapterSelectPartyKeep_`  | `bool`     | Unknown.

### Challenge

!!! note
    Only when quest category is `2`.

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `uuidHashs_{}`           | `ulong`    | Unknown.
| `phaseNos_{}`            | `int`      | Phase number, remember to convert it to hex - i.e `3072` = `pC00`.
| `isConsecutive_`         | `bool`     | Whether it can be replayed?

### Fate Episode

!!! note
    Only when quest category is `3`.

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `isStartEventTown_`      | `bool`     | Whether the event starts in town.
| `isEndEventTown_`        | `bool`     | Whether the event ends in town.
| `townType_`              | `int`      | Unknown.
| `hasStartEvent_`         | `bool`     | Unknown.
| `hasEndEvent_`           | `bool`     | Unknown.
| `hasStartTelop_`         | `bool`     | Unknown.
| `hasClearTelop_`         | `bool`     | Unknown.
| `gameCategory_`          | `int`      | Unknown.
| `location_`              | `string`    | Unknown.
| `targetDispInfo_`        | TargetDispInfo | `textHash_` is quest target/description, `type_` is unknown.


### Multi

!!! note
    Only when quest category is `4`.

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `strengthValue_`         | `int`      | Strength value.
| `rcommendedCombatPower_` | `int`      | Display value of recommended PWR.
| `islandId_`              | `string`   | Island name where the quest takes place. Used mainly for displaying the name, maps to `island` [table](../../tables/table_database.md).
| `gameCategory_`          | `int`      | Unknown.
| `multiQuestType_`        | `int`      | Unknown.
| `location_`              | `string`   | Display location name where the quest takes place. Used mainly for displaying the location, maps to `location` [table](../../tables/table_database.md).
| `enemyIds_[]`            | `ObjId[]`  | Display enemies in the quest. [Object ID](../re/obj_id.md).
| `enemyNum_[]`            | `int[]`    | Display enemies number in the quest.
| `overwriteStatusAndReward_[]` | `int[]`    | Unknown.
| `min_`                   | `int`      | Unknown.
| `max_`                   | `int`      | Unknown.
| `standard_`              | `int`      | Unknown.
| `targetDispInfo_`        | TargetDispInfo | `textHash_` is quest target/description, `type_` is unknown.
| `hasPrepareArea`         | `bool`      | Unknown.
| `isQuestStartFromBossAppear_`   | `bool`      | Unknown.
| `isUltimateParameterUse_`   | `bool`      | Unknown.
| `isBossRush_`            | `bool`      | Whether the quest is a boss rush. **Must be used for boss rushes**, controls whether to move on to other sections, otherwise quest ends early/gets stuck.

### Short Story

!!! note
    Only when quest category is `7`.

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `isPhaseMoveDelete_`     | `bool`     | Unknown.

---

### Occurrence

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `type_`                  | `int`      | Id Type `1` = Quest ID, `2` = Phase ID
| `id_`                    | `int`      | Id Value
| `count_`                 | `int`      | Count

### Reward

!!! note
    Strings are hashed and then mapped to the `reward` [table](../../tables/table_database.md).

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `first_`                 | `string`   | Reward on first clear.
| `every_`                  | `string`   | Reward on every clear.
| `rankReward[]`           | `string`   | Rewards (depending on rank).

### FSMData

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `name_`                  | `string`   | Unused.
| `hash_`                  | `ulong`    | Hash of the fsm file. **Used as a unique identifier**.
| `suffix_`                | `int`      | Suffix - maps this to `system\fsm\quest\quest_{quest_id}_{suffix}_fsm_ingame.msg`.

### Target

List of available current objectives in the quest.

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `label_`                 | `string`   | **Unique key of the target**.
| `textLabel_`             | `string`   | Localized text.
| `type_`                  | `int`      | Type of objective display value.
| `id_`                    | `int`      | Id (when applicable), i.e Enemy [Object Id](../re/obj_id.md).
| `count_`                 | `int`      | Count.
| `canFail_`               | `bool`     | Whether this target/objective is failable.
| `isDisplay_`             | `bool`     | Whether this is displayed.
| `idIndex_`               | `int`      | Unknown.
| `udsId_`                 | `int`      | Unknown.

The value `canFail_` perhaps doesn't have the best name. It seems rather more
accurate to say it acts as a `shouldFail` signal. When set to true, then a
failure will be triggered for this objective once the condition determined by
this objective's `type_` attribute has been met.

`isDisplay_` doesn't seem to have any hard rules, either. For a quest's three
typical objectives, `isDisplay_` is usually set to true, except for when using
either `type_` for displaying text strings, ironically. Some objectives do have
hidden objectives, however, which can be used to trigger additional rewards.

`type_` can take on many different (integer) values to indicate a multitude of
different quest objectives. Known values are enumerated in the table below. Note
that for many or most of these, the `id_` field isn't used and is expected to be `0`.

| `type_=`       | Description                                                               |
|----------------|---------------------------------------------------------------------------|
| `0`            | No effect. Used to displays textual objective strings only (as guidance). |
| `1`            | Appears Unused.                                                           |
| `2`            | Completion time, full quest. Triggers after `count_` seconds elapsed. Usually used when `canFail_=true` to trigger objective's failure. |
| `3`            | Collect Entity/Defeat Enemy `id_`, `count_` times.                        |
| `4`            | Unsure.                                                                   |
| `5`            | Destroy battleship installations, minimum of `count_`.                    |
| `6`            | Appears Unused.                                                           |
| `7`            | HP Percentage exceeds `count_` (defend-the-base) quests. For this value, `count_` is a float between `0.` and `1.` |
| `8`            | Unsure. Perhaps some sort of internal timer for delays? Only used once.   |
| `9`            | Appears Unused.                                                           |
| `10`           | Activate any skill, minimum of `count_` times.                            |
| `11`           | Appears Unused.                                                           |
| `12`           | Skybound Art Usage, minimum of `count_` times.                            |
| `13`           | Appears Unused.                                                           |
| `14`           | Link Attacks Count, minimum (plus 1). For "do N link attacks", set `count_` to `N+1`. |
| `15`           | Critical Condition Count, maximum (plus 1). For "do not enter critical more than N times", set `count_` to `N+1`. |
| `16..18`       | Appears Unused.                                                           |
| `19`           | Number of foe waves (defend-the-base quests), minimum of `count_`. Used with `canFail_=false`.  |
| `20`           | Appears Unused.                                                           |
| `21`           | Update/Refresh objective text. Used for specific fate story quests. Used with `canFail_=false`, `isDisplay_=false`.  |
| `22`           | Appears Unused.                                                           |
| `23`           | LinkTime Entry Count, minimum of `count_` times.                          |
| `24`           | Number of Full Bursts triggered, minimum of `count_` times.               |
| `25`           | Defeats/Kills via ether cannon, minimum of `count_`.                      |
| `26`           | Defeats/Kills via thrown object, minimum of `count_`.                     |
| `27`           | Appears Unused.                                                           |
| `28`           | Obtain/Destroy Entities or Destructible Parts. `count_` set to minimum quantity (usually just `1`).    |
| `29`           | Status Anomalies Received, maximum (plus 1). `count_=N+1`, and `id_` set to status effect's global ID. |
| `30`           | Completion Time, after defeat of a foe (plus 1). For "defeat Y within 5 minutes after defeating X", set `count_=301`. |
| `31`           | Appears Unused.                                                           |
| `32`           | Unsure.                                                                   |
| `33..37`       | Appears Unused.                                                           |
| `38`           | Attacks Dodged, minimum of `count_` times. NOT perfect dodges.            |
| `39`           | Appears Unused.                                                           |
| `40`           | Attacks Guarded, minimum of `count_` times. NOT perfect guards.           |
| `41`           | Attacks Perfect-Guarded, minimum of `count_` times.                       |
| `42`           | Defeats/Kills via Dimension Warp, minimum of `count_`. (Angra Mainyu).    |
| `43`           | Defeat/Negate light orb via ether cannon, minimum of `count_` times.      |


### Sub Mission

| Attribute                | Type       | Description                                        |
|--------------------------|------------|----------------------------------------------------|
| `target_`                | `string`   | Maps directly to the label/key in [target](#target).
| `reward_`                | `string`   | Reward for completing this sub-mission. Maps to `reward` [table](../../tables/table_database.md).
| `firstReward_`           | `string`   | First reward for completing this sub-mission. Maps to `reward` [table](../../tables/table_database.md).

### Placement Info

| Attribute                   | Type       | Description                                        |
|-----------------------------|------------|----------------------------------------------------|
| `treasureMaxCount_`         | `int`      | Max number of chests.
| `treasureMinCount_`         | `int`      | Min number of chests.
| `pickMaxCount_`             | `int`      | Max number of 'pick'/ground items (blue shine).
| `pickMinCount_`             | `int`      | Min number of 'pick'/ground items (blue shine).
| `searchItemMaxCount_`       | `int`      | Unknown.
| `searchItemMinCount_`       | `int`      | Unknown.
| `archiveMaxCount_`          | `int`      | Max number of 'archives'/note/paper items.
| `archiveMinCount_`          | `int`      | Min number of 'archives'/note/paper items.
| `multiQuestCoinMaxCount_`   | `int`      | Unknown.
| `multiQuestCoinMinCount_`   | `int`      | Unknown.

