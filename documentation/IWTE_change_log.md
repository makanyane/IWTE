# IWTE change log

When using IWTE we recommend always using the most up-to-date version, but also keep a copy of version/s you have been using successfully.  Sometimes a version upgrade can introduce a problem on a specific process and we may have to advise you to return to an earlier version until the problem is fixed.

#### Table of Contents
* [Changes from 25_02_beta onwards](#Changes-from-25_02_beta-onwards)
* [RR map mesh change notes ](#rr-map-mesh-change-notes)
* [Other changes in reverse date order](#other-changes-in-reverse-date-order)
* [Copy of some earlier release information](#copy-of-some-earlier-release-information)


## Changes from 25_02_beta onwards
with version25_02_beta (Major release/upgrade)
1) ALL  - Most components have had various software upgrades. We have tried to fix all of them but there may be some obscure or legacy processes that may encounter issues.
          (this is also the reason for the large increase in size)
        - A new settings tab has been introduced allowing you to switch certain options eg UI mode, extract type, game type, 3d view options.
        - A color scheme is now implemented supporting a dark mode alternative to the more traditional brown setting (the UI mode).
        - extract types now includes the glb type (GLTFv2 format - this has been tested with Blender 4.3).
        - game type selection will customise the main menus for Rome (rr) or Medieval 2 (m2). This hides most of the non wanted options.
        - paths within task files can be shortened to relative paths for any directories below the IWTE executable.
        - a settings file is now used to save last directories and other settings.
   M2   - vegetation model changes are now supported via glb/dae and ms3d. A correction to the normals hae been introduced.
        - vege sprite generation is performed in a hidden mode.
        - 3d viewing of .world files should now be seemless using the settings options to switch between texture, effects or shading modes, and with/without normals. 
          (the .texture files required should be in the textures directory below the model or for .world be in the IWTEsave directory. No need to convert.)
        - added unit .mesh directory to extracts option (no skeletons involved).
   RR   - mapping processes have been amended for the v2 process. Memory usage has been addressed (major slowdown on mesh production of large map mesh).
        - creation of Fe maps is now handled via a task.
        - combining textures for large maps now works from DDS or TGA files.
        - some of the features tied to version 1 of the strat map have been added into v2 (mostly mountain, ridge variability).
        - some of the features used in version 2 have had added factors added (size of added mountains/hills/volcanos).
        - updated Settlement plans to use items if issues with cas models (not found or can't open).
   M2/RR- various other improvements, fixes.

Thank you for the contributions of those that offered suggestions and feedback. Any issues found please notify so we can correct or add as I suspect the settings process is likely to have various requests tied to preferred workflows which may not be catered for.
##  RR map mesh change notes       
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

## Other changes in reverse date order

with version24_09_A (bug fixes)
1) M2/RR  - milkshape bug fix (format type).
   M2     - Correction to main object copy/pick for copying Arrowtowers (and their arrow slots across multiple selected towers)
   M2/RR  - Removal of special characters in static cas mesh names.

with version24_08_D
1) RR - new map process - bug fix where long coastlines exceeded a single cas file.
                        - changes to lakes process to  not add a river mesh if the 'lake is' RGB 2,2,2 or less (saves on river mesh)
                          and to prevent adding of 'shores' in some cases the covering lake TGA values may need to be extended past
                          the 'sea' boundary.
                        - amended default iwte_mountains_med to slightly mute its color.

with version24_08_C
1) RR - new map process - bug fix for maps where longest dimension was rows.
   M2 - New option Engines extract units bug fix. Skeletons now included and issue on returning to screen (after cancelling) resolved.


with version24_08_B
1) RR - new map process - now uses map_heights_lakes.tga if found in the 'base' directory. A version for use with vanilla included in IWTE.
   M2 - New option added Medieval 2 -> M2 Units -> Engines extract units. This will extract the engines and create dae and dds files 
       (provided vanilla M2 has been unpacked).

