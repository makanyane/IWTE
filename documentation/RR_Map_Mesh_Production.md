![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)
# The Rome Remastered Campaign Map

For more information about the RR map please see: https://wiki.twcenter.net/index.php?title=Creating_New_Campaign_Map_in_Rome_Remastered

The RR campaign map (3d view) is not generated 'on the fly' as with RTW and M2TW. It requires various mesh components and textures to be made by the modder. The components required include:
* mesh pieces
* albedo textures for summer and winter
* normal textures
* coastline mesh/meshes
* river mesh
* frame and textures 
* map tiles and coastlines text files
* The picture below shows some of the components converted and opened in Blender

![image](../IWTEgithub_images/RR-mesh-components.jpg)

## Rome Remastered Map Making using IWTE

IWTE will produce all the map components based on the data/world/maps/ tga files and your choice of input textures.

IWTE's original version of the map mesh process was released soon after Rome Remastered.  V2 is more recent and by default uses some textures built into IWTE which attempt to emulate a vanilla feel on the map.

As the map mesh can vary from a strict interpretation of the campaign map_*.tga files IWTE has introduced several new features that allow more variety, including a 'map_heights_lakes.tga' that is used to avoid coastlines and excessive sinking of inland lakes, and dummy map climates that can be used to alter the albedo textures generated.

## Main Differences between Task Versions 

| | Original Version | Version V2 | Notes |
|---|-------------------------|---|---|
| Albedo Textures	| all input tgas must be provided (textures are found via name in climate folder, requiring duplicate copies) | includes optional default vanilla style input textures (textures specified in text file) |
| Texture Variations	|	extra textures can be added based on height	(mtnhigh and mtnpeak only) | all textures can be varied based on 5 settable height zones (additional input textures can be specified for ridge/flat/steep/valley zones in hills mountains and wilderness) |
| Tints	| height related tints can be applied	| n/a |
| Winter Textures	|		requires 2nd run (requires snow added to input tgas)	|	produced on main run, uses map_snow.tga to add 'snow' (white overlay added by IWTE to output textures) |
| Dummy Climates		|	possible				| possible		|NB: not to be used in game |
| Shoreline	| colour applied to height range	| texture applied to height range near coast with added 'contour' lines |
| Hills		|		no special treatment |	small 'models' added to areas of hill ground type (ala vanilla OG) |
| Mountains_high	| ridge heights can be accentuated	|small 'models' added to areas of mountains_high ground type (ala vanilla OG)			|			
| Height scale	|		factor can be applied			|	n/a (check) | NB: not recommended as bridge heights will be wrong in game |
| Materials (normals)		| _bump.tga input textures can be used, mountains need rotated texture to get erosion effect 	| default 'erosion' effect applied to steep areas on hills/mountains etc, bump textures may still also be used


##  Factors Common to both Versions
### Region Boundaries at Rivers
For region boundaries that align properly with rivers you WILL NEED to add in the supplied  
*descr_aerial_map_tile_models.txt*  

