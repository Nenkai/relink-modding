---
icon: material/progress-download
---

# :material-progress-download: StPr - Streaming Prefetch

`.stpr` files are used to indicate which textures and entities should be preloaded within the specified [quest](../quest_ids.md).

This file is a [FlatBuffer](https://flatbuffers.dev/) file. 

* [Flatbuffer Schema](https://github.com/Nenkai/GBFRDataTools/blob/master/GBFRDataTools.FlatBuffers/StPr_StreamingPrefetch.fbs)

---

## ObjectPreloadRequest

Contains the list of [entities/objects](../re/obj_id.md) that should be loaded.


---

## TexturePreloadRequest

Contains the list of granite textures that should be loaded. Their keys are hashes of granite texture files.

For instance:

```
XXHash64("a929045e256fa2e20c1785c65c09c2f540b09037bceba4df7769a9be95779bd7")
```

Is equal to hash `804BD56EE16E60A1`.