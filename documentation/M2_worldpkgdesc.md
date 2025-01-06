![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)

# .worldpkgdesc files in M2TW Settlement Modding
.worldpkgdesc files determine [which .world is used](M2_Settlement_Modding.md#which-world-is-loaded).  
More information about .worldpkgdesc files is provided on [TWC Wiki](https://wiki.twcenter.net/index.php?title=.worldpkgdesc_-_M2TW).

## Editing .worldpkgdesc files in IWTE screen
To edit a single .worldpkgdesc use the button *Edit worldpackage* on the M2 WorldFiles screen.

![M2_worldpkgdesc_screen.jpg](../IWTEgithub_images/M2_worldpkgdesc_screen.jpg)

* Name can be anything, will appear in the battle editor selection
* Pkg Group - preset options only - press *Allow Group Selection* to activate the drop-down
* Pkg Path - path relative to data folder, must end in .world, .world file must exist there!
* Category - used for techtrees - see wiki
* Size - used for techtrees - see wiki
* Type - for settlements and forts - [see wiki](https://wiki.twcenter.net/index.php?title=.worldpkgdesc_-_M2TW#Type:)
* Variant - can be the same as 'Name' - used for adding forts in descr_strat
* Culture - any culture in your mod - see wiki for greek/ee issues
* Environment - unfortunately doesn't seem to do anything
* Faction - any faction in your mod
* Fortificationlevel - only affects forts

## Editing .worldpkgdesc files via csv

To write the contents of all the worldpkgdesc files in your mod to a csv file use the buttons:  
***Medieval 2 > Worldpkgdesc > worldpkgdesc to csv***  
select your_mod/data/settlements folder and IWTE will search all the sub-directories for .worldpkgdesc files

![M2_worldpkgdesc_to_csv.jpg](../IWTEgithub_images/M2_worldpkgdesc_to_csv.jpg)

The resulting csv file will be found in *IWTE_directory/00_worldpkgdesc* named  
*00_worldpkgdesc_path_to_folder_searched.csv*  
You can load the csv into Excel or similar spreadsheet program

![M2_worldpkgdesc_to_csv_sheet.jpg](../IWTEgithub_images/M2_worldpkgdesc_to_csv_sheet.jpg)

Each element of the pkg files is displayed in a separate column.   If you want IWTE to overwrite the files change no to yes in the Update column before saving as csv and using the 
***Medieval 2 > Worldpkgdesc > csv to worldpkgdesc*** button.


