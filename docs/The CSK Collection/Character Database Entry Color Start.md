# Character Database Entry Color Start

This feature allows you to make a UI character database entry start loading the colors from an arbitrary index instead of 0 (an example would be loading `c120` instead of the default `c00`.)

To use this feature, add a new key to the character database entry in `ui_chara_db.prc` with the type of `u8`/`byte` and a key of `color_start_index`, then set the value to be the index you want that specific entry to load the costumes from.