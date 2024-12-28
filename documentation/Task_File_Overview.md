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

[Example task files](https://github.com/makanyane/IWTE/tree/main/task_file_examples) have been supplied in the task_file_examples folder, their names indicate to which process they apply.

## Change Log Relating to Tasks
IWTE_v22_09_C\
A special task has been introduced with 22_09_C which supports running a list of tasks.
This specific task needs to be saved as a file named **yourname_list.txt** 
This is to allow it be selected seperately from other tasks

IWTE_v23_01_A\
A lot of the cas/mesh extract processes and their tasks have changed. 

IWTE_v24_09_B\
Task file tags have been generalised to cope with writing to/from .dae/.ms3d/.glb - e.g. to write out a file for milkshape supply a file name ending .ms3d