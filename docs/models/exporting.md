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

[Model Info - FlatBuffer](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MInfo_ModelInfo.fbs) is also required to edit .minfo files. Download the file and place it in the same folder as Flatbuffers.

---

## Exporting

!!! tip

    Currently, the Blender exporter can only be used with existing .minfo files.

In Blender:

* In File :material-arrow-right: Export :material-arrow-right: Granblue Fantasy Relink .minfo
* Select the `.minfo` file of the edited model.

This will create a new `.mmesh` file and a `.json` file. Copy the `.mmesh` file into every LOD folder (`model\lod0`, `model\lod1`, etc).

## Editing the MInfo

Flatbuffers is a *command-line program* that you need to run under the command prompt (`cmd` or Windows Terminal on Windows).

In the command line, run the following command:

``` markdown title="Command"
flatc --json MInfo_ModelInfo.fbs -- <path to minfo file> --raw-binary
```

This will create a new JSON file in the Flatbuffers directory. 

Using the Blender exported JSON as a reference, update the JSON in the flatc directory as follows:

* For each entry in LODInfos:
    * Replace `MeshBuffers`, `Chunks`, `VertCount`, `PolyCountX3`, and `BufferTypes` with the ones in the exported JSON.
* In `SubMeshes`, add any new submeshes to the submesh list by copying an existing submesh and replacing the name.

Back in the command line, run the following command:

``` markdown title="Command"
flatc --binary MInfo_ModelInfo.fbs <path to minfo json>
```

This will create a .bin file with the same name as your minfo. Change its file extension to .minfo, and copy it to your mod directory. 
