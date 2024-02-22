---
icon: octicons/hash-16
---

# Hashes

The vast majority of the game and its executable uses hashed strings. This makes any reverse-engineering work tedious as strings cannot always be recovered, and decompilation work can be complicated without a hash list of sorts.

Hashes can be found just about everywhere - in table files, in the executable as compile-time constants, inside model files, `prfb`/`matb`... and more.

---

## Algorithm

The algorithm is XXHash32 with some odd twist.

C# code for it can be found [here](https://github.com/Nenkai/GBFRDataTools/blob/master/GBFRDataTools.Hashing/XXHash32Custom.cs).

---

## Hash List

You can grab a zipped hash list [here](hashlist.7z).

It contains:

* Hashes for the majority of english words
* Hashes for most strings for all game files gathered with `strings2`
* Hashes for most strings gathered from the executable (1.0.3) with `strings2`
* Hashes for most strings gathered from NierAutomata.exe with `strings2`