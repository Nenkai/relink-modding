# AI Created Mods

Since the majority of mods fail to disclose heavy AI usage for creation, we unfortunately keep a list here for informational purposes.

!!! warning
    
    **We do not endorse or recommend any of these mods.**

    Feel free to review the code (if possible, if it is readable).

    The majority of the ones not disclosing AI use are based on educated guesses (in the case of mods with missing source code, analysis after decompilation).

:material-history: Last Updated: `Aug. 17, 2026`

| Name                               | Source       | Elements | Extra Notes/Evidence |
|------------------------------------|--------------|----------|-------------|
| [Attack sigils overhaul](https://www.nexusmods.com/granbluefantasyrelink/mods/696?tab=files) || Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Beatrix - Devour Causality Duration Configurable](https://www.nexusmods.com/granbluefantasyrelink/mods/714) || Undisclosed source code | No AI disclosure. Embeds an entire msg pack byte patcher `MsgPatcher` implementation instead of simply converting to and from json using the usual library. Also embeds `system/player/parameter/pl2600/pl2600_parameter.msg` in the executable instead of simply reading it from its mod folder or the game itself..
| [Buff Timer Indicator V2 for ALL Characters](https://www.nexusmods.com/granbluefantasyrelink/mods/810) | [Source Code](https://github.com/Dangoooooo613/GBFR_BuffTimerIndicator) | Source Code | Readme, [whatever this is](https://github.com/Dangoooooo613/GBFR_BuffTimerIndicator/blob/main/src/gbfr_overlay_qt_v6.py)
| [Captain Substitute Mastery Improved](https://www.nexusmods.com/granbluefantasyrelink/mods/714) || Undisclosed source code | Oddly named classes `StandaloneSkillboardFieldCoordinator`, improper use of interfaces - uses reflection to fetch `GetModdedOrAchiveFile` instead of calling the method directly..?
| [Character Voice Mixer](https://www.nexusmods.com/granbluefantasyrelink/mods/637) || Header, Source code | No disclosure. Code base overly verbose and oddly worded. [Example](https://github.com/GattoLand/GBFRCharacterVoiceMixer/blob/5ddaeb7ed24a7ef596d088d16cbc94fd55ce1d12/gbfrelink.voice.mixer.core/NativeBattleContextProvider.cs#L66-L88)
| [Chat Overlay - Enhance Chat and Voice](https://www.nexusmods.com/granbluefantasyrelink/mods/789) | [Source Code](https://github.com/cajoxorize366-oss/GBFR.ChatOverlay) | Header, Source code | Explicit disclosure. **Illegally uses the Playfab Party Voice APIs, which might come at a direct extra cost for Cygames.**
| [Configurable vouchers and transmarvels multipliers](https://www.nexusmods.com/granbluefantasyrelink/mods/615) || Header, Undisclosed source code | AI generated header, This mod also embeds an original game file in its dll file to alter it and apply it to the game, instead of shipping it aside. Contains an entire unused PE (.exe) file header scanner for some reason.
| [Configurable Mastery Point Multiplier](https://www.nexusmods.com/granbluefantasyrelink/mods/635) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Conflux Fast Auto-Advance](https://www.nexusmods.com/granbluefantasyrelink/mods/793) || | Explicit AI usage disclosure (mod tag).
| [Damage Cap Status Display](https://www.nexusmods.com/granbluefantasyrelink/mods/791) || Undisclosed source code | Explicit AI usage disclosure (mod tag). | Absolutely of the code logic is contained within Mod.cs. Uses heavy hooks with hardcoded offsets that will break between updates. [Nonsensical diagnostic messages.](../images/dnSpy_Ro7AsVWJQM.png)
| [EndlessMission BGM Broadcast CN](https://www.nexusmods.com/granbluefantasyrelink/mods/788) || Undisclosed source code | No AI disclosure. Logging messages show excessive use of semicolons and other nonsensical logging messages `[SUB] position source = wall-clock (GetPlayingSegmentInfo unavailable).`
| [Eustace - Dark Lightning (Experimental) (Vibecoded)](https://www.nexusmods.com/granbluefantasyrelink/mods/743) | [Source Code](https://github.com/KuroAllios/GBFR.Eustace.DarkLightning) || "THIS ENTIRE PROJECT IS VIBECODED. ENTIRELY. I DON'T KNOW C# AT ALL. AND LEFT IT TO SOL AUTORUN TO HANDLE EVERY SINGLE THINGS IN THIS REPO. HIGHLY EXPERIMENTAL AND I HAVE 0 IDEA ABOUT WHAT I AM DOING."
| [Expand Terminus Trait selection](https://www.nexusmods.com/granbluefantasyrelink/mods/762) || | Explicit AI usage disclosure (mod tag).
| [Extra Sigil Slots](https://www.nexusmods.com/granbluefantasyrelink/mods/657) || Header, Source code | No AI disclosure. Readme on Github: "Native architecture and refactor plan", "Smoke-test harnesses"
| [Fediel Effects Recolored (Experimental)](https://www.nexusmods.com/granbluefantasyrelink/mods/741) || Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [GBFR Auto Shoutout Suite](https://www.nexusmods.com/granbluefantasyrelink/mods/776) || Undisclosed source code | Strangely named classes: `RelinkGuardLocator`, `CurrentProcessRelinkMemoryReader`, `RelinkExecutablePreflight` and logging messages ""Relink required-byte/RVA preflight failed for {label} at RVA 0x{rva}"
| [gbfr-ultrawide](https://github.com/zhen469891/gbfr-ultrawide) || Source code | Claude usage on Github.
| [GBFR World Auto Director / GBFR Beelzebub Auto Director / GBFR Lucifer Auto Director](https://www.nexusmods.com/granbluefantasyrelink/mods/813) || Readme, Undisclosed source code | Hijacks the game's FSM component elements on the engine side instead of the game's FSM enemy script files directly?? Indecipherable intent behind code, awkward logging messages
| [GBFR PE Patch Tool](https://www.nexusmods.com/granbluefantasyrelink/mods/584) | [Source](https://github.com/BitterG/GBFR-PE-Patch-Tool) | Readme, Source code, **Main executable obfuscated using mlkem despite source code** | Claude usage on Github.
| [GBFR Team DPS Meter](https://www.nexusmods.com/granbluefantasyrelink/mods/662) || Undisclosed source code (Github but only compiled release) | Disclosure on Github.
| [gbfr-logs DLC compatibility (awa Edition)](https://www.nexusmods.com/granbluefantasyrelink/mods/596) || Source code | 'Codex' branch on Github.
| [gbfr-logs Cleista fork](https://github.com/Cleista/gbfr-logs/) || Source code | No AI disclosure, nonsensical & verbose comments. AI tends to fabricate comments responding to the intent behind prompt answers as opposed to actually document code in a meaningful manner. [Example](https://github.com/Cleista/gbfr-logs/blob/3291b0a2399e7a0b09294613141398466eb2bde9/src/assets/enemy-merge-groups.ts#L2-L6).
| [Gear UI Mouse Control (Experimental)](https://www.nexusmods.com/granbluefantasyrelink/mods/755) | [Source Code](https://github.com/KuroAllios/GBFR.MouseControl) | Source Code | Explicit AI usage disclosure (mod tag).
| [Granblue Effects Changer (AI)](https://www.nexusmods.com/granbluefantasyrelink/mods/756) | [Source Code](https://github.com/KuroAllios/GBFR.ESTColorStudio) | Source Code | "100% AI Coded."
| [Guaranteed Terminus and Behemoth sigil drops](https://www.nexusmods.com/granbluefantasyrelink/mods/636) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Id Fourfold Vengeance No Interrupt CD](https://www.nexusmods.com/granbluefantasyrelink/mods/735) || Undisclosed source code | No AI disclosure. Logging messages leaning towards AI usage 4/6 messages using a semicolon.
| [Interface SFX Mixer](https://www.nexusmods.com/granbluefantasyrelink/mods/649) || Source code | No disclosure. Overall layout, code does not use `Mod.cs`, logging messages.
| [Infinity Full Assist Unlock](https://www.nexusmods.com/granbluefantasyrelink/mods/655) || Source code | No AI disclosure. Source code has tests (?), unnecessarily verbose
| [Infinite Repeat and Skip Loot ER Update](https://www.nexusmods.com/granbluefantasyrelink/mods/816) || Undisclosed source code | No AI disclosure. [Reinvents the wheel: `MemoryPatchManager` instead of using Reloaded II APIs](../images/dnSpy_RepeatSkipLoot.png)
| [Maglielle Aim Assist - Cascading Tremolo Auto Tracking](https://www.nexusmods.com/granbluefantasyrelink/mods/761?tab=files) || Source code | Explicit AI usage disclosure (mod tag). Undisclosed source code.
| [Maglielle Bladedance Auto Horming](https://www.nexusmods.com/granbluefantasyrelink/mods/799) || Undisclosed source code | Fully native mod (not C# for some reason). Strange logging messages: `"POLICY|behavior=spawn_and_attach|target_loss=freeze|mode_selection=none\n`, `RETRY|attempt=%u|reason=transient_install_failure`
| [Maglielle Crux third mastery blance](https://www.nexusmods.com/granbluefantasyrelink/mods/800) || Undisclosed source code | Same reason as 'Maglielle Bladedance Auto Horming'
| [Moveset Swapper](https://www.nexusmods.com/granbluefantasyrelink/mods/715?tab=files) || Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Perfect dodge window bump with options](https://www.nexusmods.com/granbluefantasyrelink/mods/607) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Perfect Guard window bump with options](https://www.nexusmods.com/granbluefantasyrelink/mods/646) || Header, Undisclosed source code | Explicit AI usage disclosure 
| [QoL Ultima Sigils Combination](https://www.nexusmods.com/granbluefantasyrelink/mods/680) || Header | AI generated header, no disclosure.
| [REALTIME CHARA SWAP](https://www.nexusmods.com/granbluefantasyrelink/mods/647) || Readme, Undisclosed source code | "REALTIME SWAP BY F8 MADE BY AI SO I DONT CARE ABOUT ANYTROUBLE"
| [Relink Logs (gbfr-logs fork)](https://www.nexusmods.com/granbluefantasyrelink/mods/688) || Source code | Explicit AI "assisted" usage disclosure (bottom of mod description). The vast majority of it is still AI driven than assisted.
| [Relink Multiplier](https://www.nexusmods.com/granbluefantasyrelink/mods/695) || Undisclosed source code | No AI disclosure. Code has lots of redundant code to perform operations that Reloaded-II already offers such as an entire code cave builder and memory protection changes. AI would have no awareness of this despite being documented on Reloaded-II's website, thus built its own. Author has blocked some users from commenting after disclosure concerns.
| [Rosetta Rose Range Buff](https://www.nexusmods.com/granbluefantasyrelink/mods/801) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Seofon Tag Team combo helper.](https://www.nexusmods.com/granbluefantasyrelink/mods/768?tab=files) || Undisclosed source code | Strangely named class names: `TagTeamActionAliasPolicy`, `LocalControlGatePolicy`, `CriticalRegionPolicy`, nonsense & excessive use of semicolons in logging messages: `Combo C is disabled at startup; no scan controller or native-gate hook was installed.`, `Local SP201 field coordinator remains disabled: `
| [Siegfried Dragonsbane Pulse VI will not be cleared.](https://www.nexusmods.com/granbluefantasyrelink/mods/773) || Undisclosed source code | not using ANY `Reloaded.Hooks` apis, reimplemented hooks and code caves manually, aswell as virtual allocation manually, questionably.
| [Sigil Search](https://www.nexusmods.com/granbluefantasyrelink/mods/614) || Readme, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Sigil Picker](https://www.nexusmods.com/granbluefantasyrelink/mods/702) | [Source Code](https://github.com/Evoyn/gbfer-sigils-picker) | Source Code | Explicit AI usage disclosure (mod tag).
| [Smart Synthesis](https://www.nexusmods.com/granbluefantasyrelink/mods/602) || Header, Undisclosed source code | Incoherent and overly verbose logging messages in code i.e `" (post-shuffle result site, overrides list[0]/list[1])"`
| [Summon Drop Picker](https://www.nexusmods.com/granbluefantasyrelink/mods/677) || Header, Source code | Explicit AI usage disclosure (mod tag).
| [Tool to Modify all your damage number fonts](https://www.nexusmods.com/granbluefantasyrelink/mods/764) | [Source Code](https://github.com/Dangoooooo613/GBFR_DamageFont_ModMaker) | Source Code | Undisclosed AI usage. Github readme format + generated `docs` folder.
| [Unrestricted Party](https://www.nexusmods.com/granbluefantasyrelink/mods/783) | | Source Code | Undisclosed AI usage. Weird classes: `RttiEvidence`, `FunctionPointerEvidence`, `CompatibilityVerifier` & error messages: `The local game-string hash implementation failed its empty-key self-test.`
| [Ultima Sigils](https://www.nexusmods.com/granbluefantasyrelink/mods/661) || Header
| [Wrightstone Picker](https://www.nexusmods.com/granbluefantasyrelink/mods/682) || Source code | Explicit AI usage disclosure (mod tag).
| [YequModmanager](https://www.nexusmods.com/granbluefantasyrelink/mods/623) || Undisclosed source code **Obfuscated**, **Encryption code** | Manager is built in an extremely "businessy/enterprise-grade" manner (`IExtensionBackgroundServiceProviderV2`, `IModDeploymentModePreparationTransaction`). The main executable has obfuscated classes, some of which performing encryption related tasks and other dubious Windows API calls. Mod author has deleted some messages on their Nexus mod page regarding disclosure.