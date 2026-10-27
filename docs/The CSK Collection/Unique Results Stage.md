# Unique Results Stage

This feature lets you set a unique results stage for either a color, a victory animation, or both.

## Unique Victory Animation Results Stage

To set a stage for a specific victory animation, create the flag `mods:/camera/fighter/<Fighter Codename>/c<XX>/j02win<Y>.stage`, where:

- `<Fighter Codename>` -> The fighter's internal name used by the game

- `<XX>` -> The targeted color

- `<Y>` -> The targeted animation

Once created, open up the file in any text editor and insert the stage's dir info you want to use. A list can be found at the bottom of this page.

## Unique Fighter Color Results Stage

To set a stage for a specific fighter's color in general, create the flag `mods:/fighter/<Fighter Codename>/model/body/c<XX>/result.stage`, where:

- `<Fighter Codename>` -> The fighter's internal name used by the game

- `<XX>` -> The targeted color

Once created, open up the file in any text editor and insert the stage's dir info you want to use. A list can be found at the bottom of this page.

## Unique Fighter Results Stage

**Warning: Any cloned fighter will use the original's results stage as well if you use this method.**

To set a stage for a specific fighter in general, create the flag `mods:/fighter/<Fighter Codename>/result.stage`, where:

- `<Fighter Codename>` -> The fighter's internal name used by the game

Once created, open up the file in any text editor and insert the stage's dir info you want to use. A list can be found at the bottom of this page.


### List of Stage Dir Infos

