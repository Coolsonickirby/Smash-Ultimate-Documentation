# File Formats

## adjb
Renormal mesh adjacency (according to the ssbh_editor github page).

You can use the following program to edit adjb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)

You can use the following library to view/modify adjb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## arc

There are two types of arc extensions: the data.arc and layout.arc


### data.arc
The data.arc is the main archive file the game stores all its data in.

You can use the following programs to view and extract from the data.arc:

- [ArcExplorer](https://github.com/ScanMountGoat/ArcExplorer) (Windows/Linux) (Recommended)
- [CrossArc](https://github.com/Ploaj/ArcCross/releases) (Windows)

You can use the following library to view/modify the data.arc:

- [smash-arc](https://github.com/jam1garner/smash-arc) (Rust)

### layout.arc
The layout.arc is used to signify how the UI should look.

You can use the following program to modify the layout.arc:

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/EXPERIMENTAL_LATEST) (Windows)

## bfotf / bfttf
Binary Cafe OpenType Font / TrueType Font

You can use the following programs to create/convert bfotf/bfttf files:

- [NintyFont](https://github.com/hadashisora/NintyFont) (Windows/Linux) (Recommended)
- [BFTTFutil](https://github.com/hadashisora/BFTTFutil) (Windows)

## bin
There are multiple files with the bin extension, so I'll just cover the most common ones

### motion_list.bin
Has something to do with fighter frames?

You can use the following program to view/modify motion_list.bin:

- [yamlist](https://github.com/ultimate-research/motion_lib/releases) (Windows)

You can use the following library to view/modify motion_list.bin:

- [motion_lib](https://github.com/ultimate-research/motion_lib) (Rust)

### bgm_property.bin
A database of all the bgm hashes the game uses for lookup. Has to be ordered either alphabatically or by the hash40s.

You can use the following program to view/modify bgm_property.bin:

- [smash-bgm-property](https://github.com/jam1garner/smash-bgm-property/releases) (Windows)

You can use the following library to view/modify motion_list.bin:

- [smash-bgm-property](https://github.com/jam1garner/smash-bgm-property) (Rust)

## bntx
Binary Texture. Most commonly used for UI textures.

You can use the following programs to create/modify bntx files:

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/EXPERIMENTAL_LATEST) (Windows)
- [img2bntx](https://github.com/jam1garner/img2bntx/releases) (Windows)

You can use the following library to create bntx files:

- [bntx](https://github.com/ScanMountGoat/bntx) (Rust)

## csb
Only one file has this extension and it's the `commonsoundtable.csb` file.

You can use the following program to modify the csb file:

- [smash-csb](https://github.com/jam1garner/smash-csb) (Manual compilation required)

You can use the following library to modify the csb file:

- [smash-csb](https://github.com/jam1garner/smash-csb) (Rust)

## eff
Effect files used for fighter and stage effects.

You can use the following program to modify eff files:

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/EXPERIMENTAL_LATEST) (Windows)

## fnv
Only one file has this extension and it's the `sound_volume_fighter_num_table.fnv` file.

You can use the following program to modify the fnv file:

- [smash-fnv](https://github.com/jam1garner/smash-fnv/releases) (Windows)

You can use the following library to modify the fnv file:

- [smash-fnv](https://github.com/jam1garner/smash-fnv) (Windows)

## h264
MPEG-4 movies used by final smashes.

You can use the following ffmpeg command to convert video files to proper h264 files:

`ffmpeg -i <input file> -r 30000/1001 -vf scale=1280x720:flags=bicubic -b:v 6000k <output name>.h264`

## lc
Compiled Lua Files. Used for items and menu stuff.

You can use the following program to decompile lc files:

- [DSLuaDecompiler](https://github.com/katalash/DSLuaDecompiler) (Manual compilation required)

You can use the following program to compile lua files to lc:

- `luac -s -o <output>.lc <input>.lua` (`sudo apt-get install lua5.3`)


## lvd
Level Data. Contains multiple information for a stage, including collision, camera ranges, and blast zones.

You can use the following programs to modify the lvd files:

- [yamlvd](https://github.com/jam1garner/lvd-rs/releases) (Windows)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to modify the lvd files:

- [lvd-rs](https://github.com/jam1garner/lvd-rs) (Rust)

## msbt
Michigan Single Business Tax. Contains labels and text the game uses.

You can use the following programs to modify msbt Files:

- [Kuriimu2](https://github.com/FanTranslatorsInternational/Kuriimu2/releases) (Windows/MacOS/Linux)
- [MSBT Editor Reloaded](https://github.com/IcySon55/3DLandMSBTeditor/releases) (Windows)

You can use the following library to modify the msbt files:

- [msbt-rs](https://github.com/RoccoDev/msbt-rs) (Rust)

## nro
Compiled Fighter Code.

You can disassemble the code in the nro with:

- [Ghidra](https://github.com/NationalSecurityAgency/ghidra/releases) + [Ghidra Switch Loader](https://github.com/Adubbz/Ghidra-Switch-Loader/releases)

## nuanmb
Namco Animation Data.

You can use the following programs to view/modify nuanmb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to view/modify nuanmb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## nufxlb
Namco Effects Library. [Used for storing data about the shader programs used for rendering.](https://github.com/ultimate-research/ssbh_lib/blob/master/ssbh_lib/src/formats/nufx.rs#L1)

You can use the following library to view/modify nufxlb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## nuhlpb
Namco Helper Bone Data. [Stores bone constraints for helper bones.](https://github.com/ultimate-research/ssbh_lib/blob/master/ssbh_lib/src/formats/hlpb.rs#L1)

You can use the following program to view/modify nuhlpb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)

You can use the following library to view/modify nuhlpb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## numatb
Namco Material Data. [Stores a collection of materials used for model rendering.](https://github.com/ultimate-research/ssbh_lib/blob/master/ssbh_lib/src/formats/matl.rs#L1)

You can use the following programs to view/modify numatb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to view/modify numatb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## numdlb / nusrcmdlb
Namco Model Data. [Describes the files associated with a model.](https://github.com/ultimate-research/ssbh_lib/blob/master/ssbh_lib/src/formats/modl.rs#L1)

You can use the following programs to view/modify numdlb/nusrcmdlb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to view/modify numdlb/nusrcmdlb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## numshb
Namco Mesh Data. [Stores the geometric data used for model rendering.](https://github.com/ultimate-research/ssbh_lib/blob/master/ssbh_lib/src/formats/mesh.rs#L1)

You can use the following programs to view/modify numshb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to view/modify numshb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## numshexb
Namco Mesh Extension Data. Mesh bounding and flags. Not sure on specifics but I know it controls shadows?

You can use the following programs to view/modify numshexb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to view/modify numshexb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## nus3audio
Audio Container. Used for BGM, SFX, and Voices.

You can use the following programs to create/view/modify nus3audio files:

- [nus3audio-rs](https://github.com/jam1garner/nus3audio-rs/releases) (Windows/MacOS/Linux)
- [NUS3Audio Editor](https://gamebanana.com/tools/6927) (Windows)
- [simple-nus3audio-gui](https://gamebanana.com/tools/8340) (Windows/Linux)
- [Smash Ultimate Tools - Conversion](https://smashultimatetools.com/index.php?page=audio) OR [Smash Ultimate Tools - Editing](https://smashultimatetools.com/index.php?page=nus3audioEditor) (Multiplatform)

You can use the following library to create/view/modify nus3audio files:

- [libnus3audio](https://github.com/jam1garner/libnus3audio) (Rust)

## nus3bank
Contains options to the respective nus3audio file. Used for Volume, whether the audio pauses when the game is paused, reverb, etc...

You can use the following program to modify nus3bank files:

- [nus3bank-volume-GUI](https://github.com/Pacil142857/nus3bank-volume-GUI) (Windows)

## nus3conf
Unknown.

## nushdb
Namco Shader Data. 

You can use the following library to view/modify nushdb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## nusktb
Namco Skeleton Data. [Stores the model's skeleton used for skeletal animations.](https://github.com/ultimate-research/ssbh_lib/blob/master/ssbh_lib/src/formats/skel.rs#L1)

You can use the following programs to view/modify numshb files:

- [ssbh_editor](https://github.com/ScanMountGoat/ssbh_editor/releases) (Windows/MacOS)
- [StudioSB](https://github.com/Ploaj/StudioSB/releases) (Windows)

You can use the following library to view/modify numshb files:

- [ssbh_lib](https://crates.io/crates/ssbh_lib) (Rust)

## nutexb
Namco Texture Data. Most commonly used for in-game textures.

You can use the following programs to create/modify nutexb files:

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/EXPERIMENTAL_LATEST) (Windows)
- [img2nutexb](https://github.com/jam1garner/img2nutexb/releases) (Windows/Linux)

You can use the following library to create nutexb files:

- [nutexb](https://crates.io/crates/nutexb) (Rust)

## prc / stdat / stprm
Parameter Files. Used for databases, stage data, and stage parameters.

You can use the following programs to view/modify prc/stdat/stprm files:

- [prickly](https://github.com/BenHall-7/prickly) (Windows/MacOS/Linux)
- [param-xml](https://github.com/ultimate-research/prc-rs/releases) (Windows)
- [prcEditor](https://github.com/benhall-7/paracobNET/releases) (Windows)

You can use the following library to view/modify prc/stdat/stprm files:

- [prc-rs](https://github.com/ultimate-research/prc-rs) (Rust)

## shpc
Ambient Diffuse Lighting.

You can use the following library to view/modify shpc files:

- [shpc](https://github.com/ultimate-research/shpc)

## shpcanim
Ambient Diffuse Lighting Animation.

## sli
Only one file has this extension and it's the `soundlabelinfo.sli` file.

You can use the following program to view/modify the `soundlabelinfo.sli` file:

- [smash-sli](https://github.com/jam1garner/smash-sli/releases) (Windows/Linux)

You can use the following library to view/modify the `soundlabelinfo.sli` file:

- [smash-sli](https://github.com/jam1garner/smash-sli) (Rust)

## spt
Sound Priority Table.

## sqb
Sequence Banks.

You can use the following program to view/modify sqb files:

- [sqb_yaml](https://github.com/benhall-7/sqb-rs/releases) (Windows)

You can use the following library to view/modify sqb files:

- [sqb-rs](https://github.com/benhall-7/sqb-rs) (Rust)

## svt
Only one file has this extension and it's the `sound_volume_table.svt` file.

You can use the following program to view/modify sqb files:

- [svt](https://github.com/jam1garner/smash-svt/releases) (Windows)

You can use the following library to view/modify sqb files:

- [smash-svt](https://github.com/jam1garner/smash-svt) (Rust)

## tonelabel
File containing hashes for related nus3audio.

You can use the following program to create a tonelabel:

- [nus3audio-rs](https://github.com/jam1garner/nus3audio-rs/releases) (Windows/MacOS/Linux)

You can use the following library to create a tonelabel:

- [libnus3audio](https://github.com/jam1garner/libnus3audio) (Rust)

## webm
Video files used for the intro, cutscenes, and technique videos.

You can use the following ffmpeg command to convert video files to proper webm files:

`ffmpeg -i <input file> -vf scale=1280:720 -vsync cfr -ar 48000 -r 29.970 -c:v libvpx-vp9 -b:v 2M -c:a libvorbis <output name>.webm`

## xmb
LOD and model parameters.

You can use the following program to convert a xmb file:

- [xmb](https://github.com/ultimate-research/xmb_lib/releases) (Windows)

You can use the following library to modify a xmb file:

- [xmb_lib](https://github.com/ultimate-research/xmb_lib) (Rust)