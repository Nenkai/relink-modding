---
icon: material/music-note-plus
---

# :material-music-note-plus: Audio Creation

!!! tip

    It is recommended to read the [Audio Playback Page](audio_extraction.md) before proceeding.

!!! warning

    BGMs (or stuff inside `.pck` are not supported yet), if you know how to edit these, reach out!


---

## :material-folder-text: Requirements

* Everything mentioned in the [Audio Playback Page](audio_extraction.md)
* [WWise](https://www.audiokinetic.com/en/download/) (ugh). Make an account, get the launcher, install Wwise. **You only need the Authoring Package** for Windows. Untick anything else.
* [wwiseutil](https://github.com/hpxro7/wwiseutil/releases), used to edit `.bnk`

---

## :material-new-box: Creating `.wem` files

You will need `.wav` files ahead of time.

??? abstract "Easy Method - sound2wem"

    Get [sound2wem](https://github.com/EternalLeo/sound2wem). Specifically the `zSound2wem.cmd` file. Put it next to the other utilities such as Wwiser.

    Then simply run the following command:

    ```batch
    zSound2wem.cmd <wav file>
    ```

    This will convert your `.wav` file to `.wem`.

??? abstract "Other Method - Using Wwise directly (higher control)"

    This part uses Wwise directly in case you need more control over the `.wem` output.

    * On the left side (Project Explorer), Head to **ShareSets** :material-arrow-right: Conversion Settings :material-arrow-right: Default Work Unit :material-arrow-right: **Default   Conversion Settings**.
    * Set the first row's *Format* to **Vorbis**.
    * ++shift+i++ to bring up the Audio Importer
        * Alternatively, head to Project Explorer again, Audio :material-arrow-right: Interactive Music Hierarchy, Right-Click & Import Audio Files.
    * From there, import any audio files.
    * In Audio :material-arrow-right: Interactive Music Hierarchy :material-arrow-right: Default Work Unit, you should be able to see your files. From there you can edit some of the   parameters such as *volume* if needed.
    * ++shift+c++ to convert the file.
    * Head to Documents & `WWISE\WwiseProjects\<PROJECT NAME>\.cache\Windows\SFX\`. Wem files will be located there.

---

## Locating which files to edit

If you did not generate `.txtp` files for playback, it is highly recommended you do so first through Wwiser.

Open the target `.txtp` file and inspect the first few lines - you should be able to find the wems that are used for a certain event.

For most part when looking at characters you'll be looking at the banks that end with `_m.bnk`.

## Editing `.bnk`

1. Open `wwiseutil` and the `.bnk` file linked to audio you would like to edit.
2. Find `Id` column that matches. Hit **Replace** and select your `.wem` file you created earlier.
3. Hit **Save**. Make sure to select `SoundBank file (*.bnk)`.
4. Bank is ready for the game.

!!! tip
    You can also use [FusionTools](https://www.nexusmods.com/mafiadefinitiveedition/mods/98) or [RingingBloom](https://github.com/Silvris/RingingBloom) for this process.

---

Credits to korone for establishing the [first guide](https://www.bilibili.com/read/cv33210537) (Chinese).