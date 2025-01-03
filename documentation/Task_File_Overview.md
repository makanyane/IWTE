# Task File Overview
The task file process purpose is to help speed up some repeat processes that we are planning to use within our [PKH mod development](https://discord.gg/wCktBnYnSM) which was the initital reason for IWTE many years ago.
 
The task file process may get specific updates as and when we feel the need.\
As a consequence the data used within each process may change over time, but we are assuming the basic workings will stay as they are.
Note that the task files that IWTE generates will default to either the directory where an initial task was run or into a directory = executable_path/iwte_tasks.

For some button options IWTE generates a task equivalent to the screen selections used. These are generally identified starting with 'iwte_'. 

Task files must be text files with the file name ending **_task.txt**

There are a few simply syntax items anyone wanting to use this process should be aware of
1. Anything following a # sign on the same line is regarded as a comment and will not be used.
2. All 'data_ids' are identified as a continuous string starting and ending with less than/greater than signs eg <task_id>
3. Anything following the taskid is considered as the data that that particular data_id needs. If the data does not match the requirement it will cause an error.
4. A list of data is simply the data following a task_id and ending with the next task_id (or end of file)
5. Data_ids should be exactly as required or will not be recognised (small letters please).
6. Any name with spaces will be broken into mutiple data items so please avoid spaces, otherwise enclose in double quotes -->  "like this"
7. Each task file will expect one <task_id> in a text file.
8. Sequence within the file is not important. Some of the data ids in a task file may be optional, these are normally marked as optional in the comments in the example fles. Some data may be optional in some processes but not others.
9. The task file is sometimes run in the same subdirectory as the data you are trying to manipulate.
10. Relative paths, **downwards** from the IWTE.exe directory can generally be used, start the path with /
11. Whilst not a rule if something goes splat its worth checking the messages above the error to see if that tells you why.  If something goes splat with a 'divided by zero' message that is normally a deliberate stop point as you've reached an unsupported issue.

[Example task files](../task_file_examples) have been supplied in the task_file_examples folder, their names indicate to which process they apply.

## Task IDs
| ID | Example task/s | Documentation | Notes |
| ----|----|----|----|
| cas_bone_name_change | [CAS_bone_name_change_task.txt](../task_file_examples/CAS_bone_name_change_task.txt) |
| cas_to_extract | [CAS_cas_to_extract_no_anim_task.txt](../task_file_examples/CAS_cas_to_extract_no_anim_task.txt)<br>[CAS_extract_to_CAS_with_multiple_anims_task.txt](../task_file_examples/CAS_extract_to_CAS_with_multiple_anims_task.txt) | [strat_models.md)](../documentation/strat_models.md)
| extract_to_cas | [CAS_extract_to_CAS_with_multiple_anims_task.txt](../task_file_examples/CAS_extract_to_CAS_with_multiple_anims_task.txt)
| cas_data_csv | [CAS_data_to_csv_task.txt](../task_file_examples/CAS_data_to_csv_task.txt)
| cas_texture_csv | [CAS_texture_tga_list_to_csv_task.txt](../task_file_examples/CAS_texture_tga_list_to_csv_task.txt)
| world_effects_and_shading | [M2_SETTLEMENT_world_effect_and_shading_task.txt](../task_file_examples/M2_SETTLEMENT_world_effect_and_shading_task.txt) | | M2 only |
| dds_to_texture_directory | [M2_TEXTURE_dds_to_texture_directory_task.txt](../task_file_examples/M2_TEXTURE_dds_to_texture_directory_task.txt) | [M2 Texture Conversion Options](Image_Editing_and_Conversion.md#m2-texture-conversion-options) | M2 only |
| texture_to_dds_directory | [M2_TEXTURE_texture_to_dds_directory_task.txt](../task_file_examples/M2_TEXTURE_texture_to_dds_directory_task.txt) | [M2 Texture Conversion Options](Image_Editing_and_Conversion.md#m2-texture-conversion-options) | M2 only |
| unit_card_data | [M2_UNIT_CARD_data_for_Feral_Blender_addon_task.txt](../task_file_examples/M2_UNIT_CARD_data_for_Feral_Blender_addon_task.txt) | | M2 only |
| convert_from_skeleton_to_new |
| extract_to_mesh | [M2_UNIT_extract_to_mesh_body_WEAPON_SHIELD_anims_task.txt](../task_file_examples/M2_UNIT_extract_to_mesh_body_WEAPON_SHIELD_anims_task.txt) | | M2 only |
| mesh_to_extract | [M2_UNIT_mesh_to_extract_with_anims_list_task.txt](../task_file_examples/M2_UNIT_mesh_to_extract_with_anims_list_task.txt)<br> [M2_UNIT_mesh_to_extract_body_and_WEAPON_anims_task.txt](../task_file_examples/M2_UNIT_mesh_to_extract_body_and_WEAPON_anims_task.txt)<br>[M2_UNIT_mesh_to_extract_body_WEAPON_and_MOUNT_task.txt](../task_file_examples/M2_UNIT_mesh_to_extract_body_WEAPON_and_MOUNT_task.txt)  | | M2 only |
| modeldb_mesh_to_extract | [M2_UNIT_modeldb_mesh_to_extract_task.txt](../task_file_examples/M2_UNIT_modeldb_mesh_to_extract_task.txt) | | M2 only |
| create_map_pieces | [RR_MAP_MESH_older_version_task.txt](../task_file_examples/RR_MAP_MESH_older_version_task.txt) | | RR only (map) |
| create_map_pieces_V2 | [RR_MAP_MESH_v2_modified_textures_task.txt](../task_file_examples/RR_MAP_MESH_v2_modified_textures_task.txt) | | RR only (map) |
| combine_piece_textures_v2 | [RR_MAP_MESH_combine_piece_textures_task.txt](../task_file_examples/RR_MAP_MESH_combine_piece_textures_task.txt) | | RR only (map) |
| settlement_plan_edit  | [RR_SETTLEMENT_plan_edit_task.txt](../task_file_examples/RR_SETTLEMENT_plan_edit_task.txt) | [battlemap_settlements_RR_and_RTW.md](../documentation/battlemap_settlements_RR_and_RTW.md)| RR (/RTW\*) |
| extract_to_settlement_plan | [RR_extract_to_SETTLEMENT_plan.txt](../task_file_examples/RR_extract_to_SETTLEMENT_plan.txt) | | RR (/RTW\*)
| rrdds_extract_to_dds_directory | [RR_dds_extract_to_dds_directory_task.txt](../task_file_examples/RR_dds_extract_to_dds_directory_task.txt) | [RR dds LZ4 Compression Conversion Options](Image_Editing_and_Conversion.md#rr-dds-lz4-compression-conversion-options) | RR only (Lz4 dds) |
| task_tex_conv_tga_to_dxt1_nomipmaps_dds | [TEXCONV_tga_to_dds_albedos_task.txt](../task_file_examples/TEXCONV_tga_to_dds_albedos_task.txt) | | launches TexConv |
| task_tex_conv_tga_to_dxt5_dds | [TEXCONV_tga_to_dds_materials_task.txt](../task_file_examples/TEXCONV_tga_to_dds_materials_task.txt) | |  launches TexConv |

## Change Log Relating to Tasks
IWTE_v22_09_C\
A special task has been introduced with 22_09_C which supports running a list of tasks.
This specific task needs to be saved as a file named **yourname_list.txt** 
This is to allow it be selected seperately from other tasks

IWTE_v23_01_A\
A lot of the cas/mesh extract processes and their tasks have changed. 

IWTE_v24_09_B\
Task file tags have been generalised to cope with writing to/from .dae/.ms3d/.glb - e.g. to write out a file for milkshape supply a file name ending .ms3d
