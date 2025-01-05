![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)
# M2TW Settlement Modding
Modding battlemap settlements in M2TW is a relatively complex task.  IWTE is the only currently maintained tool for this branch of modding.  Before launching into designing new settlements modders should aquire some understanding of the files involved and experiment with modifying existing settlements.

All buildings and some other objects that appear on M2TW battlemaps are loaded from .world files. 
Some information about the structure of the .world file is provided on [TWC Wiki](https://wiki.twcenter.net/index.php?title=.world_file_-_M2TW) (info for geeks only, not needed for modding).

.world files are used for:
* settlements
* techtrees inside settlements
* bridges
* ambient objects

## Which .world is loaded?

The .world chosen is determined by the CONTENTS of .worldpkgdesc files.  More information about .worldpkgdesc files is provided on [TWC Wiki](https://wiki.twcenter.net/index.php?title=.worldpkgdesc_-_M2TW).

The important bits:
* you need a *packagedb.txt* file in your mod-folder for your .worldpkgdesc files to be read, its contents will normally be:
  
      ; List of directories to search for packages
      .\settlements
  you could specify other folders to include but that's likely to be confusing to other modders
* mod-folder .worldpkgdesc files do not overwrite data level .worldpkgdesc files even if they have the same name/location, instead you could get either loaded randomly
* the most specific .worldpkgdesc is always used, so a pkg that specifies a faction will be used instead of one that only specifies culture
* its the CONTENTS that matter
* it really is the CONTENTS that matter, if you've got old copies of pkgs called *xxxxNotUsed.worldpkgdesc* the game will still use it, the only way to stop that is change the extension, or make sure its not in the folder/s listed in the packagedb.txt
* location doesn't matter so long as its in the folder/s listed in the packagedb.txt - it doesn't need to be in the same folder as the .world it's calling!  For your sanity though, either keep them in the same folder as their .world OR put all the pkg files in one folder with self-explanatory names, e.g. huge_city_for_spain.worldpkgdesc
* each .worldpkgdesc will load one .world file - multiple pkgs can refer to the same .world if you need to re-use it for other factions/purposes

When a .world is loaded it will load the .worldcollision file that is in the same folder and which has the same name.
So *my_settlement.world* requires *my_settlement.worldcollision* in the same folder. ALL other paths are specified INSIDE the .world or .worldterrain.

FOLDER NAMES ARE IRRELEVANT, apart from making sure you have the paths correct. Adding things to the *settlements/north_european* folder does not make the northern_european culture use them!!!  (apart from anything else it's not even spelt the same! - sorry rant over...)

## Which files are loaded from the .world?

![M2-world-referenced-paths.jpg](../IWTEgithub_images/M2-world-referenced-paths.jpg)

![M2-worldterrain-mask-paths.jpg](../IWTEgithub_images/M2-worldterrain-mask-paths.jpg)

