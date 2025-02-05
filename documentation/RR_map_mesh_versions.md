![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)
# Rome Remastered Map Mesh - Version Options

IWTE's original version of the map mesh process was released soon after Rome Remastered.  V2 is more recent and by default uses some textures built into IWTE which attempt to emulate a vanilla feel on the map.

As the map mesh can vary from a strict interpretation of the campaign map_*.tga files IWTE introduced several new features that allow more variety, including a 'map_heights_lakes.tga' that is used to avoid coastlines and excessive sinking of inland lakes, and dummy map climates that can be used to alter the albedo textures generated.  Dummy climates are an example of giving IWTE different data to that which will be used in game, this is fine but should be used with caution in case it confuses players about where they can move, or what they should expect on a battle map.

Both map generation processes contain options to accentuate certain features and/or change the textures to take heights and slopes into account.

### Main differences between versions 

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
