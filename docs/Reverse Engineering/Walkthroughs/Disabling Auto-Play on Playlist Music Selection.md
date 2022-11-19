# Disabling Auto-Play on Playlist Music Selection

This walkthrough will explain the process of using the shared Smash Ultimate Research Server to disable and prevent the music from being played after selecting a track in the normal playlist menu.

## Things we'll cover
   - Using Ghidra and the shared Smash Ultimate Research Server to find useful functions
   - Using GDB to break at said functions and view backtraces
   - Track down the instruction which calls the function to play the music after selecting it
   - `nop`ing said instruction to prevent the song from playing after selecting it
   - Creating a skyline plugin with our research to automatically preform the patch for us

Let's get started!

## The start
So first things first, lets go ahead and open up the main decompiled code in Ghidra from the shared Smash Ultimate Research Server.
![Inital screen of Ghidra](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_1.png)

Let's go ahead and search in the symbol tree for anything that might be related to music and see if we get any hits. I'll use `bgm` since that's something commonly associated with music.
![Search results of 'bgm'](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_2.gif)

Hooo boy! That's a lotta stuff! Luckily for us though, we can ignore everything in the `Exports` since those are only accessed by the lua files. We have some functions with the label `FUN_`, so we'll ignore all of those until we're desperate. There are some functions inside namespaces, which from my expierence don't matter much. There are also a couple of labels, but those are for the game's reference. So now we're left with the following functions:
   
   - `bgm_related`
   - `get_bgm_save_no`
   - `get_ui_bgm_entry_idx_by_id`
   - `play_bgm_by_prc_entry_index`

`bgm_related` and `get_bgm_save_no` are out of it for me, since the first one is still not exactly known while the other is clearly known for something unrelated to our mission. So now we only have two.

I'll personally decide to go with `play_bgm_by_prc_entry_index`, since that function sounds like it's in charge of playing the bgms.

Now that we decided on the function, we'll need to get it's offset. To do so, we'll click on the function in the `Symbol Tree` and look at the first offset after the function declaration.
![Offset for the function after the declaration](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_3.png)
As we can see here, the offset is `71033135f0`. However, we need to remove the `710` prefix and put a `0x` prefix instead because `710` is the base address in Ghidra. So the offset we'll use in Rust and GDB will be `0x33135f0`

## Breaking
We have our offset, so now we can start having the real fun 😈! We'll go ahead and start GDB in Debian and `Super Smash Bros. Ultimate` on the switch. Once GDB attaches and finds main, we can run `break_at 0x33135f0` to set a breakpoint at the function we found. That means everytime that function runs, the game will pause and we can see what's going on in memory.
![Running gdb-multiarch and entering 'break_at 0x33135f0'](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_4.png)

Let's go ahead and enter `c`, then get to the Stage Selection Screen and open up a playlist. When we trying playing a song with the `Y` button, the game freezes! Don't worry though, your game didn't crash. GDB stopped the game and now you can run commands in GDB.
![GDB breaking on a function](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_5.png)

We can enter our commands into GDB, we'll run the `usual` command to get the current $pc (pc being the current offset we're at in the code), the $lr (lr being the instruction that we'll jump back to after our function is over), and the backtrace (a list keeping track of which offset to jump back to).
!['usual' command being run on manually played back song](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_6.png)

Keeping a note of this output in case we need to compare it to another scenario will be extremely helpful the more deeper you dive into reversing.

We'll continue (type `c` and hit enter) and try to select a song by choosing it this time. When we press `A` to choose the game, the game freezes again! Just like before, the function got called, so let's go ahead and run the `usual` command again.
!['usual' command being run on chosen song](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_7.png)

Oho? What's this? The third offset in the chosen song playback is different than the third offset in the manually chosen playback. That's pretty interesting. Let's go ahead and jump to the third offset in the chosen song playback in Ghidra.

## Tracking
We can press `g` in Ghidra to jump to an offset. Although when we jump to an offset, we need to add `710` before the offset, since Ghidra starts at `710` (so in our case, we'll be jumping to `7101b352ac` in Ghidra)
![Jumping to 7101b352ac in Ghidra](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_8.png)
(Please ignore the horrible hard to read text on the right, that's just a side-effect with the Dark Mode Ghidra theme lol)

If we look closely, we can see that we landed at the instruction right after a `bl` (branch link), which is how aarch64 calls functions. If we double click the function, we can see that it calls `play_bgm_by_prc_entry_index` in it
![Going inside the unknown function](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_9.png)

## Noping
So now that we know that function calls another function that runs the `play_bgm_by_prc_entry_index`, lets change the `bl` instruction to a `nop`. Since I didn't explain it earlier, a `nop` is a instruction that does absolutely nothing, and that's what makes it special. So let's say that we don't want the `bl` instruction to jump to a different function. All we need to do is replace the `bl` instruction with a `nop` instruction and mission accomplished! To replace the instruction with a nop, we just need to copy the offset of the `bl` instruction (`7101b352a8` -> `0x1b352a8`) and use the `no_op` function we have in GDB.
(If you accidentally continued, then you can freeze the game at any moment by pressing `Ctrl + C`)
![noping the function in GDB](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/pic_10.png)

Now whenever the game hits the code to jump to the other function, instead it'll see a `nop`, then it'll think it has to do nothing and keep going, which means the function to play the music will be skipped. Let's continue the game and see what happens when we try playing a song.
![type:video](../../img/Walkthroughs/Disabling%20Auto-Play%20on%20Playlist%20Music%20Selection/success.mp4)

Success! Congratulations! You have successfully reversed and patched the game to not auto-play the music on selection in the playlist menu!

## Converting into a Skyline Plugin
We have our newfound knowledge on how to prevent the game from automatically playing the music when we pick a song, but now we have to manually no_op the function every time we want the game to not play the song. If we want to distribute this as a mod so that users can enjoy it, we can't expect them to have GDB and be willing to put up with manually noping the instruction themselves every time. That's where skyline plugins come in! We'll create a sklyine plugin that patches the offset with a `nop` instruction every time the game boots!

So first, we'll run the usual `cargo skyline new <project_name>` to make a new skyline project. Then open up that folder with your favorite IDE (I'll be using VSCode).

Go to `src/lib.rs` and remove the `println!(...)` line from the main function. Now make a new line in `main()` and write the following:
`skyline::patching::Patch::in_text(0x1b352a8).nop().expect("Failed to patch 0x1b352a8")`
This line basically says "Hey, go to the .text section (where the code is stored), then jump to the offset given (`0x1b352a8`, which is what we noped), then nop. If you fail to nop it, then throw an error message!". Now we can run `cargo skyline run` and test it out in-game! 

## Conclusion
I'd say we cleared all of our goals in this walkthrough! We used the Shared Research Server to track down a promising function, used GDB to break and inspect the stack trace, tracked down the instruction which jumped to the function that called the `play_bgm` function, noped said instruction, and converted it to a skyline plugin.