with version24_08_A
1) RR - new version of IWTE strat mapping. Old 'create map mesh and create map frame options have been removed from the drop down menu. 
        A single option 'RR strat map' has now replaced them.
        The new option will ask for the base directory and the output directory. It will then generate the relevant files in the output directory. 
        It is a WIP and does take a long time to run 15-20mins on a vanilla sized map.
        If you have the utility Texconv.exe in the same folder as IWTE it will generate the required DDS files and remove the TGA's. 
        The last name of the output directory will be used in the generated text files.
        A new snow_map.tga is included with correct sizing for the vanilla RR map.
   M2 - corrected Texture to dds task to include subdirectory path.


with version 24_05_b - RTW/RR/M2 bug fix
1) RTW/RR - bug fix. Updating geography.db was not replacing 'none' entries.
2) M2 - bug fix. meshnames for cannon ball0 and Ballista arrow0 corrections.

with version 24_05_A - RTW/RR/M2 bug fix
1) RTW/RR/M2 - Correction to cas animation conversion from dae. Corruption introduced with 23_10_A (2). Caused corruption of bone index.

with version 24_02_A - M2 bug fixes
1) M2 - check on modeldb incluudes check on correct serialisation string.
2) M2 - bug fix skeleton/evt process corrected for camel skeletons.

with version 23_12_A - M2 - enhancement/fixes
1) Bounding sphere error (sometimes crashed) has been corrected.
2) copy main object copies arrowtower and gatehouses firing slots from the selected (or picked) object. 
 If the arrowtower to copy from has less objects than the receiving tower the arrow slots in the copyfrom last level will be copied to the copy to extra levels.
3) Selecting the open 3 binaries always asks for a new save file name.

with version 23_10_A - RR/M2 - cas conversion issues/bug fixes
1) RR/M2 - fixed crash tied to changes in 23_06_A (incorrectly checking for names when processing an animation format cas).
2) RR/M2 - fixed cas animation issues which were ignoring position changes.
3) RR/M2 - fixed cas to dae/ms3d spaces not being replaced by double underscore for non skeleton cas.
4) RR/M2 - if alpha color not returned in dae (rgba) IWTE will default to 255 rather than 0.
5) RR    - Engine cas models should default to the correct settings.


with version 23_06_B
1) RR - engines - removed automatic IWTE crash when default/animation pose does not match cas mesh pose.
                  warning messages are still issued in the cmd window as there is likely a corruption.

with version 23_06_A
1) RR - Amendments to support engine handling.
      - double underscore in bone name converted back to space (needed for wheel rotation).
      - cas mesh bone names switched to first animation names on export to dae (names in first/default animation drive wheel rotation)
      - IWTE will detect and crash if animated cas has bones not aligned with the cas mesh (eg the unused animation ballista_cranking.cas) 
2) RR/M2 - IWTE creates an error message containing mesh name and size if vertex/triangle limit exceeded.


with version 23_05_A
1) M2 - Amendment to ms3d terrain edditing. 
2) M2/RR - cas model amendment to reduce vertex data.
3) special case to handle ampersand in a mesh name.

with version 23_03_A
1) RR - strat map - Amendment to the mountain ridge process to reduce the little peaks/teeth effect. 
   RR - strat map - Amended volcano slightly to avoid a triangulation issue.

with version 23_02_C
1) RR - bug fix - index issue when exceeding 255 textures to create the strat map.
2) M2 - bug fix - issue reading the EDU correctly in certain cases when generating the unit card spreadsheet.

with version 23_02_B
1)RR - strat map change - extra default climate colors changed. Black was removed in version 23_02_A but total number has been increased to 10 (from 4 in earlier versions)
       see Rome remastered map making info.
2)M2 - Modeldb to mesh corrected to produce all dds used (it was producing just the ones for the first faction).
3)M2 - Added task unit_card_data which can be used to help produce the spreadsheet required to use the Feral unit card tool.
4)M2 - Amended adding a mainobject for walls so that multiple default objects can be selected and classed as walls and have their docking points and breaches set (provided their collisions exist).
5)RR/M2 - Added example in the task processes to use the cas_texture_csv task to create a csv of the textures within the cas models. 

