# Strat Models (static)

General Modding Points to Note:
* Static strat models used on the campaign map in RTW, RR and M2TW are all in the same .cas format.
* The textures used for each mesh are specified INSIDE the .cas file and not in external text files.
* Failing to include the correctly named .tga file can cause the game to crash on campaign load (except in RR where the missing texture will be rendered as pink).
* If the model .cas in a mod-folder uses a vanilla texture, that .tga must be added to the mod-folder.
* Textures can additionally be supplied as dds files named .tga.dds, this allows user manipulation of the mip-maps and smaller file sizes.  A .tga with the correct name should still be supplied, but this can just be 1px size.

## cas_to_extract

The task id you need to convert static cas models to dae/glb/ms3d is **cas_to_extract**, see [task file example](https://github.com/makanyane/IWTE/blob/main/task_file_examples/CAS_cas_to_extract_no_anim_task.txt).

This process can also be accessed from buttons *Cas Models > Cas_mesh to extract*, see picture below

![image](../IWTEgithub_images/cas-to-extract.jpg)

When using the buttons the type of extract (dae/glb/ms3d) will be set by the Extract File type currently selected.
The *Cas_mesh to directory* button performs a similar conversion of all the cas files in a directory.  The task ID for that function is **cas_to_extract_directory** and will need a **<directory_in>** specified.

## Residences

Campaign map settlement models are normally referred to as 'residences' and found in data/models_strat/residences.

General Modding Points to Note:
* RTW and RR settlements have the 'city' element in a different .cas file to the 'wall' elements as walls can be upgraded separately.
* M2TW settlements can have 'faction_variants'
* RTW and M2TW residences are specified in descr_cultures.txt
* RR residences are specified at the top of each settlement_plan text file
* Residence models have a 'symbol' mesh which controls the strat flag position, this mesh should NOT have a texture
* Models with too many triangles or vertexes can cause crashes
* RTW and M2TW residences can have some triangles that face away from the camera removed to reduce size.  RR residences can be viewed from any angle.
