# IWTE Image Processing Functions

Whilst not primarily a graphics program IWTE has a variety of image editing/viewing/processing functions:
*  [Basic Image Editing](#Basic-Image-Editing) 
*  [M2 Terrain Mask Editing](#M2-Terrain-Mask-Editing)
*  [M2 Texture Conversion Options](#M2-Texture-Conversion-Options)
*  [RR dds LZ4 Compression Conversion Options](#rr-dds-lz4-compression-conversion-options)
*  [Strat Map tga/hgt Editing](strat_map_base_file_editing.md)

If not saved into the source directory, edited images will normally be saved to the *IWTEsave* directory.

## Basic Image Editing

A variety of image file types can be opened and edited in IWTE including M2 '.texture' files which are .dds files with an additional header section.  The recommended save type for edited files is .tga which you can then convert to other formats if desired. To show the alpha layer (if an image file has one) click the 'A' symbol, you can then change the View/Hide or opacity options for the top layer to view it.

![image](../IWTEgithub_images/Image-editing.jpg)

There are limitations to the editing options. Images can not be re-sized and alpha layers cannot be added. You're likely to find a dedicated graphics program such as Photoshop more useful for most purposes except viewing images in conjunction with Total War assets.

## M2 Terrain Mask Editing

Terrain mask editing is a special case of image editing.  You are required to load the settlement's .worldterrain file before loading the mask so the mask image can be stretched to the size it will appear in game.  You can then optionally also load the settlements 3 binary files and view the settlement outline relative to the mask.

![image](../IWTEgithub_images/M2_terrain_mask_editing.jpg)

## M2 Texture Conversion Options

M2TW '.texture' files are .dds files with an additional header section which is required by the game.  IWTE includes various options for converting to/from .texture including batch converting all the files in a directory.

![image](../IWTEgithub_images/M2-texture-options.jpg)

Also available via task file see:   
[M2_TEXTURE_dds_to_texture_directory_task.txt](https://github.com/makanyane/IWTE/blob/main/task_file_examples/M2_TEXTURE_dds_to_texture_directory_task.txt)  
[M2_TEXTURE_texture_to_dds_directory_task.txt](https://github.com/makanyane/IWTE/blob/main/task_file_examples/M2_TEXTURE_texture_to_dds_directory_task.txt)

## RR dds LZ4 Compression Conversion Options

Some .tga.dds files used in Rome Remastered have been compressed using lz4.  IWTE provides various options for uncompressing or compressing the dds files.

![image](../IWTEgithub_images/RR-dds-lz4-compression.jpg)

If your graphics program still can't open the uncompressed dds files (they may be in DXT10 format) you can use [TexConv.exe](https://github.com/Microsoft/DirectXTex/wiki/Texconv) to convert them to another form of dds or to tga.

Also available via task file see:   
[RR_dds_extract_to_dds_directory_task.txt](https://github.com/makanyane/IWTE/blob/main/task_file_examples/RR_dds_extract_to_dds_directory_task.txt)