with version 23_02_A
1) RR - strat map creation - minor amendments and slight improvements on timings.
2) RR/M2 - bug fix - corrected left/right swap in IWTE view 
3) M2 - bug fix - world shading/effects
4) M2 - bug fix - weapon animation cas incorrectly overwritten when used as a non default animation.

with version 23_01_B
1) M2/RR - bug fix for option dae/ms3d to cas - crashing due to wrong internal name.

with version 23_01_A
1) M2 - bug fix to recently introduced bug on Shield weapon handling.
2) M2 - bug fix modeldb read looping if no end of line detected.
3) M2(RR) - Added conversion and readback for Milkshape battle units
4) M2 - added option to support modeldb units to ms3d
5) M2 - some renaming of selection options tied to support for milkshape.
6) M2/RR - various amendments/fixes tied to unit amendment processes.

Please note the milkshape functionaility is based on the existing IWTE dae functionaility. 
Naming/comments is different to older (non IWTE) ms3d processes used in m2. 

with version 22_12_B
1) M2 - bug fix - worldpkgdesc not updated correctly for culture changes in settlements using the csv files.
2) M2/RR - create warning message window if cas_mesh or *.mesh(M2) has no weighting assigned.
3) M2 - Added mesh_view option which displays a mesh and its bone weightings with normals.
4) M2/RR - cas Mesh view option now displays the bone weightings similar to the mesh. 

with version 22_12_A
1) M2 - added modeldb check for the unit type count.
2) M2 - an ability to use black and white instead of the blue/green for pathfinding.
3) M2 - An ability to use a new skeleton (which should have a mesh related to it) and then convert existing skeleton.dat (format) associated animations. see task example convert_from_skeleton_to_new
4) M2 - bug fix - a change to correct the pathfinding changes stopping re-editing of the pathfinding file.
5) M2 - automatically convert textures to dds for selected modeldb unit types (part of the select from modeldb process).
6) M2 - Creating/Renaming the extracted skeleton animations that have a different bone count to the skeleton (it adds a suffix to the created animation cas file).

with version 22_11_C
1) M2 - bug fix - correction to creation of descr_skeleton.txt file

with version 22_11_B
1) M2 - bug fix - corrected evt file sound name (removed quotations).

with version 22_11_A
1) M2 - bug fix - Weighting check for converting mesh to dae was not functioning correctly and causing a crash.
2) M2 - bug fix - If a skeleton has a bone with  a parent higher than itself a warning message is issued (previously IWTE crashed)
        and the parent is automatically re-assigned to bone 0.
3) M2 - new process Medieval 2 > M2 units > skeletons convert to cas/evt. This will read the skeleton dat/idx and extract the animations, evt and create a descr_skeleton.txt.
        The extracted animations are the caliban style (full) cas files. This should support the game recreating the skeleton.dat/idx and packdat/idx files.
4) M2 - new process Medieval 2 > M2 units > modeldb units to dae. This will bring up a list of the models in the modeldb file and allow you to select and extract them to create dae files. 
        The individual task files are also created to allow conversion back. 

with version 22_09_C
1) RR - strat map - IWTE bug fix (bug introduced in 22_07_C).
   RR/M2 - extra task parameter to correct cas saved with incorrect scale versus mesh 
           eg to fix RR mount_elephant_african_cataphract_lod0.cas when extracting to blender
           add line 
           <cas_skeleton_scale_correction>                     100.00 
           to the cas to dae task
   RR/M2 - New process to run a list of tasks

with version 22_09_B
1) M2 - bug fix - correction for handling M2 unpacked animations (it wasn't treating it as M2).

with version 22_09_A
1) RR - strat map
      - Bug fix - river crash fix for specific case on edge of map.
      - Amendment to texture handling to reduce impact of non tiling textures.
 2) RR - Bug fix to handle bone names with spaces

