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
| Magic/Date            | uint           | Should be `20230729`, **explicitly checked**. Might correspond to a date, 2023/07/09. |
| LODInfos              | [LodInfo](#lodinfo)[]      | Parameters for each lod. Each index corresponds to a `data/model_streaming/lod{number}` entry.
| ShadowLODInfos        | [LodInfo](#lodinfo)[]      | Parameters for each shadow lod. Each index corresponds to a `data/model_streaming/shadowlod{number}` entry.
| A4                    | float          | Unknown. May be related to LOD distance.
| SubMeshes             | [SubMeshInfo](#submeshinfo)[]  | List of submeshes. Addressed by lod infos.
| Materials             | [MaterialInfo](#materialinfo)[] | List of materials used.
| BonesToWeightIndices  | ushort[]       | An array that matches bone indices to weight indices. Any bones not in this list are non-deform.
| DeformBoneBoundaryBox | BBox           | Appears to be a boundary box for every deform bone. Not sure what the purpose of this is.
| A9                    | Vec4           | Unknown.
| A10                   | [Unk_A10](#Unk_A10)        | Unknown. Used very rarely in bgXXXX files
| A11                   | [Unk_A11](#unk_a11)        | Unknown.
| A12                   | float          | Unknown.
| A13                   | float          | Unknown.
| A14                   | float          | Unknown.
| A15                   | float          | Unknown.
| A16                   | float          | Unknown.
| A17                   | float          | Unknown.
| A18                   | float          | Unknown.
| A19                   | float          | Unknown.
| A20                   | float          | Unknown.
| A21                   | byte           | Unknown.
| A22                   | byte           | Unknown.
| A23                   | byte           | Unknown.
| A24                   | byte           | Unknown.
| A25                   | byte           | Unknown.
| A26                   | byte           | Unknown.
| A27                   | byte           | Unknown.
| A28                   | byte           | Unknown.
| A29                   | byte           | Unknown.
| A30                   | byte           | Unknown.
| A31                   | byte           | Unknown.
| A32                   | byte           | Unknown.

---

### LODInfo

Contains information on how to read a specific .mmesh, depending on LOD.

Anything polygon related are in terms of polygons times the number of vertices per polygon.  As all models are made of tris, these can be thought of as polygon index times 3.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| MeshBuffer            | [MeshBufferLocator](#meshbufferlocator) | Location of each mesh buffer.                      |
| Chunks                | [LodChunk](#lodchunk)[]        | Parameters for each lod. Each index corresponds to a `data/model_streaming/lod{number}` entry.
| VertCount             | uint              | Total of vertices for this lod mesh.
| PolyCountX3           | uint              | The number of polygons (times 3) in the entire .mmesh.
| BufferTypes           | byte              | Bitflags determining what mesh buffers are contained in the LOD. 1 = Mesh data (vertex then indices), 2 = Vertex Weight Indices, 8 = Vertex Weights
| A6                    | byte              | Unknown.

---

### MeshBufferLocator

A `.mmesh` is broken into different "buffers".

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| Offset                | uint64            | Offset of the buffer within `.mmesh`.              |
| BoundaryBox           | BBox              | Size of the buffer within `.mmesh`.

---

### LodChunk

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| Offset                | uint              | Beginning polygon index (times 3) for the chunk.   |
| Count                 | uint              | Number of polygons (times 3) in the chunk.
| SubMeshID             | byte              | The index of the submesh the chunk belongs to.
| MaterialID            | byte              | The index of the material the chunk belongs to.
| A5                    | byte           | Unknown.
| A6                    | byte           | Unknown.

---

### SubMeshInfo

All .minfos are comprised of one or more submeshes. These submeshes can be toggled on and off separately.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| Name                  | string            | Name of the sub mesh.                      |
| BoundaryBox           | BBox              | A boundary box for the submesh.

---

### MaterialInfo

Contains all material slots.

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| Hash                  | XXHash32Custom(str) | Unknown String hash. May need to be unique. Also referenced in a few master.evtb files.            |
| A2                    | byte              | Unknown, likely bitflags.

---

### Unk_A10

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| A1                    | XXHash32Custom(str) | Unknown String hash. Not always used.            |
| A2                    | float             | Unknown.
| A3                    | byte             | Unknown.
| A4                    | byte             | Unknown.

---

### Unk_A11

| Field Name            | Type              | Description                                        |
|-----------------------|-------------------|----------------------------------------------------|
| A1                    | int               | Unknown.                                           |
| A2                    | Vec3 (?)          | Unknown.
| A3                    | Vec3 (?)          | Unknown.
