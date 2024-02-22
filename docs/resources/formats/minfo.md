---
icon: material/axis-arrow-info
---

# Model Info - .minfo

`.minfo` is the main file for any model. It describes how many lods a model has, the materials to use, how to read the `.mmesh` file buffer & more.

This file is a [FlatBuffer](https://flatbuffers.dev/) file. 

* [Flatbuffer Schema](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MInfo_ModelInfo.fbs)
* [010 Editor Template](https://github.com/Nenkai/010GameTemplates/blob/main/Cygames/Granblue%20Fantasy%20-%20Relink/MInfo_ModelInfo.bt)

## Header

| Field Name            | Type           | Description                                        |
|-----------------------|----------------|----------------------------------------------------|
| magic                 | uint           | Should be `20230729`, **explicitly checked**. Might correspond to a date, 2023/07/09. |
| lods                  | [StreamLOD](#streamlod)[]      | Parameters for each lod. Each index corresponds to a `data/model_streaming/lod{number}` entry.
| ShadowLODInfos        | [StreamLOD](#streamlod)[]      | Parameters for each shadow lod. Each index corresponds to a `data/model_streaming/shadowlod{number}` entry.
| a4                    | float          | Unknown. May be related to LOD distance.
| sub_meshes            | [SubMeshInfo](#submeshinfo)[]  | List of submeshes. Addressed by lod infos.
| materials             | [MaterialInfo](#materialinfo)[] | List of materials used.
| bones_to_weight_indices | ushort[]       | An array that matches bone indices to weight indices. Any bones not in this list are non-deform.
| deform_bone_boundary_box | BBox           | Appears to be a boundary box for every deform bone. Not sure what the purpose of this is.
| vec4_9                | Vec4           | Unknown.
| a10                   | [Unk_A10](#Unk_A10)        | Unknown. Used very rarely in bgXXXX files
| vec3_11               | Vec3           | Unknown.
| float12               | float          | Unknown.
| float13               | float          | Unknown.
| float14               | float          | Unknown.
| float15               | float          | Unknown.
| float16               | float          | Unknown.
| float17               | float          | Unknown.
| float18               | float          | Unknown.
| float19               | float          | Unknown.
| float20               | float          | Unknown.
| byte21                | byte           | Unknown.
| byte22                | byte           | Unknown.
| bool23                | bool           | Unknown.
| bool24                | bool           | Unknown.
| bool25                | bool           | Unknown.
| bool26                | bool           | Unknown.
| bool27                | bool           | Unknown.
| bool28                | bool           | Unknown.
| bool29                | bool           | Unknown.
| bool30                | bool           | Unknown.
| bool31                | bool           | Unknown.
| bool32                | bool           | Unknown.

---

### StreamLOD

Contains information on how to read a specific .mmesh, depending on LOD.

Anything polygon related are in terms of polygons times the number of vertices per polygon.  As all models are made of tris, these can be thought of as polygon index times 3.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| mesh_buffers          | [MeshBufferLocator](#meshbufferlocator) | Location of each mesh buffer.                      |
| chunks                | [LodChunk](#lodchunk)[]        | Parameters for each lod. Each index corresponds to a `data/model_streaming/lod{number}` entry.
| vertex_count          | uint              | Total of vertices for this lod mesh.
| poly_count_x3         | uint              | The number of polygons (times 3) in the entire .mmesh.
| buffer_types          | byte              | Bitflags determining what mesh buffers are contained in the LOD. 1 = Mesh data (vertex then indices), 2 = Vertex Weight Indices, 8 = Vertex Weights
| a6                    | byte              | Unknown.

---

### MeshBufferLocator

A `.mmesh` is broken into different "buffers".

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| offset                | uint64            | Offset of the buffer within `.mmesh`.              |
| BoundaryBox           | BBox              | Size of the buffer within `.mmesh`.

---

### LodChunk

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| offset                | uint              | Beginning polygon index (times 3) for the chunk.   |
| count                 | uint              | Number of polygons (times 3) in the chunk.
| sub_mesh_id           | byte              | The index of the submesh the chunk belongs to.
| material_id           | byte              | The index of the material the chunk belongs to.
| a5                    | byte           | Unknown.
| a6                    | byte           | Unknown.

---

### SubMeshInfo

All .minfos are comprised of one or more submeshes. These submeshes can be toggled on and off separately.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| name                  | string            | Name of the sub mesh.                      |
| bbox                  | BoundaryBox       | Boundary box for the sub mesh.                     |

---

### MaterialInfo

Contains all material slots.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| unique_name_hash      | XXHash32Custom(str) | Unknown String hash. May need to be unique. Also referenced in a few master.evtb files.            |
| unk_flags             | byte              | Unknown, likely bitflags.

---

### Unk_A10

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| unk_id                | XXHash32Custom(str) | Unknown String hash. Not always used.            |
| a2                    | float             | Unknown.
| a3                    | byte             | Unknown.
| a4                    | byte             | Unknown.

