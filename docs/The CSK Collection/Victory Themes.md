# Victory Themes Features

**It's recommended to use [this unshared victory theme mod](https://gamebanana.com/mods/629194) so options to override on multiple characters.**

The features related to the victory theme are conglomerated to this page. You can get the list of all victory themes from [here](https://smashultimatetools.com/index.php?page=audio) (make sure to click `More Options` and select `Victory Themes`)


## Color Specific Victory Themes (formerly known as "One Slot Victory Themes")

To set a victory theme for a specific color, you can simply rename your custom victory theme file to `<original_victory_filename>_c<XX>.nus3audio` (where `<XX>` is the color you want to set) and place it in `stream;/sound/bgm`.

Examples:

- `bgm_z47_f_sonic_c02.nus3audio` -> Changes Sonic's third color victory theme

- `bgm_z01_f_mario_c00.nus3audio` -> Changes Mario's first color victory theme

- `bgm_z46_f_snake_c04.nus3audio` -> Changes Snake's fifth color victory theme


## Unique Victory Animation Victory Theme

To set a victory theme for a specific victory animation, you can simply rename your custom victory theme file to `<original_victory_filename>_j02win<X>.nus3audio` (where `<X>` is the victory animation number) and place it in `stream;/sound/bgm`.


Examples:

- `bgm_z47_f_sonic_j02win2.nus3audio` -> Changes Sonic running and grabbing the Chaos Emerald animation victory theme

- `bgm_z99_f_buddy_j02win1.nus3audio` -> Changes Banjo throwing a Jiggy into the air, catching it, then giving a thumbs up animation victory theme


## Combining both of these

You can combine both of these features to set a victory theme for a specific animation if the character is on a specific color. To do so, simply rename your custom victory theme file to `<original_victory_filename>_j02win<Y>_c<XX>.nus3audio` (where `<Y>` is the victory animation number and `<XX>` is the color you want to set) and place it in `stream;/sound/bgm`.

Example:

- `bgm_z16_f_iceclimber_j02win2_c01.nus3audio` -> Changes Ice Climbers second color nodding and high fiving animation victory theme

## Using a configuration file

While the older way of using this feature was limited to a configuration file, this is now left as an option for those who still want to use it. To use a configuration file, simply create a file in `mods:/osvt/<Config File>.toml` (where `<Config File>` is any legal filename.)

The structure of the configuration is as follows:

```toml
[<bgm_filename>]
c<XX> = <value>
j02win<Y> = <value>
j02win<Y>_c<XX> = <value>
```

where:

- `<bgm_filename>` -> The filename of the victory theme

- `<XX>` -> The color you want to target

- `<Y>` -> The victory animation you want to target

- `<value>` -> Either the index to use from the victory file, or a string to another victory filename to use

An example of a configuration file is provided here:

```toml
[bgm_z47_f_sonic]
c01 = "bgm_u09_sadv2_liveandlearn"
c02 = "bgm_z01_f_mario"
j02win2 = 1
j02win2_c02 = "bgm_u12_snc06_hisworld_instrumental"

[bgm_z01_f_mario]
c00 = "bgm_z47_f_sonic"
c01 = "bgm_a04_lnd_chika"
```

This configuration will do the following:

`[bgm_z47_f_sonic]`:

- `c01` -> Cause Sonic's second color to play Live and Learn if the victory animation isn't the second one

- `c02` -> Cause Sonic's third color to play Mario's victory theme if the animation isn't the second one

- `j02win2` -> Cause the "grabbing Chaos Emerald" animation to play the first index in Sonic's victory theme file

- `j02win2_c02` -> Cause the "grabbing Chaos Emerald" animation to play "His World" IF Sonic is set to the third color

`[bgm_z01_f_mario]`:

- `c00` -> Cause Mario's first color to play Sonic's victory theme

- `c01` -> Cause Mario's second color to play "Underground Theme - Super Mario Land (Remix)"