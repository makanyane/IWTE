![IWTE banner](../IWTEgithub_images/IWTEbanner.jpg)

# On wall deployment in M2TW settlements
The wall deployment is controlled from inside the .world file, IWTE offers a graphical way of viewing the deployment settings and ways of adding or amending wall deployment blocks.

The wall deployment blocks are assigned to objects, objects such as walls which have areas of their top surface destroyed in later damage states generate have different deployment outlines assigned for each damage state, this is what causes units to fall if they are standing on a part of a wall which gets destroyed.

Each wall deployment block must comprise one flat area. Please be aware of an AI quirk; the ai attacking in a siege will only attack one target per block, so ideally the gate should not share the same block as wall sections.

## View existing wall deployment

Viewing existing wall deployment blocks shows they are made up of an overall area defined by edges, and individual points with a facing which determine where troops will try and stand.

![M2_building_view_wall_deployment](../IWTEgithub_images/M2_building_view_wall_deployment.jpg)

View in conjunction with 'view world' 'view links/ladders - 2d' and iview door points' to see how things inter-relate.

![M2-deployment-blocks](../IWTEgithub_images/M2-deployment-blocks.jpg)


## Add new depoyment block
