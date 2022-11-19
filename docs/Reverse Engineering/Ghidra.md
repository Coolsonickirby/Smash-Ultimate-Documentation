# Ghidra Setup

## Requirements
   - [JDK 17 64-bit](https://adoptium.net/temurin/releases/)
   - [Ghidra 10.1.4](https://github.com/NationalSecurityAgency/ghidra/releases/tag/Ghidra_10.1.4_build)

## Setting up Ghidra
1. Download and install `JDK 17`
2. Download and extract the `Ghidra 10.1.4` zip
3. Go inside the `ghidra_10.1.4_PUBLIC` folder and double click `ghidraRun.bat`

## Connecting to the shared Smash Ultimate Research Server
1. Click `File -> New Project`
2. Select `Shared Project`
3. Type `ghidra.arcropolis.com` in the `Server Name` field
4. Check the `Request Anonymous Access` and hit `OK`
5. Click `OK` on the `Anonymous Server Login` pop-up
6. Select the `SmushLoaderino` repository and click `Next >>`
7. Click `Finish` and wait
8. Double click `main_1301 (Ghidra 10.1.2)` and the decompiled code will show up after loading