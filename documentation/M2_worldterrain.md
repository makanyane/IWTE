#M2TW .worldterrain file

Each .world (settlement, techtree, ambient or bridge) in M2TW battlemaps uses a .worldterrain file.  
The worldterrain controls the terrain heights and how they merge with surroundings, it also loads masks and textures that are applied to the ground surface.  The merge applied to the heights will also control how much of the information on the .worldvegetation is applied.

See also:
* [M2TW Settlement Modding](M2_Settlement_Modding.md#m2tw-settlement-modding) - overview here
* [M2 Terrain Mask Editing](Image_Editing_and_Conversion.md#m2-terrain-mask-editing)
* [Files loaded from .worldterrain](M2_Settlement_Modding.md#files-loaded-from-worldterrain)
* [.worldterrain - M2TW](https://wiki.twcenter.net/index.php?title=.worldterrain_-_M2TW) - on TWC Wiki

## .worldterrain File Structure
There are up to three sections in a .worldterrain file:  
* heights - float values (+ or -) in a list for a specified number of rows and columns - applied by the game at 8 metre spacing
* terrain merge - float values between 0 to 1.0 in a list matching the heights numbers of rows and columns - used to merge the heights value, e.g. 1.0 terrain height fully applied, 0.0 terrain height ignored
* 'battle merge' - used in settlement terrains only (to give flat area for be-sieging attackers) - applies a notional flat plane at 0 height to extent of around 251x251 rows and columns of terrain - uses float values between 0 to 1.0 to control how this merges with underlying terrain
