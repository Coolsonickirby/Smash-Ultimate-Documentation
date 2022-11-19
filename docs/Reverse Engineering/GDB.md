# GDB Setup

# Disclaimer
GDB will only work for the switch console itself! That means you cannot use an emulator (Ryujinx or Yuzu) as a subsititue!

## Setup
### Requirements
   - [Debian WSL](https://www.microsoft.com/store/productId/9MSVKQC78PK6) (Windows)
   - [Custom .gdbinit](https://github.com/Coolsonickirby/smash-ultimate-research-setup/tree/main/gdbinit)

### Setting up on the Switch side
1. Make sure you have the latest Atmosphere set up and running!
2. Edit `sd:/atmosphere/config/system_settings.ini` (or create it if it's not there) and paste the following in (reboot the switch after you save the file):
```ini
[atmosphere]
enable_htc = u8!0x0
enable_standalone_gdbstub = u8!0x1
```

### Setting up WSL (Windows Only)
1. Download `Debian` from the Microsoft Store
2. Once it's done, run the `Debian` application
   - If you run into `The Windows Subsystem for Linux optional component is not enabled`, then search for `Windows Features`, then scroll down and enable `Windows Subsystem for Linux`
3. Set a password and confirm

### Setting up GDB
1. Run `sudo apt-get -y update && sudo apt-get -y install gdb-multiarch && sudo apt-get -y install wget` (this will update your repos, install gdb-multiarch, and install wget)
2. Run `wget https://raw.githubusercontent.com/Coolsonickirby/smash-ultimate-research-setup/main/gdbinit/.gdbinit -O ~/.gdbinit && wget https://raw.githubusercontent.com/Coolsonickirby/smash-ultimate-research-setup/main/gdbinit/attach.py -O ~/attach.py` (this will download and set up the custom .gdbinit file and the associated attach.py script with it)
3. Run `nano ~/.gdbinit` and scroll down until you get to the `target extended-remote` line
4. Edit the IP in the file to be your switch's IP (you can find the switch's IP by going to `System Settings -> Internet -> IP Address`)
5. Hit `Ctrl + X -> Y -> Enter`
6. You're done, GDB is now set up with auto-attach + a handful of useful functions!

### Using GDB
1. Open up `Debian` if you're on Windows
2. Run `gdb-multiarch`
3. Run `Super Smash Bros. Ultimate` on the switch once it says to "Launch your game"
4. Let it auto-attach and set $main automatically
5. Set up any breakpoints, no_ops, stubs, etc...
6. Type `c` and hit enter

## GDB Functions
The .gdbinit file we set up earlier has these handful of functions that will be pretty useful in your reversing endeavors!

   - `my_bt` -> Prints the backtrace as absolute addresses. Often misses the first address on the backtrace but you can just p/x $lr for that.
   - `my_bt2` -> Prints the backtrace with offsets relative to the base of main.
   - `no_op <offset>` -> Takes an offset into main and NOPs the instruction at that address
   - `stub <offset>` -> Takes an offset into main and stubs the function at that address
   - `replace <offset> <new_instruction>` -> Replaces the instruction at an offset with the new instruction
   - `get_pc` -> Gets the PC as an offset relative to the base of main
   - `break_at <offset>` -> Sets a breakpoint at an offset relative to the base of main
   - `localize <register/address>` -> Converts the value in the register (or the passed address) to an offset relative to the base of main
   - `xxd <address> <size>` -> Print a xxd dump of the address
   - `usual` -> Runs `get_pc`, `localize $lr`, & `my_bt2` to get the current offset, the calling offset, and the backtrace in one command instead of three