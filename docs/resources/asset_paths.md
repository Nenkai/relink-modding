---
icon: material/file-tree
hide:
  - toc
  - footer
---

# :octicons-rel-file-path-16: File Tree/Asset Paths


!!! tip
    Entity folders are omitted, refer to [Entity Prefixes](entity_prefixes.md).

```{ .sh .no-copy }
.
├─ cloth/    # Unknown.
├─ curve/    # Unknown.
│
├─ effect/   # Location of all model effects.
│  ├─ cubemap/                    # Unknown.
│  ├─ primitive/                  # Unknown.
│  ├─ savedata/                   # Effect (est) files used per model.
│  ├─ texture/                    # Unknown.
│  ├─ vectorfield/                # Unknown.
│  ├─ vertexanimationtextures/    # Unknown.
│  └─ <model_id>.bxm              # Binary XML, links model IDs to effect (savedata) files.
│
├─ fasttravel/       # Fast Travel Definitions.
│  └─ fasttravelpoint.msg
│
├─ filter/           # Environment filters, per phase.
│  ├─ p{phase_id}/       # Phase folder.
│  └─ release/           # Release folder.
│
├─ font/         # Font textures & glyph definitions.
├─ granite/      # Granite SDK Tile Sets - Textures for most models in the game.
│  ├─ 2k/            # 1080p
│  └─ 4k/            # 4k
│
├─ layout/           # Layout setup for each phase & more.
├─ localibl/         # Image-based lighting (IBL) textures
│  ├─ {uuid[0]}{uuid[1]}.wtb        # Depends on 'mUuid' from layout, specifically 'LocalIBLSceneObject' scene objects.
│  └─ irradiance/
│     └─ {uuid[0]}{uuid[1]}_irradiance.wtb
│
├─ model/        # Model metadata for each model.
│  └─ {type}/           # Model type.
│     └─ {model_id}/       # Model Id.
│        ├─ vars/                  # Material Variations (i.e per color pack)
│        │  └─ {index}.mmat            # Material.
│        ├─ {model_id}.minfo       # Model Info, links the model to meshes and materials.
│        ├─ {model_id}.skeleton    # Model Skeleton/Bones.
│        └─ {model_id}.sop         # Unknown. Might be script/physics based control.
│
├─ model_streaming/       # Model meshes for streaming.
│  ├─ lod{number}/             # LODs. Referenced by .minfo.
│  │  └─ {model_id}.mmesh           # Model Mesh data.
│  └─ shadowlod{number}/       # Shadow LODs. Referenced by .minfo.
│     └─ ...
│
├─ ph{first_digit}/   # Phases. Phases control how stages (st) are loaded. 
│  |                  # Folder is always the first hex digit of the full 3 numbers.
│  └─ ph{all_digits}/      # All phases.
│     ├─ {phase_id}.lst       # List of all files linked to this phase folder.
│     └─ {phase_id}_sub.bxm   # Binary XML. Describes player spawn position & stages to load.
│
├─ quest/   # Quests.
│  └─ {quest_id}/    # Per-quest folder (hex number).
│     ├─ baseinfo.msg       # Contains both display information & other important quest data.
│     └─ sectionlist.msg    # Unknown.
│
├─ shader/   # Shaders.
├─ skycube/  # Per-phase skycubes.
├─ sound/    # All game sounds in wwise format - se, bgm, voices & more.
│
├─ st{first_digit}/   # Stages. Stages are effectively maps, loaded by phases.
│  |                  # Folder is always the first hex digit of the full 3 numbers.
│  └─ r{all_digits}/       # Stage Room.
│     ├─ r{stage_id}.col         # Collision.
│     ├─ r{stage_id}.list        # List of all files linked to this phase folder.
│     ├─ r{stage_id}.occl        # Occlusion data.
│     ├─ r{stage_id}_se.sar      # Sound metadata.
│     └─ r{stage_id}_soundfx.sar # Sound metadata.
│
├─ system/   # System data. Databases, FSM/scripts, character data & loads more.
│  ├─ behaviorparam/             # FSM Behavioral data (mainly for map objects) 
│  │  behaviortree/              # FSM Behavioral Tree, controls how certain enemies (or other) 
│  │  │                          # behave with some of their attacks & more.
│  │  │  
│  │  ├─ playerai/                   # AI Behavior tree data.
│  │  └─ {model_id}/                 # Entity Behavior tree data.
│  ├─ breakobject/               # Breakable map object data.
│  │  ├─ data/
│  │  │  └─ {model_id}_param.msg         # Breakable object data for each model. Hp, Recovery & more.
│  │  └─ breakobjectlist.msg         # List of all breakable object entities.
│  ├─ breakrelationship/         # Unknown. Data is per stage room.
│  ├─ camera/                    # Camera data. Default, per-move, contextual & more.
│  ├─ cloud/                     # Clouds data.
│  ├─ decal/                     # Map decal textures.
│  ├─ enemy/                     # Enemy parameters (stats, move stats, ability & everything else)
│  │  ├─ emcountermanagerparam.msg      # Unknown.
│  │  └─ {model_id}/             # Enemy data.
│  ├─ event/                     # Unknown.
│  ├─ finishcamera/              # Camera data when "finishing" the boss, per enemy.
│  ├─ fogboard/                  # Unknown.
│  ├─ foliage/                   # Unknown.
│  ├─ fsm/                       # Finite State Machine/Scripts. Controls most logic in the game.
│  ├─ grandcypher/               # Unknown.
│  ├─ ibl/                       # Image-based lighting. Unknown.
│  ├─ ies/                       # Unknown.
│  ├─ input/                     # Input parameters. Mainly vibration.
│  ├─ lighttex/                  # Unknown.
│  ├─ noise/                     # Unknown.
│  ├─ npc/                       # NPC Motion metadata (?)
│  ├─ objread/                   # Maps object ids to model ids. Very important, it tells what assets should be loaded per object-id.
|  ├─ player/                    # Player data. TODO
|  ├─ preset/                    # Quest presets for guest players/npcs.
|  ├─ scenario/                  # Unknown.
|  ├─ streaming_prefetch/        # Unknown.
|  └─ table/                     # Database Tables & Game Text/Localization.
│     ├─ scenario/                   # Story/Scenario sentences/voice-lines data & localization.
│     ├─ text/                       # General text localization.
│     ├─ voice/                      # Unknown.
│     ├─ voice_text/                 # Unknown.
│     └─ *.tbl                       # Database tables.
│
├─ texture/    # Non-streamed model textures.
├─ timeline/   # Unknown.
└─ ui/         # Refer to below.
...
```

