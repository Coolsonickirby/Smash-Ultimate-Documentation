# Dumping the data.arc

## Requirements
- One of the following:
    - A Hacked Switch
        - [nxdumptool](https://github.com/DarkMatterCore/nxdumptool/releases)
    - Ryujinx (Windows/Linux)
    - Yuzu (Windows/Linux)

## Dumping with a Hacked Switch
1. Open up the Homebrew Launcher and launch nxdumptool
    - If you're using a gamecard, then select the `Dump Gamecard` option
    - If you downloaded the game digitally, then select `Dump installed SD card / eMMC content` and select `Super Smash Bros. Ultimate`
2. Select the `RomFS options`
3. Set `Use update/DLC` to the latest update version (currently `v1769472`)
4. Press `RomFS section data dump` and wait for the game to dump
5. Shut down your switch and insert your SD Card into your computer
6. Navigate to `sd:/switch/nxdumptool/RomFS`
7. 
    - If your SD Card is FAT32, delete the `.nrr` folder in `Super Smash Bros. Ultimate <Update Number> (01006A800016E800) (UPD)` then go back to the `RomFS` folder and open up command prompt in that folder and run the following command (replace &lt;Update Number&gt; with the update number and &lt;output dir&gt; with where you want to save the data.arc locally)
    `copy /b "Super Smash Bros. Ultimate <Update Number> (01006A800016E800) (UPD)\*" "<output dir>\data.arc"`
    ![Opening up cmd in a folder (Thanks to TNN for the example)](../img/General/cmd_in_folder.gif)
    - If your SD Card is exFAT, then just copy the data.arc in `Super Smash Bros. Ultimate <Update Number> (01006A800016E800) (UPD)` somewhere to your PC
8. Remove the dump on your sd card
9. You're done

## Dumping with Ryujinx
1. Right-click on `Super Smash Bros. Ultimate` game and select `Manage Title Updates`
2. Make sure the latest update is selected and click `Ok`
3. Right-click on `Super Smash Bros. Ultimate` and click `Extract Data -> RomFS`
4. Wait for Ryujinx to finish dumping `Super Smash Bros. Ultimate`
5. You're done

## Dumping with Yuzu
1. Right-click on `Super Smash Bros. Ultimate` game and select `Properties`
2. Make sure the latest update is checked and click `OK`
3. Right-click on `Super Smash Bros. Ultimate` and click `Dump RomFS -> Dump RomFS`
4. Wait for Yuzu to finish dumping `Super Smash Bros. Ultimate`
5. You're done