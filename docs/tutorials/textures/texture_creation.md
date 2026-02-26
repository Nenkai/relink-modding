---
icon: material/image-plus
---

# :material-texture: Creating Textures

## New Method (GBFRDataTools)

Using GBFRDataTools, you can create textures aswell as rebuild, or create texture atlases from scratch.

NOTE: Currently all textures are converted to BC7 when not using `.dds`. If you need finer control, use your own `.dds` files. (Texconv is used for this process, which may not be compatible with linux)

### Building WTBs

You can provide a standard image (`.png`, will be converted using BC7_UNORM), or a `.dds` (properties will be kept, you are free to create it however you want using i.e Compressonator, Intel Texture Works, Paint.NET plugin, etc)

You may pass `--no-mipmaps`, which you **should**, for UI textures since those don't need mipmaps.

Provide a folder to batch convert multiple images to a wtb for each one of them.

```
GBFRDataTools img-to-png -i <input/folder> [--no-mipmaps]
```

### RE-Building Texture Atlas

You can also build texture atlas, which are used for UI textures. This scenario is for i.e editing a single texture in a texture atlas.

The texture atlas details will be picked from the `.tex.yaml` file, which should have been created when drag-dropping the original `.tex.texb` into GBFRDataTools.

```
GBFRDataTools img-to-png -i <.tex.texb file path>
```

### Building Texture Atlas from scratch

You can also build texture atlas, which are used for UI textures. This scenario is for whenever you ACTUALLY need a new texture atlas into the game.

The texture atlas will be generated, you just have to provide a folder that contains pngs/dds files.

```
GBFRDataTools img-to-tex-atlas -i <folder>
```

### Old Method - Nier CLI

1. Download [Nier CLI](https://github.com/ArthurHeitmann/nier_cli/releases/tag/v1.3.0_mgrr). This program is used to convert `.wtb` texture files to a standard viewable image format, or into `.wtb`.
2. Create a new folder named `<YOUR_FILE_NAME>.wtb_extracted`. `<YOUR_FILE_NAME>` should be replaced with the output texture file name you want. The `.wtb_extracted` at the end of the folder is important.
3. Create and/or add one or multiple `.dds` files to the folder.
4. Drag the folder into the `Nier CLI` executable. **This will overwrite any `.wtb` file if any already exists with the same name.**