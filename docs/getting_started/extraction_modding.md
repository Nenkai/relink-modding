---
icon: material/export
---

# Getting Started

Welcome to the world of GBFR Modding! This is where we will go over the basics for modding the game.

## :material-folder-text: Game Files

!!! tip
    The game folder can be found under `<Steam Folder>\steamapps\common\Granblue Fantasy Relink`.

You should be able to find the following files/folders:

* `data/` - This is where most sound files are.
* `data.i/X` - **These contain the actual game contents that you will first need to extract.**

In order to do so, install [.NET 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0), download [GBFRDataTools](https://github.com/Nenkai/GBFRDataTools/releases) and extract it preferably next to the game executable.

---

## GBFRDataTools

### :material-folder-move: Extracting Files

GBFRDataTools is a *command-line program* that you need to run under the command prompt (`cmd` or Windows Terminal on Windows).

In order to extract most game files, run it as such:

``` markdown title="Command"
GBFRDataTools.exe extract-all -i <path to data.i> 
```

**Replace `<path to data.i>` to the path to the `data.i` file.**

It will take some time to extract.

!!! note

    Not *all* files will be extracted, but most. You can see the current progress on the [GBFRDataTools](https://github.com/Nenkai/GBFRDataTools) page.
    
    This is because none of the data files holds the path names for their contents and had to be guessed. If you'd like to contribute, the file list can be found [here](https://github.com/Nenkai/GBFRDataTools/blob/master/GBFRDataTools/filelist.txt), and a file accessor logger can be found [here](https://github.com/WistfulHopes/gbfrelink.utility.filenamelogger)

---

### :material-folder-plus: Modding

??? abstract "Method 1: Using Mod Manager"

    :material-arrow-right: Refer to the [Mod Manager Page](mod_manager.md).

??? abstract "Method 2: Modding Manually"

    !!! warning

        It is important that you create a backup of `data.i` first. If you do not have one, you can verify game files integrity on Steam.


    To add or update contents, simply add them to the `data` folder. **You should preserve the same paths.**

    !!! example

        If you want to mod `system/table/ability.tbl`, drop it to the `data` folder as such:
        ```{ .sh .no-copy }
        .
        ├─ data/ # Always preserve game paths
        │  └─ system/
        │     └─ table/
        │        └─ ability.tbl
        │
        ...
        ```

    Then run the following command:
    ``` markdown title="Command"
    GBFRDataTools.exe add-external-files -i <path to data.i> 
    ```

    !!! note

        If you are editing or adding files, you must re-run the command! You may also need to restore your original `data.i` if you've removed a file that was previously registed and wish to restore it.

If you have successfully gotten your mod to work, congratulations!

---

??? abstract "Inner Workings"

    *NOTE: This section only goes into detail as to how it all works and is completely optional*.

    #### New Files

    The `data.i` file is an index file. It holds all the information about the game's contents inside numbered `data` files. It is split in two types of content:

    * Content *inside* archive files such as `data.0`, `data.1` and so on.
    * Content *outside* archive files such as the sound files initially present inside the `data` folder.

    For some more notes:

    * `data.i` is a FlatBuffer file. The schema has been [fully reverse-engineered](https://github.com/Nenkai/GBFRDataTools/blob/master/GBFRDataTools/Entities/IndexFile.fbs).
    * All file paths are hashed using [XXHash64](https://github.com/Cyan4973/xxHash). Files are compressed using [LZ4](https://en.wikipedia.org/wiki/LZ4_(compression_algorithm)).
    * The XXHash seed can be provided by the index file. It is set to 0 by default.
    * All file hashes are ordered by their value for binary searching. Same for their descriptors within the index file, making it impossible to guess paths based on their order   inside data files.
    * When modding, GBFRDataTools simply marks existing or new files as external files.
    * `data.2` is hardcoded to not be used.