text file into the folder:  
*...mod_name/data/*   

and add the supplied or created  
*rivers_a.cas*  

file to the folder:  
*...mod_name/data/terrain/aerial_map/tile_models/river_a*  

Ignoring both files will result in misalignment between rivers and region borders, adding one but not both will result in very messed up region borders!

### Large Maps with a Large Number of Textures
Very large maps which have hundreds of piece tiles may get the dissappearing frame bug due to too many textures.  

  **combine_piece_textures**   
task can be used to join 4 adjoining textures into one - this should be applied to the textures whilst they are in tga format
as part of the process IWTE will modify the cas pieces uv mapping and produce the desc_map_tiles.txt file required to assign 4 tiles to the same texture.

## VERSION _V2 
<task_id>   **create_map_pieces_v2** 

The simplest possible version of this process can be run from the buttons:   
*IWTE > Rome Remastered > Create Strat Map Mesh*   
button.  This will produce the mesh and all necessary components including vanilla style textures.  
The only inputs required are the FOLDER containing your;  
  * map_regions.tga
  * map_features.tga
  * map_heights.tga
  * map_ground_types.tga
  * map_climates.tga
  * map_snow.tga		(optional - if you want snow applied to your winter textures)
  * map_heights_lakes.tga	(optional - use if you want lakes shown on the mesh higher than sea level and without surf)  
Specify your output folder - if this folder has the same name as your campaign folder the text files will be created with the correct path.  If you use a differently named folder you will have to manually edit the descr_map_coastlines.txt and descr_map_tiles.txt

If you specify the folder:
	*your_mod/data/terrain/campaign/campaign_name*
then all the files will be placed in position ready to be used in game.

Running the process from the button will generate a task file for you which you can use to repead the process or adapt if necessary.

## Additional Settings

TO BE CHECKED

## Changing Textures 

To change the textures used away from the default ones included in IWTE.exe add a tag and path to your task file, e.g.
	<strat_map_texture_descr>        "D:\IWTE_folder\my_strat_map_texture_descr.txt" 
That text file will then control the textures used for each climate/ground_type/height_zone combination.

EXAMPLE TEXTURE DESCR FILES
	tutorials_and_guides/RR_MAP_v2_TEXTURES_vanilla_example_texture_descr.txt
shows the set-up used to generate a set of textures that look similar in style to the RR vanilla map using the inbuilt IWTE default/generated textures

*RR_MAP_v2_TEXTURES_basic_example_texture_descr.txt*  
gives a simplified set-up removing the additional tags for steep/valley/flat/ridge etc, and removing the variation by height zone (it is not recommended that you use this version as-is, it's just to show that you don't have to include the extra tags/zones)

* RR_MAP_v2_TEXTURES_own_textures_example_texture_descr.txt*
shows what a simple file using some of the new ground_type tags and your own textures could look like - the example is from a work-in-progress mod based on Britain, the climate variations are minimal so the climate default textures are used for most climates except where variations such as white cliffs are required

Paths inside the texture descr files are relative, those starting \iwtepack will look inside the IWTE.exe

### Recommended Further Reading (V2)
TWC Wiki:	https://wiki.twcenter.net/index.php?title=IWTE_-_Rome_Remastered_Functions

PLEASE ALSO SEE EXAMPLE TASK FILES
Create mesh and textures v2;	 	task_file_examples/RR_MAP_MESH_v2_vanilla_style_textures_task.txt

##      ORIGINAL VERSION    
<task_id>   **create_map_pieces** 

Please note this process is still supported but is seperate and different to the newer v2 process (from 4th August 2024)

IWTE map making is primarily a task based operation and you should set up a task to use it to its full potential.  
The task allows options to be switched easily and makes it very easy to rerun or change things.  
It will require a basic once off setup but should be easy enough to maintain.  
Some of the 'tags' used in the file have changed with IWTE releases see notes below.  
tag names are very important if you use an incorrect name it will not be found.  

Please be aware the texture producing components of the map will take a long time to run. It is always best to have a console window open to see the progress.  
You can of course open multiple IWTE versions for use at the same time or get on with something else whilst it runs as a background task.

Please note the files will be produced at a 2048x2048 standard size. 

To create and use a specific bump map to provide variation to the material (normal) it just needs to be named the same as your input *.tga but ending *_bump.tga.   
Any bump map tgas should be placed in the appropriate climate ground type folder. 

### Recommended Further Reading (Original Version)
Kirsi's - Mapping Guide:  				https://drive.google.com/file/d/1b4hKawiIf2ZoqsBnGUNpsGQowbgMrusI/view?usp=drivesdk  
TWC Wiki:						https://wiki.twcenter.net/index.php?title=IWTE_-_Rome_Remastered_Functions  
Makanyane's Demonstration Textures and Folder Setup:	https://drive.google.com/file/d/1TnICOKHdNzf0n5vmKbyvZjAGX8MnDVQI/view?usp=sharing  

PLEASE ALSO SEE EXAMPLE TASK FILES
Create mesh and textures original version;	 	task_file_examples/RR_MAP_MESH_older_version_task.txt  
Converting material tgas to dds;	 		task_file_examples/TEXCONV_tga_to_dds_materials_task.txt  
Converting albedo tgas to dds;	 			task_file_examples/TEXCONV_tga_to_dds_albedos_task.txt  

##       CHANGE NOTES       
IWTE_v22_02_B : added <sea_drop_list> and <drop_loop_factor> to control drop in sea depths

IWTE_v22_06_C : added beach parameters
```
# beach related parameters
<beach_factor>                    0.50               # 0 to 1 ratio for beach v non beach texture (higher makes beach color stronger)
<beach_rgb_list>                 208 187 161         # RGB color for the beach)
<beach_high>                      1.1                # Beach height high point (beach will cover up to this height at 100 percent color)
<beach_merge_high>                1.5                # additional height to merge beach color eg merge from 1.1 to 2.6
```
IWTE_v22_07_A : added parameters
```
# added 4 dummy climates - they can be used in the climates tga that IWTE will use but should NOT be used in game.
# set up is the same as other climates and are identified by the rgb values indicated.
<dummy_white_gt_dir>                           "I:\IWTE_v22_07_A\base-textures\dummy_white"		#255 255 255
<dummy_black_gt_dir>                           "I:\IWTE_v22_07_A\base-textures\dummy_black"		#0 0 0
<dummy_green_gt_dir>                           "I:\IWTE_v22_07_A\base-textures\dummy_green"		#0 255 0
<dummy_blue_gt_dir>                           "I:\IWTE_v22_07_A\base-textures\dummy_blue"		#0 0 255

#river height parameter value is equivalent to applying a greyscale reduction. 
#if you use extreme values you will get extreme results and I would advise amending your TGA heights.
<river_drop_height>                     1.5                     # rgb equivalent drop in river height. A value above 10 may look extreme and best to amend your map heights tga

#Added parameters to set the background colors for River (beds/edges), Fords, and Volcanos.
#They are RGB values
<river_rgb_list>                 75 67 55                      # rgb for river bed and edge
<ford_rgb_list>                  146 125 88                    # rgb for Ford edge 
<volcano_rgb_list>               101 90 73                     # rgb for volcano
```
IWTE_v22_07_C : parameter for textures
```
<texture_size>        1024             # will generate textures at 2048 pixel size instead of 2048. You need to make sure your textures tile correctly.
```

IWTE_v23_02_B
```
list of dummy climates has been updated.
 <dummy_black_gt_dir>            "I:\IWTE_v23_02_B\base-textures\dummy_black"		# 0 0 0 has been removed (due to a clash within IWTE).

<dummy_white_gt_dir>             "I:\IWTE_v22_07_A\base-textures\dummy_white"		# 255 255 255 existing
<dummy_green_gt_dir>             "I:\IWTE_v22_07_A\base-textures\dummy_green"		#   0 255   0 existing
<dummy_blue_gt_dir>              "I:\IWTE_v22_07_A\base-textures\dummy_blue"		#   0   0 255 existing

<dummy_yellow_gt_dir>            "I:\IWTE_v23_02_B\base-textures\dummy_yellow"            # 255 255   0 added
<dummy_cyan_gt_dir>              "I:\IWTE_v23_02_B\base-textures\dummy_cyan"              #   0 255 255 added
<dummy_magenta_gt_dir>           "I:\IWTE_v23_02_B\base-textures\dummy_magenta"           # 255   0 255 added
<dummy_navy_gt_dir>              "I:\IWTE_v23_02_B\base-textures\dummy_navy"              #   0   0 128 added
<dummy_grey_gt_dir>              "I:\IWTE_v23_02_B\base-textures\dummy_grey"              # 128 128 128 added
<dummy_purple_gt_dir>            "I:\IWTE_v23_02_B\base-textures\dummy_grey"              # 128   0 128 added
<dummy_silver_gt_dir>            "I:\IWTE_v23_02_B\base-textures\dummy_grey"              # 192 192 192 added 
```




