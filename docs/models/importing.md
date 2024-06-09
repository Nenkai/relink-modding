---
icon: material/application-import
---

# :material-application-import: Model Importing

!!! note

    Importing requires some prior Blender knowledge.

## Installing the Blender Add-on

### Requirements:

* [Blender (3.5 or Higher)](https://www.blender.org/download/)
* [GBFR Blender Tools](https://github.com/WistfulHopes/GBFRBlenderTools/releases) is required for importing models from the game.
* [FlatBuffers - Windows.flatc.binary.zip](https://github.com/google/flatbuffers/releases)

### Installation:

1. Download and the `io_gbfr_blender_tools.zip` file from GitHub.
2. In blender go to `Edit` :material-arrow-right: `Preferences` :material-arrow-right: `Add-ons`
3. Click `Install...` in the top right.
4. Drag in the `io_gbfr_blender_tools.zip` file and install it.
5. Toggle on the checkbox for the `Granblue Fantasy Relink Blender Tools` add-on.
6. In the addon's prefences, set the filepath to the FlatBuffers `flatc.exe` file.
7. Close the preferences window.

---

## Importing

1. **Make sure you have the `.minfo`, `.skeleton`, and `.mmesh` for a model all in the same folder together to be able to import them.**
    
    !!! tip
        * You can learn how to extract files [here](../tutorials/file_extraction.md).
        * Check out [Entity Prefixes](../resources/entity_prefixes.md#models) for a list of model prefixes.
        * Check out [Model IDs](../resources/model_ids.md) to find a certain model's ID.
        * Model heads are split into their own files.
        * `.minfo` and `.skeleton` files are found under `model/<model prefix>/<model id>/`.
        * `.mmesh` files are found under `model_streaming/lod0/`.
    
2. Go to `File` :material-arrow-right: `Import` :material-arrow-right: `Granblue Fantasy Relink (.minfo)`
3. Drag in the model's `.minfo` file and press the `Import` button.
4. Done! Some models may fail to import currently, please open an issue to let us know by opening an issue on GitHub.

!!! warning "Textures"

    :material-arrow-right: Refer to the [Model Textures (Granite)](../tutorials/textures/texture_extraction.md#model-textures-granite) section on the Texture Extraction page for getting model textures.
    
    Textures must be manually applied to the model in blender.

---

## :octicons-video-16: Video Tutorial

<video controls>
    <source src="../GBFR_Blender_Model_Import.mp4" type="video/mp4">
</video>

---

## Tool Shelf 

### (Press `N` in the `3D View` to open the tool shelf, then click the `GBFR` Tab)

* :material-texture-box: `Split Mesh along UVs:` Prevents the textures from looking warped in areas on export. (Makes sure to separate vertices that are shared among 2 separate UV islands).
* :material-sphere: `Sort Materials:` Sorts the order of the materials list so it should be close enough to how they import. Helps with stopping materials from going invisible when out of order.
* :material-vector-triangle: `Limit & Normalize Weights:` Limits all vertex weights to 4 groups and normalizes them.
* :material-vector-triangle: `Translate Bones:` Allows you to switch between the GBFR bone names and Unity/Blender standard bone names.
* :material-vector-triangle: `Separate by Materials:` Separates the model's main mesh into several meshes, one for each material. Also renames them to the material names.
* :material-vector-triangle: `Join all meshes:` Joins all the model's meshes into 1 mesh.
* :material-vector-triangle: `Select Zero Weight Vertices:` Selects all vertices that are not connected to any bones. Exporting with 0 weight vertices fails, so this prevents this highlights the unweighted vertices for you to deal with.
* :material-vector-triangle: `Flip Normals:` Flips the facing of selected geometry in edit mode, so if the model appears inside out, you can flip the facing so it's right-side out.
* :material-vector-triangle: `Remove Doubles:` Joins vertices that are very close together but not joined.
* :material-sphere: `Materials Section:` Use this section to set the material indices of the materials that will correlate with the materials listed in the `.mmat`s.