with version 22_07_C
1) RR - Bug fix - unit unpacking - selecting wrong directory then correct one gave an error message.
2) RR - strat map
      - correction to texture/material at map edges.
      - Added parameter to create textures at 1024x1024 (instead of 2048x2048).
      - Added task option to combine textures and amend cas pieces (it is a seperate task).
      - generates a version of the descr_map_tiles.txt file 

with version 22_07_B - bug fixes
1) RR - Strat map 
        - coastline mesh bug fixes.
        - mesh albedo/material texture bug when using large piece sizes
   M2 - Removed button options for for worldvegetation (as now replaced by drop down options).
      - slight renaming of the tga files created for the wordvegetation.
   

with version 22_07_A
1) RR - Strat map enhancements
      - Changed River mesh creation to reduce amount of created river mesh.
      - Changed IWTE lakes mesh creation. It now uses a quarter of the mesh required previously.
      - introduced new parameters to lower river heights whilst valleying the close surrounding area.
      - introduced 4 IWTE dummy climates (ie for use only with map mesh creation). 
      - introduced new parameters to support amending colors for river, ford and volcano positions (amended).
2) M2 - Added options to generate 4 vegetation TGA's and read back (individually) for the worldvegetation file.
        warning - naming will be improved once I have feedback.
3) RR - Amendments to cas editing task process to support cas horse riders (similar to M2 mesh process). 


with version 22_06_C
1) RR - Settlement Plan  - Changed the required directories to exclude the final '\data'. This is to support easier inclusion of BI directories.
        You just need to supply your mod directory and the remastered directory down to Total War ROME REMASTERED\Contents\Resources\Data
      - included the gateway slot underlays
      - The 2d now shows the grid axis, a 2000 square and a 1700 square so you can more easily determine size limits for placing items.	 
        I have not tested the size limits that the game may have.
      - bug fix tied to comments at the end of a line.
2) RR/M2 - cas mesh viewer - should open up a simple 3d window to view cas models quickly rather than download to DAE. 
        Please note closing the window does cause a known error if it is reopened in the same session (its fine if you leave it).
3) RR - Strat map creation includes some new parameters to allow a height based beach color to be added. See the map making info text file.  
        

with version 22_06_B
1) RR - bug fix - settlement editing bug fix for diagonal wall link (adding a new one wasn't diagonal!)

with version 22_06_A
1) M2 - included recalculation of world bounding sphere whenever the settlement model is changed and removed the button requiring manual triggering.
2) M2 - Added message to indicate if someone has exceeded the object/group size limit (M2 settlements) for the collada interface.
3) RR - Added message to indicate if a mesh is missing weight data.
4) RR - Amended RR buildings item/cas options : 
        A) new item to cas option converts an item to its cas content. 
           The resultant cas files will be named after the item and have a lod level assigned to the name.
        B) items.db/items to cas uses the items db and the cas items in the supplied items file to convert those items to cas.
        C) items.db/cas to items uses the items db and cas to make items 
           (only required in some specific cases as a replacement item to the ones already generated) 
        note that options B and C are renamed options from the 22_04_A release.
5) RR - Settlement plan - edit walls. Requires a settlement plan to read then allows updates amendments to its walls only.
6) RR - Settlement plan edit - Requires settlement plan, mod data directory, Vanilla data directory. Supports editing of the settlement plan.
        It also provides an option to extract the plan to dae and creates a task file to load the dae file back. 
        Please note that only the basic items are editable and if a cas file cannot be opened the item will get omitted at this time. This should only
        be a problem with some early cas models cas version less than 2.151 eg in Roman village.


with version 22_04_A
1) RR - Item to cas converter - Rome Remastered > RR Buildings > item to cas. This will ask for a directory containing BOTH the descr_items.db AND an items directory
        which should contain only the items you wish to extract. If an item texture is found not ending with the '.tga' suffix it will be added.
