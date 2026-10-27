# Force Stage Form

Thanks to [joobert](https://github.com/joobert), this feature allows you to force a stage to always load into a specific form. To use this feature, add a new key to the stage database entry in `ui_stage_db.prc` with the type of `Hash40` and a key of `force_form`, then set the value to be the form you want it to load into. The following forms are valid:

- `normal` -> The normal version of the stage
- `battle` -> The battlefield version of the stage
- `end`    -> The final destination version of the stage