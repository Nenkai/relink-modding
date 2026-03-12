---
icon: material/information-variant
---

# User Defined Params

User defined params is a 16 bytes blob resource stored in the executable (`USER_DEFINED_PARAMS`).

It holds:

* 0x00 - The language (4 bytes)
* 0x04 - Application version (3 bytes, patch/minor/major)
* 0x08 - Display version (3 bytes, patch/minor/major)
* 0x0C - Number of granite tile sets to load (if `0`, load all based on `application version minor * 3` so `1` = load `0.gts` through `6.gts`)

Minor in particular is often used in the code as a feature/system unlock flag (which, do not work without the required files).

## PS Version

On the PS versions, user attributes are located in the `param.sfo` instead.



