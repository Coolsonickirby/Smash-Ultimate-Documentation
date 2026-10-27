# Automatically adding new characall files

Instead of manually adding new entries to the nus3bank and soundlabelinfo for new announcer character calls, The CSK Collection scans all files in `mods:/sound/bank/narration`, and if it's a new file, then it automatically adds it to the nus3audio, nus3bank, and soundlabelinfo so that those new files can be accessed by the game.

To use this feature, simply add your new `vc_narration_characall_....` file to `mods:/sound/bank/narration`. The file can be one of the following:

- `wav`
- `idsp` (Recommended)
- `lopus`
- `nus3audio`

It's recommended to use an `idsp` file, but any of the formats should work. If you run into an issue with any other format aside from `idsp`, then try converting it to an `idsp` and using that.