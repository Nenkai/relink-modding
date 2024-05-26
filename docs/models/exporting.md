---
icon: material/application-export
---

# :material-application-export: Model Exporting

!!! note

    Exporting requires basic knowledge of how to use Blender.

## Blender Add-on

Make sure you have the [GBFR Blender Tools Add-on](../models/importing.md#installing-the-blender-add-on) installed.

---

## Exporting

!!! Warning
    Exporting still has some issues and you are likely to encounter many issues.

1. **Make sure you create a folder to export to, and place a copy of the model's original `.minfo` in that folder.**
    * **Do not place any of the other `.skeleton` or `.mmesh` files in this folder, they will be overridden!**
2. Ensure your model is set up according to the [Exporting Checklist](#exporting-checklist).
3. Go to `File` :material-arrow-right: `Export` :material-arrow-right: `Granblue Fantasy Relink (.mmesh)`
4. Name the model to the same name as the `.minfo` (i.e. Should be `pl1400.mmesh` for `pl1400.minfo`)
5. Press the `Export` button and wait.
6. Done! Your exported model's generated `.minfo`, `.mmesh`, and `.skeleton` files can be found in the `_Exported_Minfo` folder created where you exported to.

!!! info
    To check for errors in the export you can re-import the exported file.

---

### :material-texture: Exporting Textures

By this point you must be wondering how to export textures for the game *without* using granite. This is done by editing the [Material Set](../resources/formats/mmat.md) (`.mmat`) file.

* Get [FlatBuffers / flatc](https://github.com/google/flatbuffers/releases), which you should already have if you already imported models. Extract it.
* Get the [FlatBuffer MMat schema](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MMat_ModelMaterial.fbs). Schemas are used to tell `flatc` how to read and write the material files.
* Run the following command to convert the `.mmat` file into a human readable `.json` file:

``` { .yaml .annotate }
flatc --json --strict-json -- <path_to_fbs_file> --raw-binary <path_to_mmat_file>
```

!!! tip

    `<path_to_fbs_file>` should be the path to the `.fbs` file and `<path_to_mmat_file>` should be the path to the `.mmat` file.

* You should now have a `.json` file next to the original `.mmat` file. Open it in a text editor (preferably something like [Notepad++](https://notepad-plus-plus.org/downloads/)).

* Scroll down to `granite_params`. **Remove the entire section**. 

??? example

    Section to remove:
    
    ```json
    "granite_params": {
        "page_file": [
          "f46ebc1f33247b5ba4448a428b107edcdc0f4b0451f06b3701615823a41c94e9"
        ],
        "layer_to_shader_map_name_hash": [
          "g_AlbedoMap",
          "g_NormalMap",
          "g_Mask1",
          "g_Mask2"
        ],
        "unk4": 4,
        "unk5": 1,
        "tile_set_number": 1
    },
    ```

Now, inside the `texture_maps` section, you will see all the textures associated to each material map. As you've removed the granite section, your textures will need to be put in the following folders (if they aren't already there):

* 4k: `texture/4k/{name}.texture`
* 2k: `texture/2k/{name}.texture`

These textures files are simply `.wtb` files with a different extension. Follow [this simple guide](../extraction/texture_creation.md) to create `.wtb` files. Change your `.wtb` extension to `.texture` once that's done.

!!! note
    DDS files are required beforehand.

---

## :octicons-checklist-16: Exporting Checklist

This list is subject to change as model exporting changes and is more fully understood.

* The model must have an armature and a mesh.
* The model can only have 1 Mesh object, you must join all meshes together.
* Each material must be assigned a material index using the addon's [Tool Shelf Panel](../models/importing.md#tool-shelf). These indices correspond with the materials list found in the model's `.mmat` files.
* The mesh cannot have any vertices with zero vertex group weights assigned to it. Use the `Select Zero Weights` button in the GBFR tool shelf panel to select them. It is up to you to deal with them via weight painting, deleting, etc.
* The armature's bone names must match to the GBFR Bone Index names if they are to be animated. Use an original game model to see the naming scheme of humanoid bones (TODO: Create viewable bone name list).
* The armature must be pointed upwards on the Z-Axis. Remember to `CTRL+A > All Transforms` to apply all transforms on the Armature.
* Models can only have 1 UV Map.
* The GBFR Model format has a limit of 65535 total vertex group weights. Your model should have a reasonable amount of bones to accomodate this, if not merge the bones down.
* Bone collection/group names can only contain alphanumeric characters, no special characters (i.e. Japanese characters)

---

## Other

??? abstract "Known Export Issues, Requirements, and Fixes"
    
    ### Issues & Fixes

    * Parts of the model are invisible in game:
        * Each material must be assigned a material index using the addon's [Tool Shelf Panel](../models/importing.md#tool-shelf). These indices correspond with the materials list found in the model's `.mmat` files.
    * Parts of the model are transparent in game: 
        * Your mesh's normals are there are inverted, flip / recalculate your normals for affected areas.
    
    ### Old issues that should now be fixed automatically

    * Model's Geometry Explodes:
        * This is caused due to having any loose vertices/edges. To fix this, select the mesh and press the `Delete Loose Verts & Edges` button in the GBFR panel.
    * UVs look weird/distorted:
        * You must split the geometry along all outer Edges of the UV islands. Press the `Split Vertices`: `Along UV Islands`.
    * Model is rotated 90 degrees forward:
        * Exported All Transforms for the model and Armature must be applied before export. Select all objects and press `CTRL+A > All Transforms` to do this.
    * Parts of the mesh are stretching and not really following the bones:
        * You need to limit your total Vertex Group weights to `3`, then `Normalize All` your weights your weights.
            * This is automatically applied by the exporter on export. If it didn't work, parts of your mesh are missing weights, you can't have any geometry with 0 weight.
    
    ### Other

    * You can add bones to the armatures, but there is no guaruntee they will animate properly.
