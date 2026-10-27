# Play Music on CSS

This feature will specifically play music on the Character Selection Screen, and will revert back to the menu track when going back to the Stage Selection Screen.

![type:video](<../img/The CSK Collection/play_music_on_css.mp4#center>)

To enable this feature, create a file called `mods:/flags/play_music_on_css.flag`. After creating the file, open it up with any text editor, then add a `ui_bgm_id` per line to select which tracks can be picked for the CSS Menu Music.

An example file would be as such:
```
ui_bgm_a67_sm64_slider
ui_bgm_w02_sm64_rainbowcruise
```

This will pick either Slide or Slide (Remix) to play in the CSS. To get the list of tracks and their respective filenames, you can use [this site](https://smashultimatetools.com/index.php?page=audio). Just make sure to add `ui_` to the filename when adding it to the flag.