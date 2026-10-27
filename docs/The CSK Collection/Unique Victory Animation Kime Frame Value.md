# Unique Victory Animation Kime Frame Value

The "Kime Frame" refers to the intense splash after the character that won performs their victory animation.

![The red and white splash screen that shows up after Sonic pumps his fist is the "Kime"](<../img/The CSK Collection/kime_example.gif#center>)

<div align="center"><sup>The red and white splash screen that shows up after Sonic pumps his fist is the "Kime"</sup></div>

By default, for all animations it's set to happen at frame 130. You can customize this by creating a file at `camera/fighter/<Fighter Name>/<cXX>/j02win<Y>.kime`, where:

- `<Fighter Name>` -> The fighter's codename
- `<cXX>` -> The color you want to set the kime frame for
- `<Y>` -> The victory animation you want to change the kime frame for

Once you created the file, open it up in Notepad (or any text editor) and enter the frame you want the Kime to happen at, then save it.