## UI Paths

!!! tip

    Remove `fhd\` for the 4k version.

```{ .sh .no-copy }
ui/
├─ atlas/         # General texture atlases/spritesheets.
│  │  <lang>/         # Spritesheets that contain text which are localized.
│  │  ├─ common_icon_lb               # Unknown.
│  │  ├─ common_icon_main             # Unknown.
│  │  ├─ common_number                # Unknown.
│  │  ├─ common_window                # "New Grade!"
│  │  ├─ hud_emmode                   # "OVERDRIVE"
│  │  ├─ hud_ex_chracter              # Tweyen HUD
│  │  ├─ hud_linklevel                # "Link Time", "Linked!" "Ready"
│  │  ├─ hud_num_battle               # "Overkill!"
│  │  ├─ hud_plparameter              # "Level Up!"
│  │  ├─ pause_challengemission       # "Completed!"
│  │  ├─ pause_limitbonus             # "Over Mastery Bonuses"
│  │  ├─ pause_note                   # "Cleared!"
│  │  ├─ pause_pause_common           # "SKIN", "New Fate Episode!"
│  │  ├─ quest_quest_common           # "Skill", "CLEARED"
│  │  ├─ result_result_background     # "Battle Results"
│  │  ├─ result_result_trial          # Score Mode "New Record", "Battle Results", "Cleared"
│  │  ├─ shop_shop_common             # "Sold Out"
│  │  ├─ shop_ticket                  # "Trade unwanted items for Knickknack Vouchers!"
│  │  ├─ shop_zathba_appraisal        # "Appraised!"
│  │  ├─ telop_timeup                 # "Time's Up"
│  │  └─ telop_upgrade                # "Success!!", "Awakened!!" "New Level Cap!!" & 3 more
│  │
│  ├─ blacksmith_weapon       # Blacksmith UI.
│  ├─ common_button_system    # Default controller buttons/ui.
│  ├─ common_button_tab01     # Tab menu (i.e Overmastery tab buttons)
│  ├─ common_cursor_action01  # Quest cursor
│  ├─ common_cursor_mission   # Quest objective cursor
│  ├─ common_entrance         # Notification
│  ├─ common_icon_ability     # Character abilities icons
│  ├─ common_icon_equip       # Sigil/Weapon icons
│  ├─ common_icon_item        # Item icons, masks & overlay
│  ├─ common_icon_lb          # Mastery tree & Overmastery icons
│  ├─ common_icon_lb02        # Mastery tree & Overmastery icons (#2)
│  ├─ common_icon_main        # General UI icons
│  ├─ common_icon_mini        # Character avatars (top left) & dialog reaction icons
│  ├─ common_icon_save        # Saving icon (bottom right)
│  ├─ common_icon_skill       # Sigil trait (aka skill) icons
│  ├─ common_icon_stamp       # Stickers (aka stamps) icons
│  ├─ common_icon_status      # Buff icons
│  ├─ common_icon_text        # Inventory icons
│  ├─ common_mission          # Quest hud
│  ├─ common_number           # Number textures (not damage) - refer to hud_num_battle
│  ├─ common_subtitle01       # Unknown
│  ├─ common_tips_command     # Unknown
│  ├─ common_win_cut          # Event dialogue window textures/overlays
│  ├─ common_win_talk         # Character dialog bubbles
│  ├─ common_win_voice        # Unknown
│  ├─ common_window           # General window frames/overlays/icons
│  ├─ end_credit_em7700_staff_roll_mini  # Lucilius staff roll textures
│  ├─ end_credit_staff_roll   # Staff roll textures
│  ├─ hud_bonus               # Unknown
│  ├─ hud_chainchance         # Chaining textures (clock, etc)
│  ├─ hud_communication       # Chat (communication) frames/textures/overlays
│  ├─ hud_compass             # Compass (top) icons
│  ├─ hud_emparameter         # Unknown (enemy related)
│  ├─ hud_ex_bahamut          # Bahamut control parameters
│  ├─ hud_ex_chracter         # Character-specific hud
│  ├─ hud_ex_gun              # Cannon/gun textures
│  ├─ hud_ex_tank             # Tayu'itar/tank/mech textures
│  ├─ hud_gauge_contents      # Gauges/lucilius labors icons
│  ├─ hud_guide_ability       # Enemy gauges & more
│  ├─ hud_guide_action        # Unknown
│  ├─ hud_guide_command       # Battle Command (skill) HUD textures
│  ├─ hud_guide_dead          # Battle Critical/Death textures
│  ├─ hud_guide_item          # Battle Items textures
│  ├─ hud_guide_status        # Unknown
│  ├─ hud_information         # Info textures (i.e notifs, char level up)
│  ├─ hud_linklevel           # Link time textures
│  ├─ hud_num_battle          # Damage number textures
│  ├─ hud_object_em           # Unknown (lock-on texture & others?)
│  ├─ hud_plname              # Level-up texture
│  ├─ hud_plparameter         # Character status textures (top left)
│  ├─ hud_trialbattle         # Practice mode HUD textures
│  ├─ loading_loading01       # Loading icon textures
│  ├─ loading_loading02       # Loading background textures
│  ├─ pause_background        # Pause Menu background
│  ├─ pause_background02      # Pause Menu background (#2)
│  ├─ pause_challengemission  # Unknown
│  ├─ pause_controller        # Unknown
│  ├─ pause_frame             # Pause menu HUD frame (top left)
│  ├─ pause_item              # Inventory item description frames
│  ├─ pause_limitbonus        # Limit bonus (overmastery) HUD
│  ├─ pause_multi_setting     # Pause Menu multiplayer/co-op settings HUD
│  ├─ pause_note              # Lyria's Journal HUD
│  ├─ pause_options           # Settings HUD
│  ├─ pause_party             # Party Menu HUD
│  ├─ pause_pause_common      # Pause menu general HUD
│  ├─ pause_pause_stage       # Unknown
│  ├─ pause_preset            # Pause menu character frames (& labels)
│  ├─ pause_skilltree         # Skill Tree general icons
│  ├─ pause_top               # Pause Menu icons & notification frames
│  ├─ quest_chapter_select    # Story quest chapter HUD
│  ├─ quest_quest_common      # Quest Rank Icons & others
│  ├─ quest_quest_fate        # Fate Episode Hud
│  ├─ quest_quest_point       # Quest HUD (unknown)
│  ├─ quest_quest_select      # Quest Selection frames
│  ├─ quest_quest_top         # Quest Main Menu textures & frames
│  ├─ result_evaluation       # Result Screen HUD
│  ├─ result_result_background  # Result Screen Background
│  ├─ result_result_commom    # Result Screen Icons
│  ├─ result_reward           # Result Screen Reward frame/background
│  ├─ shop_awake              # Weapon Awakening HUD
│  ├─ shop_background         # Siero/Trade HUD Background
│  ├─ shop_frame              # Siero/Trade HUD Frame
│  ├─ shop_gene               # Siero/Trade Transmute HUD
│  ├─ shop_mix                # Siero/Trade Sigil Synthesis (Gem Mix) HUD
│  ├─ shop_shop_common        # Siero/Trade General HUD
│  ├─ shop_ticket             # Siero/Trade Vouchers HUD
│  ├─ telop_bossbattle        # Unknown
│  ├─ telop_chapter           # Chapter Frames/Background/Mask
│  ├─ telop_gameover          # Game Over Background
│  ├─ telop_questclear        # Quest Clear anim textures (?)
│  ├─ telop_queststart        # Unknown
│  ├─ telop_trialbattle       # Practice Mode Leaderboard numbers
│  ├─ telop_upgrade           # Upgrade anim/textures (?)
│  ├─ title_data_slot         # Save Load HUD
│  ├─ title_news              # Game News HUD
│  ├─ title_player_setup      # Captain Gender Select HUD
│  ├─ title_title             # Title Screen HUD
│  ├─ worldmap_wmap_img_st00  # Ainsteddo Archipelago West map textures
│  ├─ worldmap_wmap_img_st01  # Ainsteddo Archipelago East map textures
│  ├─ worldmap_wmap_img_st02  # Northern Crystal Line map textures
│  ├─ worldmap_wmap_img_st03  # Leautagne Island map textures
│  ├─ worldmap_wmap_img_st04  # Dahli Island map textures
│  ├─ worldmap_wmap_img_st05  # Phondam, the Scarred Isles map textures
│  ├─ worldmap_wmap_img_st06  # Almerain Island map textures
│  ├─ worldmap_wmap_img_st07  # Pilar of Vayoi map textures
│  ├─ worldmap_wmap_img_st08  # The Forgotten Sky map textures
│  ├─ worldmap_wmap_img_st09  # The Final Vision
│  └─ worldmap_worldmap01     # Unknown
│
├─ data/          # Links windows to their assets 
├─ fonts/         # Font & their material definitions for prefabs
├─ layouts/       # Defines all windows (layouts) in the game
│  ├─ blacksmith     # Blacksmith Window
│  │  ├─ code            # Unknown
│  │  ├─ gene            # Sigils (Gems)
│  │  └─ weapon          # Weapons
│  │     └─ noatlastextures
│  │        ├─ bs_wpn_cra_cloud_scroll01      # Unknown
│  │        ├─ bs_wpn_cra_ringflare01_add     # Unknown
│  │        └─ bs_wpn_{model_id}              # Spritesheet for every weapon which are upgradable
│  │
│  ├─ common     # Common Window
│  │  ├─ button_system          # Unknown
│  │  ├─ button_system_win32    # Buttons (Windows)
│  │  │  └─ noatlastextures
│  │  │     ├─ icons for every key
│  │  ├─ button_tab01           # Unknown
│  │  ├─ chara_plprm            # Character Dialogue Avatars
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_chrprm_{model_id}_{num}
│  │  ├─ chara_voice            # Character Dialogue/Voice Avatars (for dialogues)
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_chrvo_{model_id}_{num}
│  │  ├─ cursor_action01        # Unknown
│  │  ├─ cursor_mission         # Unknown
│  │  ├─ entrance               # Unknown
│  │  ├─ entrance_win32         # Unknown
│  │  ├─ icon_item              # Unknown
│  │  ├─ icon_main              # Unknown
│  │  ├─ icon_save              # Unknown
│  │  ├─ icon_status            # Unknown
│  │  ├─ icon_text_win32        # Keyboard Keys
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_ictxt01
│  │  ├─ image_article          # Item Images Backgrounds
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgarticle_{unk}_{gender}_{num}
│  │  ├─ image_article          # Lyria's Journal Enemy Backgrounds
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgbook_{model_id}_{num}
│  │  ├─ image_capture          # Misc Location & Story Moment Screenshots
│  │  │  └─ noatlastextures
│  │  ├─ image_chain            # SBA Chain Images
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgchain_{model_id_number}
│  │  ├─ image_chain            # SBA Chain Images
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgchain_{model_id_number}
│  │  ├─ image_chami            # NPC Images (for side quests)
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgchm_{mob_id}
│  │  ├─ image_chapter          # Story Chapter Images
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgcpt_{num}_{gender}
│  │  ├─ image_chara            # Character Images
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgchr_{model_id_number}
│  │  ├─ image_chrcolor         # Character Color Preview
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgcol_{model_id}_c{color_num}
│  │  ├─ image_equip(_s)        # Equipped Item Textures (Weapons, Awakened Effects, Sigil Shapes)
│  │  │  └─ noatlastextures
│  │  ├─ image_fate             # Fate Episode Images
│  │  │  └─ noatlastextures
│  │  │     ├─ cmn_imgfate_frame01
│  │  │     ├─ cmn_imgfate_mask01
│  │  │     └─ cmn_imgfate_{model_id_number}_{ep_number}_{img_number}
│  │  ├─ image_gene             # Sigil Shapes
│  │  ├─ image_item             # All Item Textures & Frames
│  │  ├─ image_mainstory        # Story Scenario Images
│  │  │  └─ noatlastextures
│  │  │     └─ cmn_imgmain_{scenario_id}_{gender}
│  │  ├─ image_news             # News Screen Images
│  │  ├─ image_quest            # Quest Location Images
│  │  ├─ image_word             # Lyria's Journal Location & Other Images
│  │  ├─ info_cmn               # Unknown
│  │  ├─ mission                # Unknown
│  │  ├─ subtitle01             # Unknown
│  │  ├─ win_cut                # Unknown
│  │  ├─ win_talk               # Unknown
│  │  ├─ win_voice              # Unknown
│  │  ├─ window                 # Unknown
│  │  └─ window_win32           # Unknown
TODO
...
```