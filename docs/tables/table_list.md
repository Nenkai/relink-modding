---
icon: material/table-multiple
---

# :material-table-multiple: Table List

* `ability` - Responsible for defining character abilities/skills for the UI
* `ap_open_rank`
* `ap_tree_*` - Defines the AP (mastery/msp tree) for every character
* `badge` - Defines all the titles
* `badge_note_category`
* `bloom_talk` - Defines bubble speech text when passing near a NPC/Character in story/town
* `break_obj` - Defines rewards on breaking certain `bh` entities
* `bubble_talk_progress`
* `chapter_select` - Defines chapter selection
* `chara` - Defines all characters (mainly ui, characters/entities are vastly hardcoded in this engine and cannot be freely added/removed)
* `chara_color` - Defines color packs for each character
* `chara_costume`
* `chara_diff`
* `chara_drain`
* `chara_exp` - Defines all experience levels for each character
* `chara_exp_type`
* `chara_gem`
* `chara_guest_npc_parameter`
* `chara_invite` - Defines initial stats like level for characters upon invitation/recruitment
* `chara_level_sync` - Defines level sync/power adjustment for use in Quick Quest
* `chara_power_adjust`
* `chara_power_attenuate`
* `chara_status` - Defines character stats for level ranges (interpolated)
* `chara_status_fate` - Defines character stats for level ranges in fate episode (interpolated)
* `chara_str` - All strings used in chara tables (likely important!)
* `chest_reality_lot`
* `collectibles_*`
* `command_list` - Defines the d-pad commands ui in battle, depending on context
* `command_list_chara`
* `command_list_constant`
* `communication_autofixedphrase` - Defines chat text that may appear online automatically
* `communication_charaautofixedphrase` - Defines chat text that characters may say online automatically
* `communication_emotion`
* `communication_fixedphrase` - Defines predefined chat text for online
* `communication_shortcut`
* `communication_stamp` - Defines chat stickers for online
* `constant` - Various game constants, result screen wait times, prologue bahamut rewards based on damage, max transmarvel stock, how many msp required for the next repeat level (at max level), gem mix/sigil synthesis success rates for siero success hint
* `contribution`
* `dialog` - Defines all dialogs in the game
* `dlc` - Defines all dlc contents for each pack
* `dlcpack` - Defines each dlc pack
* `dropcoin_param` - Rupies drop params?
* `enemy` - Defines enemies in the game
* `enemy_exp` - Defines exp levels for each enemy in the game
* `enemy_level`
* `enemy_parts` - Defines part breaking rewards for certain enemies (i.e Pyet-A)
* `enemy_status` - Defines enemy stats per level range (interpolated)
* `enemy_status_easy` - Defines enemy stats per level range for story easy mode
* `enemy_status_extrem` - Defines enemy stats per level range for story extreme mode
* `enemy_status_hard` - Defines enemy stats per level range for story hard mode
* `evaluation` - Defines titles given on battle end
* `facility_continue_voice`
* `facility_voice_condition`
* `facility_voice_list`
* `fate_bgm_table` - Defines background music/bgm to play during fate episodes
* `fate_episode` - Defines fate episodes for each character
* `fate_episode_story`
* `fate_episode_str` All strings used in fate episodes tables (likely important!)
* `filter` - Defines item filtering (ui)
* `filter_category` - Defines item filtering categories (ui)
* `formation_slot` - Defines party formation during certain contexts?
* `gacha` - Defines transmutation levels
* `gacha_lot` - Defines transmutation item rewards
* `gacha_rate_group` - Defines transmutation item group rewards
* `gameover_tips` - Defines Game Over screen tips
* `gem` - Defines sigils aka gems
* `gem_mix` - Unused? Related to sigil synthesis aka gem mix.
* `gem_mix_rupi` - Defines rupie cost of sigil synthesis aka gem mix depending on combined trait level.
* `gem_mix_success` - Defines grand success success rate of sigil synthesis aka gem mix depending on combined trait level.
* `gem_rare`
* `gem_sell` - Defines the sell price of sigils aka gem depending on combined trait level.
* `gem_ticket` - Defines the number knicknack voucher aka ticket earned on sigil aka gem traded depending on combined trait level.
* `hud_mode`
* `information_dialog`
* `information_quest`
* `island` - Defines islands (for ui).
* `item` - Defines all items in the game.
* `item_category` - Defines item categories.
* `item_consume` - Defines items that can be consumed (mostly potions like Green Potion, Blue Potion, as these are also items).
* `item_important` - Defines key items
* `item_junk` - Defines curio aka item junk tiers
* `item_junk_appear_rate` - Defines curio drops
* `item_junk_archive` - Defines story archive notes that can be obtained through curios aka item junk
* `item_junk_rate_group` - Defines curio aka junk tier group drops for each tier
* `item_material_common_anima`
* `item_material_common_boss`
* `item_material_common_special`
* `item_material_common_stage`
* `item_material_list` - Defines items lists needed to upgrade certain items.
* `item_pendulum` - Defines wrightstones aka pendulums
* `item_pendulum_sell` - Defines the sell price of wrightstones aka pendulums depending on combined trait level.
* `item_pendulum_ticket` - Defines the number knicknack voucher aka ticket earned on wrightstones aka pendulum traded depending on combined trait level.
* `item_quest_detail_disp`
* `item_tier_map` - Defines items lists needed to upgrade certain items.
* `karma_value`
* `limit_bonus` - Defines specific character masteries
* `limit_bonus_mediation` - Defines overmastery tiers
* `limit_bonus_mediation_category` - Defines available overmastery types per tiers
* `limit_bonus_mediation_weight` - Defines overmastery level chance per tier
* `limit_bonus_param` - Parameters for each specific character mastery
* `limit_bonus_param_type`
* `limit_bonus_type`
* `loading_lot` - Defines loading screens & their text messages
* `loading_text_random` - Defines loading screens random texts
* `loading_text_ref`
* `loading_view` - Defines loading views
* `lobby_create_menu_comment_steam`
* `lobby_create_menu_playstyle_steam`
* `location` - Defines locations (for ui)
* `matching_setting`
* `matching_setting_menu`
* `matching_setting_toggle`
* `matching_strength_value`
* `menu_unlock` - Defines menu unlocks
* `mob` - Defines enemies (for lyria's story?)
* `ngword_symbols` - Defines swear filter symbols?
* `ngword_whitelist` - Defines swear filter white list?
* `ngwordlist` - Defines ng (not good) word list/swear filter
* `opening` - Defines opening intro staff credits
* `option_*` - Defines options
* `overlay_map`
* `phase`
* `phase_reward`
* `photo_*` - Defines photo mode
* `quest_baseinfo_ex_data` - Defines quest base info extra data (important!)
* `quest_bgm_event_list` - Defines Wwise events for quests
* `quest_bgm_table` - Defines bgms for quests
* `quest_difficulty`
* `quest_overkill_table` - Defines MSP multipliers depending on how much damage was done past a boss's health bar (and how many?)
* `quest_param`
* `quest_rank`
* `result_box_rate`
* `reward` - Defines all rewards in the game
* `reward_demo`
* `reward_geen_rare`
* `reward_item_rare`
* `reward_lot` - Defines all reward groups in the game
* `reward_point`
* `reward_quest_rank`
* `reward_shuffle_lot`
* `saveinfo`
* `skill` - Defines all traits aka skills in the game
* `skill_level_lot`
* `skill_lot`
* `skill_status` - Defines trait aka skill values per level
* `skill_type_lot`
* `sort` - Defines item sorting parameters (for ui)
* `sort_item`
* `special_combat`
* `speedrun_bgm`
* `staffroll` - Defines credits/staff roll
* `staffroll_bgm` - Defines credits/staff roll background music
* `staffroll_lyrics`
* `stagename` - Defines location names per phase id
* `status` - Defines buffs/debuffs aka status (largely hardcoded, mainly used for localization & icon to use)
* `story` - Defines story cutscenes
* `story_note_archive` - Defines lyria's story notes
* `story_note_archive_category`
* `story_note_bgm` - Defines lyria's story BGM/background music
* `story_note_chapter` - Defines lyria's story chapters
* `story_note_picturebook_*`
* `story_note_tips`
* `story_note_tips_category`
* `story_note_wordlist`
* `story_note_wordlist_category`
* `target_task` - Defines town quests?
* `telop_chapter`
* `telop_location`
* `town_treasure_reward` - Defines town treasures/rewards
* `trade` - Defines available siero trades/buyable items
* `trade_refill`
* `trade_shop`
* `treasure_chest` - Defines all chests available through the story
* `trophy` - Defines all ingame trophies
* `tutorial_*`
* `voice_emotion`
* `weapon` - Defines all weapons in the game
* `weapon_exp` - Defines rupie cost per exp level
* `weapon_limit` - Defines weapon uncap levels
* `weapon_skill_level` - Defines weapon skill/trait levels (and depending on whether it's awakened)
* `weapon_status` - Defines weapon stats per level
* `weapon_status_awake` - Defines weapon stats per awakened level
* `weapon_status_level_sync` - Defines weapon stats (for level sync/power adjustment, quick quest)
* `weapon_status_plus`