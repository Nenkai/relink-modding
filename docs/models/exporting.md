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

* [Flatbuffers](https://github.com/google/flatbuffers/releases/) is required for exporting models. Download the latest binary for your operating system (e.g. Windows.flatc.binary.zip) and extract it anywhere.
* Once extracted, in the Blender Add-On Preferences window and expand the exporter add-on. At the bottom put in the path to the FlatBuffers `flatc.exe`.

---

## Exporting

In Blender:

* In File :material-arrow-right: Export :material-arrow-right: Granblue Fantasy Relink .mmesh
* Choose the path to export the mesh to. Make sure you have a copy of the original model's `.minfo` in this folder.
    * Do not have the original `.skeleton` or `.mmesh` in this folder, they will be overwritten.
* The exported model will be placed in a new folder where you exported to called "_Exported_MInfo".

This export will create a new set of `.minfo`, `.mmesh`, and `.skeleton` files, as well as a `.json` file. The `.json` file is only for debugging purposes.
To put the model into the game's files, copy the `.mmesh` file into every LOD folder (`model_streaming\lod0`, `model_streaming\lod1`, etc). Also copy the exported `.minfo` into the corresponding model's folder (`model\<model type>\<model name>`). If you have modified the model's skeleton, copy it to the model's folder too.
