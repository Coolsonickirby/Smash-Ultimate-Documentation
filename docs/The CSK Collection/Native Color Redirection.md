# Native Color Redirection

To redirect colors natively in-game, create a file called `mods:/flags/reslot.toml` in your mod folder, then use the following config as a base:

```toml
[chara_id]
c<Source Color> = <Target Color>
```

Where `<Source Color`> amd `<Target Color>` are numbers (limited from 0 to 255.)

An example of a proper config would look something like this:
```toml
[pichu]
c00 = 6
c06 = 0

[sonic]
c00 = 2

```

In this example, Pichu's flower color and the default color swap places, and Sonic's default color is set to the light blue skin. You can add as many character entries as you want.