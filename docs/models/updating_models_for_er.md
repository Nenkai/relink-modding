---
icon: material/update
---

# :material-update: Model Mods and Endless Ragnarok

Endless Ragnarok has made some shader changes that requires material files (`.mmat`) files to be updated, as they contain constant buffers & shader parameters used for shaders. If you do not do this, models may appear darker than they should.

**This cannot be automated as certain mods may have made legitimate changes to these constant buffers.**

The mesh and model are however completely reusable and require no editing.

## For Users

You *can* right-click the Mod Manager in Reloaded-II, press 'Configure' and turn on "Auto-Upgrade .mmat constant buffers".

!!! WARNING

	This is a last resort option and may break other model mods. Preferably seek to use updated mods.

	This forces mods to match with original model data.

	There may still be issues regarding certain mods.

## For Modders

### Solution 1: Use a mod loader configuration to automatically force update constant buffers

This is a mod loader feature. You can instruct the mod loader to force a modded material file to match the constant buffers present in an original model file. **(Note: this applies to the mod loader version to be released alongside the DLC)**.

!!! WARNING

    Only use this if you did not previously alter constant buffers voluntarily (i.e for extra shader values tuning).

	There may still be issues if the original model has had shader parameter changes.

In your modded folder, create `GBFR/config/material_config.json`. Here is a sample file:

```json
{
	"force_match_constant_buffer_file_list": [
		"model/fp/fp1600/vars/0.mmat",
		"model/pl/pl1600/vars/0.mmat"
	]
}
```

This will force `model/fp/fp1600/vars/0.mmat` and `model/pl/pl1600/vars/0.mmat` to be updated based on the original models.

### Solution 2: Diff the material files and apply the changes manually

This is the more manual solution if you need a more fine-grained way of verifying constant buffers, incase you previously updated these on your own.

* First, convert your modded `.mmat` file to json as well as the original from Endless Ragnarok. You can use [this section](exporting.md#materials) to do this.
* Next, use a program such as [WinMerge](https://winmerge.org) to compare both material files (original to modded).

Your goal from here is to copy constant buffer data from the original to the modded such that it matches. You may aswell copy other elements such as shader params if you feel like, for accuracy.