# Custom Palutena Guidances

The CSK Collection changes how Palutena Guidance works, allowing for new guidances to be created and associated with a Character ID instead of a Fighter Kind. You can read more on this page to learn how to create your own guidance.

**Note: `mod:/` in this guide refers to your custom mod folder.**

### Requirements
- A `wav` file containing all the dialouge with a sample rate of 48khz (if you're unsure of how to change the sample rate, then please refer to the [Music Modding guide](<../Modding/Audio.md#music-modding>))

### Optional
- [Example `wav` file](<../img/The CSK Collection/vc_smashappeal_angeland_pit_clone.wav>)
- [Example `json` file](<../img/The CSK Collection/pit_clone_0.json>) (you can use `Load Config` to load the file and interact with it in the editor)

## Creating the Guidance

1. Navigate to [PaluGuide](https://coolsonickirby.com/PaluGuide/)

2. Enter the following information in the respective boxes at the lower left:
    - `ui_chara_id` -> The Character ID you want to set the guidance for
    - `pattern` -> The cXX index you want this guidance to target
    - `name_id` -> The `name_id` of the Character ID

3. Press `Load Audio File` on the bottom right side and select the `wav` from earlier

4. Add the amount of regions you desire (usually one for each character that speaks)

5. Move and resize each region by dragging either the center of it around or dragging the left/right edge of it inward/outward respectively.

6. Select each region in the `Regions` section, then fill out the following information:
    - `Event Start` (will run when entering the region):
        - `Left` -> The portrait that will appear on the left side
        - `Left (Outside)` -> The portrait that will appear on the left side closer to the screen's edge
        - `Right` -> The portrait that will appear on the right side
        - `Right (Outside)` -> The portrait that will appear on the right side closer to the screen's edge
        - `Text Delay` -> The amount of frames the text will be delayed from showing up
    - `Event End` (will run when leaving the region):
        - `Slide Left Out` -> Will slide the portraits on the left out of the screen
        - `Slide Right Out` -> Will slide the portraits on the right out of the screen
    - `Text` -> The text that will show up

7. Select the first region in the `Regions` section and press `Toggle` to preview your custom guidance

8. Once you're ready, press `Save` and save the generated file

## Preparing the guidance for in-game

1. In your mod folder, create the following path: `mod:/smashappeal/palutena/data`

2. Place the generated file in that folder

3. Convert your `wav` file to a nus3audio. You can use the following (**Make sure looping is disabled!**):
    - [Music Modding guide](<../Modding/Audio.md#music-modding>)
    - [SmashUltimateTools](https://smashultimatetools.com/index.php?page=audio)

4. Rename your nus3audio to the following: `vc_smashappeal_angeland_<name_id>.nus3audio`, where `<name_id>` is the `name_id` you used earlier

5. Create the following path: `mod:/stream;/sound/smashappeal`

6. Place your nus3audio file in that folder

7. Test it out in game!

## Example Video
<iframe width="1280" height="470" src="https://www.youtube.com/embed/PBXNtJ0fI7Q?si=tB0-UImcJPw6HF4K" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>