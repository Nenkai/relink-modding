---
icon: material/file-music
---

# :material-file-music: Audio Playback/Conversion

Relink uses AudioKinetic's [Wwise](https://www.audiokinetic.com/en/wwise/overview/) as its Audio Middleware for playback and file formats. It is generally a pain to deal with both for extraction and creation of new audio.

There are two distinct proprietary formats:

* `.bnk` - These contain instructions on how to play audio, but *does not necessarily contain audio by themsleves* (except for `_m` banks). You can most of these in the `data/sound` folder of the game.
* `.pck` - Contains actual sounds. You can *not* simply extract these and play them. You will need to process them through *Wwiser*, and will specifically be located in the `sound` folder.

---

## :material-folder-text: Requirements

* Game files extracted beforehand. 
* [foobar2000](https://www.foobar2000.org/), Music player.
* [vgmstream](https://github.com/vgmstream/vgmstream/releases/), Get `.fb2k-component` file. This is a plugin for foobar2000.
* [Python 3](https://www.python.org/downloads/), Required for Wwiser.
* [Wwiser](https://github.com/bnnm/wwiser), Used to process `.bnk` files.
* [QuickBms + wwise_pck_extractor.bms + BnkExtr](BnkExtr_QuickBms.zip), Used to extract `.pck` files and `.bnk` containing audio if you need it.
* [wwnames.txt](wwnames.txt) (Right-click Save), Names for each Wwise 'event', to tell sound files apart. This file has been manually created after reverse-engineering.

Install foobar2000 + plugin, extract the rest in the same folder, make sure to place `wwnames.txt` next to Wwiser.

## :material-speaker-play: Playing Audio

You should make a copy of the `data/sound` folder away from the game, and merge the extracted `sound` folder with it so that you have both `.pck` and `.bnk` files.

1. Drag and drop one or more `.pck` files to `extract_pck.bat`. This should create a `wem` folder with `wem` files.
2. Open `wwiser.pyz`. Hit **Load banks** to load `.bnk` files (or **Load dirs** to load ALL `.bnk` in a folder). Load `Init.bnk` before any other banks. Wait until the files have loaded.
3. Hit **Generate TXTP**. This will create a `txtp` folder with each file containing instruction on how to play every Wwise event.
4. Drag the folder or individual txtp files to *foobar2000*. 

!!! tip
    
    You should mark `.txtp` files to always open with foobar2000.

---

## Additional Information

All this wouldn't have been possible without bnnm's tools and time spent on audio reverse-engineering!

### Wwise Information

* [How Wwise Works](https://github.com/bnnm/wwiser/blob/master/doc/WWISER.md)
* [Ripping Wwise Games](https://github.com/bnnm/wwiser-utils/blob/master/doc/RIPPING.md)
* [Reversing Wwise Names](https://github.com/bnnm/wwiser-utils/blob/master/doc/NAMES.md)

### Wwise, Relink & Other Details

* Every character that speaks has an associated sound & `lipsync` file found in the `sound/lipsync` folder. These were used to reverse the Wwise event names.
* For some reason, `YellowTown` = Folca, `RedTown` = Seedhollow.
* Character emotes/motions and their linked files are defined in their `<entity>_<id1>_<number>_seq_edit_se.xml` file i.e `np/np0300/np0300_3040_0_seq_edit_se.xml`.
* Audio playback through FSM happens using `SoundTriggerAction`, `SoundOneVelAutoTriggerAction` (and potentially more).
* The `.wem` files contain a file name (except for certain packs), but aren't necessarily the *event*'s.
