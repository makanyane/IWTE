![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)
# M2TW worldterrain masks
Each .worldterrain file used for settlements, techtrees or ambients can have up to 4 mask files specified.  In vanilla these are normally used for path, mud, farm1, farm2, but you can use them to apply any sort of ground texture within the .worldterrain area.

The picture below shows a .worldterrain loaded in IWTE for mask/texture path changes.

![M2-worldterrain-mask-paths.jpg](../IWTEgithub_images/M2-worldterrain-mask-paths.jpg)

Each mask controls a macro and micro texture placement.  The paths and names of all the masks and textures are editable. All the files must end .tga in these entries, but the actual files supplied should be .texture.  The scaled size of the textures can also be changed.

If the path to a mask texture is not found you will get the macro/micro textures applied over the whole terrain.  Missing macro/micro textures will display as black.

## M2 Terrain Mask Editing

Terrain mask editing is a special case of image editing.  You are required to load the settlement's .worldterrain file before loading the mask so the mask image can be stretched to the size it will appear in game.  You can then optionally also load the settlements 3 binary files and view the settlement outline relative to the mask.

![image](../IWTEgithub_images/M2_terrain_mask_editing.jpg)

NOTE: Masks used for techtree slots should have at least the outer pixel as pure black, having any grey (applied texture) in the outer area results in the tecthree slots' ground texture overspilling onto a wide area of the settlement.
