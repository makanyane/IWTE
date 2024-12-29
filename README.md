# IWTE
# *****PLEASE NOTE THIS REPOSITORY IS WIP AND SOME TASKS/INFO RELATE TO THE AS YET UNRELEASED 2025 VERSION OF IWTE*****

Repository for the IWTE tool, developed by wilddog to enable modding of the Total War games, Medieval 2 Total War, Rome Total War and Rome Remastered.

Information about IWTE and Total War modding is also available on [TWC WIKI](https://wiki.twcenter.net/index.php?title=IWTE)\
Other tutorials and links are listed [here](documentation/tutorials_and_links.md).

Information in this repository relates to using IWTE in conjunction with [Blender](https://www.blender.org/).  Blender is a powerful and FREE 3d modelling program. 
Extract to dae/glb may also work with 3dsMax but problems with 3dsMax use are not supported by the IWTE team.  The original Milkshape (ms3d) options have been retained but are not generally detailed here.  If you are new to modding with IWTE we do not recommend using ms3d as it has size and other limitations.

#### Table of Contents
* [Task File Processes](#Task-File-Processes)
* [Preferences](#preferences)
* [Launching and Error Reporting](#Launching-and-Error-Reporting)
* [Functions for M2TW](#Functions-for-M2TW)
* [Functions for RTW and Rome Remastered](#Functions-for-RTW-and-Rome-Remastered)
* [License](#License)


## Task File Processes
Many processes undertaken by IWTE are accessible and/or easier to use via the task file process.  The process is initiated by selecting a task file from the button shown below.

![image](IWTEgithub_images/task-file-button.jpg)

For further information see [Task File Overview.md](documentation/Task_File_Overview.md)

## Preferences
As from 2025 versions certain preferences can be set and stored.

![image](IWTEgithub_images/preferences.jpg)

Settings and some frequently used paths will be stored in iwte_settings.txt in the IWTE folder.

Options accessed from main screen buttons are:
* Extract File\
dae, glb, or ms3d - the selected type will be used as default for cas to extract and mesh to extract processes, please note that some conversions are not possible to ms3d due to file format limits.  Glb files can be used in Blender 4+ where support for dae has been withdrawn.
* Game\
all, m2, rr or rtw - select a specific game if you wish to tidy the appearance of IWTE by removing game related functions you don't need
* Mode\
dark or brown - brown is close to the light brown appearance of the pre 2025 IWTE versions

## Launching and Error Reporting
Please launch IWTE using a .bat file, the bat file should be in the same folder as the IWTE.exe and have content:

    IWTE_v25_01A.exe
    cmd /k
The top line should be the name of your current IWTE.exe\
Launching via the .bat file will allow the command window to stay open in the event of an error occurring.  Some errors are also reported via IWTE's pop-up window as in the picture below.

![image](IWTEgithub_images/error-messages.jpg)

The pop-up window allows you to show/hide details, although it will normally be easier to read information in the command window.  If your error is simple e.g. a file not found issue from a task file, you can click 'ignore', fix the file reference and run the task again.  For more complex problems make a copy or screenshot of the error message and click 'close' to shut IWTE.

Useful information will normally be found just before the 'Traceback' part of the error message, and just after the Files listed in the Traceback.

## Functions For M2TW
The following list is a quick round-up of IWTE's current capabilities for M2TW:
* Battlemap - Settlements:\
Editing of .world, .worldcollision, .animinstances, .worldterrain, .worldpathfinding, .worldvegetation and .worldpkgdesc files. Using these files you can completely change the settlement layout, models, textures, effects and lighting.
* Battlemap - Building Animations:\
Editing and creation of new wall, gate and tower animations.
* Battlemap - Environment:\
Editing of vegetation.db, Descr_geography_new.db and .lighting files. Adding/amending of vegetation models and generation of vegetation sprites.
* Battlemap - Mesh Models:\
Editing of skydome mesh and banners. Editing of .mesh unit/siege models whilst merged to .cas skeleton and chained anims. Animation editing including use of animated bone_weapon groups. (via Blender/Max only)
* Battlemap - Model Traversable Network:\
For siege engines, editing by conversion to .txt and back.
* Battlemap - Texture Conversion:\
Single file and directory level conversion of texture>dds>texture and tga>texture
* Campaign Map - [Strat Models (static)](documentation/strat_models.md)\
Editing of residences, trees, resources in Milkshape/Blender/Max.
* Campaign Map - [Cas Texture Check CSV](documentation/cas_texture_csv.md)\
Lists all texture names referenced by .cas files in selected directories in CSV format. 
* Campaign Map - Strat Models (characters)\
Editing of animated character .cas models in Milkshape/Blender/Max. Includes the ability to chain animations together, edit and save back to separate anims.
* Campaign Map - Map Editing\
Supports simple editing of the stratmap TGA and HGT files with files shown at correct relative sizes. This also shows a 3d view of the strat map being edited as well as selection of different colour schemes for the heights HGT map.
* Misc - Image Editing\
A simple painting process editor which supports basic editing of several file types (terrain masks can be edited shown at actual size in relation to settlement).

## Functions For RTW and Rome Remastered
The following list is a quick round-up of IWTE's current capabilities for RTW (including BI and Alexander) and [Rome Total War Remastered.](https://github.com/FeralInteractive/romeremastered).
* Campaign Map - Map Mesh - Rome Remastered Only\
Provides various options for creating the 3d map mesh and textures required in Rome Remastered.
* Campaign Map - Map Editing\
Supports simple editing of the stratmap TGA and HGT files with files shown at correct relative sizes. This also shows a 3d view of the strat map being edited as well as selection of different colour schemes for the heights HGT map.
* Campaign Map - [Strat Models (static)](documentation/strat_models.md)\
Editing of residences, trees, resources in Milkshape/Blender/Max.
* Character Extraction - Rome Remastered Only\
Extracts and converts .cas files for battlemap units and campaign map figures from .pack files.
* Skeletons and Animations:\
Unpacks Rome Remastered skeletons and animations and provides skeleton to text and back option. Allows editing of animations, including in 'chained' format to view and edit multiple animations together.
* Battlemap Settlements:\
Provides [.items to .cas conversions](documentation/battlemap_settlements_RR_and_RTW.md#item-to-cas-conversion-with-iwte). Provides [settlement plan editing options](documentation/battlemap_settlements_RR_and_RTW.md#settlement-plan-editing-with-iwte) including a 2d window option to edit plans including wall layouts and a conversion to 3d options to allow editing in Blender.
* Battlemap - Environment:\
Allows read/edit of geography.db
* Misc - [Cas Texture Check CSV](documentation/cas_texture_csv.md)\
Lists all texture names referenced by .cas files in selected directories in CSV format. 
* Misc - dds Conversion:\
Decompresses dds image files that use LZ4 compression, also applies LZ4 compression


# License
**IWTE disclaimer**\
IWTE IS PROVIDED "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED.

IWTE is a python based application which makes use of the following libraries. 
Please see the licence for each item for more detail (available on their respective web sites). :
Access to the software is obtained from their respective sites.
* Python     PSF
* Numpy      BSD-3
* Scipy      BSD-3
* PySide2    LGPLv3
* Lz4        BSD-3
* Pillow     HPND

The below executables can be called by IWTE. They are provided as is via Nvidia (see Nvidia_licence.pdf). You can obtain them from the Nvidia site.
* nvdtx.exe
* Readdxt.eve

The below executable can be called by IWTE. It is provided as is and is subject to the MIT licence. Newer versions can be obtained from the [microsoft github page](https://github.com/Microsoft/DirectXTex/wiki/Texconv).
It is used to handle certain texture conversions.
* Texconv.exe
