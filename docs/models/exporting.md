---
icon: material/application-export
---

# :material-application-export: Model Exporting

!!! note

    Exporting requires basic knowledge of how to use Blender.

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

??? abstract "Known Export Issues, Requirements, and Fixes"

    ## To check for errors in the export you can re-import the exported file.
    
    ### Issues & Fixes
    * Model's Geometry Explodes:
        * There is currently an issue with the exporter that if you edit all of the faces of the model in some way (merging verts by distance), that the mesh will explode.
        * If you're doing significant edits, you need to keep at least 1 face of every material of the original mesh intact and untouched. You can just store these faces scaled down inside the model.
    * Only 1 mesh is allowed on the exported model, so join all meshes together by selecting them all and Pressing `CTRL+J`.
    * Parts of the model are invisible in game:
        * You must keep the original order of Materials in the Materials tab. Compare it to when you first imported the model and sort accordingly.
    * Parts of the model are transparent in game:
        Your mesh's normals are there are inverted, flip / recalculate your normals for affected areas.
    * UVs look weird/distorted:
        * Due to an Exporter issue, you must split the geometry along all outer Edges of the UV islands. Best way to do this is select the outer edges of the UV islands, mark them as seams, then in the 3D view select all the seams and Split by selected.
    
    ### Old issues that should now Auto fix
    * Model is rotated 90 degrees forward:
        * Exported All Transforms for the model and Armature must be applied before export. Select all objects and press `CTRL+A > All Transforms` to do this.
            * This is automatically applied to the mesh before export
    * Parts of the mesh are stretching and not really following the bones:
        * You need to limit your total Vertex Group weights to `3`, then `Normalize All` your weights your weights.
            * This is automatically applied by the exporter on export. If it didn't work, parts of your mesh are missing weights, you can't have any geometry with 0 weight.
    
    ### Other
    * You can add bones to the armatures, but there is no guaruntee they will animate properly.
