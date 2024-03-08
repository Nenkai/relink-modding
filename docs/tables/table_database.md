---
icon: material/database
---

# Table Database

The table files `.tbl`, located under `system/table` holds most of the data for the game. Items, abilities, gems (sigils), and a lot more. 

In order to make it easier for editing, it is recommended to first convert them to [SQLite](https://en.wikipedia.org/wiki/SQLite) for easier manipulation.

---

## Converting to SQLite

To convert them to SQLite, you can use [GBFRDataTools](https://github.com/Nenkai/GBFRDataTools) >1.2.0 which you should already have.

``` markdown title="Command"
GBFRDataTools.exe tbl-to-sqlite -i <path to table folder> -o <output SQLite file>
```

You can then preview them using any SQLite database editor, such as [SQLiteStudio](https://sqlitestudio.pl/)

!!! tip

    If you care about your eyes, switch to Dark Mode in:
    
    * Tools :material-arrow-right: Open configuration dialog :material-arrow-right: Look & feel (Style) :material-arrow-right: Current style: Fusion Dark.

---

## Converting back to .tbl

``` markdown title="Command"
GBFRDataTools.exe tbl-to-sqlite -i <path to SQLite file> -o <path of output table folder>
```

---

## Additional Notes

* For random-looking-values, [Hashes](../resources/re/hashes.md) are used for table relationships. Blank columns signify a hash of `887AE0B0` (empty string/no value).
* The actual type of each column can be found by inspecting the `.headers` files of GBFRDataTool under the `Headers` folder.
* Many of the columns are unknown and may need to be figured out first.
* **Please contribute!** There are many tables that have yet to be figured out. The headers are located [here](https://github.com/Nenkai/GBFRDataTools/tree/tables/GBFRDataTools.Database/Headers) on the repo. Same goes for hashes, if you manage to bruteforce the original string for certain hashes, the list is located [here](https://github.com/Nenkai/GBFRDataTools/blob/tables/GBFRDataTools.Database/Data/ids.txt).



