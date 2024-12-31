# cas_texture_csv

**cas_texture_csv** is the task id needed to run the IWTE process that generates a .csv file listing all the textures named INSIDE the cas files, see [task file example](../task_file_examples/CAS_texture_tga_list_to_csv_task.txt).  The process must be run from a task file it is not available via button functions.

You can opt to include all sub-directories of your starting directory, so you could select the models_strat directory and include sub-directories to give results including files in residences and faction_variant folders.

The csv file can be opened in a spreadsheet program such as Excel and the columns adjusted/filtered to enable you to find the information you need.

![image](../IWTEgithub_images/cas-texture-csv.jpg)

General Modding Points to Note:
* RTW and M2 will crash if the tga files specified inside cas models are not supplied
* texture.tga location is normally relative to the .cas file, e.g. in /textures folder below the .cas location
* if you have the .cas file in the mod-folder you also need its specified tga in the mod-folder regardless of whether it exists in vanilla/data 
* RR generally does not crash if tga files are missing but will display the object in bright pink instead
* textures are always referred to as *image_name.tga* even if the file finally used is a dds called *image_name.tga.dds*
* where tga.dds files are used you may also have to supply a same named .tga file to avoid crashes in RTW and M2

## Changing texture names inside .cas files

The texture names inside cas files may be changed by converting to 3d extract and modifying in Blender before converting back to .cas

Texture names can also be changed via IWTE screen. 

See [strat_models.md#cas-texture-names](strat_models.md#cas-texture-names)