2) RR - cas to item converter - Rome Remastered > RR Buildings > cas to item. This will ask for a directory containing BOTH the descr_items.db AND a 
        models_building directory (set up the same as RR models_building directory structure) which should contain only the cas files you wish to convert. This
        is only meant to be used for some animated cas files which you are trying to use (the impact on the game engine has not been tested).
        This is just an alternate method allowing you to create a replacement item for one you have already generated an item for (and a new descr_items.db)
        in case the animation wasn't working as expected.
3) M2 - Removed the addition of the weapon04 bone and reference in the M2 mesh files IF it is not used (old milkshape routines cannot handle it).
        


 
with version 22_02_B
1) RR - Map Mesh - Added tags <sea_drop_list> and <drop_loop_factor> used to control sea depth drop.
2) RR - Map Mesh - Amended rivers that end with a Ford to look like a rive End (to ensure mesh all links up)
3) RR - New Skeleton from model - amended to include descr_skeleton_feral_overrides.txt. 
        You need to add data\animations\extra into the anim extract directory you are using in order to correctly find the animations.
4) RR - zeroed the translation flags in the skeleton when using the above option.
        (AFAIK they don't do anything in the BI version of RR which is the version we test IWTE on. They do impact Rome version so people may need to re-add).
5) RR - Skeleton to text. Correction to align handling of animal footstep sounds (previously defaulted to human).



with version 22_02_A
1) All - bug fix to retain any color bytes in original cas file for non unit cas files (they were previously removed other than for settlement platforms). 
2) All - Edit cas texture reference option added to Model Files menu. (Replaces strat_map texture editing which has been removed).
3) All - correction to animations 'flipping' in certain circumstances when loading a dae animation.
4) RR - Ability to write and read back an RR version of an unpacked text format skeleton file.
5) RR - Added option 'Models skeleton replacement' this is to use a new cas_mesh model to change a directory of existing cas_mesh models to the same skeleton setup.
        e.g. to convert similar models including ethnic variants and lower lods.
There are no RR map mesh changes involved in this release. Only known issue (with the tool) is Fords used as a river end point.



with version 22_01_A
1) RR - Amended river creation process to reduce number of vertices/triangles to support large detailed maps with rivers.
2) RR - As part of the above the river bends have been altered and will require you to add the new river_a.cas file into the mod folder.
        If you don't there will be a difference on the region boundaries (because they are now different!).
3) M2 - Fixed the 3d view of the settlement ground terrain so it doesn't show mostly white (sorry about that).
4) All - bug fix to read cas version 3.13.
5) RR - Changed drop down menu to include "RR units" options. This now contains the following:
        The character model extraction 
        Animations extraction and packing (RR version and extractions only extract as scale size 1.0)
        Skeletons extraction and packing (RR version only - Use existing NON IWTE processes for Rome OG)
        New scaled Skeleton (RR Version only)
        New skeleton from Model option (RR versions only - also modifies the unpacked animations referenced in the unpacked skeleton)
        YOU need to separately convert OG stuff to RR versions before using any of the above.
6) RR - Further speed up on Map texturing.


## Copy of some earlier release information

Below is some basic info taken from earlier release notes.
**********************************************************

Some basic notes: 
Make sure type of structure aligns with texture type, ie. essentially reflective plane and water need to be together and then the others. Litter is identified but not used. Think it may be useful for some perimeter bits so added it at this stage.

Collisions:  Collision models are not automatically updated by this tool.  Deleted objects will be removed from the objects list in the collision file, but their collision model table will be left in place, as it may be shared by other objects.  Added objects are added to objects list in the collision file but have -1 entry so they do not use a collision model.   Individual objects can be selected to have collision model added later.  

Animinstances: The file is ammended to the extent of preserving existing animations for gates, walls and towers etc, if their objects are retained in the world file.   You can add existing CA animations to the file but There is no way currently to add your own. The tool will not check if you add the wrong animation (or collision) so this may crash in game if you make a mistake. 

Perimeters: Objects are not automatically added to the perimeters you need to add the necessary ones via the option. It will not check if you ahev perimeter 3 and 1 but no perimeter 2!

