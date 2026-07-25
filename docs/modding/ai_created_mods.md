# AI Created Mods

Since the majority of mods fail to disclose heavy AI usage for creation, we unfortunately keep a list here for informational purposes.

!!! warning
    
    **We do not endorse or recommend any of these mods.**

    Feel free to review the code (if possible, if it is readable).

    The majority of the ones not disclosing AI use are based on educated guesses (in the case of mods with missing source code, analysis after decompilation).

| Name                               | Source       | Elements | Extra Notes/Evidence |
|------------------------------------|--------------|----------|-------------|
| [gbfr-ultrawide](https://github.com/zhen469891/gbfr-ultrawide) || Source code | Claude usage on Github.
| [GBFR PE Patch Tool](https://www.nexusmods.com/granbluefantasyrelink/mods/584) | [Source](https://github.com/BitterG/GBFR-PE-Patch-Tool) | Readme, Source code, **Main executable obfuscated using mlkem despite source code** | Claude usage on Github.
| [gbfr-logs DLC compatibility (awa Edition)](https://www.nexusmods.com/granbluefantasyrelink/mods/596) || Source code | 'Codex' branch on Github.
| [Smart Synthesis](https://www.nexusmods.com/granbluefantasyrelink/mods/602) || Header, Undisclosed source code | Incoherent and overly verbose logging messages in code i.e `" (post-shuffle result site, overrides list[0]/list[1])"`
| [Perfect dodge window bump with options](https://www.nexusmods.com/granbluefantasyrelink/mods/607) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Sigil Search](https://www.nexusmods.com/granbluefantasyrelink/mods/614) || Readme, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Configurable vouchers and transmarvels multipliers](https://www.nexusmods.com/granbluefantasyrelink/mods/615) || Header, Undisclosed source code | AI generated header, This mod also embeds an original game file in its dll file to alter it and apply it to the game, instead of shipping it aside. Contains an entire unused PE (.exe) file header scanner for some reason.
| [YequModmanager](https://www.nexusmods.com/granbluefantasyrelink/mods/623) || Undisclosed source code **Obfuscated**, **Encryption code** | Manager is built in an extremely "businessy/enterprise-grade" manner ("IExtensionBackgroundServiceProviderV2", "IModDeploymentModePreparationTransaction"). The main executable has obfuscated classes, some of which performing encryption related tasks and other dubious Windows API calls. Mod author has deleted some messages on their Nexus mod page regarding disclosure.
| [Configurable Mastery Point Multiplier](https://www.nexusmods.com/granbluefantasyrelink/mods/635) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Guaranteed Terminus and Behemoth sigil drops](https://www.nexusmods.com/granbluefantasyrelink/mods/636) || Header, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Sigil Search](https://www.nexusmods.com/granbluefantasyrelink/mods/614) || Readme, Undisclosed source code | Explicit AI usage disclosure (mod tag).
| [Character Voice Mixer](https://www.nexusmods.com/granbluefantasyrelink/mods/637) || Header, Source code | No disclosure. Code base overly verbose and oddly worded. [Example](https://github.com/GattoLand/GBFRCharacterVoiceMixer/blob/5ddaeb7ed24a7ef596d088d16cbc94fd55ce1d12/gbfrelink.voice.mixer.core/NativeBattleContextProvider.cs#L66-L88)
| [Perfect Guard window bump with options](https://www.nexusmods.com/granbluefantasyrelink/mods/646) || Header, Undisclosed source code | Explicit AI usage disclosure 
| [REALTIME CHARA SWAP](https://www.nexusmods.com/granbluefantasyrelink/mods/647) || Readme, Undisclosed source code | "REALTIME SWAP BY F8 MADE BY AI SO I DONT CARE ABOUT ANYTROUBLE"
| [Interface SFX Mixer](https://www.nexusmods.com/granbluefantasyrelink/mods/649) || Source code | No disclosure. Overall layout, code does not use `Mod.cs`, logging messages.
| [Infinity Full Assist Unlock](https://www.nexusmods.com/granbluefantasyrelink/mods/655) || Source code | No AI disclosure. Source code has tests (?), unnecessarily verbose/'enterprise-like' code ("AssistModeUnlockPolicy", "BuildVerificationStatus", "BuildIdentity", "FullAssistGatePolicy", ...)
| [GBFR Team DPS Meter](https://www.nexusmods.com/granbluefantasyrelink/mods/662) || Undisclosed source code (Github but only compiled release) | Disclosure on Github.
| [Ultima Sigils](https://www.nexusmods.com/granbluefantasyrelink/mods/661) || Header
| [Extra Sigil Slots](https://www.nexusmods.com/granbluefantasyrelink/mods/657) || Header, Source code | No AI disclosure. Readme on Github: "Native architecture and refactor plan", "Smoke-test harnesses"
| [Wrightstone Picker](https://www.nexusmods.com/granbluefantasyrelink/mods/682) || Source code | Explicit AI usage disclosure (mod tag).
| [QoL Ultima Sigils Combination](https://www.nexusmods.com/granbluefantasyrelink/mods/680) || Header | AI generated header, no disclosure.
| [Summon Drop Picker](https://www.nexusmods.com/granbluefantasyrelink/mods/677) || Header, Source code | Explicit AI usage disclosure (mod tag).
| [Relink Logs (gbfr-logs fork)](https://www.nexusmods.com/granbluefantasyrelink/mods/688) || Source code | Explicit AI "assisted" usage disclosure (bottom of mod description). The vast majority of it is still AI driven than assisted.
| [Relink Multiplier](https://www.nexusmods.com/granbluefantasyrelink/mods/695) || Undisclosed source code | No AI disclosure. Code has lots of redundant code to perform operations that Reloaded-II already offers such as an entire code cave builder and memory protection changes. AI would have no awareness of this despite being documented on Reloaded-II's website, thus built its own. Author has blocked some users from commenting after disclosure concerns.