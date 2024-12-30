# Battlemap Settlement Editing - RR and RTW

Battlemap Settlements in RR and RTW are created and modified via settlement plans in text format.  The settlement plans list positions of wall sections, dbb entries and other components.  The components used originate as models in .cas format. Some .cas files are converted by the game into .item files or .bpi files.

#### Table of Contents
* [Item to Cas Conversion with IWTE](#item-to-cas-conversion-with-iwte)
* [Settlement Plan Editing with IWTE](#settlement-plan-editing-with-iwte)
  * [Settlement Plan Editing in 2d Window](#settlement-plan-editing-in-2d-window)
    * [Wall Layout Editing](#wall-layout-editing)
  * [Settlement Plan Editing in 3d Program](#settlement-plan-editing-in-3d-program)

## Item to Cas Conversion with IWTE

Some RTW mods were released with new buildings in the final .item format but .cas files were not supplied, additionally some RTW OG building .cas files were in an old .cas format which isn't read by the conversion tools.  The item to cas functions are supplied to allow modders to retrieve .cas files they can work on from .items

![image](../IWTEgithub_images/item-to-cas.jpg)

The functions are accessible via buttons.

*Rome Remastered > Battle Map Settlements > **item to cas*** allows you to select a single .item file for conversion.  The resultant .cas files will be written to sub-folders below your .item location called *anyoutfiles/models_building*. If the .item had multiple lod levels they will be written out to separate .cas files.

*Rome Remastered > Battle Map Settlements > **items.db/items to cas*** requires you to select the *descr_items.db* file, which should be in the folder above the *items* folder.  All the .items listed in the .db file will be converted if found. The resultant .cas files will be written to a folder called *to_cas* and will be arranged in the sub-folders specified by the items.db file.

*Rome Remastered > Battle Map Settlements > **items.db/cas to items*** also requires you to select the *descr_items.db* file, you must therefore have already run the game process to regenerate the .db.  IWTE will convert the listed cas files to items which will be placed in a folder called *to_item*.   **NOTE!!!  You only need IWTE generated .item files if you have animated spot_fx files and have problems with the game's generation of the animated .item from .cas.**

## Settlement Plan Editing with IWTE

To open a settlement plan to edit use the buttons\
*Rome Remastered > Battle Map Settlements > **settlement plan edit***\
That will open a form where you can select the settlement plan, the mod directory and the Rome Remastered main data directory. NB: that is resources/data, not resources/data/data!  It needs to be the higher level so BI entries can also be found if used by the mod. 

![image](../IWTEgithub_images/settlement-plan-edit.jpg)

Running this process will generate a task file with the **settlement_plan_edit** task id, this can be adapted or re-used. An example task file is also provided [here](../task_file_examples/RR_SETTLEMENT_plan_edit_task.txt).  

You have the option of generating a dae or glb file of the settlement to work on in Blender.  Ms3d is not supported for this function due to size limitations.

*Rome Remastered > Battle Map Settlements > **settlement plan - edit walls***\
Provides a simplified version which only loads/changes the wall layout.

### Settlement Plan Editing in 2d Window

![image](../IWTEgithub_images/settlement-plan-edit-2d.jpg)

In the 2d Window you can select move and rotate objects. Use the *Settlement actions* drop down to select objects to add, to switch modes or to save.  Saved files will modify the starting settlement plan and produce a new file in the same directory called:\
*original_name_new00.txt*\
the number will increment if that file exists. The original text file has to be used as a basis to retain the strat model/underlay/ground_types/street_plan information which is not changed via IWTE.

Useful shortcuts:
* Tab swaps mode between wall and object selection
* M switches on movement option
* R switches on rotation option
* Delete button on keyboard will delete all selected walls/objects

Heights and exact rotations can be set for selected objects in the *Main Processes* window.  If you have a settlement underlay with a lot of height changes we'd recommending using the 3d method for most changes.

The *add dbb item* button opens up multiple other sections which then access ALL the possible available dbb items in alphabetically divided sections.

Most objects are shown on the 2D view by a diagram representing their lowest lod level. Slots are shown by a diagram representing the outline of objects in their default version.  The street_plan and underlay shapes are shown diagramatically but are not editable in this method.

#### Wall Layout Editing
The walls in RTW/RR have to be laid out on set grid points so they form a continuous and exactly linked perimeter. Failing to link the walls correctly will cause the game to crash when launched.

Because the wall pieces have to be located on grid points the 2D window method is the only way to edit the wall layout using IWTE.  Rotation of wall elements is restricted to 45 or 90 degree increments. To rotate an element select it and then hit R on your keyboard. To move an element select it and then drag.

To add items use the *Settlement actions* drop down menu on the 2D View Window. Select *add wall item* and then the item you want, and/or note the keyboard shortcuts which will add more of those items. New items will appear in the center of the current 2d  view.

IWTE does not sanity check your layout so please familiarise yourself with the possible combinations and types of links in existing plans.

### Settlement Plan Editing in 3d Program

If you opted 'yes' for either dae or glb a representation of the settlement in 3d will have been produced and saved to *anyoutfiles* sub-folder below your settlement plan location.  These files can be imported into Blender.

![image](../IWTEgithub_images/settlement-plan-edit-3d.jpg)

The floor (a representation of the underlay shape), the street_plan (a single mesh representing the street_plan) and any wall objects are not changeable in this system and will be ignored on read back of the 3d file.

Other dbb elements are shown with one mesh representing all the elements at the lowest lod level. Slots are shown using their default option.  Dbb objects can be deleted, moved and rotated as desired. If you want more of an existing object you can duplicate the object, additional .001 numbering added by Blender will be ignored.  You can add other dbb elements if you know the name.  The only things read back from the file are the names, locations and rotations around the z axis.

You must move things in **Object Mode**, do not use Edit Mode and do NOT apply transforms!  You should still be able to see the location and rotation of the object in the side-bar.

When you've finished your changes export to dae or glb.  You can use the task file created by IWTE to create a revised settlement plan.




