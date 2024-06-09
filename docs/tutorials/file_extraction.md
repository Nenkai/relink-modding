---
icon: material/export
---

# File Extraction

## :material-folder-text: Game Files

!!! tip
    The game folder can be found under `<Steam Folder>\steamapps\common\Granblue Fantasy Relink`.

You should be able to find the following files/folders:

* `data/` - This is where most sound files are.
* `data.0, data.1, etc.` - **These contain the actual game contents that you will first need to extract.**
* `data.i` - **The index file for the numbered data files, you will extract from them using this file.**

---

## :material-folder-move: Extracting Files

### Requirements

* [.NET 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
* [GBFRDataTools](https://github.com/Nenkai/GBFRDataTools/releases)

---

### Extracting a file

GBFRDataTools is a *command-line program* that you need to run under the command prompt (`cmd` or Windows Terminal on Windows).

1. Download GBFRDataTools and extract it, preferably next to the game executable.
2. Open a Command Prompt (Not in Admin mode) and drag in the GBFRDataTools.exe file, this will path to the tool.
    * !!! note 
        You can press enter to run the program with no commands yet. This will print out the list of commands you can run. Also, you can press the `Up Arrow` on your keyboard to show the previous command you entered.
3. type `extract -i `.
4. Drag in your data.i file located in the Game's install folder: `...\steamapps\common\Granblue Fantasy Relink\data.i`
5. type in ` -f ` and put a path to a game file like `model/pl/pl1400/pl1400.minfo`.
    * Refer to the [Asset Paths](../resources/asset_paths.md) page for finding files.
    * You can also search through `filelist.txt` in the GBFRDataTools folder for file paths.
6. Press enter, this will extract that one specified file.

``` markdown title="Example Command - Extract single file"
"<path to GBFRDataTools>/GBFRDataTools.exe" extract -i "<path to your data.i>" -f "model/pl/pl1400/pl1400.minfo"
```
**Replace `<path to data.i>` to the path to the `data.i` file.**

---

### Extracting all files

If you want to just extract all known files just replace `extract` with `extract-all` and get rid of the `-f command`.

``` markdown title="Example Command - Extract all files"
"<path to GBFRDataTools>/GBFRDataTools.exe" extract-all -i "<path to data.i>"
```
It will take some time to extract all files.
!!! note

    Not *all* files will be extracted, but most. You can see the current progress on the [GBFRDataTools](https://github.com/Nenkai/GBFRDataTools) page.
    
    This is because none of the data files holds the path names for their contents and had to be guessed. If you'd like to contribute, the file list can be found [here](https://github.com/Nenkai/GBFRDataTools/blob/master/GBFRDataTools/filelist.txt), and a file accessor logger can be found [here](https://github.com/WistfulHopes/gbfrelink.utility.filenamelogger)

---

### Extracting all files matching filter

If you want to mass extract files from paths that contain a certain string, run `extract-all` with `-f "put matching string here"` on the end.

``` markdown title="Example Command - Extract all files containing 'pl1400' in the path"
"../GBFRDataTools.exe" extract-all -i "<path to data.i>" -f "pl1400"
```
or
``` markdown title="Example Command - Extracts all .wtb files"
"../GBFRDataTools.exe" extract-all -i "<path to data.i>" -f ".wtb" 
```

!!! note
    You can put `-o "<Path to a folder>"` at the end of the commands to extract the files to a specified folder.

---

### :octicons-video-16: Video Tutorial
<video controls>
    <source src="../GBFR_Data_Tools_Extract_Model_Files.mp4" type="video/mp4">
</video>

---

## Additional Information

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