Effects: can be created via their text files and then added using the tool. Only issue here is the tool does not support certain lighting of surrounding objects so fires etc do not cast light to the extent they did in the CA models.

Split Objects: Should handle the objects split over 2 different structures by deleting all of them in the other structure and adding single entries back in (this is to protect collision - complete deletion meant trying to handle deletion of vertices etc so this was left).

Deletes: take everything associated out with the involved objects, eg. pathfinding, effects, and game objects like arrow towers.

MS3d files generate with file names including complex and structure identifiers and then internal groups are identified with the following IMPORTANT structure eg .
    Eo102_g0_c6s1 
this breaks down as
 E= extracted - any other letter and this will cause a break at this point all further groups are considered new (ie adds and anything left in memory will be considered a delete)
 o = object but is irrelevant
 102 = 1st number = the object number within the COMPLEX - this is because complex numbers spread over several structures.
 _ =irrelevant other than if a second number exists there needs to be a non numeric seperator
 g = irrelevant just identifies a group next
 0 = 2nd number -number of group within that object - ie an object can have several groups eg max seen is 6 (it is tied to damage changes and needs to match to collision information).
 _C6s1 = complex and strucuture identifiers -irrelevant but useful if merging bits from other structures 

The above allows a match up to ensure charatceristics of objects are retained. Rules you need to follow :
  i) Always add items at the end - because if a group isn't recognised as an extracted one for that structure it assumes a split point and eveything after it is added and everything 'missed' is deleted.
  ii) Always delete complete objects  - eg deleting 1 of a group of 3 items belonging to an object may give a mismatch for collisions which still expects 3 - this is because of overlaps in collisions where damage stages are reused (ie more than one group of 3 objects refers to the same damage. Also I think it probably upsets code to handle object groups in different structures.
  iii) When adding new items - the fist number is considered the object and if a second number exists after non-number seperator its the group. Group sequence doesn't matter it will simply renumber 0, 1 etc.  Eg; if you want two new objects with two groups each, number the ms3d groups like:
  1-1
  1-2
  2.1
  2.2
or similar.

File handling feature :
  A)for structure changes you will be asked to select the .collision and .animation files and for change or adds the ms3d file.
  B) You then select the new file identifier (name) - all files will be assigned this identifier ie identifier.world, identifier.collision etc  We suggest you do not overwrite the original files, choose a new name and then rename the old files with x etc.. then switch new files to proper name to test.
  C) Each structure change results in a set of new files being written and reference .txt files, these can take a lot of disc space for large settlements.
  D) Test feature is repeated updates - each update after the first results in a NEW file beign created with a sequential number eg identifier_1.world, identifier_1.collision  This feature is only recently being tested so watch out. It allows you to back track hrough changes in case you deleted soemthing you shouldn't have.... 


**********************************************************************************

Textures
1) Select appropriate texture from the list
2) Select appropriate button
   A) Read binary world file - allows selection and input of binary.world - this repeats on various screens
   B) Change texture - allows you to change the type of texture and its path and its normal path. Changing type here doesn't cause corresponding change in struture type info so changing water to something else would cause a crash!   
   C) Add a texture - allows adding of a texture SO YOU CAN THEN ASSIGN it to a strucure ( see structure info above). If you do not assign it then it will be lost as this is just an internal table.

relevant things to watch - water should be assigned to structures with reflective planes. It will cause a crash if not (or at least if you have a reflective plane that doesn't have water). Also water uses the same texture name for texture and normal.


HOW TO USE TERRAIN FUNCTIONS
***********************************************************************************
RESIZING:
Resize buttons should be self evident but please use the same resize parameter for all terrain files relating to the same settlement. A size of 215 takes the complete battlefield. You can overlap slightly. Any value below the current files size value has no affect. ie this tool enlarges only.

Parameter information:
Resize must be to an odd value - and this only enlarges. Any smaller value will achieve nothing but can be used with the merge functionality (eg if you decide to remerge the edges).

***********************************************************************************
WORLD TERRAIN OPTIONS
1). Create an ms3d file - you can then edit in Milkshape or view it there. Note if you create a very large terrain size and try to export to ms3d you may encounter the ms3d limit on number of vertexes.

