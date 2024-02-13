---
icon: material/application-export
---

# :material-application-export: Model Exporting

!!! note

    Exporting requires Blender knowledge and command line usage.

## Blender Plugin

[GBFRBlenderExporter](https://github.com/WistfulHopes/GBFRBlenderImporter/releases) is required for model exports. Download the latest release of the ***Exporter***, not the ***Importer***.

In Blender:

* In Edit :material-arrow-right: Preferences :material-arrow-right: Add-ons
* Click `Install`
* Select the zip file you just downloaded
* Make sure to tick `Granblue Fantasy Relink Mesh Exporter`.

## Flatbuffers

[Flatbuffers](https://github.com/google/flatbuffers/releases/) is required to edit .minfo files. Download the latest binary for your operating system (e.g. Windows.flatc.binary.zip) and extract it anywhere.

[Model Info - FlatBuffer](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MInfo_ModelInfo.fbs) is also required to edit .minfo files. Download the file and place it in the same folder as FlatBuffers.

[Model Info - Converter](https://gist.github.com/AlphaSatanOmega/fa6fe4160cae91f8037b01534ddc32c1) is also required. Download the file as a zip, extract and place the `MInfo_Converter.py` in the same folder as FlatBuffers. To run, requires any version of [Python 3](https://www.python.org/downloads/) installed.
---

## Exporting

!!! tip

    Currently, the Blender exporter can only be used with existing .minfo files.

In Blender:

* In File :material-arrow-right: Export :material-arrow-right: Granblue Fantasy Relink .minfo
* Select the `.minfo` file of the edited model.

This will create a new `.mmesh` file and a `.json` file. Copy the `.mmesh` file into every LOD folder (`model_streaming\lod0`, `model_streaming\lod1`, etc).

## Converting the MInfo
Now take both the `.json` file exported from Blender, and the original model's `.minfo` and drag both of them onto the `MInfo_Converter.py` in the FlatBuffers folder. 

This will automatically create a converted `.minfo` witth all the mesh info from the blender `.json` and place it in a folder called "`_flatc_conversion`" next to the Blender export. The edited `.json` is also placed there for debugging purposes.

Take this converted `.minfo` and place it into the corresponding `model/<model prefix>/<model name>` folder (i.e. `model/pl/pl1400/`).

---

??? abstract "Manual .minfo Editing"
    
    *NOTE: This section only goes into detail as to how to manually go about editing the MInfo and is completely optional*.

    ## Manually Editing the MInfo
    
    Flatbuffers is a *command-line program* that you need to run under the command prompt (`cmd` or Windows Terminal on Windows).
    
    In the command line, run the following command:
    
    ``` markdown title="Command"
    flatc --json MInfo_ModelInfo.fbs -- <path to minfo file> --raw-binary
    ```
    
    This will create a new JSON file in the Flatbuffers directory. 
    
    Using the Blender exported JSON as a reference, update the JSON in the flatc directory as follows:
    
    * For each entry in LODInfos:
        * Replace `MeshBuffers`, `Chunks`, `VertCount`, `PolyCountX3`, and `BufferTypes` with the ones in the exported JSON.
    * In `SubMeshes`, add any new submeshes to the submesh list by duplicating an existing submesh in the flatc `.json` in the `Submeshes` list, and simply replacing the name.
    
    Back in the command line, run the following command:
    
    ``` markdown title="Command"
    flatc --binary MInfo_ModelInfo.fbs <path to minfo json>
    ```
    
    This will create a .bin file with the same name as your minfo. Change its file extension to .minfo, and copy it to your mod directory. 