Below is a list of Stage Dir Infos. You can pick them out from here and put it in the file you've created.
```
stage/75m/normal
stage/75m/battle
stage/animal_city/normal
stage/animal_city/battle
stage/animal_island/normal
stage/animal_island/battle
stage/animal_village/normal
stage/animal_village/battle
stage/balloonfight/normal
stage/balloonfight/battle
stage/battlefield/normal
stage/battlefield/battle
stage/battlefield_l/normal
stage/battlefield_l/battle
stage/battlefield_s/normal
stage/battlefield_s/battle
stage/bayo_clock/normal
stage/bayo_clock/battle
stage/bonusgame/normal
stage/bonusgame/battle
stage/bossstage_dracula/normal
stage/bossstage_dracula/battle
stage/bossstage_final1/normal
stage/bossstage_final1/battle
stage/bossstage_final2/normal
stage/bossstage_final2/battle
stage/bossstage_final3/normal
stage/bossstage_final3/battle
stage/bossstage_galleom/normal
stage/bossstage_galleom/battle
stage/bossstage_ganonboss/normal
stage/bossstage_ganonboss/battle
stage/bossstage_marx/normal
stage/bossstage_marx/battle
stage/bossstage_rathalos/normal
stage/bossstage_rathalos/battle
stage/brave_altar/normal
stage/brave_altar/battle
stage/buddy_spiral/normal
stage/buddy_spiral/battle
stage/campaignmap/normal
stage/campaignmap/battle
stage/common/normal
stage/common/battle
stage/demon_dojo/normal
stage/demon_dojo/battle
stage/dk_jungle/normal
stage/dk_jungle/battle
stage/dk_lodge/normal
stage/dk_lodge/battle
stage/dk_waterfall/normal
stage/dk_waterfall/battle
stage/dolly_stadium/normal
stage/dolly_stadium/battle
stage/dracula_castle/normal
stage/dracula_castle/battle
stage/duckhunt/normal
stage/duckhunt/battle
stage/end/normal
stage/end/battle
stage/fe_arena/normal
stage/fe_arena/battle
stage/fe_colloseum/normal
stage/fe_colloseum/battle
stage/fe_shrine/normal
stage/fe_shrine/battle
stage/fe_siege/normal
stage/fe_siege/battle
stage/ff_cave/normal
stage/ff_cave/battle
stage/ff_midgar/normal
stage/ff_midgar/battle
stage/flatzonex/normal
stage/flatzonex/battle
stage/fox_corneria/normal
stage/fox_corneria/battle
stage/fox_lylatcruise/normal
stage/fox_lylatcruise/battle
stage/fox_venom/normal
stage/fox_venom/battle
stage/fzero_bigblue/normal
stage/fzero_bigblue/battle
stage/fzero_mutecity3ds/normal
stage/fzero_mutecity3ds/battle
stage/fzero_porttown/normal
stage/fzero_porttown/battle
stage/homeruncontest/normal
stage/homeruncontest/battle
stage/icarus_angeland/normal
stage/icarus_angeland/battle
stage/icarus_skyworld/normal
stage/icarus_skyworld/battle
stage/icarus_uprising/normal
stage/icarus_uprising/battle
stage/ice_top/normal
stage/ice_top/battle
stage/jack_mementoes/normal
stage/jack_mementoes/battle
stage/kart_circuitfor/normal
stage/kart_circuitfor/battle
stage/kart_circuitx/normal
stage/kart_circuitx/battle
stage/kirby_cave/normal
stage/kirby_cave/battle
stage/kirby_fountain/normal
stage/kirby_fountain/battle
stage/kirby_gameboy/normal
stage/kirby_gameboy/battle
stage/kirby_greens/normal
stage/kirby_greens/battle
stage/kirby_halberd/normal
stage/kirby_halberd/battle
stage/kirby_pupupu64/normal
stage/kirby_pupupu64/battle
stage/luigimansion/normal
stage/luigimansion/battle
stage/make_snow.py/normal
stage/make_snow.py/battle
stage/mariobros/normal
stage/mariobros/battle
stage/mario_3dland/normal
stage/mario_3dland/battle
stage/mario_castle64/normal
stage/mario_castle64/battle
stage/mario_castledx/normal
stage/mario_castledx/battle
stage/mario_dolpic/normal
stage/mario_dolpic/battle
stage/mario_galaxy/normal
stage/mario_galaxy/battle
stage/mario_maker/normal
stage/mario_maker/battle
stage/mario_newbros2/normal
stage/mario_newbros2/battle
stage/mario_odyssey/normal
stage/mario_odyssey/battle
stage/mario_paper/normal
stage/mario_paper/battle
stage/mario_past64/normal
stage/mario_past64/battle
stage/mario_pastusa/normal
stage/mario_pastusa/battle
stage/mario_pastx/normal
stage/mario_pastx/battle
stage/mario_rainbow/normal
stage/mario_rainbow/battle
stage/mario_uworld/normal
stage/mario_uworld/battle
stage/metroid_kraid/normal
stage/metroid_kraid/battle
stage/metroid_norfair/normal
stage/metroid_norfair/battle
stage/metroid_orpheon/normal
stage/metroid_orpheon/battle
stage/metroid_zebesdx/normal
stage/metroid_zebesdx/battle
stage/mg_shadowmoses/normal
stage/mg_shadowmoses/battle
stage/mother_fourside/normal
stage/mother_fourside/battle
stage/mother_magicant/normal
stage/mother_magicant/battle
stage/mother_newpork/normal
stage/mother_newpork/battle
stage/mother_onett/normal
stage/mother_onett/battle
stage/nintendogs/normal
stage/nintendogs/battle
stage/pac_land/normal
stage/pac_land/battle
stage/photostage/normal
stage/photostage/battle
stage/pickel_world/normal
stage/pickel_world/battle
stage/pictochat2/normal
stage/pictochat2/battle
stage/pikmin_garden/normal
stage/pikmin_garden/battle
stage/pikmin_planet/normal
stage/pikmin_planet/battle
stage/pilotwings/normal
stage/pilotwings/battle
stage/plankton/normal
stage/plankton/battle
stage/poke_kalos/normal
stage/poke_kalos/battle
stage/poke_stadium/normal
stage/poke_stadium/battle
stage/poke_stadium2/normal
stage/poke_stadium2/battle
stage/poke_tengam/normal
stage/poke_tengam/battle
stage/poke_tower/normal
stage/poke_tower/battle
stage/poke_unova/normal
stage/poke_unova/battle
stage/poke_yamabuki/normal
stage/poke_yamabuki/battle
stage/punchoutsb/normal
stage/punchoutsb/battle
stage/punchoutw/normal
stage/punchoutw/battle
stage/resultstage/normal
stage/resultstage/battle
stage/resultstage_edge/normal
stage/resultstage_edge/battle
stage/resultstage_jack/normal
stage/resultstage_jack/battle
stage/rock_wily/normal
stage/rock_wily/battle
stage/settingstage/normal
stage/settingstage/battle
stage/sf_suzaku/normal
stage/sf_suzaku/battle
stage/shamfight/normal
stage/shamfight/battle
stage/sonic_greenhill/normal
stage/sonic_greenhill/battle
stage/sonic_windyhill/normal
stage/sonic_windyhill/battle
stage/spiritsroulette/normal
stage/spiritsroulette/battle
stage/spla_parking/normal
stage/spla_parking/battle
stage/sp_edit/normal
stage/sp_edit/battle
stage/staffroll/normal
stage/staffroll/battle
stage/streetpass/normal
stage/streetpass/battle
stage/tantan_spring/normal
stage/tantan_spring/battle
stage/tomodachi/normal
stage/tomodachi/battle
stage/trail_castle/normal
stage/trail_castle/battle
stage/training/normal
stage/training/battle
stage/wario_gamer/normal
stage/wario_gamer/battle
stage/wario_madein/normal
stage/wario_madein/battle
stage/wiifit/normal
stage/wiifit/battle
stage/wreckingcrew/normal
stage/wreckingcrew/battle
stage/wufuisland/normal
stage/wufuisland/battle
stage/xeno_alst/normal
stage/xeno_alst/battle
stage/xeno_gaur/normal
stage/xeno_gaur/battle
stage/yoshi_cartboard/normal
stage/yoshi_cartboard/battle
stage/yoshi_island/normal
stage/yoshi_island/battle
stage/yoshi_story/normal
stage/yoshi_story/battle
stage/yoshi_yoster/normal
stage/yoshi_yoster/battle
stage/zelda_gerudo/normal
stage/zelda_gerudo/battle
stage/zelda_greatbay/normal
stage/zelda_greatbay/battle
stage/zelda_hyrule/normal
stage/zelda_hyrule/battle
stage/zelda_oldin/normal
stage/zelda_oldin/battle
stage/zelda_pirates/normal
stage/zelda_pirates/battle
stage/zelda_skyward/normal
stage/zelda_skyward/battle
stage/zelda_temple/normal
stage/zelda_temple/battle
stage/zelda_tower/normal
stage/zelda_tower/battle
stage/zelda_train/normal
stage/zelda_train/battle
```