2). Replace an ms3d file - this allows you to read in the Mikshape file (this is similar to previously released tools but with the option to use the merge distances parameter*).

3). Create Terrain TGA - creates a TGA using the height parameters** currently set (if you change the default parameters make a note of your revised values at time of TGA extraction and use the same ones for re-import).

4). Replace with terrain TGA (with option to use the merge distances parameter*) - reads in GREY SCALE VALUES ONLY and uses the height parameters** currently set  (if you changed default values when you generated the TGA initially, you must use the same values to re-import)

*Merge Distances - this is optional.
The parameters set the number of vertices over which the merge value transitions from 0 to 1. This value determines the relative blending of the background tile versus the settlement tile. At 0 you don't see the settlement tile and at 1 you only see the settlement tile. Small values will give a clear cut border  where they join. Larger values allow a gradual merge. Caution. Make sure that anywhere were the settlement has buildings or rocks or lakes that you want to show up correctly should be under a pixel which has been set to 1 - or you will see floating or sunk buildings etc.

You can edit the merging effects to smooth out corners etc better manually via the heights Terrain TGA's alpha channel. 

**Height  TGA parameters
These are used to control the height TGA's creation and replacement. You should use the same parameters for BOTH conversions so make a note of them. These parameters determine how to convert to a greyscale and back again.. There is a very simple premise used here. Anything that starts off too low will be coloured blue, anything which is too high will be coloured red (too high relative to the scale chosen that is). When reading back  ONLY greyscale values will be read (including their alphas).

This is very useful for preventing height changes to where a building is currently placed. Use the pathfinding  TGA as a layer (re-sized to fit) and simply colour the heights map below blocked areas to ensure no changes will occur. The set up also allows fine detail height changes via TGA's by allowing the full greyscale range to be assigned to a limited height range and ignoring out of range values. That's said you should be careful how you use it.

***********************************************************************************
WORLD PATHFINDING
1). Create Pathfinding TGA2 creates a simple Pathfinding file which you edit using either the green for not blocked or the blue for blocked (no alphas involved). Simply add more of whichever you want to do.

2). Replaces with the new TGA  (Alphas are created in this process).

3). Create pathfinding TAG3 is a different version of TGA2. It highlights the non 'true colours' used in the file and creates an outline effect of the block areas. Handy for seeing boundaries a bit clearer.

It is assumed at this stage that the extra bytes inserted in the column view (hidden from you) have no affect (TGA1 - the 1.5x lengthened view seen in previous editors) was removed because of this.

***********************************************************************************
WORLD VEGETATION
This extracts two groups as TGA's (there are two other groups but they don't look like they are used)

1). Group 3 TGA - this has alphas which are needed for it to work. I haven't analysed fully but the colours cause vegetation (Trees) to appear on the tiles. Its probably simplest to ignore or use a clone stamp and then select and set the alpha afterwards. I'll probably look into this in more detail later. 

2). Group 4 TGA allows you to add trees and shrubs. Just use the colours shown to add more. No alphas are needed here. The process generates TGA pixels from co-ordinates sot here is some very minor loss of detail. Note that a likely enhancement could be to generate the back ground shrubs when expanding the size but this can be done quite easily within any TGA editing package anyway.

***********************************************************************************

Guess that's all I can think of...


So special thanks to KnightErrant who's code and advice was used as the basis for this tool. I simply extended the use of his code. Also to Makanyane who has helped test items of the tools.

And of course special thanks to Argantonio for his ongoing discoveries in this area. 

***********************************************************************************

If you have any queries about the use of this tool contact Wilddog. 


Please always work on copies of files. If you don't then don't use this tool.. the rest as they say is at your own risk.
IWTE was created for use with my own mod and is provided to help other modders.  

IWTE IS PROVIDED "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. 
