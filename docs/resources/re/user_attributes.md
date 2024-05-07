---
icon: material/information-variant
---

# User Defined Params

User defined params is a 16 bytes blob resource stored in the executable.

It holds:

* 0x00 - The language (4 bytes)
* 0x04 - Application version (3 bytes, patch/minor/major)
* 0x08 - 4 bytes (unused)
* 0x0C - Number of granite tile sets to load - 0 means load all (`version minor * 3` so `v1.1` = load `0.gts` through 6)

Minor in particular is often used in the code as a feature/system unlock flag (which, do not work without the required files).

## PS Version

On the PS versions, user attributes are located in the `param.sfo` instead.



