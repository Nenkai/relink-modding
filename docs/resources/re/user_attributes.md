---
icon: material/information-variant
---

# User Defined Params

User defined params is a 16 bytes blob resource stored in the executable.

It holds:

* The language (4 bytes)
* The game version (3 bytes, patch/minor/major)
* Rest is unused.

Minor in particular is often used in the code as a feature/system unlock flag (which, do not work without the required files).

## PS Version

On the PS versions, user attributes are located in the `param.sfo` instead.



