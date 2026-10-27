# Unshared Final Smash Movies

To use this feature, place the movie file you have prepared in `prebuilt:/movie/fighter/<Fighter Name>/<cXX>/<Movie File>`, where:

- `<Fighter Name>` -> The fighter's codename
- `<cXX>` -> The color you want the movie to be for
- `<Movie File>` -> Usually named `final_00.h264`, with Joker having an extra one called `final_01.h264` for the alternate All-Out Attack

## **Important!**

Most final smash movies that are on GameBanana come with a `config.json` that adds an `unshare-blacklist` key. While this does fix it not loading normally, it messes with this feature. To fix this, just open up the `config.json` and remove the `unshare-blacklist` key and array.