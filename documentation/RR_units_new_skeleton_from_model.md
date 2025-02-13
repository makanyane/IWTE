![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)
# Rome Remastered - New Skeleton from Model

The process takes bone information from an existing model, compares with bone information from a new model and converts the existing skeleton and animations to match the new model.  Start the process using the buttons:  
** Rome Remastered > Units > New skeleton from model **

This will open a form table for you to browse to the directories you want and/or type in information as shown below:

![RR_units_new_skeleton_from_model.jpg](../IWTEgithub_images/RR_units_new_skeleton_from_model.jpg)

The process has to work from before and after unit .cas models as they are the only element that stores the bone names.  Bone names are needed so IWTE can retain information from the anims, e.g. any movements that bone_Relbow had in the original anims will be transferred to bone_Relbow in the new animations.  Movements for bones which do not exist with the same name in the new animation will be deleted. No movements will be applied to bones with new names.  The picture below shows an example of before and after unit models.  Only the Armature structure is relavent for this process.

![RR_units_new_skeleton_from_model_base.jpg](../IWTEgithub_images/RR_units_new_skeleton_from_model_base.jpg)
